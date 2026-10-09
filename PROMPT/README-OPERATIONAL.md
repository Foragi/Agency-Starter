# Agency Starter — Operational Edition

## Objetivo

Base operacional para agentes construírem sites premium de forma consistente, rápida e reutilizável.

## Stack alvo

```text
Next.js
React
TypeScript
Tailwind
shadcn/ui
Motion
GSAP
Supabase
Vercel
```

## Documentos

```text
AGENTS.md                  regras do agente
PROJECT.md                 contexto do projeto
DESIGN.md                  linguagem visual
COMPONENTS.md              biblioteca de componentes
ANIMATIONS.md              sistema de animações
PAGE-BUILD-PROTOCOL.md     processo de criação de páginas
```

## Fluxo

```text
ChatGPT
↓ estratégia + copy + arquitetura
Figma / direção visual
↓
Claude Code / Codex
↓
Agency Starter
↓
Next.js
↓
QA
↓
Vercel
```

## Regra principal

```text
entender
→ inspecionar
→ reutilizar
→ compor
→ adaptar
→ criar somente quando necessário
→ testar
→ melhorar o sistema
```

## Evolução

```text
Cliente
→ Projeto
→ Solução
→ Validação
→ Abstração
→ Agency Starter
→ Próximo Cliente
```

## Catálogos operacionais

A camada de decisão agora inclui:

- `COMPONENT-CATALOG.md` — catálogo de componentes, variantes, usos e critérios de criação.
- `SECTION-CATALOG.md` — catálogo de seções e estruturas de página por tipo de projeto.
- `AGENT-DECISION-MATRIX.md` — matriz operacional para decisões de componentes, animações, dados, SEO, acessibilidade e QA.
- `AGENTS-ADDENDUM.md` — regras adicionais de execução e evolução do Starter.

Fluxo recomendado:

```text
AGENTS.md
   ↓
PROJECT.md + DESIGN.md
   ↓
COMPONENT-CATALOG.md
   ↓
SECTION-CATALOG.md
   ↓
AGENT-DECISION-MATRIX.md
   ↓
PAGE-BUILD-PROTOCOL.md
   ↓
implementação
   ↓
QA
   ↓
documentação/evolução
```
