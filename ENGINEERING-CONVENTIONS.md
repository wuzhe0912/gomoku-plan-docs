# Gomoku Multi-Repo Engineering Conventions

Applies to:
- `gomoku-plan-docs`
- `gomoku-client`
- `gomoku-server`

Last updated: 2026-02-20

## Commit Message Format

Use:

```text
[Type][Scope] Short description
```

Examples:

```text
[Feature][board] Add 15x15 grid rendering on canvas
[Fix][ws] Reject invalid move when it is not player's turn
[Docs][plan] Update v0.0.1 phase timeline
```

### Type

- `Feature`: new feature or capability
- `Fix`: bug fix
- `Refactor`: code refactor without behavior change
- `Chore`: tooling, config, CI, or maintenance
- `Docs`: documentation update
- `Style`: styling-only change without logic impact
- `Test`: add or update tests

### Scope

Shared scopes:
- `plan`: planning and roadmap docs
- `board`: board rendering and move interactions
- `ai`: AI logic and evaluation
- `worker`: Web Worker related changes
- `ws`: WebSocket protocol and handlers
- `room`: room lifecycle and matchmaking flow
- `game`: game rules and state management
- `api`: HTTP endpoints and schemas
- `ui`: presentation and UX behavior
- `infra`: Docker, deploy, environment setup
- `deps`: dependency updates

## Commit Rules

- Keep one logical change per commit.
- Commit title only. Do not include `Co-Authored-By` or auto-signature lines.
- Use imperative, concise descriptions.
- Update docs when behavior or workflow changes.

## Branch Naming

Recommended:

```text
feature/<scope>-<short-topic>
fix/<scope>-<short-topic>
chore/<scope>-<short-topic>
docs/<scope>-<short-topic>
```

## Public Repo Safety

- Never commit secrets, tokens, or private keys.
- Keep `.env` ignored and provide `.env.example` when env vars are needed.
- Sanitize screenshots/logs before publishing.

## Documentation Language

- Default prose can be Traditional Chinese.
- Keep technical terms in English (for consistency in code and searchability).

