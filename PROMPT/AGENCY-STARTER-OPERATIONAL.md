# AGENCY STARTER — OPERATIONAL SYSTEM


---

# AGENTS.md

# AGENTS.md — Agency Starter

## 0. Missão

O Agency Starter é uma base reutilizável para landing pages, sites premium e sistemas. Este arquivo é o contrato operacional para Claude Code, Codex e outros agentes.

Princípio: **REUTILIZAR → COMPOR → ADAPTAR → CRIAR → VALIDAR → EVOLUIR**

O agente não deve tratar cada projeto como se fosse criado do zero.

## 1. Leitura obrigatória

Antes de alterar código, leia:
1. `AGENTS.md`
2. `PROJECT.md`
3. `DESIGN.md`
4. `COMPONENTS.md`
5. `ANIMATIONS.md`
6. documentação específica da área, quando existir.

Depois inspecione o código real. A documentação não substitui a inspeção.

## 2. Hierarquia de decisão

Sempre decidir nesta ordem:
1. componente existente;
2. composição de componentes existentes;
3. variante;
4. novo componente reutilizável;
5. implementação específica da página.

Nunca criar solução nova antes de verificar as opções anteriores.

## 3. Antes de codar

**ENTENDER:** objetivo, público, CTA, páginas, seções, interações, requisitos visuais e técnicos.

**INSPECIONAR:** componentes semelhantes, variantes, sections, animações, tokens e padrões responsivos.

**PLANEJAR:** composição, componentes a reutilizar/adaptar/criar, animação e QA.

Só então implementar.

## 4. Páginas

`app/**/page.tsx` deve ser principalmente composição:

```tsx
export default function Page() {
  return (
    <>
      <Header />
      <main>
        <Hero />
        <ServicesSection />
        <TestimonialsSection />
        <CTA />
      </main>
      <Footer />
    </>
  )
}
```

Evitar páginas monolíticas, conteúdo repetido, animações complexas inline e lógica visual extensa.

## 5. Componentes

Criar componente quando ele possui comportamento/identidade própria, será reutilizado, reduz complexidade real ou representa um padrão.

Não criar componente apenas para mover poucas linhas.

Se a diferença for apenas visual, preferir variantes. Se a API começar a acumular muitos flags, reconsiderar a abstração.

## 6. Design System

`DESIGN.md` é a autoridade visual. Não inventar cores, espaçamentos, radius, sombras ou tipografia quando houver tokens equivalentes.

## 7. Responsividade

Todo componente deve funcionar em mobile, tablet, desktop e telas grandes. Pensar mobile-first. Verificar overflow, textos longos, imagens, grids, navegação, touch targets e viewport.

## 8. Motion

Motion é o padrão para animações de UI/React: fade, slide, scale, stagger, hover, tap, layout e reveals simples.

## 9. GSAP

GSAP é reservado para timelines complexas, scroll choreography, pin, scrub, parallax avançado e sequências coordenadas.

Regra: **UI simples → CSS/Motion; timeline complexa → GSAP.**

Não controlar o mesmo elemento simultaneamente por Motion e GSAP sem necessidade explícita.

## 10. Performance

Preferir `transform` e `opacity`. Evitar animações frequentes de `width`, `height`, `top`, `left`, `margin` e `padding`.

Respeitar `prefers-reduced-motion`.

## 11. Next.js

Server Components são o padrão. Usar `"use client"` somente para estado, eventos, browser APIs, Motion, GSAP ou interações client-side.

## 12. TypeScript

Props devem ser tipadas. Evitar `any` sem justificativa.

## 13. Acessibilidade

Obrigatório considerar HTML semântico, teclado, foco, contraste, labels, alt, estados de erro e reduced motion. Preferir `<button>` a `<div onClick>`.

## 14. Imagens

Usar otimização apropriada do Next.js e considerar dimensões, aspect ratio, prioridade, lazy loading, qualidade, alt e formato.

## 15. Forms

