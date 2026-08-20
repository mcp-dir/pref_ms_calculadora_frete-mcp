# Instalação rápida

Prefeitura MS: Calculadora de Fretes é um servidor MCP remoto hospedado em `https://api.mcp.ai/p_pref_ms_calculadora_frete`. Você não baixa nem roda nada localmente — só aponta seu cliente pra essa URL.

A auth acontece em runtime: clientes com **OAuth 2.1** (Claude Desktop, Cursor, VS Code recentes) abrem o browser na 1ª chamada (magic-link). Clientes sem OAuth recebem a tool `authenticate` — abra `https://app.mcp.ai/agent-auth`, faça login, copie o JWT e cole no chat.

---

## Claude (Web e Desktop)

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → `Prefeitura MS: Calculadora de Fretes` / `https://api.mcp.ai/p_pref_ms_calculadora_frete`.

Config file (legado): `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) ou `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{ "mcpServers": { "pref_ms_calculadora_frete": { "type": "http", "url": "https://api.mcp.ai/p_pref_ms_calculadora_frete" } } }
```

## Cursor

[➕ Instalar no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=pref_ms_calculadora_frete&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9wcmVmX21zX2NhbGN1bGFkb3JhX2ZyZXRlIn0=)

`.cursor/mcp.json`:
```json
{ "mcpServers": { "pref_ms_calculadora_frete": { "url": "https://api.mcp.ai/p_pref_ms_calculadora_frete" } } }
```

## VS Code (Copilot Chat)

[➕ Instalar no VS Code](vscode:mcp/install?name=pref_ms_calculadora_frete&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_pref_ms_calculadora_frete%22%7D)

`.vscode/mcp.json`:
```json
{ "servers": { "pref_ms_calculadora_frete": { "type": "http", "url": "https://api.mcp.ai/p_pref_ms_calculadora_frete" } } }
```

## Outros clientes MCP

Qualquer cliente com **MCP over HTTP**. URL fixa:

```
https://api.mcp.ai/p_pref_ms_calculadora_frete
```

Dúvidas? [pref_ms_calculadora_frete@mcp.ai](mailto:pref_ms_calculadora_frete@mcp.ai)
