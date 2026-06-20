<div align="center">
<img src="./banner.svg" alt="sirocco.gallery" width="100%"/>
<br/><br/>

 
**A live WebMCP design surface.** Design-intent enforcement that AI agents can
call — in the browser and in your coding agent. An agent drafts UI; the *steward*
names where it drifts from a design system's tokens; it corrects until the build
honors them.

→ [sirocco.gallery](https://sirocco.gallery)

## The idea

A design system is only as good as the discipline that keeps to it. The steward
removes the discipline problem and offers it to agents as a tool:

- **A deterministic drift check** — every colour and corner of some CSS, measured
  against a set of design tokens, with each drift named (what you wrote vs. the
  exact token expected).
- **A rubric** for the judgment tokens can't measure — role, register, restraint,
  temperature, intent. The deterministic check is the floor; the rubric is the
  layer above it, which the agent's own model reasons through.

It's demonstrated on six **house instruments** (curated token sets). Bring your
own tokens to point the same steward at your system.

## Two agent surfaces

- **WebMCP (in the browser).** The page registers tools on
  `document.modelContext`; an in-browser agent discovers and calls them. Verified
  in Chrome's WebMCP preview with a real model driving the tools end to end.
- **MCP connector (in your IDE).** A remote MCP server (`/api/mcp`) you add to a
  coding agent (Claude Code, Cursor) so the steward runs inside your dev loop.

Both are deterministic + the rubric — no model calls or external services in the
check itself.

## Surfaces

| Route | What |
|---|---|
| `/session` | **the floor** — watch an agent run the loop across the instruments (scripted, and a live model on demand) |
| `/steward` | what the steward is |
| `/mint` | normalize any design system into a canonical token set |
| `/lab` | the registered WebMCP tools, run by hand |
| `/instrument` | bring-your-own: your tokens, your connector |

## Status

An evolving reference implementation — honest snapshot:

- Deterministic drift check; WebMCP tool surface; the floor (scripted + a live
  agent run); the steward rubric; the MCP connector's **open tier** (verified with
  a standard MCP client).
- Bring-your-own (your own tokens + a per-purchase connector) and its commerce
  path — live, with verification still in progress.
- Not production-hardened. Treat it as a reference implementation, not a finished
  product.

## Develop

```bash
npm install
npm run dev      # http://localhost:4321
npm run build
```

## Layout

```
src/pages      routes, incl. /api/* endpoints (the WebMCP/MCP surfaces live here)
src/lib        check · normalize · the run engine · the steward rubric · the MCP server
src/data       the instruments and their token sets
docs/          working notes
```

## Notes

WebMCP is an early, evolving web standard; the in-browser surface needs a browser
with the WebMCP preview enabled. Everything else runs anywhere.

## Tech

[Astro](https://astro.build) · Vercel · [`@modelcontextprotocol/sdk`](https://modelcontextprotocol.io) · the WebMCP draft (`document.modelContext`)
