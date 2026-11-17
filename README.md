# AI Testing — Playwright + MCP (TypeScript)

## Setup
```bash
npm install
npx playwright install
```

## Run tests
| Command | Purpose |
|---|---|
| `npm test` | Run all tests (chromium, firefox, webkit) |
| `npm run test:headed` | Run with visible browser |
| `npm run test:ui` | Playwright UI mode |
| `npm run report` | Open HTML report |
| `npm run codegen` | Record a test |
| `npm run typecheck` | TypeScript check |

Set `BASE_URL` to test a different site: `BASE_URL=http://localhost:3000 npm test`

## Playwright MCP server
Configured via `playwright-mcp.config.json` (browser, headless, viewport, capabilities).

- **Claude Code** — `.mcp.json` (auto-detected in this folder; approve on first launch)
- **VS Code / Copilot** — `.vscode/mcp.json`
- **Cursor / Claude Desktop / others** — add:
  ```json
  { "mcpServers": { "playwright": { "command": "npx", "args": ["@playwright/mcp", "--config", "/absolute/path/to/playwright-mcp.config.json"] } } }
  ```
- **HTTP mode** — `npm run mcp:http`, then point your client to `http://localhost:8931/mcp`

## Structure
```
playwright.config.ts        Test runner config
playwright-mcp.config.json  MCP server config
tests/
  pages/HomePage.ts         Page Object example
  example.spec.ts           Sample tests
```
