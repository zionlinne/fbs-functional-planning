# Formalize or Lose It

Research artifact for **Formalize or Lose It: What Executable Constraints Control in an Agent Swarm**.

## Feasibility Scheduler snapshot

[`fbs/`](fbs/) contains the source, documentation, and tests from the [upstream PR5 snapshot](https://github.com/zionlinne/feasibility-scheduler/tree/7630497cdb0b51682488ae14c31c74dce99109c7).
See the [functional planning documentation](fbs/docs/FUNCTIONAL_PLANNING.md) for plan validation, work-unit ownership, and acceptance.

To run the local code checks with Python 3.10+:

```sh
cd fbs
python -m pip install pytest
python -m pytest -q
```

## Independent pre-hackathon data

[Pre-hackathon FBS runs](data/pre-hackathon/) contains the structured records of eight executions of the same fulfillment task on 2–3 November 2026. It includes the paper's historical baseline, per-case acceptance outcomes, the scheduler event timelines, and source digests. The baseline logs identify the scheduler revision as `local-dev`.
