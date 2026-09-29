# deskaway-docs

Documentation that spans more than one DeskAway repo: cross-repo
architecture decisions, product specs, and system diagrams.

This is the front door to the system — start here to find out what DeskAway
is and which repo does what. Component-specific docs live with their code.

## Status

**Early development, nothing works yet.**

That applies to the product, not just this repo. The wire envelope and the
connection messages are now defined in `deskaway-protocol`; every other
component is still scaffolding with no running code. This repo holds the index
below and the first entry of the threat model,
[`security/threat-model.md`](./security/threat-model.md). No cross-repo ADR or
spec has been written yet.

## Running locally

Nothing to run. This repo is Markdown, with no site generator and no build
step.

```sh
git clone https://github.com/away-desk/deskaway-docs.git
```

Read it in your editor or on GitHub. Well under ten minutes. If a docs site
is added later, its build command belongs in this section.

## The rest of DeskAway

All components are under the
**[away-desk](https://github.com/away-desk)** org:

| Repo | What it does | Stack |
| --- | --- | --- |
| [deskaway-protocol](https://github.com/away-desk/deskaway-protocol) | The wire contract every component speaks. Start here. | JSON Schema |
| [deskaway-relay](https://github.com/away-desk/deskaway-relay) | Cloud broker: sockets, pairing, sessions, recording | Node / TypeScript |
| [deskaway-agent](https://github.com/away-desk/deskaway-agent) | Planning: task to checklist, reversibility, replanning | Python |
| [deskaway-desktop](https://github.com/away-desk/deskaway-desktop) | Windows host that executes a run | .NET |
| [deskaway-android](https://github.com/away-desk/deskaway-android) | Phone client: start, watch and approve a run | Kotlin |
| [deskaway-infra](https://github.com/away-desk/deskaway-infra) | Cloud infrastructure and runbooks | Terraform |

Roughly, the shape of the system: a phone
([android](https://github.com/away-desk/deskaway-android)) drives a run
executing on a Windows machine
([desktop](https://github.com/away-desk/deskaway-desktop)), brokered through
the cloud ([relay](https://github.com/away-desk/deskaway-relay)), with the
plan produced by [agent](https://github.com/away-desk/deskaway-agent) and
every message shaped by
[protocol](https://github.com/away-desk/deskaway-protocol).

## Contributing

Guidance for this repo — including what belongs here rather than in a
component repo, and the rule every README follows — is in
[AGENT.md](./AGENT.md).
