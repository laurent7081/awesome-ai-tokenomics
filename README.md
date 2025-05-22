# Awesome AI Tokenomics [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<a href="https://github.com/QuesmaOrg/awesome-ai-tokenomics"><img src=".github/logo.svg" align="right" width="110" alt=""></a>

> Pricing, measurement, optimization, and governance of tokens used by AI models.

Tools, papers, benchmarks, and vendor pages on what AI tokens cost and where they go.

## Contents

- [Monitor](#monitor)
  - [Dashboards](#dashboards)
  - [eBPF Kernel Capture](#ebpf-kernel-capture)
  - [Observability](#observability)
  - [Observability Platforms](#observability-platforms)
  - [OTel for LLMs](#otel-for-llms)
  - [Tracing](#tracing)
- [Optimize](#optimize)
  - [Caching](#caching)
  - [Cheap Local Models](#cheap-local-models)
  - [Compression](#compression)
  - [Context Engineering](#context-engineering)
  - [Cost Controls](#cost-controls)
  - [Gateways and Proxies](#gateways-and-proxies)
  - [Harness Efficiency](#harness-efficiency)
  - [Memory](#memory)
  - [Multi-Agent Systems](#multi-agent-systems)
  - [Prompt Agent Loop](#prompt-agent-loop)
  - [Retrieval Memory](#retrieval-memory)
  - [Retry and Reliability](#retry-and-reliability)
  - [Routing Model Selection](#routing-model-selection)
  - [Search and Retrieval Boundary](#search-and-retrieval-boundary)
  - [Serving Inference](#serving-inference)
  - [Test-Time Compute](#test-time-compute)
  - [Tool Protocol Overhead](#tool-protocol-overhead)
- [Govern](#govern)
  - [Allocation Chargeback](#allocation-chargeback)
  - [Anomaly Detection](#anomaly-detection)
  - [Billing Audit FinOps](#billing-audit-finops)
  - [Budgets Caps](#budgets-caps)
  - [Policy Enforcement](#policy-enforcement)
  - [Spend Management](#spend-management)
  - [Unit Economics](#unit-economics)
- [Understand](#understand)
  - [Buyer Incentives](#buyer-incentives)
  - [Compression Efficacy](#compression-efficacy)
  - [Consolidation](#consolidation)
  - [Market Competitors](#market-competitors)
  - [Market Sizing](#market-sizing)
  - [Model Economics](#model-economics)
  - [Pricing Models](#pricing-models)
  - [Reliability SLAs](#reliability-slas)
  - [Unit Economics](#unit-economics-1)
- [Measure](#measure)
  - [Benchmarks Evals](#benchmarks-evals)
  - [Cache Accounting](#cache-accounting)
  - [Cost Anatomy](#cost-anatomy)
  - [Energy Carbon](#energy-carbon)
  - [Harness Overhead](#harness-overhead)
  - [Metering](#metering)
  - [Transcript Analysis](#transcript-analysis)
  - [Whole Bill Accounting](#whole-bill-accounting)
- [Related lists](#related-lists)

### Legend

Each entry ends with a kind badge: ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) (blue, with the license when known), or a gray badge for ![paper](https://img.shields.io/badge/paper-555?style=flat-square), ![bench](https://img.shields.io/badge/bench-555?style=flat-square), ![data](https://img.shields.io/badge/data-555?style=flat-square), ![co](https://img.shields.io/badge/co-555?style=flat-square) for companies, and ![report](https://img.shields.io/badge/report-555?style=flat-square). Plain entries are articles. GitHub-hosted tools also carry a live last-commit badge.

## Monitor

### Dashboards

- [antiburn](https://github.com/antiburn/antiburn) - Desktop app for macOS, Windows and Linux that reads local session logs from coding agents, flags token-burn causes, and applies and verifies supported configuration fixes. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/antiburn/antiburn?style=flat-square&label=)
- [ccusage](https://github.com/ccusage/ccusage) - CLI that reads local agent logs to report token usage and cost across coding-agent sources, with caching-aware pricing. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/ccusage/ccusage?style=flat-square&label=)
- [Claude Code Usage Monitor](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) - Live terminal dashboard for Claude Code usage with burn-rate analytics, limit detection, and session-expiry forecasts. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/Maciek-roboblog/Claude-Code-Usage-Monitor?style=flat-square&label=)
- [claude-usage](https://github.com/phuryn/claude-usage) - Local dashboard for Claude Code token usage, costs, and session history. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/phuryn/claude-usage?style=flat-square&label=)
- [ClaudeBar](https://github.com/tddworks/ClaudeBar) - Menu-bar app for macOS that monitors AI coding quotas across multiple providers. ![tool: MIT declared in README](https://img.shields.io/badge/tool-MIT_declared_in_README-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/tddworks/ClaudeBar?style=flat-square&label=)
- [CodeBurn](https://github.com/getagentseal/codeburn#find-and-fix-waste) - Usage tracker for coding tools whose optimize command flags harness-waste patterns with dollar estimates. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square)
- [Codex Usage Tracker](https://github.com/douglasmonsky/codex-usage-tracker) - Local-first dashboard, CLI, and MCP tools that index Codex CLI logs into SQLite to show where tokens, credits, and cost go, including cache ratios. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/douglasmonsky/codex-usage-tracker?style=flat-square&label=)
- [CodexBar](https://github.com/steipete/CodexBar) - Menu-bar app for macOS that shows limits, reset timers, credit balances, and spending across AI providers. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/steipete/CodexBar?style=flat-square&label=)
- [CodeZeno Usage Monitor](https://github.com/CodeZeno/Claude-Code-Usage-Monitor) - Windows taskbar widget that shows Claude Code quota and usage without opening a terminal. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/CodeZeno/Claude-Code-Usage-Monitor?style=flat-square&label=)
- [Datadog LLM Observability Cost](https://docs.datadoghq.com/llm_observability/monitoring/cost/) - Datadog documentation on per-request LLM cost estimates computed from token counts and public pricing. ![co](https://img.shields.io/badge/co-555?style=flat-square)
- [gh-aw](https://github.com/github/gh-aw) - GitHub Agentic Workflows runtime with per-run token and cost metering and budget caps that stop a workflow mid-run. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/github/gh-aw?style=flat-square&label=)
- [Grafana Cloud GenAI Observability](https://grafana.com/docs/grafana-cloud/monitor-applications/ai-observability/genai/observability/) - Prebuilt Grafana Cloud dashboard for LLM cost, token usage, and latency, built on the OpenLIT SDK. ![co](https://img.shields.io/badge/co-555?style=flat-square)
- [OpenLIT](https://github.com/openlit/openlit) - OpenTelemetry-native platform with a self-hosted dashboard for LLM cost, token, and latency observability. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/openlit/openlit?style=flat-square&label=)
- [OpenUsage](https://github.com/robinebers/openusage) - Native Swift macOS menu-bar meter for AI coding subscriptions, showing session and weekly limits, credits, and estimated spend. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/robinebers/openusage?style=flat-square&label=)
- [TokenTracker](https://github.com/mm7894215/TokenTracker) - Local-first token and cost dashboard for coding tools, with a desktop pet, native widgets, and achievements. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/mm7894215/TokenTracker?style=flat-square&label=)

### eBPF Kernel Capture

- [AgentSight](https://github.com/eunomia-bpf/agentsight) - Uses eBPF to watch an AI agent from the kernel boundary and correlate what it said it would do with what it did. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/eunomia-bpf/agentsight?style=flat-square&label=)
- [OpenTelemetry eBPF Instrumentation](https://opentelemetry.io/docs/zero-code/obi/) - Zero-code eBPF instrumentation from OpenTelemetry that captures GenAI and MCP traces at the kernel layer without an SDK. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square)

### Observability

- [Braintrust](https://www.braintrust.dev) - Closed-source eval and observability SaaS whose span metrics normalize cached prompt tokens across providers and expose per-user and per-model spend. ![co](https://img.shields.io/badge/co-555?style=flat-square)
- [Langfuse](https://langfuse.com) - Open-source platform for tracing, evaluating, and analyzing LLM and agent transcripts, with a prompt-management layer. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square)

### Observability Platforms

- [OpenAI Prompt Cache Diagnostics](https://developers.openai.com/api/docs/guides/prompt-caching/diagnostics) - OpenAI guide to a Responses API feature that returns a machine-readable reason why a prompt prefix was not reused from the cache. ![tool: proprietary](https://img.shields.io/badge/tool-proprietary-blue?style=flat-square)

### OTel for LLMs

- [OpenLLMetry](https://github.com/traceloop/openllmetry) - Open-source set of OpenTelemetry-based SDKs and instrumentations for LLM apps, built by Traceloop. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/traceloop/openllmetry?style=flat-square&label=)
- [OpenTelemetry GenAI Semantic Conventions](https://github.com/open-telemetry/semantic-conventions-genai) - OpenTelemetry conventions that define vendor-neutral token, cost, and cache attribute names for GenAI telemetry.

### Tracing

- [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Source-available (Elastic License 2.0) LLM tracing platform that records per-span token counts and USD cost via OpenTelemetry. ![tool: Elastic-2.0](https://img.shields.io/badge/tool-Elastic--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/Arize-ai/phoenix?style=flat-square&label=)
- [claude-tap](https://github.com/liaohch3/claude-tap) - Local trace viewer that intercepts API traffic from coding agents and shows per-request token breakdowns: input, output, cache read, cache creation. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/liaohch3/claude-tap?style=flat-square&label=)
- [LangSmith Cost Tracking](https://docs.langchain.com/langsmith/cost-tracking) - LangChain documentation on cost tracking in LangSmith, its commercial LLM and agent observability service. ![co](https://img.shields.io/badge/co-555?style=flat-square)
- [Opik](https://github.com/comet-ml/opik) - Open-source (Apache-2.0) LLM observability platform from Comet, with per-span USD cost estimated from token usage. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/comet-ml/opik?style=flat-square&label=)

## Optimize

### Caching

- [khazad](https://github.com/GuglielmoCerri/khazad) - Transport-layer semantic cache for LLM APIs on Redis 8 Vector Sets that intercepts HTTP traffic without application code changes. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/GuglielmoCerri/khazad?style=flat-square&label=)
- [LMCache](https://github.com/LMCache/LMCache) - Self-hosted KV-cache layer beneath vLLM that gives token-level cache-hit observability for teams that own their GPUs. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/LMCache/LMCache?style=flat-square&label=)
- [prompt-cache](https://github.com/messkan/prompt-cache) - Go LLM proxy with a three-tier semantic cache that uses a cheap verification model for borderline similarity matches. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/messkan/prompt-cache?style=flat-square&label=)
- [Redis LangCache](https://redis.io/langcache/) - Managed semantic cache with a REST API that returns a stored response when a new query is similar to a past one. ![tool: proprietary](https://img.shields.io/badge/tool-proprietary-blue?style=flat-square)

### Cheap Local Models

- [llama.cpp](https://github.com/ggml-org/llama.cpp) - Open-source (MIT) local LLM inference engine with a built-in OpenAI-compatible server. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/ggml-org/llama.cpp?style=flat-square&label=)
- [Ollama](https://github.com/ollama/ollama) - Runtime for running open-weight models locally on hardware you already own. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/ollama/ollama?style=flat-square&label=)

### Compression

- [Context Mode](https://github.com/mksglu/context-mode) - MCP server that sandboxes tool calls and returns only the distilled result to the model. ![tool: Elastic-2.0](https://img.shields.io/badge/tool-Elastic--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/mksglu/context-mode?style=flat-square&label=)
- [headroom](https://github.com/headroomlabs-ai/headroom) - Apache-2.0 context-compression tool for LLM and agent pipelines. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/headroomlabs-ai/headroom?style=flat-square&label=)
- [lean-ctx](https://github.com/yvgude/lean-ctx) - Rust MCP server that mediates what a coding agent reads, with a savings ledger and an accounting of its own context overhead. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/yvgude/lean-ctx?style=flat-square&label=)
- [LLMLingua](https://github.com/microsoft/LLMLingua) - Microsoft prompt-compression library that uses a small model to drop low-information tokens before a prompt reaches the target LLM. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/microsoft/LLMLingua?style=flat-square&label=)
- [llmtrim](https://github.com/fkiene/llmtrim) - Local proxy that compresses a coding agent's prompt, tool schemas, and history before forwarding, and can reroute Claude calls to Grok. ![tool: MPL-2.0](https://img.shields.io/badge/tool-MPL--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/fkiene/llmtrim?style=flat-square&label=)
- [Minification of State-in-Context Agents](https://arxiv.org/abs/2606.01326) - ICPC 2026 study of minifying code in a coding agent's context, measuring the input-token savings against the accuracy cost. ![paper](https://img.shields.io/badge/paper-555?style=flat-square)
- [rtk](https://github.com/rtk-ai/rtk) - Single-binary Rust CLI proxy that compresses the output of common dev commands before it reaches a coding agent's context window. ![tool: Apache-2.0](https://img.shields.io/badge/tool-Apache--2.0-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/rtk-ai/rtk?style=flat-square&label=)
- [snip](https://github.com/edouard-claude/snip) - Single-binary Go CLI proxy that filters dev-command output before it reaches a coding agent, using declarative YAML filter pipelines. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/edouard-claude/snip?style=flat-square&label=)
- [TOON](https://github.com/toon-format/toon) - Compact, human-readable, lossless serialization of the JSON data model, designed for LLM input. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/toon-format/toon?style=flat-square&label=)

### Context Engineering

- [AgentDiet](https://arxiv.org/abs/2509.23586) - Paper on an inference-time module that strips useless, redundant, and expired information from an agent's trajectory. ![paper](https://img.shields.io/badge/paper-555?style=flat-square)
- [Anthropic Context Management](https://platform.claude.com/docs/en/build-with-claude/context-editing) - Anthropic documentation for context editing, the memory tool, and server-side compaction in the Claude API.
- [Claude Code Compaction Engine](https://barazany.dev/blog/claude-codes-compaction-engine) - Blog post describing the three-tier compaction engine Claude Code uses to trim a filling context window, and its cache and correctness failure modes.
- [CliffCompaction](https://github.com/nguyenvuthientrang/cliffcompaction) - CMU autocompaction proxy that shrinks an agent's context only by truncating or dropping content, never by LLM rewriting, and works in front of Claude Code or Codex. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/nguyenvuthientrang/cliffcompaction?style=flat-square&label=)
- [Codex CLI Compaction Issue](https://github.com/openai/codex/issues/16812) - GitHub issue reporting that a Codex CLI upgrade made context compaction fire more often and raised token consumption for identical tasks.
- [Context Rot](https://www.trychroma.com/research/context-rot) - Chroma study of how LLM output quality changes as input length grows, with task difficulty held fixed. ![report](https://img.shields.io/badge/report-555?style=flat-square)
- [ContextBudget](https://arxiv.org/abs/2604.01664) - Paper on BACM, a method where an agent decides when and how much to compress its history based on the remaining context budget. ![paper](https://img.shields.io/badge/paper-555?style=flat-square)
- [Cursor Dynamic Context Discovery](https://cursor.com/blog/dynamic-context-discovery) - Cursor blog post on loading tool schemas and large outputs on demand instead of eagerly, and on Composer self-summarization.
- [Repomix](https://github.com/yamadashy/repomix) - Packs an entire repository into a single AI-friendly file, reports token counts, and uses Tree-sitter to compress code to signatures. ![tool: MIT](https://img.shields.io/badge/tool-MIT-blue?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/yamadashy/repomix?style=flat-square&label=)
- [RULER](https://github.com/NVIDIA/RULER) - NVIDIA long-context benchmark that measures how model quality holds up as the context window fills. ![bench](https://img.shields.io/badge/bench-555?style=flat-square) ![last commit](https://img.shields.io/github/last-commit/NVIDIA/RULER?style=flat-square&label=)
- [Self-Compacting Language Model Agents](https://arxiv.org/abs/2606.23525) - Paper introducing SELFCOMPACT, where the model itself decides when and how to compress a growing agent trace. ![paper](https://img.shields.io/badge/paper-555?style=flat-square)
- [Serena](https://github.com/oraios/serena) - Open-source MC