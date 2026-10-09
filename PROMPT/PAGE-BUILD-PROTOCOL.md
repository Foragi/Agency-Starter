# PAGE BUILD PROTOCOL

## FASE 1 — CONTEXTO

Ler:

```text
AGENTS.md
PROJECT.md
DESIGN.md
COMPONENTS.md
ANIMATIONS.md
```

Extrair objetivo, público, CTA, tom, páginas, conteúdo e direção visual.

## FASE 2 — AUDITORIA

Inspecionar:

```text
app/
components/
sections/
animations/
lib/
public/
```

Pesquisar por Hero, Header, Footer, Card, Section, CTA, Form, Testimonial, Pricing e FAQ.

## FASE 3 — MAPA

Montar a composição:

```text
Header
Hero
Section
Section
Section
CTA
Footer
```

Cada seção deve ter objetivo.

Exemplo:

```text
Hero → atenção
Proof → confiança
Features → entendimento
Benefits → desejo
Testimonials → prova social
CTA → conversão
```

## FASE 4 — COMPONENTES

```text
Existe? → usar
Parecido? → adaptar
Pequena mudança? → variant
Padrão novo reutilizável? → criar
Caso único? → local
```

## FASE 5 — COMPOSIÇÃO

Construir de fora para dentro:

```text
Page → Section → Container → Pattern → Component → Primitive
```

## FASE 6 — CONTEÚDO

Garantir headline clara, subheadline útil, CTA explícito, conteúdo escaneável e hierarquia correta. Não usar lorem ipsum em implementação final.

## FASE 7 — DESIGN

Aplicar tokens, typography, spacing, grid, radius, colors e shadows. Evitar valores arbitrários.

## FASE 8 — RESPONSIVIDADE

Implementar mobile → tablet → desktop. Verificar hero, grids, navigation, cards e forms.

## FASE 9 — ANIMAÇÃO

```text
Precisa?
  não → sem animação
  sim
  ↓
CSS resolve?
  sim → CSS
  não
  ↓
Motion resolve?
  sim → Motion
  não → GSAP
```

## FASE 10 — ACESSIBILIDADE

Semantic HTML, headings, buttons, links, labels, alt, focus, keyboard, contrast e reduced motion.

## FASE 11 — SEO

Title, description, canonical, OG, headings, links e structured data quando aplicável.

## FASE 12 — QA

Visual, responsive, functional, accessibility, performance e technical QA.

## FASE 13 — BUILD

Executar apenas scripts existentes:

```bash
npm run lint
npm run typecheck
npm run test
npm run build
```

## FASE 14 — REVISÃO

Perguntar:

```text
Usei algo que já existia?
Criei duplicação?
A página segue o Design System?
A animação é necessária?
O mobile funciona?
O teclado funciona?
O build passa?
```

## FASE 15 — EVOLUÇÃO

Se surgir padrão reutilizável comprovado:

```text
extrair → documentar → adicionar ao Starter
```

O resultado deve parecer feito especificamente para o cliente, mas ser tecnicamente construído sobre um sistema consistente e reutilizável.
