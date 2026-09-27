# DeskAway Docs

Cross-repo documentation for DeskAway: architecture decisions, product
specs, and anything that spans more than one component.

Component-local docs live with their code. This repo is for the rest.

## Component repositories

| Repo | Contents |
| --- | --- |
| [deskaway-protocol](https://github.com/away-desk/deskaway-protocol) | Wire protocol: JSON Schemas, enums, versioning policy |
| [deskaway-relay](https://github.com/away-desk/deskaway-relay) | Node/TypeScript relay: HTTP + WebSocket, pairing, recording |
| [deskaway-agent](https://github.com/away-desk/deskaway-agent) | Python planning/classification service |
| [deskaway-desktop](https://github.com/away-desk/deskaway-desktop) | .NET Windows agent host |
| [deskaway-android](https://github.com/away-desk/deskaway-android) | Android client |
| [deskaway-infra](https://github.com/away-desk/deskaway-infra) | Terraform: envs, modules, runbooks |

## Layout

Not yet established. Suggested starting points as content lands:

- `adr/` — architecture decision records
- `specs/` — product and feature specs
- `diagrams/` — source files for system diagrams
