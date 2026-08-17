# Kamil — Day 4 Notes

## Stop hooks

A hook is code that automatically runs when an event happens.

Engineering Guardian first targets Claude Code's `Stop` event.

Our real captures already showed useful fields including:
- session_id
- transcript_path
- cwd
- stop_hook_active
- last_assistant_message

`stop_hook_active` matters because repeated blocking can create a loop.

Command hooks run code.
Prompt hooks ask a model to judge.

For factual claims, Engineering Guardian should prefer deterministic code.

## 140-session taxonomy

The 16 documented patterns were:

1. Rules Ignored
2. Context Amnesia
3. Memory Assert
4. Incorrect Artifacts
5. Apology Loop
6. Phantom Execution
7. Blind Edits
8. Ignores Stderr
9. Tautological QA
10. Unverified Summaries
11. Never Surfaces Mistakes
12. Skips Steps
13. No Verification Gates
14. LSP Integration Failures
15. Multi-Tab Token Waste
16. Model Downgrade Without Notification

Our project focuses only on completion claims that can be checked reliably, such as:
- did a command actually run?
- did tests actually pass?
- did a file actually change?
- did verification happen after the final edit?

## Claude Security lesson

Anthropic's Claude Security plugin challenges findings before reporting them and computes its verification tally in code.

This supports our rule:

**Agents route and explain. Tools decide.**

## Conclusion

Engineering Guardian is not valuable merely because it is a Stop hook.

Its value is claim-specific verification plus a benchmark comparing verification strategies.
