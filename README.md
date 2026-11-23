# Arthus — plugin para assistentes de IA

[English below](#english)

O Arthus grava e transcreve as suas reuniões e escreve resumos com decisões e tarefas. Este plugin
liga o seu assistente de IA à sua conta do Arthus. Você pergunta sobre as reuniões e cuida das
tarefas sem sair da conversa.

## O que vem no plugin

- **O servidor do Arthus**, no endereço `https://mcp.arthus.ai/mcp`. Ele usa o MCP, o padrão aberto
  que liga assistentes a apps. Nenhuma senha ou chave fica no plugin: você entra pela tela do
  Arthus.
- **Três skills**, que ensinam o assistente a usar o Arthus bem:
  - `recap` — o que ficou combinado numa reunião: decisões, tarefas e o que ficou em aberto. Cita
    o tempo de cada fala e termina com o link.
  - `my-week` — as suas tarefas em aberto, as atrasadas primeiro, e as decisões do período.
  - `prepare` — prepara a próxima reunião com uma pessoa, uma empresa ou sobre um assunto.

## O que o assistente pode e não pode fazer

- **Pode:** achar reuniões e ler o resumo e a transcrição. Também lista tarefas, muda o andamento
  ou o prazo, move ou renomeia reuniões, dá nome aos locutores quando você confirma o nome e cria
  projetos.
- **Não pode:** gravar, apagar ou arquivar reuniões, criar link público, enviar e-mail ou importar
  arquivos. Isso continua no app do Arthus.
- **Ainda não disponível pelo assistente:** perguntas respondidas pela IA do Arthus e a geração de
  mapa mental.

Na tela do Arthus, você escolhe o que cada assistente pode fazer. Para desconectar, use
**Configurações → Assistentes de IA**.

## Como instalar

O passo a passo de cada assistente fica em <https://arthus.ai/conectar>.

No primeiro uso, o assistente abre a tela de login do Arthus. Você entra e escolhe o que ele pode
fazer.

<!-- Só prometa o que prova (revisão de 22/10): a tabela por assistente volta aqui, linha a linha,
quando cada cliente passar na matriz de testes do dono (PLANO_MCP_E_CLI §10.3). -->

## Privacidade

- O assistente só vê o que você vê no Arthus, com os limites do seu plano. No Grátis, são as
  reuniões dos últimos 30 dias.
- O que o assistente lê das reuniões passa a ser tratado também pela empresa dele, sob as regras
  dela.
- Resumos, tarefas e títulos marcados como da IA foram escritos pela IA do Arthus e podem ter
  erros. Cada reunião vem com o link para você conferir na fonte.
- Política de Privacidade: <https://arthus.ai/pt-BR/privacidade> · Termos de Uso:
  <https://arthus.ai/pt-BR/termos>

## Contato

<contact@arthus.ai>

---

## English

Arthus records and transcribes your meetings and writes summaries with decisions and tasks. This
plugin connects your AI assistant to your Arthus account. You ask about your meetings and handle
your tasks without leaving the conversation.

### What is in the plugin

- **The Arthus server**, at `https://mcp.arthus.ai/mcp`. It uses MCP, the open standard that
  connects assistants to apps. No password or key is stored in the plugin: you sign in on the
  Arthus screen.
- **Three skills** that teach the assistant to use Arthus well:
  - `recap` — what was agreed in a meeting: decisions, tasks and what was left open. It quotes the
    time of each passage and ends with the link.
  - `my-week` — your open tasks, overdue first, and the decisions of the period.
  - `prepare` — gets you ready for the next meeting with a person, a company or about a subject.

### What the assistant can and cannot do

- **Can:** find meetings and read the summary and the transcript. It also lists tasks, changes
  their status or due date, moves or renames meetings, names speakers when you confirm the name,
  and creates folders.
- **Cannot:** record, delete or archive meetings, create public links, send email or import files.
  Those stay in the Arthus app.
- **Not yet available through the assistant:** questions answered by Arthus AI and mind map
  generation.

On the Arthus screen, you choose what each assistant may do. To disconnect, use
**Settings → AI assistants**.

### How to install

The steps for each assistant are at <https://arthus.ai/conectar>.

On first use, the assistant opens the Arthus sign-in screen. You sign in and choose what it may do.

### Privacy

- The assistant only sees what you see in Arthus, within your plan's limits. On Free, that is the
  meetings of the last 30 days.
- What the assistant reads from your meetings is also handled by the assistant's company, under
  its rules.
- Summaries, tasks and titles marked as AI-written were written by Arthus AI and may have errors.
  Each meeting comes with its link, so you can check the source.
- Privacy Policy: <https://arthus.ai/pt-BR/privacidade> · Terms of Use:
  <https://arthus.ai/pt-BR/termos>

### Contact

<contact@arthus.ai>

---

## Para quem mantém: os manifestos e de onde vem cada campo

Esta pasta é a fonte única. Ela mora em `connect/plugins/arthus/` no repositório do Arthus e é
copiada para o repositório público por `connect/scripts/publicar-plugin.mjs`. Conferido em
22/10/2026.

| Arquivo | Para quem | Fonte |
| --- | --- | --- |
| `.claude-plugin/plugin.json` | Claude Code e o diretório da Anthropic. `icon`, `documentationUrl`, `supportUrl`, `privacyPolicyUrl` e `termsOfServiceUrl` são os campos de listagem do diretório; o Claude Code os ignora ao carregar | <https://code.claude.com/docs/en/plugins/manifest-reference> |
| `.claude-plugin/marketplace.json` | O nosso marketplace. O plugin é a própria raiz (`"source": "./"`) | <https://code.claude.com/docs/en/plugins/publish>, <https://code.claude.com/docs/en/plugins/marketplace-reference> |
| `.codex-plugin/plugin.json` | ChatGPT e Codex. `interface` é a listagem; `extensions.com.openai.review` leva os casos de teste | <https://developers.openai.com/plugins/deploy/submission>, <https://developers.openai.com/plugins/guides/submit-claude-plugin> |
| `.mcp.json` | Claude Code e Codex. `type: "http"` + `url`; o Codex aceita esse formato (teste `codex-rs/codex-mcp/src/plugin_config_tests.rs`) | <https://code.claude.com/docs/en/plugins/manifest-reference>, <https://github.com/openai/codex> |
| `plugin.json` | Antigravity. O esquema só aceita `name` e `description`, por isso não leva `version` | <https://antigravity.google/docs/plugins.md> |
| `mcp_config.json` | Antigravity. Só `serverUrl`, sem credencial no arquivo | <https://antigravity.google/docs/mcp> |
| `skills/*/SKILL.md` | Os três. Cabeçalho YAML com `name` e `description`; linguagem neutra de provedor, como a OpenAI pede | <https://code.claude.com/docs/en/skills>, <https://antigravity.google/docs/skills>, <https://developers.openai.com/plugins/guides/submit-claude-plugin> |

Regras: sem hooks, commands, agents nem `userConfig`, o menor denominador comum entre os três.
A `version` é a mesma em `.claude-plugin/plugin.json`, `.codex-plugin/plugin.json` e no
`server.json` do MCP Registry. Ela é igual à do workspace `connect/` e só sobe quando muda
manifesto ou skill. Os testes em `connect/plugins/test/plugins.test.mjs` conferem isso.
