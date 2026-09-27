# AGENT.md — deskaway-docs

Documentation that belongs to no single component: architecture decisions
spanning repos, product specs, and the diagrams that explain how the pieces
fit. It is the landing page for the whole system.

The test for whether something belongs here: if it would have to be written
identically in two repos, it goes here. If it only describes one repo, it
stays with that repo's code.

## Folder structure

```
README.md                 # index of every component repo
AGENT.md                  # this file
CLAUDE.md                 # pointer to this file
```

That is the entire repo today. The layout below is proposed, not built —
create a directory when there is something real to put in it, not before:

```
adr/                      # cross-repo architecture decision records
specs/                    # product and feature specs
diagrams/                 # source files, not just exported images
```

Component-local docs live with their code and stay there — `deskaway-relay`
has its own `docs/adr/` for decisions that only affect the relay, and the
same goes for the agent and desktop repos.

## Conventions

- One decision per ADR, numbered and dated, and never rewritten after it is
  accepted. A reversal is a new ADR that supersedes the old one, with a link
  in both directions.
- An ADR lands here only if it constrains more than one repo. Relay-only
  choices belong in `deskaway-relay/docs/adr/`.
- Commit diagram sources alongside any exported image. An image nobody can
  edit is a dead end.
- The component table in `README.md` is the system's index. A new repo in the
  org is not done until it appears there.
- Link to code, don't restate it. Anything copied out of a repo will drift;
  describe the shape and point at the source.

## Rule: keep README.md current

The README is the one file a newcomer is guaranteed to read. Revisit it
whenever this repo's answer to any of the four questions below changes — not
on a schedule.

Every DeskAway README answers four things, in this order:

1. **What this one repo is**, in two lines, and where it sits in the whole
   system.
2. **Its current status**, stated honestly. Right now that is *early
   development, nothing works yet.*
3. **How to run it locally**, aiming for under ten minutes.
4. **A link back** to the org or to `deskaway-docs`, so someone landing here
   can find the rest.

How to apply it:

- Keep those four as the first four sections, in that order. Anything else
  goes after them.
- Status rots fastest. The moment the first thing in this repo actually
  runs, that line changes in the same PR. "Nothing works yet" is honest
  only until it isn't.
- If a setup step breaks, or creeps past ten minutes, fix the README in the
  PR that caused it. A stale run section is worse than no run section.
- Never write intent as if it were fact. Anything not yet true is either
  labelled as planned or left out entirely.
- Two lines means two lines. If section 1 needs a third paragraph, that
  content belongs in `deskaway-docs`.
