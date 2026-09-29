# Threat model

What DeskAway trusts, what it cannot verify, and what follows from that. This
file starts small and grows as the system does. The full model is due on Day 50.
Until then, each entry records a property at the moment the design creates it,
so nobody later mistakes it for a guarantee.

Each entry says what is true, why, what it means for someone relying on it, and
what does or does not mitigate it.

## Known properties

### T1. The scope shown on the phone is self-reported by the desktop

*Recorded 2026-09-29, from the envelope design (Unit 2).*

**What is true.** When a desktop connects, its `hello` message states the
folder it will confine work to (`folder`) and the version of its scope rules
(`scopeVersion`). The phone's pairing and approval screens show that folder.
The relay passes it on but **cannot verify it**. Only `role` and `deviceId` in
`hello` are checked against the authenticated connection; every other field is
the desktop's own claim. The schema labels each field with `x-deskaway-trust`
(see `deskaway-protocol/schemas/control/hello.v1.json`).

**Why.** Scope is a carried value, not an operating-system-enforced wall. The
desktop app enforces its own scope. Nothing outside the desktop observes where
commands actually run.

**What it means.** A modified or compromised desktop app could display one
folder on the phone and work in another. Anyone approving a step on the phone is
trusting the desktop app, not the relay or the OS.

**Mitigations today.** None beyond the desktop app enforcing scope itself, in
`Core/Scope`. The protocol labels the field honestly so it is never presented
as verified.

**Rules that follow.**

- Any UI that shows the folder must present it as the desktop's claim, not as
  an enforced boundary.
- No server-side decision may treat `folder` as a security boundary.

**Would change if** scope became OS-enforced (for example a sandboxed user
account or a filesystem filter driver), or the desktop's reported state became
remotely attestable.
