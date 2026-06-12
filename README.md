# Dual Agent SDK

Generator-Critic dual-agent orchestration framework for Python and TypeScript.

## Install

### Python

```bash
pip install dual-agent-sdk
```

### TypeScript

```bash
npm install dual-agent-sdk
```

## Quick Start

```python
import asyncio
from dual_agent_sdk import (
    DualAgentOrchestrator, AnthropicAdapter, OpenAIAdapter,
)

async def main():
    orchestrator = DualAgentOrchestrator(
        generator=AnthropicAdapter(model="claude-sonnet-4-6"),
        critic=OpenAIAdapter(model="gpt-4o"),
    )
    result = await orchestrator.run("Write a secure auth middleware")
    print(result.content)

asyncio.run(main())
```

## Features

- Generator-Critic dual-agent pattern
- 6-layer anti-loop convergence protocol
- Semantic loop detection with meta-judge escalation
- Multi-provider: Anthropic, OpenAI, any OpenAI-compatible API
- Python (Pydantic) + TypeScript (Zod) with identical APIs

## Docs

See [docs/](docs/) for architecture, API reference, and convergence protocol details.

## License

MIT
