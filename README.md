# Personal Agent

A full-stack personal AI assistant project based on a durable agent architecture. The repository combines a Nuxt web application with an Eve agent runtime, authentication, persistent memory, and optional integrations across multiple communication and productivity surfaces.

> **Project note:** This repository is based on the open-source Personal Agent Template and remains a template/customization project rather than an original AI model or hosted production service.

## Product Preview

A conceptual view of the assistant as a personal AI workspace: a focused chat interface backed by persistent context, memory, authentication, agent tools, and optional external integrations. The presentation emphasizes **durable conversations, contextual assistance, tool use, and multi-channel agent interaction** rather than a standalone chatbot UI.

## What It Does

- Provides a web chat interface for interacting with a personal AI assistant.
- Maintains durable conversations and user context across sessions.
- Supports long-term memory with user approval before memory is saved.
- Includes channel support for web chat, Slack, and iMessage through the project's integration layer.
- Provides GitHub and Linear integrations when their connections are configured.
- Includes a daily-summary workflow built around saved context and connected work items.
- Uses an Eve agent runtime with configurable instructions, tools, skills, and channels.

## Architecture

```text
Web / Slack / iMessage
        |
        v
   Eve Agent Runtime
        |
        v
 Nuxt 4 + Nitro API
        |
        +--> Better Auth
        +--> SQLite / NuxtHub
        +--> Long-term Memory
        +--> Connected Services
```

The agent's runtime instructions are dynamically assembled from the base instructions and, when available, the authenticated user's stored context. The default agent configuration uses Claude Sonnet through the AI provider configured by the project.

## Tech Stack

- TypeScript
- Nuxt 4 / Vue 3
- Eve agent framework
- Vercel AI SDK
- Better Auth
- Drizzle ORM
- SQLite / NuxtHub
- Tailwind CSS / Nuxt UI
- GitHub tools integration
- Linear integration
- Sendblue adapter for iMessage

## Project Structure

```text
personal-agent/
├── agent/          # Agent definition, instructions, channels, tools, and skills
├── app/            # Nuxt application UI
├── server/         # Nitro server routes and application backend
├── shared/         # Shared agent configuration and types
├── docs/           # Architecture and environment documentation
├── public/         # Static assets
└── package.json    # Project scripts and dependencies
```

## Local Development

### Requirements

- Node.js 24+
- pnpm 9+

### Setup

```bash
git clone https://github.com/Scarlet-Twinz/personal-agent.git
cd personal-agent
pnpm install
cp .env.example .env
pnpm db:migrate
pnpm dev
```

Then open `http://localhost:3000`.

### Environment

The application expects environment configuration for authentication and internal service communication. Keep secrets in `.env` and never commit them to the repository.

## Development Commands

```bash
pnpm dev
pnpm typecheck
pnpm build
pnpm db:generate
pnpm db:migrate
```

## Current Status

This repository is best presented as an **AI agent engineering / full-stack integration project**. Its value is in the architecture around durable sessions, memory, authentication, tool use, and multi-channel interaction—not in claiming a custom foundation model.

The project is currently configured around the template's example agent persona and integrations. Additional production deployment configuration should be treated as environment-specific rather than assumed from the repository alone.

## Attribution

The project is based on the open-source Personal Agent Template from Vercel Labs. The original template and its upstream documentation should be credited when distributing or presenting derivative work.

## Author

**Anthony Emmanuella Mmasinachi**

GitHub: [@Scarlet-Twinz](https://github.com/Scarlet-Twinz)

## License

MIT
