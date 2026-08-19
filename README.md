# Mikael Hillman-Pépin

I design the systems *around* AI agents — how work divides between humans and machines, how knowledge persists across sessions, how failures stay contained, and how you establish that work is actually correct.

Most of my attention goes to the last one. An agent reporting success is making a claim, not delivering a result, and the distance between those two is where real systems fail quietly. What follows is what I run on. Each rule carries the derivation that would justify retiring it.

## Working rules

**A process cannot certify its own side effect.** If a write matters, confirm it through an independent read path — one the acting process does not control. An exit code and a "written" log line describe intent, not observation.

**A check that cannot fail is not a check.** A new guard gets mutated — broken deliberately — and if no named test goes red, I wrote a comment with syntax rather than a check.

**Absence is data, never proof.** "Nothing found" is at least three states: empty, missing, and unverifiable. Code that returns one value for all three eventually reports a failed lookup as a confirmed absence.

**A gate enforced at one call site is not enforced.** Enumerate every route to the guarded action, including ones added after the gate, and put the check on the boundary they all cross.

**A verifier inside the author's context inherits the author's blind spot.** Anything terminating an irreversible action must be reviewed from fresh context, and a stronger reviewer's findings are hypotheses to check, not verdicts to apply.

Each of these replaced a weaker version of itself. That is the only reason it is written down.

## How the work is organized

A long-lived session holds context and makes rulings. The mechanical work of shipping software — convergence rounds, code review, dispositions, documentation sweeps — runs in delegated processes that hand back only the decisions that need judgment. The design goal is that a human touches the choices a human should make, and nothing else.

Two structural commitments do most of the work:

**Discretion moves from runtime to design time.** *Whether* to run a check is the decision that fails under pressure. So when a gate fires is encoded up front; only what it does is left to judgment in the moment.

**Rules are durable artifacts, not habits.** Each is written to a fixed form — what to do, what makes it fire, and the derivation it came from — so that the derivation doubles as the retirement test. A rule nobody can trace is a rule nobody can delete.

Every pull request gets an automatic review from a different model family before I look at it; design decisions on consequential paths get a second cross-family pass. The reason is the rule above: a reviewer sharing the author's context shares the author's blind spots.

## What I'm building

Most of it is private. Listed together because they are the same problem in different domains — where the work divides, how state stays inspectable, and what a system does when it cannot verify something.

- **Quantitative infrastructure** — operated by agents rather than eyeballed by a human, on paths where a wrong all-clear is worse than a stoppage.
- **Agent-behaviour research** — pre-registered experiments with frozen materials and fixed sample sizes, so operating rules get replaced by measurements instead of anecdotes.
- **Evidence analysis** — an investigative scaffold where the working state stays inspectable and contradictions are preserved rather than collapsed into a single story.
- **Actuarial computation** — life-contingency math where the jurisdictional basis is part of the answer, and internal consistency identities must hold before any number is reported.
- **Spreadsheet conversion** — turning opaque workbooks into code, with the original workbook as the oracle: nothing counts as correct until the two agree.
- **Editorial drafting** — a system with no publishing capability at all; the hard part is verifying claims whose readers have no way to check them.
- **A consumer conversational product** — behaviour definitions hot-reload in production, so safety has to be structural rather than a deploy-time gate.

## Public repos

Three worth opening:

- **[mm-ibkr-mcp](https://github.com/MrRolie/mm-ibkr-mcp)** — an Interactive Brokers MCP server: the tool surface an agent actually gets, with approval gating and profile validation between a request and anything that touches an account.
- **[netjsonmon](https://github.com/MrRolie/netjsonmon)** — a CLI for discovering and ranking JSON API endpoints from real browser traffic. Built for inspecting network APIs, persisting captures, and finding the endpoints that actually carry data.
- **[step_criterion](https://github.com/MrRolie/step_criterion)** — a small published Python package for stepwise model selection, deliberately explicit about the statistical limitations of the method it implements.

## Background

Actuarial science and financial engineering. Finance trains you to reason about uncertainty, incentives, evidence, and consequences that are real — which turns out to be reasonable preparation for building systems whose failure modes are not yet charted.
