# Agentic AI Engineering Drills

Structured Python notebooks for engineers building agentic AI systems — LLM APIs, tool use, agent loops, memory/RAG, multi-agent orchestration, and production serving.

Companion project to [ml-engineering-drills](../ml-engineering-drills) — same drill format (lesson → exercises → hidden solutions), but each lesson opens with a **context section**: the real-world problem being solved, a common production pitfall, and where the pattern shows up in actual agent frameworks. Explanations are deliberately more thorough here than in the base ML repo, without cutting technical depth — every exercise still has a real, checkable solution.

---

## Modules

### module1.ipynb &nbsp;·&nbsp; LLM API Foundations

| Topic | Concepts |
|---|---|
| Messages API | system vs user vs assistant roles, multi-turn conversation state |
| Sampling controls | temperature, top_p, max_tokens, stop sequences |
| Tokens & context window | tokenization basics, context limits, truncation strategies |
| Streaming | SSE streaming responses, incremental parsing, time-to-first-token |
| Structured output | JSON mode, schema-constrained generation, Pydantic-validated responses |
| Prompt caching | cache breakpoints, cost/latency tradeoffs, cache invalidation pitfalls |

### module2.ipynb &nbsp;·&nbsp; Tool Use & Function Calling

| Topic | Concepts |
|---|---|
| Tool definitions | JSON schema for tools, naming/description conventions that affect model behavior |
| The tool-call loop | request → tool_use → execute → tool_result → re-request |
| Parallel tool calls | batching independent calls, aggregating results |
| Tool choice | forced tool use, `auto` vs `any` vs named tool, disabling tools mid-conversation |
| Error handling | malformed arguments, tool execution failures fed back to the model, retry loops |

### module3.ipynb &nbsp;·&nbsp; Agent Loops & Architectures

| Topic | Concepts |
|---|---|
| ReAct pattern | reason → act → observe, from-scratch implementation |
| Planning | explicit upfront plans vs implicit step-by-step reasoning |
| Agent state machines | modeling agent status (planning/acting/waiting/done), transition guards |
| Loop control | iteration limits, cost budgets, timeout/circuit-breaker patterns |
| Guardrails | input/output validation, allow-lists for tool actions, refusal handling |
| Self-correction | reflection steps, critique-and-revise loops, verifying own outputs |

### module4.ipynb &nbsp;·&nbsp; Memory & Context Engineering

| Topic | Concepts |
|---|---|
| RAG fundamentals | chunking strategies, embeddings, similarity search, retrieval pipelines |
| When *not* to RAG | small-context alternatives, full-document stuffing, tool-based lookup |
| Short vs long-term memory | conversation buffers, summarization-based compaction, persistent memory stores |
| Context window management | sliding windows, relevance-based pruning, token budgeting across turns |
| Vector stores | indexing, top-k retrieval, metadata filtering |

### module5.ipynb &nbsp;·&nbsp; Multi-Agent Systems

| Topic | Concepts |
|---|---|
| Supervisor/worker pattern | task decomposition, dispatch, result aggregation |
| Sub-agent delegation | scoped sub-agents, isolated context, returning summaries not transcripts |
| Agent-to-agent communication | message passing, shared vs isolated state |
| MCP (Model Context Protocol) | server/client model, exposing tools and resources across agents |
| Human-in-the-loop | approval gates, escalation on low confidence, interrupt/resume |
| Orchestration | sequential vs parallel sub-agent execution, fan-out/fan-in |

### module6.ipynb &nbsp;·&nbsp; Serving & Production

| Topic | Concepts |
|---|---|
| FastAPI for agents | wrapping an agent loop in an API, request/response models |
| Streaming to clients | SSE endpoints, incremental token/event forwarding |
| Concurrency | `asyncio.Semaphore` for rate limiting, concurrent agent runs, backpressure |
| Observability | tracing agent steps, structured logging of tool calls, latency breakdowns |
| Cost tracking | token accounting per run, budget enforcement, alerting on runaway loops |
| Testing agents | mocking LLM calls, deterministic evals, `pytest` fixtures for agent harnesses |

### module7.ipynb &nbsp;·&nbsp; Live Coding Patterns

| Topic | Concepts |
|---|---|
| ReAct from scratch | minimal agent loop with no framework, under interview time pressure |
| Tool router | dispatching to the right tool from a registry, argument validation |
| Eval harness | scoring agent outputs against expected results, pass/fail assertions |
| Retry & backoff | exponential backoff on LLM/tool failures, idempotency considerations |
| Robust output parsing | handling malformed JSON from a model, partial-output recovery |

### practice.ipynb &nbsp;·&nbsp; 40-50 Mini Problems

| Tier | Problems | Focus |
|---|---|---|
| Warm-up | 1–12 | schema validation, prompt formatting, token counting |
| Core | 13–26 | tool routing, agent loop control, structured output parsing |
| Applied | 27–38 | mini RAG pipelines, memory compaction, sub-agent delegation |
| Full stack | 39–50 | end-to-end agent with eval harness, guardrails, cost tracking |

> Solutions are hidden in `# SOLUTION` comments. Try each problem before peeking.

---

## Usage

Open notebooks in Jupyter or VS Code and work through the modules in order. Each section follows the pattern: **context** (why this matters, where it bites in production) → **lesson** (annotated examples) → **exercises** (hidden solutions behind `# SOLUTION` comments).

## Tags

`python` `agentic-ai` `llm` `agents` `tool-use` `function-calling` `rag` `multi-agent` `mcp` `fastapi` `async` `pytest` `prompt-engineering` `interview-prep` `jupyter-notebook` `exercises`
