# Artem Krivoshchekov

Buenos Aires · [roxl.net](https://roxl.net) · [LinkedIn](https://linkedin.com/in/artschekoff) · therawlex@gmail.com

Most of my last year has gone into one narrow problem: making command-line tools that an AI agent can drive without a person watching. A single binary, flags in, JSON out, and enough self-description that the model figures out the call on its own. It's a different design problem than a CLI built for humans, and I got interested enough in it to write a dozen.

Before that I spent about nine years doing normal things — SharePoint and PowerShell at an integrator, .NET, React, a lot of Laravel and WooCommerce, a stretch of security research. Nothing about the current work makes sense without that part, so it's below too.

**A note on this repo list:** a fair share of it is forks I keep around for patches or reading. Everything in Selected Work is code I wrote.

---

## Tools for agents

Go, mostly. All of them exist because I hit the same wall while working with coding agents: the model can reason fine, but the thing it needs to call is either a GUI, a chatty CLI that burns half the context on ASCII tables, or an API that needs a wrapper nobody wrote.

**[jira-cli](https://github.com/artschekoff/jira-cli)** — a wrapper around Atlassian's `acli` that returns JSON on stdout instead of formatted text. Ships as a Claude Code plugin with command guides for the four things you actually do all day: load ticket context, create work items, comment, prime the agent. This one gets used daily.

**[joplin-cli](https://github.com/artschekoff/joplin-cli)** — console access to Joplin notes through the Web Clipper REST API, with a machine-readable schema. Started as a Go port of `dweigend/joplin-mcp-server` and grew from there. 30s timeout, three retries, because the local Joplin server is flakier than you'd hope.

**[omniplan-cli](https://github.com/artschekoff/omniplan-cli)** — self-describing CLI for OmniPlan 4 on macOS. The "self-describing" part is the point: the tool documents its own schema so an agent can discover what it can do rather than being told.

**[kie-ai-cli](https://github.com/artschekoff/kie-ai-cli)** and **[kie-ai-mcp](https://github.com/artschekoff/kie-ai-mcp)** — CLI and MCP server for the Kie AI image API. Credentials are encrypted with AES-256-GCM and bound to the device, since the alternative is another API key sitting in a dotfile. The MCP side does batch generation in parallel.

**[imagemagick-mcp](https://github.com/artschekoff/imagemagick-mcp)** and **[imagemagick-cli](https://github.com/artschekoff/imagemagick-cli)** — one tool, `crop_resize_blur_bg`, that reframes an image to exact dimensions without distorting it: crop what you can, fill the rest with a blurred version of the same image. Cut a banner from 1.4 MB to 61 KB on the case that made me write it.

**[gcalc-mcp](https://github.com/artschekoff/gcalc-mcp)** — Google Calendar over stdio, wrapping `gcalcli` behind a vetted subcommand allowlist. Twelve tools, and the allowlist is there so an agent can't improvise its way into `gcalcli delete`.

**[mdtopdf](https://github.com/artschekoff/mdtopdf)** — Markdown to PDF with GitHub styling, one Go binary, about 200 lines. goldmark for parsing, chroma for highlighting, chromedp for the render. Written after the third time a Node toolchain broke on a machine where I just wanted a PDF.

**[codex-prompts](https://github.com/artschekoff/codex-prompts)** — the five prompt templates I keep reaching for: code review, dependency check, test generation, refactor hunting, security audit.

## Infrastructure and contracts

**[egress-guard](https://github.com/artschekoff/egress-guard)** — a domain-allowlist egress firewall for CI runners: dnsmasq as a sinkhole plus iptables, with an audit mode so you can see what a build phones home to before you start blocking it. Small, but it answers a question most pipelines can't.

**[qbit-docker](https://github.com/artschekoff/qbit-docker)** — reproducible Docker setup for a QbitX node, mainnet and testnet, AMD64 and 386, state persisted outside the container.

**[aynn-blockchain-public](https://github.com/artschekoff/aynn-blockchain-public)** — Solidity from NFT marketplace work, plus DeFi trading and MEV contracts. Published as a demonstration set, not a live deployment.

## The nine years before

**Integration and enterprise (2017–2019).** .NET MVC and Oracle to start, then SharePoint: JS integrations, and a [PowerShell module set](https://github.com/artschekoff/powershell-sharepoint) for the administrative work nobody wants to do by hand — backups, disk reports, bulk operations.

**Web and e-commerce (2019–2023).** React and Redux, TypeScript, then years of Laravel and the WordPress/WooCommerce world. [polyimport](https://github.com/artschekoff/polyimport) came out of that: WpAllImport talks to WPML but not to Polylang, so imported products lost their language links. The plugin reconnects them. Also wrote up the [Material-UI to MUI migration](https://github.com/artschekoff/react-material-mui-migration), including the dual-ThemeProvider workaround, after doing it the hard way.

**Security and forensics (2023 onward).** Mobile and desktop artifact extraction, OSINT tooling, WHOIS/DNS/breach lookups. This is where the reading list lives more than the code, and it's why the egress and credential-storage parts of the tools above look the way they do.

Along the way: [ROXL](https://roxl.net), my own studio — solution design, audits, rescuing legacy and vibe-coded projects, and lately building AI agents for business automation.

## Stack

| | |
|---|---|
| Writing most days | Go, TypeScript, Python |
| Long history with | C# / .NET, PHP (Laravel, WooCommerce, MODX), PowerShell |
| Also shipped | Rust, Solidity, Java |
| Frontend | React, Redux, TypeScript, Gatsby |
| Infra | Docker, iptables/dnsmasq, CI pipelines, MCP servers |
| Interested in | agent harnesses, context economics, egress control, forensics |

---

Available for contract and consulting work through [roxl.net](https://roxl.net) — [30 minutes on the calendar](https://calendly.com/therawlex/30min) is usually enough to tell whether I'm the right person.
