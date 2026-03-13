# bodegami-plugin

Plugin centralizado para o Claude Code com skills, agents, MCPs e hooks.

## Skills disponíveis

| Skill | Invocação | Descrição |
|---|---|---|
| `algorithmic-art` | `/algorithmic-art` | Cria arte generativa interativa com p5.js. Gera filosofia algorítmica + artefato HTML self-contained com controles de seed e parâmetros. |

## Estrutura

```
bodegami-plugin/
├── .claude-plugin/plugin.json   # Manifesto do plugin
├── skills/                      # Skills invocáveis
├── agents/                      # Subagents especializados
├── hooks/hooks.json             # Hooks automáticos
├── scripts/                     # Scripts auxiliares dos hooks
└── .mcp.json                    # MCP servers
```

## Instalação

### Opção 1 — Manual (via comandos no Claude Code)

Execute os comandos abaixo dentro do Claude Code:

```bash
# 1. Adiciona o repositório como marketplace
/plugin marketplace add Bodegami/bodegami-plugin

# 2. Lista os plugins disponíveis
/plugin list

# 3. Instala o plugin
/plugin install bodegami-plugin@Bodegami/bodegami-plugin
```

### Opção 2 — Automático (via projeto Git)

Adicione o arquivo `.claude/settings.json` no repositório do projeto que vai usar o plugin. Qualquer pessoa que clonar o projeto já receberá o plugin automaticamente, sem precisar rodar nenhum comando.

```json
{
  "extraKnownMarketplaces": {
    "bodegami-tools": {
      "source": { "source": "github", "repo": "Bodegami/bodegami-plugin" }
    }
  },
  "enabledPlugins": {
    "bodegami-plugin@bodegami-tools": true
  }
}
```

## Teste local

```bash
claude --plugin-dir ./bodegami-plugin
```
