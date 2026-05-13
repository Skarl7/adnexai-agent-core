# AdnexAI Agent Core

> Multi-agent AI orchestration framework for business automation

[![Node.js](https://img.shields.io/badge/Node.js-%3E18.0-339933?logo=node.js&logoColor=white)](https://nodejs.org)
[![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white)](https://js.langchain.com)
[![n8n](https://img.shields.io/badge/n8n-EA4B71?logo=n8n&logoColor=white)](https://n8n.io)

**Built by** [Skarl7](https://github.com/Skarl7) | [AdnexAI](https://www.adnexai.co.uk)

---

## Architecture

```
+---------------------------------+
|       Agent Orchestrator        |
|  (Task Router + State Manager)  |
+----------+----------+-----------+
| Intake   | Research | Comms     |
| Agent    | Agent    | Agent     |
+----------+----------+-----------+
| n8n      | RAG      | WhatsApp  |
| Workflows| Engine   | Telegram  |
+----------+----------+-----------+
```

## Quick Start

```javascript
const { Orchestrator, IntakeAgent } = require('adnexai-agent-core');

const orchestrator = new Orchestrator({
  llm: 'openai/gpt-4o-mini',
  memory: 'in-memory'
});

const agent = new IntakeAgent({
  name: 'Legal Intake Bot',
  formFields: ['name', 'email', 'serviceType'],
  outputChannel: 'telegram'
});

orchestrator.registerAgent(agent);
await orchestrator.run('new client intake');
```

## Features

- Modular multi-agent architecture
- n8n workflow integration
- Multi-channel notifications (WhatsApp, Telegram, Email)
- GDPR-aware data handling
- Swappable LLM backends (OpenAI, Claude)

## Roadmap

- [x] Core orchestrator with state management
- [ ] MCP server support
- [ ] LangGraph integration
- [ ] WhatsApp Business API connector
- [ ] Analytics dashboard

## License

Apache 2.0

---
*AdnexAI ecosystem - www.adnexai.co.uk*
