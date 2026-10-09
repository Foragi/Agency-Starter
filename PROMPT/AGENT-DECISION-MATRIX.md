# AGENT-DECISION-MATRIX.md

## Agency Starter — Matriz de Decisão para Claude Code e Codex

Este arquivo transforma princípios do Starter em decisões operacionais.

---

# 1. Antes de codar

Sempre determine:

```text
OBJECTIVE
AUDIENCE
PRIMARY CTA
PAGE TYPE
SECTIONS
COMPONENTS
ANIMATIONS
DATA
INTEGRATIONS
QA
```

Se qualquer item crítico estiver indefinido, não invente.

Use o contexto existente ou marque como pendência.

---

# 2. Decisão de componente

```text
Preciso de UI?
  ↓
Existe componente?
  ├─ Sim → usar
  └─ Não
      ↓
Existe composição?
      ├─ Sim → compor
      └─ Não
          ↓
É só visual?
          ├─ Sim → variante
          └─ Não
              ↓
É reutilizável?
              ├─ Sim → criar componente
              └─ Não → implementação local
```

---

# 3. Decisão de animação

```text
Precisa animar?
  ├─ Não → não animar
  └─ Sim
      ↓
É microinteração?
      ├─ Sim → CSS
      └─ Não
          ↓
É reveal/hover/layout/stagger?
          ├─ Sim → Motion
          └─ Não
              ↓
Precisa timeline/scroll/pin/scrub?
              ├─ Sim → GSAP
              └─ Não → reconsiderar necessidade
```

---

# 4. Decisão Server vs Client

Padrão:

```text
Server Component
```

Adicionar `"use client"` apenas quando houver necessidade real, como:
- estado
- interação
- browser APIs
- hooks de cliente
- animação que exige runtime no cliente

Não transformar uma página inteira em Client Component por conveniência.

---

# 5. Decisão de dados

Se o conteúdo é:
- estático → pode permanecer no componente/página quando simples
- repetitivo → array/objeto
- editável pelo usuário → backend
- sensível → nunca hardcode
- segredo → environment variable

Nunca colocar secrets no client.

---

# 6. Decisão de Supabase

Use Supabase quando houver necessidade real de:
- persistência
- autenticação
- dados relacionais
- leads
- dashboard
- conteúdo dinâmico

Não adicionar backend apenas porque o Starter possui Supabase.

---

# 7. Decisão de SEO

Toda página pública deve revisar:

```text
title
description
canonical quando necessário
Open Graph
headings
semantic HTML
sitemap
robots
structured data quando aplicável
```

Não inserir keywords artificialmente.

---

# 8. Decisão de acessibilidade

Sempre verificar:

```text
keyboard
focus
contrast
labels
alt
heading hierarchy
semantic HTML
reduced motion
touch target
error messaging
```

Acessibilidade não é etapa opcional.

---

# 9. Decisão de performance

Prioridades:

1. evitar JS desnecessário
2. otimizar imagens
3. evitar animações pesadas
4. reduzir client components
5. evitar layout shift
6. lazy-load quando apropriado
7. preservar streaming/server rendering quando útil

Não otimizar sacrificando clareza sem evidência.

---

# 10. Decisão de novo componente

Novo componente só deve entrar no Starter se:

```text
[ ] representa padrão real
[ ] não é específico de cliente
[ ] tem API clara
[ ] pode ser usado novamente
[ ] não duplica componente existente
[ ] foi testado
[ ] foi documentado
```

---

# 11. Formato recomendado de plano do agente

Antes de implementar uma página complexa:

```md
## Page Plan

### Objective
...

### Primary CTA
...

### Section Map
1. ...
2. ...
3. ...

### Components
- Existing:
- Composed:
- Variants:
- New:

### Animation
- CSS:
- Motion:
- GSAP:

### Data
...

### Integrations
...

### QA
- Responsive:
- Accessibility:
- Performance:
- SEO:
```

---

# 12. Formato recomendado de conclusão

Ao terminar uma tarefa:

```md
## Implementation Summary

### Changed
- ...

### Components reused
- ...

### Components created
- ...

### Animation
- ...

### QA
- ...

### Known limitations
- ...

### Recommended next step
- ...
```

O agente deve ser transparente sobre limitações.

---

# 13. Regra de ouro

> Não codifique a primeira solução possível.
>
> Primeiro encontre a melhor solução reutilizável dentro do sistema.
