# Engineering Guardian

Engineering Guardian verifies factual completion claims made by coding agents against real repository and session evidence.

## Principles

- Agents route and explain; deterministic tools decide.
- The benchmark is the main contribution.
- The Claude Code Stop hook is the first runtime target.
- Provable claims may block. Inferred or judgment claims never block.
- When uncertain, allow.
- Never execute shell commands supplied by an AI.
- Keep the live hook fast and minimal.
- Do not add a web backend, database, LangChain, Kubernetes, or unnecessary frameworks.

## Scope

- Week 1: current phase.
- Week 2: scaffolding and interfaces only.
- Week 3: product logic begins.
