# Claude Project Template

Template de projeto com GitHub Actions para usar Claude Code agents em PRs e Issues.

## Quick Start

### 1. Criar Novo Projeto

Clique em **"Use this template"** > **"Create a new repository"**

### 2. Configurar Secret

No seu novo repositório:
1. Vá em **Settings > Secrets and variables > Actions**
2. Clique **New repository secret**
3. Nome: `ANTHROPIC_API_KEY`
4. Valor: sua API key da Anthropic

### 3. Instalar Claude App (Opcional)

Para usar `@claude` em comentários:
1. Acesse https://github.com/apps/claude
2. Clique **Install**
3. Selecione seu repositório

## Comandos Disponíveis

Comente em qualquer **Pull Request** para acionar os agents:

| Comando | Descrição |
|---------|-----------|
| `/review` | Code review completo |
| `/security` | Auditoria de segurança (OWASP Top 10) |
| `/test` | Sugestões de testes |
| `/docs` | Melhorias de documentação |
| `/refactor` | Sugestões de refatoração |
| `/debug` | Análise de bugs potenciais |
| `/explain` | Explicação do código |

### Chamar Agents Específicos

```
/agent <nome-do-agent> <prompt opcional>
```

Exemplos:
```
/agent security-auditor verificar SQL injection
/agent data-scientist analisar este dataset
/agent ml-engineer sugerir melhorias no modelo
```

### Agents Disponíveis

**Desenvolvimento:**
- `code-reviewer`, `frontend-developer`, `backend-developer`
- `react-specialist`, `nextjs-developer`, `python-pro`
- `typescript-pro`, `rust-engineer`, `golang-pro`

**DevOps:**
- `devops-engineer`, `kubernetes-specialist`, `terraform-engineer`

**Segurança:**
- `security-auditor`, `penetration-tester`

**Dados/ML:**
- `data-scientist`, `data-engineer`, `ml-engineer`

**Qualidade:**
- `debugger`, `refactoring-specialist`, `test-automator`

## Auto-Review em PRs

Para ativar review automático em PRs:
1. Adicione a label `claude-review` ao PR
2. O Claude fará review automaticamente em cada push

## Execução Manual

1. Vá em **Actions** > **Claude Code Agents**
2. Clique **Run workflow**
3. Escolha o agent e digite o prompt
4. Clique **Run**

## Estrutura do Template

```
.
├── .github/
│   └── workflows/
│       ├── claude-agents.yml       # Workflow principal
│       └── claude-quick-commands.yml # Comandos rápidos
├── README.md
└── CLAUDE.md                       # Instruções para o Claude
```

## Personalização

### Adicionar Novos Comandos

Edite `.github/workflows/claude-quick-commands.yml`:

```yaml
"/meu-comando")
  PROMPT="Act as meu-agent. Faça algo específico."
  TITLE="Meu Título"
  ;;
```

### Configurar CLAUDE.md

Crie um arquivo `CLAUDE.md` na raiz do projeto com instruções específicas para o Claude sobre seu projeto.

## Segurança

Os workflows incluem:
- ✅ Sanitização de input contra injeção de comandos
- ✅ Validação de nomes de agents
- ✅ Proteção de API key nos logs (`set +x`)
- ✅ Tratamento de erros robusto

## Requisitos

- Conta Anthropic com API key
- GitHub Actions habilitado no repositório

## Links Úteis

- [Claude Code Docs](https://docs.anthropic.com/claude-code)
- [Anthropic Console](https://console.anthropic.com)
- [GitHub Actions](https://docs.github.com/en/actions)

---

*Template criado com Claude Code*
