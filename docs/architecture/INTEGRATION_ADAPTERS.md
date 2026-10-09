# Integration Adapters

> **Status:** PROPOSED

## Purpose

Integration Adapters provide a uniform interface between the Factory Core
and external systems: model providers, tool services, APIs, and platforms.
Adapters isolate the factory from provider-specific implementation details.

## Adapter Types

### Model Provider Adapters

| Provider | Status | Notes |
|---|---|---|
| OpenAI | PROPOSED | Chat Completions, Assistants API |
| Anthropic | PROPOSED | Claude API, Message batches |
| DeepSeek | PROPOSED | DeepSeek API compatibility |
| Google | PROPOSED | Gemini API |
| Local/Ollama | PROPOSED | Self-hosted model inference |

### Tool Integration Adapters

Tools are the mechanism by which agents interact with the world. Each tool
has an adapter that provides:

- Unified schema definition.
- Error handling and retry logic.
- Cost and rate-limit tracking.
- Permission scoping.

### Protocol Adapters

| Protocol | Status | Notes |
|---|---|---|
| MCP (Model Context Protocol) | PROPOSED | Standardized tool exposure |
| A2A (Agent-to-Agent) | PROPOSED | Inter-agent communication |
| OpenAI Agents SDK | PROPOSED | Agent framework integration |
| LangGraph | PROPOSED | Workflow orchestration |

## Adapter Contract

Every adapter must implement:

1. init() -- Initialize connection, authenticate.
2. execute(params) -- Execute the tool or API call.
3. validate(result) -- Validate the result against expectations.
4. cost() -- Report token/compute cost incurred.
5. cleanup() -- Close connections, release resources.

## Adding New Adapters

1. New adapters start at EXPERIMENTAL in the capability lifecycle.
2. Must pass benchmarking and evaluation.
3. Must be reviewed by the Security Threat Intelligence Team.
4. Promoted to ACTIVE only with Owner approval.
5. Must not break existing adapter contracts.
