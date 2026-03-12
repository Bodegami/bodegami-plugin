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

```bash
/plugin marketplace add Bodegami/bodegami-plugin
/plugin install bodegami-plugin@Bodegami/bodegami-plugin
```

Ou via `.claude/settings.json` no projeto:

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
