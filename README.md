# AgentTaskBench

AgentTaskBench is a lightweight open-source harness for checking whether an AI coding agent actually completed a task correctly instead of only sounding confident.

It gives you a small, readable structure for:

- writing a task specification
- stating agent rules and acceptance criteria
- running local validation
- recording the outcome as pass or fail

## Why This Exists

Coding agents often produce plausible answers without fully satisfying the task. That creates a gap between output quality and task completion quality.

AgentTaskBench exists to close that gap with simple, local, inspectable examples. It is designed to make failure modes obvious:

- scope drift
- partial fixes
- missed validation
- hidden behavior regressions
- overconfident but unverified output

## What Problem It Solves

This repo helps a human give an agent a well-scoped task and then verify the result with a repeatable local check.

Instead of asking, "Did the model give a good-looking response?", you can ask:

- Did it change only what was allowed?
- Did the tests pass?
- Did the result match the acceptance criteria?
- Can I see the evidence in a consistent format?

## Quickstart

Run the bundled examples from the repo root:

```bash
./scripts/run_validation.sh examples/python_bugfix
./scripts/run_validation.sh examples/spec_drift_guard
```

If you want to inspect a benchmark example, open the files in its folder:

- `TASK.md`
- `AGENT_RULES.md`
- `ACCEPTANCE_CRITERIA.md`
- `RESULT.md`
- `src/`
- `tests/`

## Repo Structure

```text
agent-taskbench/
├── docs/
├── examples/
├── scripts/
├── templates/
├── logs/
├── out/
├── PROJECT_STATUS.md
├── CONTRIBUTING.md
├── SECURITY.md
└── CHANGELOG.md
```

## Example Workflow

1. Choose an example benchmark.
2. Read `TASK.md` and `AGENT_RULES.md`.
3. Hand the task to a coding agent.
4. Run the example validator.
5. Compare the validator output with `ACCEPTANCE_CRITERIA.md`.
6. Record the result in `RESULT.md`.

That workflow keeps the evaluation anchored in behavior, not just narrative.

## What Skills It Demonstrates

This project is useful as a portfolio piece because it shows:

- task decomposition
- evaluation design
- test-driven validation
- careful scoping
- failure-mode awareness
- readable documentation
- cross-platform scripting basics

## Limitations

- It is intentionally simple and does not include a database, web app, or orchestration layer.
- It validates a handful of local examples rather than running a large benchmark suite.
- It does not measure model reasoning internally; it measures task outcomes externally.
- It is designed for clarity first, not scale.

## Roadmap

Possible next steps after v0.1:

- add more example tasks in different languages
- standardize machine-readable results
- add a simple summary generator
- add batch execution across all examples
- add scoring metadata for benchmark comparison

## Portfolio Positioning

AgentTaskBench is meant to read like a practical systems-and-evaluation project, not a toy demo. It shows that the author can define success criteria, build validation around them, and design for failure detection instead of demo theater. For hiring managers and AI engineering teams, that signals good judgment, strong workflow thinking, and a bias toward measurable outcomes.

