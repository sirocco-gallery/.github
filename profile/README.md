<div align="center">
<img src="./sirocco_banner.svg" alt="sirocco.gallery" width="100%"/>
</div>
<br/><br/>

 # sirocco

**A live WebMCP design surface** — the *provider* half of a WebMCP reference
implementation. Design-intent enforcement that AI agents can call, in the browser: an agent drafts UI; the **steward** names where it drifts from a design system's tokens; it corrects until the build honors them.

→ [sirocco.gallery](https://sirocco.gallery)

See live demo here: [sirocco WebMCP provider and refraktor consumer loop](https://youtu.be/4yLuqEr58PA)

>
A design system is only as good as the discipline that keeps to it. The steward
removes the discipline problem and offers it to agents as a tool:

- **A deterministic drift check** — every colour and corner of some CSS, measured
  against a set of design tokens, with each drift named (what you wrote vs. the
  exact token expected).
- **A rubric** for the judgment tokens can't measure — role, register, restraint,
  temperature, intent. The deterministic check is the floor; the rubric is the
  layer above it, which the agent's own model reasons through.

It's demonstrated on six **house instruments** (curated token sets).
>

## The complete loop — both halves

A capability isn't real until something on the other side uses it. sirocco is
shipped as a matched pair:

- **Provider (this repo)** — sirocco.gallery registers the steward's checks as
  agent-callable tools on `document.modelContext`, the reference implementation.
- **Consumer (Refraktor)** — [**Refraktor repo**](https://github.com/sirocco-gallery/refraktor)
  a general-purpose Chrome side-panel agent that discovers and drives any page's
  WebMCP tools through a Gemini chat.
- [Refraktor](https://chromewebstore.google.com/detail/refraktor/nkafbaaanaamfjdljndmieichdgkhgii) is available via the Chrome Web store 

## Agent surface

- **WebMCP (in the browser).** The page registers tools on
  `document.modelContext`; an in-browser agent discovers and calls them. Verified
  in Chrome's WebMCP preview with a real model driving the tools end to end, and by
  a second, independent consumer (the Model Context Tool Inspector).

## Surfaces

| Route | What |
|---|---|
| `/session` | **the floor** — watch an agent run the loop across the instruments (scripted, and a live model on demand) |
| `/steward` | what the steward is |
| `/demo` | the loop on film — the tools driven by two independent consumers |
| `/mint` | normalize any design system into a canonical token set |
| `/lab` | the registered WebMCP tools, run by hand |

## Status

An evolving reference implementation — honest snapshot:

- ✅ Deterministic drift check; the WebMCP tool surface (verified across two
  consumers); the floor (scripted + a live agent run); the steward rubric; the MCP
  connector's open tier (verified with a standard MCP client); the companion
  consumer extension (verified across two providers).
- ✅ **v1 leads with the capability, openly.** No account, no paid tier surfaced —
  the whole loop is free and walkable.
- Not production-hardened. Treat it as a reference implementation, not a finished
  product.

## Deployment and Infrastructure
  [![Deployed with Vercel](https://vercel.com)](https://sirocco-gallery.vercel.app/)
  
  This repo contains an end-to-end WebMCP ecosystem - both a provider surface and a consumer extension.

  ## The Backend Provider surface (sirocco.gallery):
  sirocco.gallery is a live WebMCP provider site. 
  that exposes five callable tools. It leverages 
  Vercel's capabilities and serverless 
  infrastructure to handle the stateless, bursty 
  nature of incoming tool calls during the Google 
  Chrome WebMCP origin trial.

  ## The Client Consumer (Chrome web store):
  A general browser consumer extension built with 
  design conformance awareness. It runs locally in 
  the browser to discover and interact directly 
  with the  Vercel hosted provider surface, 
  demonstrating how serverless architecture can 
  seamlessly power client side AI protocol 
  interactions. 

## Notes

WebMCP is an early, evolving web standard; the in-
browser surface needs a browser
with the WebMCP preview enabled (Chrome 146+ behind 
a flag). Everything else runs
anywhere.

[Astro](https://astro.build) · Vercel · [`@modelcontextprotocol/sdk`](https://modelcontextprotocol.io) · the WebMCP draft (`document.modelContext`) · [A Ziola Project](https://www.ziola.dev/index.html)
