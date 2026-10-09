# AGENTS-ADDENDUM.md

## Regras adicionais para operação de agentes

Este arquivo complementa `AGENTS.md`.

---

## 1. Não começar pela implementação

Antes de editar código:

1. ler `AGENTS.md`
2. ler `PROJECT.md`
3. ler `DESIGN.md`
4. consultar `COMPONENT-CATALOG.md`
5. consultar `SECTION-CATALOG.md`
6. consultar `ANIMATIONS.md`
7. inspecionar a implementação existente

Depois disso, formular o plano.

---

## 2. Pesquisa local antes de criação

Antes de criar:

```text
grep/search por componente
grep/search por padrão
verificar exports
verificar variantes
verificar uso existente
```

O objetivo é impedir duplicação.

---

## 3. Não alterar globalmente para resolver problema local

Se uma página precisa de uma exceção visual:

preferir, nesta ordem:

1. composição
2. prop
3. variante
4. extensão localizada

Só alterar tokens/globais quando o problema realmente pertence ao sistema.

---

## 4. Mudança global exige validação

Alterações em:
- tokens
- componentes compartilhados
- layout global
- typography
- navigation
- animation primitives

devem disparar revisão das páginas que dependem deles.

---

## 5. Código deve refletir intenção

Evitar:

```tsx
<div className="...">
```

sem estrutura semântica quando um elemento mais apropriado existe.

Preferir:

```tsx
<section>
<header>
<nav>
<main>
<article>
<footer>
```

quando semanticamente correto.

---

## 6. Conteúdo e código

Não misturar lógica de negócio com apresentação sem necessidade.

Preferir:

```text
data
 ↓
component
 ↓
section
 ↓
page
```

---

## 7. Animação

Nunca adicionar animação apenas para "deixar mais premium".

Pergunte:

> O que esta animação comunica ou melhora?

Se a resposta for nada, remover.

---

## 8. QA mínimo

Antes de considerar uma página concluída:

### Visual
- desktop
- tablet
- mobile
- estados de hover/focus
- overflow

### Funcional
- links
- botões
- formulários
- menu
- navegação

### Acessibilidade
- teclado
- foco
- contraste
- labels
- reduced motion

### Performance
- imagens
- client JS
- animações
- layout shift

### Build
- TypeScript
- lint
- build
- erros de runtime

---

## 9. Se algo falhar

Não mascarar.

Registrar:

```text
Problema:
Causa:
Impacto:
Correção aplicada:
O que ainda falta:
```

---

## 10. Evolução do Starter

Um projeto cliente pode revelar:

- novo componente
- nova variante
- nova seção
- nova animação
- novo padrão de formulário
- nova regra de QA

Mas o padrão só entra no Starter depois de demonstrar reutilização.

---

# Regra final

O agente não é apenas um gerador de código.

Ele é um operador do sistema Agency Starter.

Sua responsabilidade é:

```text
entender
→ reutilizar
→ compor
→ adaptar
→ criar
→ validar
→ documentar
→ melhorar o sistema
```