Todo formulário deve possuir label, validação, loading, sucesso, erro, prevenção de submissão duplicada e feedback acessível.

## 16. Supabase

Nunca expor service role keys, secrets ou tokens privados. Considerar RLS, autenticação, autorização, server-side operations e environment variables.

## 17. SEO

Páginas públicas devem considerar title, description, canonical, Open Graph, headings, sitemap, robots e structured data quando aplicável.

## 18. QA

Não esperar o fim. Fluxo: **implementar → verificar → corrigir → continuar**.

Antes de concluir:
- visual;
- mobile/tablet/desktop;
- teclado/foco/labels/alt/contraste/reduced motion;
- links/buttons/forms/navigation;
- performance;
- lint;
- typecheck, se existir;
- testes, se existirem;
- build.

## 19. Não quebrar o Starter

Antes de alterar componente global:
1. descubra onde é usado;
2. entenda props;
3. entenda variantes;
4. avalie impacto;
5. prefira variante quando a mudança é específica.

## 20. Evolução

Uma melhoria entra no Starter quando foi validada, é reutilizável, reduz trabalho futuro e não adiciona complexidade desnecessária.

**Projeto → solução → validação → abstração → Starter**

## 21. Definição de pronto

Implementação, arquitetura, Design System, responsividade, acessibilidade, animações, SEO, performance, lint e build devem estar em ordem, sem placeholders indevidos, código morto ou dependências desnecessárias.

## 22. Princípio final

O Agency Starter é um sistema de decisão:

**O que já existe? → O que posso reutilizar? → O que posso compor? → O que posso adaptar? → O que realmente precisa ser criado? → Como isso melhora o Starter?**

---

# COMPONENTS.md

# COMPONENTS.md — Component System

## 1. Taxonomia

```text
Primitives → UI Components → Patterns → Sections → Pages
```

**Primitives:** Button, Container, Heading, Text, Icon, Link, Input.

**UI Components:** Card, Badge, Avatar, Accordion, Dialog, Tabs, FormField.

**Patterns:** FeatureGrid, LogoCloud, TestimonialGroup, PricingGrid, FAQList, ContactForm.

**Sections:** Hero, Features, Testimonials, Pricing, FAQ, CTA, Footer, LogoCloud, Stats.

## 2. Matriz de decisão

| Necessidade | Primeira opção |
|---|---|
| botão | Button |
| título | Heading |
| conteúdo limitado | Container |
| item repetido | Card existente |
| seção existente | Section existente |
| pequena diferença | Variant |
| composição recorrente | Pattern |
| bloco de página | Section |
| caso único | componente local |

## 3. Inventário alvo

Procurar antes de criar:

```text
Navigation: Header, Navbar, MobileMenu
Hero: Hero, HeroSplit, HeroCentered, HeroMedia, HeroEditorial
Cards: ServiceCard, FeatureCard, TestimonialCard, PricingCard, TeamCard, CaseStudyCard
Sections: FeaturesSection, ServicesSection, TestimonialsSection, PricingSection, FAQSection, CTASection, LogoCloud, StatsSection
Forms: Input, Textarea, Select, FormField, ContactForm, NewsletterForm
Feedback: Toast, Alert, Loading, EmptyState
Footer: Footer, FooterColumns
```

Esses nomes são uma taxonomia; o agente deve confirmar quais existem no código.

## 4. Escolha de Hero

Considerar densidade de conteúdo, mídia, objetivo de conversão, CTA e linguagem visual. Escolher o Hero existente mais próximo. Não criar novo Hero apenas por diferença de copy.

## 5. Cards

Um Card deve representar uma entidade: Service, Feature, Testimonial, Pricing, Team ou Case Study. Evitar `GenericCard` gigante com dezenas de props condicionais.

## 6. API

Boa:

```tsx
<Card title="..." description="..." href="..." />
```

Suspeita:

```tsx
<Card isHero isDark isLarge hasImage hasIcon compact editorial premium />
```

