# Independent FBS runs before the hackathon

This dataset records eight executions on 2–3 November 2026 (Asia/Shanghai), before the 6–8 November Swarm Alignment Hackathon. All eight used the same byte-identical task specification for an offline order and multi-warehouse fulfillment service. The original task SHA-256 appears in [source-digests.json](source-digests.json).

## Paper baseline

The paper's historical baseline is `2026-11-03-fbs-baseline`. The output directory started empty. The coordinator provided the plan, transports, and integration, and three native Worker authors contributed. The historical driver relayed bridge responses under manual coordination. The composition stage used a synthetic response envelope before the real independent verifier ran.

The verifier passed **125 of 125 cases** and executed **2,599 assertions**. The reported end-to-end time was **528.248634 seconds**. The 93 scheduler events begin after the initial planning request, so the event span is shorter than the reported elapsed time. The run records `local-dev` as its scheduler revision. The PR5 snapshot in this repository provides implementation context. The historical run's source commit is unknown.

## Files

- [runs.csv](runs.csv) lists each verified stage, with scheduler completion reported separately from the verifier result. The native repair run has a row for each of its two verifier stages.
- [acceptance-cases.csv](acceptance-cases.csv) contains all 1,125 case results across the nine recorded verifier stages, including case failures and errors, with assertion and invocation counts. `assertions_executed` counts total assertions, including failed ones.
- [events/](events/) contains one CSV per execution. Each preserves the event sequence, timestamps, event types, and task transitions. The scheduler timestamps retain their recorded time offsets. Run IDs use the date in Asia/Shanghai.
- [baseline-summary.json](baseline-summary.json) records the baseline verifier totals, task states, and module-execution evidence. [baseline-delivery-sha256.json](baseline-delivery-sha256.json) records the nine delivered files' SHA-256 hashes.
- [source-digests.json](source-digests.json) identifies the original event and verifier records used to prepare these exports. The hashes refer to the original records.

The earlier executions include timeouts, prepared deliveries, a diagnostic continuation, a repair, and a revision of an existing implementation. Treat them as historical engineering evidence. In particular, `2026-11-03-api-032224` stopped before automatic completion. Its 125-case pass came from a later manual verifier invocation. The execution modes distinguish fresh generation, replay, repair, and revision. The underlying verifier leaves disk corruption and crash recovery during commit outside its coverage.

The release contains structured exports of the local records. It publishes event and outcome fields, with original prompts, machine-local paths, and full invocation bodies omitted.
