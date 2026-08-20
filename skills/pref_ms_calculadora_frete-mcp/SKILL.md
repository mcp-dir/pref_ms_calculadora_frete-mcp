---
name: pref_ms_calculadora_frete-mcp
description: Skill da REST API do Prefeitura MS: Calculadora de Fretes na MCP.AI: 1 endpoint em /api/pref_ms_calculadora_frete. Prefeitura MS: Calculadora de Fretes, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Prefeitura MS: Calculadora de Fretes — REST API skill

Você tem acesso à **Prefeitura MS: Calculadora de Fretes** REST API na MCP.AI.

> Prefeitura MS: Calculadora de Fretes, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/pref_ms_calculadora_frete
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/pref_ms_calculadora_frete/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"tipo_transporte":"...","data_prestacao":"...","distancia":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/pref_ms_calculadora_frete/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `pref_ms_calculadora_frete_consultar`

Prefeitura MS: Calculadora de Fretes, consulta em fonte oficial. _(POST /api/pref_ms_calculadora_frete/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `tipo_transporte` | string | Sim | Parâmetro de consulta "tipo_transporte". |
| `tipo_prestacao` | string | Não | Parâmetro de consulta "tipo_prestacao". |
| `data_prestacao` | string | Sim | Parâmetro de consulta "data_prestacao". |
| `quantidade` | string | Não | Parâmetro de consulta "quantidade". |
| `distancia` | string | Sim | Parâmetro de consulta "distancia". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_pref_ms_calculadora_frete` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