Muitos flags indicam abstração ruim.

## 7. Checklist de novo componente

```text
[ ] procurei equivalente
[ ] procurei variante
[ ] procurei pattern
[ ] defini responsabilidade
[ ] defini API
[ ] defini estados
[ ] defini responsividade
[ ] defini acessibilidade
[ ] defini animação, se necessária
[ ] confirmei valor futuro
```

**Componentes representam padrões; páginas representam necessidades.**

---

# ANIMATIONS.md

# ANIMATIONS.md — Motion System

## 1. Hierarquia

```text
CSS → Motion → GSAP
```

Escolha a menor ferramenta capaz de produzir o resultado.

## 2. CSS

Usar para hover simples, transitions, transform, opacity, focus e microinterações.

## 3. Motion

Usar para reveal, fade, slide, scale, stagger, hover, tap, layout e componentes interativos.

## 4. GSAP

Usar para timeline, ScrollTrigger, scrub, pin, parallax avançado e coreografia complexa.

## 5. Padrões

Fade = opacity.

Reveal = opacity + translate.

Stagger = entrada sequencial.

Scale = discreto.

Parallax = somente quando melhora narrativa.

## 6. Regras

Evitar animações contínuas sem função, bounce excessivo, efeitos em tudo, delays longos e movimento que prejudique leitura.

Referências iniciais:
- micro interaction: 120–200ms
- UI transition: 200–400ms
- reveal: 400–800ms
- hero choreography: 600–1200ms

Ajustar conforme design.

## 7. Scroll

Deve melhorar narrativa, não bloquear interação, não causar layout shift, funcionar em touch e respeitar reduced motion.

## 8. Reduced motion

Complex animation → fade/estado simples.
Parallax → desabilitar.
Scrub → desabilitar.
Movimento grande → reduzir.

Conteúdo nunca depende da animação para existir.

## 9. GSAP lifecycle

Inicializar no client, limpar contextos/listeners, evitar timelines duplicadas, considerar Strict Mode e preferir refs/escopo em vez de seletores globais.

## 10. Checklist

```text
[ ] propósito
[ ] ferramenta correta
[ ] sem conflito
[ ] performance
[ ] mobile
[ ] reduced motion
[ ] cleanup
[ ] conteúdo não depende da animação
```

---

# DESIGN.md

# DESIGN.md — Design System

## 1. Princípio

O sistema deve produzir interfaces consistentes, premium, legíveis, responsivas e acessíveis.

## 2. Tokens

Centralizar:

```text
color
typography
spacing
radius
shadow
container
breakpoint
motion
z-index
```

## 3. Cores

Organizar semanticamente:

```text
background
foreground
muted
primary
secondary
accent
border
success
warning
error
```

Não espalhar hexadecimais arbitrários.

## 4. Tipografia

Escala semântica:

```text
display
h1
h2
h3
h4
body-lg
body
body-sm
caption
label
```

## 5. Spacing

Usar escala consistente. Evitar valores isolados quando um token resolve.

## 6. Containers

Respeitar largura máxima, gutters e padding responsivo.

## 7. Radius

Usar escala controlada. Não misturar valores arbitrários sem intenção.

## 8. Shadows

Discretas e funcionais. Não aplicar sombra em todos os cards.

## 9. Botões

Estados:

```text
default
hover
focus
active
disabled
loading
```

Variantes seguem a mesma API.

## 10. Cards

Hierarquia possível:

```text
media
eyebrow
title
description
metadata
action
```

Nem todo card precisa de todos os campos.

## 11. Grid

Preferir grids previsíveis e responsivos.

## 12. Hierarquia visual

```text
Primary
Secondary
Supporting
```

Nem tudo deve competir pela atenção.

## 13. Acessibilidade visual

Garantir contraste, legibilidade, foco visível, touch target adequado e não depender apenas de cor.

**Design System não é prisão. É uma linguagem.**

---

# PAGE-BUILD-PROTOCOL.md

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
