---
name: cfm_estabelecimento-mcp
description: Skill da REST API do Conselho Federal de Medicina: Estabelecimentos de Saúde na MCP.AI: 1 endpoint em /api/cfm_estabelecimento. Conselho Federal de Medicina: Estabelecimentos de Saúde, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Conselho Federal de Medicina: Estabelecimentos de Saúde — REST API skill

Você tem acesso à **Conselho Federal de Medicina: Estabelecimentos de Saúde** REST API na MCP.AI.

> Conselho Federal de Medicina: Estabelecimentos de Saúde, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/cfm_estabelecimento
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
curl -X POST https://api.mcp.ai/api/cfm_estabelecimento/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cnpj":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/cfm_estabelecimento/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `cfm_estabelecimento_consultar`

Conselho Federal de Medicina: Estabelecimentos de Saúde, consulta em fonte oficial. _(POST /api/cfm_estabelecimento/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Sim | Parâmetro de consulta "cnpj". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_cfm_estabelecimento` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
