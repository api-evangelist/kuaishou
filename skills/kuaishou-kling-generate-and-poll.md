---
name: kling-generate-and-poll
description: Generate an image or video with Kuaishou's Kling AI and retrieve the result, using the official Kling CLI or the hosted MCP server at https://kling.ai/mcp.
api: kuaishou:kling-ai
generated: '2026-08-12'
method: generated
source: >-
  https://registry.npmjs.org/@klingai/cli-global README (v0.1.3, published 2026-07-08) and
  package dist/cli.js; https://kling.ai/.well-known/oauth-protected-resource;
  https://kling.ai/app/mcp/guide
operations:
  - who_am_i
  - text_to_image
  - image_to_image
  - text_to_video
  - image_to_video
  - query_tasks
  - query_membership_and_credits
transport: mcp
mcp_url: https://kling.ai/mcp
scopes:
  - generation.create
  - generation.read
  - account.credit.read
---

# Generate with Kling AI and poll for the result

Kling AI is Kuaishou Technology's video and image generation platform. It is an **asynchronous**
API: you submit a generation task, get back a `generationId`, then poll until the task reaches a
terminal state. Every tool name below is published by Kuaishou in the README of its own
`@klingai/cli-global` npm package, which states that CLI commands map 1:1 to backend MCP tools.

## Before you start

- Install the CLI: `npm i -g @klingai/cli-global` (or `@klingai/cli-cn` for a China-site account).
  Node.js 18+ is required. Both install the same `kling` command.
- Or connect an MCP client directly to `https://kling.ai/mcp`. It is a streamable-HTTP MCP server
  behind OAuth: an anonymous `tools/list` returns **HTTP 401** with
  `WWW-Authenticate: Bearer resource_metadata=https://kling.ai/.well-known/oauth-protected-resource/mcp`.
  Complete the authorization-code flow (PKCE S256, dynamic client registration at
  `https://kling.ai/auth/register`) and request the scopes you need:
  `generation.create` to submit, `generation.read` to poll, `account.credit.read` to check credits.
- Generation **spends credits**. Kuaishou states that MCP and CLI accept only *paid* credits from the
  Personal workspace — bonus credits will not work through these surfaces.

## Steps

1. **Authenticate.**

   ```bash
   kling login
   ```

   Credentials are written under `~/.kling/`. The CLI never prints tokens.

2. **Discover capability before you spend anything.** Do not hard-code a model name; the server
   declares what is available and what parameters each model takes.

   ```bash
   kling who_am_i
   ```

   This returns the current identity plus available models and their parameter specs. Generation
   commands require an explicit `--model <name>` from this list, unless you pass `--omni` to select
   the omni-family model.

3. **Check your budget** if the run is large.

   ```bash
   kling account
   ```

   (MCP tool `query_membership_and_credits`.)

4. **Submit the generation.** Pick the tool that matches your inputs:

   | Inputs | Tool / command |
   |---|---|
   | prompt only, want an image | `text_to_image` |
   | reference image(s) + prompt, want an image | `image_to_image` |
   | prompt only, want a video | `text_to_video` |
   | reference image + prompt, want a video | `image_to_video` |

   ```bash
   kling text_to_image --model <model-from-who_am_i> "a shiba inu sitting by a cafe window"
   kling text_to_video --model <model-from-who_am_i> "drone shot over a snowy peak" --duration 10
   ```

   If you need to send a local file, upload it first — `file_upload` returns a ticket and an
   `uploadUrl`; the client PUTs the file there and gets a public URL back. The CLI does this for you
   when you pass `--image ./local.jpg`.

5. **Poll for the result.** Either poll inline, or submit first and poll later with the returned id:

   ```bash
   # inline: wait up to 300 seconds
   kling text_to_video --model <model> "..." --poll 300

   # or, separately
   kling query_tasks <generationId> --poll 120
   ```

   Bare `--poll` defaults to 60 seconds. Video generation routinely needs longer than that — use
   120–300s. The client treats `submitted`, `pending`, `queuing`, `queueing`, `processing` and
   `running` as non-terminal; keep polling while the status is one of those.

6. **Read the assets.** Results come back in `works[].url`. Where the account is entitled to them,
   watermark-free URLs are in `works[].url_without_watermark`.

## Conventions and failure handling

- **stdout is JSON.** Use `--quiet` for compact single-line JSON. Diagnostics go to stderr.
- **Exit codes:** `0` success, `1` failure, `130` user cancellation.
- **Errors** come back as `{"code": <int>, "message": "<string>", "request_id": "<uuid>"}` with a real
  HTTP status. `1001` / HTTP 401 means the `Authorization` header is missing — re-run `kling login`.
  Quote `request_id` in any support conversation; it is the only correlation handle Kling returns.
- **There is no idempotency key.** Nothing on the public surface makes a retried submission safe, and
  each submission spends credits. Do **not** blindly retry a submit on a timeout — poll with
  `query_tasks` using the `generationId` you already have.
- **There are no rate-limit headers.** You cannot read remaining budget from a response. Track your
  own concurrency, and check `kling account` between batches.
- **Polling timed out** is not a failure: the CLI prints that the task is still generating and tells
  you to continue with `query_tasks <generationId>`. Do that rather than re-submitting.

## Not covered

The REST equivalents of these tools (`https://api-singapore.klingai.com/v1/...`, JWT-signed with an
Access Key ID and Secret) are documented at `https://kling.ai/document-api`, a JavaScript-rendered
site. The exact REST paths, request bodies and the JWT claim set are **not** reproduced here because
they could not be read from a machine-readable source. Use `who_am_i` and `tool_list` for the
authoritative, live parameter specs.
