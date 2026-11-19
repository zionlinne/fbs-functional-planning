# Independent FBS runs from the opening days

This export covers five FBS executions from 6–8 November 2026, using dates in Asia/Shanghai (UTC+08:00). The original timestamps retain their time offsets. Both scoped fulfillment runs took place late on 7 November in UTC and early on 8 November in Asia/Shanghai.

## Recorded outcomes

- **6 November, document search.** A native PR5 run started from an empty implementation directory. The verifier passed 35 of 35 cases and executed 202 assertions. The measured interval from the first native planning request to completion was 219.609 seconds.
- **7 November, document search.** One run passed 35 of 35 cases. A fresh retry reached final acceptance and was rejected with 33 of 35 cases passing. Both runs executed 202 assertions against the same task and case inventory. Their timestamps measure the launcher start to the final scheduler event.
- **8 November, order fulfillment.** The first and second scoped Worker rounds passed 125 of 125 cases each and executed 2,599 assertions each. The reported elapsed times were 378.812 and 400.953 seconds. Both started from empty implementation directories with four fresh Worker contexts and a supplied plan. Root retained the task and existing interface design. The second round also revised guidance on error handling, transaction and audit ownership, and module boundaries.

The [3 November fulfillment baseline](../pre-hackathon/) used the same task specification and 125-case inventory. Worker context counts, orchestration details, and timer boundaries are relevant to comparisons. The two scoped observations alone cannot establish a causal effect of prompt length.

## Files

- [runs.csv](runs.csv) records the run and verifier outcomes and defines the interval in `elapsed_scope`.
- [acceptance-cases.csv](acceptance-cases.csv) records all 355 case outcomes, including the two failures in the rejected run.
- [events/](events/) contains the 430 scheduler events, in original sequence, with timestamps, event types, and task states.
- [worker-prompt-lengths.csv](worker-prompt-lengths.csv) contains the historical character counts for four scoped Worker prompts in each fulfillment round. These counts cover those rendered prompts and use Unicode characters.
- [source-digests.json](source-digests.json) identifies the source evidence and records SHA-256 digests of the underlying task and run records.

These structured exports omit original prompt text, machine-local paths, and full invocation bodies.
