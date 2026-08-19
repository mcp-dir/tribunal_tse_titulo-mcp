---
name: tribunal_tse_titulo-mcp
description: Skill da REST API do Tribunal TSE: Título Eleitoral na MCP.AI: 1 endpoint em /api/tribunal_tse_titulo. Tribunal TSE: Título Eleitoral, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TSE: Título Eleitoral — REST API skill

Você tem acesso à **Tribunal TSE: Título Eleitoral** REST API na MCP.AI.

> Tribunal TSE: Título Eleitoral, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_tse_titulo
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
curl -X POST https://api.mcp.ai/api/tribunal_tse_titulo/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"birthdate":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_tse_titulo/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_tse_titulo_consultar`

Tribunal TSE: Título Eleitoral, consulta em fonte oficial. _(POST /api/tribunal_tse_titulo/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `birthdate` | string | Sim | Parâmetro de consulta "birthdate". |
| `mother` | string | Não | Parâmetro de consulta "mother". |
| `father` | string | Não | Parâmetro de consulta "father". |
| `name` | string | Não | Parâmetro de consulta "name". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `titulo_eleitoral` | string | Não | Parâmetro de consulta "titulo_eleitoral". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_tse_titulo` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
