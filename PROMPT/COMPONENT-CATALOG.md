# COMPONENT-CATALOG.md

## Agency Starter — Catálogo Operacional de Componentes

Este documento é a referência de decisão para Claude Code, Codex e desenvolvedores.
Antes de criar um componente novo, procure neste catálogo.

---

# 1. Regra de decisão

Use esta ordem:

1. **Componente existente**
2. **Composição de componentes existentes**
3. **Variante de componente existente**
4. **Novo componente reutilizável**
5. **Implementação específica de página** — somente quando não houver valor de reutilização

Nunca crie um componente novo apenas porque a aparência é diferente.

Pergunta principal:

> "Estou criando uma nova categoria de comportamento ou apenas uma nova apresentação de algo que já existe?"

Se for apenas apresentação → variante/composição.
Se for novo comportamento/padrão → novo componente.

---

# 2. Taxonomia

```text
Primitive
  ↓
UI Component
  ↓
Pattern
  ↓
Section
  ↓
Page
```

### Primitive
Elementos básicos e altamente reutilizáveis:
Button, Input, Badge, IconButton, Container, Heading, Text, Separator.

### UI Component
Componentes com uma responsabilidade visual/funcional:
Card, Accordion, Dialog, FormField, NavigationItem.

### Pattern
Composição recorrente:
ServiceCard, TestimonialCard, PricingCard, FeatureGrid, FAQList.

### Section
Bloco de página com intenção própria:
Hero, ServicesSection, TestimonialsSection, PricingSection, CTASection.

### Page
Composição final orientada ao objetivo do projeto.

---

# 3. Primitives

## Button

**Propósito:** ação principal ou secundária.

**Quando usar:**
- CTA
- envio de formulário
- navegação acionável
- ações de interface

**Variantes recomendadas:**
- primary
- secondary
- outline
- ghost
- destructive

**Não criar:**
- `HeroButton`
- `PricingButton`
- `CTAButton`

Se a aparência mudar, prefira variante.

---

## Link

**Propósito:** navegação.

**Use para:**
- páginas
- âncoras
- recursos externos

**Regra:** se navega, é link; se executa ação, é button.

---

## Heading

**Propósito:** hierarquia tipográfica.

**Use para:**
- títulos de seção
- títulos de página
- headings semânticos

Não use tamanho visual para decidir hierarquia semântica.

---

## Text

**Propósito:** texto secundário/body.

Evite criar componentes como:
- `HeroText`
- `CardDescription`
- `SectionParagraph`

Use composição e tokens.

---

## Container

**Propósito:** largura, alinhamento e gutters consistentes.

Todo conteúdo principal deve respeitar o container global do Design System.

Não criar containers com larguras arbitrárias por seção sem necessidade.

---

## Badge

**Propósito:** status, categoria ou pequeno destaque.

Exemplos:
- "Mais popular"
- "Novo"
- "Premium"
- categoria de serviço

---

## IconButton

**Propósito:** ação representada prioritariamente por ícone.

Obrigatório:
- label acessível
- área de toque adequada
- estados de foco/hover

---

# 4. UI Components

## Card

Base visual para conteúdo agrupado.

Use quando:
- conteúdo precisa de agrupamento visual
- há repetição de itens
- existe hierarquia interna clara

Não transformar todo bloco de conteúdo em card.

---

## Accordion

Use para:
- FAQ
- conteúdo expansível
- informações secundárias

Não use accordion para conteúdo essencial que deveria estar visível.

---

## Modal / Dialog

Use para:
- ação contextual
- confirmação
- conteúdo que não precisa ocupar a página inteira

Evite modal para substituir páginas completas.

---

## FormField

Responsabilidade:
- label
- input/control
- help text
- error
- estado

Formulários devem reutilizar esta estrutura.

---

## Input / Textarea / Select

Devem seguir os tokens globais de:
- typography
- spacing
- border
- radius
- focus
- error
- disabled

Nunca estilizar cada formulário de maneira isolada sem motivo.

---

# 5. Navigation

## Header

Use como composição principal de navegação.

Deve suportar:
- logo
- navigation
- CTA
- mobile trigger

Evitar lógica de negócio dentro do Header.

---

## Navbar

Responsável pela navegação desktop.

---

## MobileMenu

Responsável exclusivamente pela experiência mobile da navegação.

Deve:
- ser acessível por teclado
- possuir foco adequado
- permitir fechamento previsível
- respeitar reduced motion

---

# 6. Heroes

A escolha do Hero deve partir da intenção, não da estética.

## HeroCentered

**Use quando:**
- mensagem é simples
- headline é dominante
- produto/serviço precisa de clareza
- não há necessidade de imagem lateral

Estrutura:

```text
Eyebrow
Headline
Description
CTA
Optional proof
```

---

## HeroSplit

**Use quando:**
- texto + imagem precisam coexistir
- produto/serviço pode ser explicado visualmente
- há equilíbrio entre conteúdo e mídia

Estrutura:

```text
Text | Media
```

---

## HeroMedia

**Use quando:**
- imagem/vídeo é parte central da proposta
- o visual precisa dominar a primeira dobra

Não use apenas porque "fica bonito".

---

## HeroEditorial

**Use quando:**
- marca possui forte direção editorial
- tipografia e composição são protagonistas
- posicionamento premium/artístico é importante

---

## Hero

Componente base/generalista.

Quando uma variante existente resolve, prefira-a.

Não criar:
- `HeroClinic`
- `HeroAgency`
- `HeroSaaS`

Crie dados/configuração ou variante quando necessário.

---

# 7. Cards de conteúdo

## ServiceCard

Use para:
- serviços
- tratamentos
- soluções
- categorias de oferta

Estrutura típica:

```text
Media/Icon
Title
Description
Optional metadata
Optional CTA
```

---

## FeatureCard

Use para:
- benefícios
- funcionalidades
- diferenciais
- capacidades

Não usar ServiceCard para funcionalidades só porque o visual parece parecido.

---

## TestimonialCard

Use para:
- depoimentos
- prova social
- reviews

Dados mínimos:

```ts
{
  quote: string
  author: string
  role?: string
  avatar?: string
}
```

Nunca inventar depoimentos.

---

## PricingCard

Use para:
- planos
- pacotes
- ofertas comparáveis

Deve suportar:
- nome
- preço
- descrição
- features
- CTA
- destaque opcional

---

## TeamCard

Use para:
- equipe
- especialistas
- profissionais

---

## CaseStudyCard

Use para:
- projetos
- resultados
- estudos de caso
- portfólio

---

# 8. Sections

## FeaturesSection

Intenção:
**explicar capacidade ou benefício.**

Use quando o usuário precisa entender "o que isso oferece".

---

## ServicesSection

Intenção:
**apresentar oferta.**

Use quando existem serviços/produtos que precisam ser explorados.

---

## TestimonialsSection

Intenção:
**reduzir risco e aumentar confiança.**

Use depois de uma proposta/oferta quando prova social for relevante.

---

## PricingSection

Intenção:
**facilitar decisão comercial.**

Use quando preço ou planos fazem parte da estratégia.

Não inserir pricing apenas para preencher uma página.

---

## FAQSection

Intenção:
**remover objeções.**

As perguntas devem vir de dúvidas reais do público.

---

## CTASection

Intenção:
**conduzir para a próxima ação.**

Um CTA deve ter:
- intenção clara
- headline
- contexto curto
- ação principal

Evitar múltiplos CTAs competindo sem necessidade.

---

## LogoCloud

Intenção:
**prova de confiança por associação.**

Use somente com marcas/logos autorizados e reais.

---

## StatsSection

Intenção:
**comunicar evidência quantitativa.**

Nunca inventar números.

---

# 9. Forms

## ContactForm

Use para:
- contato
- orçamento
- solicitação de atendimento

Antes de implementar:
- definir destino dos dados
- validação
- mensagens de erro
- loading
- sucesso
- política de privacidade quando aplicável

---

## NewsletterForm

Use para:
- captura de email
- newsletter
- lead magnet

Não reutilizar como formulário genérico de contato.

---

# 10. Feedback

## Toast

Use para feedback temporário após ação.

Exemplos:
- salvo
- enviado
- copiado

Não use toast para mensagens críticas que precisam permanecer visíveis.

---

## Alert

Use para informação importante persistente.

---

## Loading

Use para estados de carregamento.

Sempre considerar:
- conteúdo inesperado
- layout shift
- acessibilidade

---

## EmptyState

Use quando uma área legítima não possui conteúdo.

Deve explicar:
1. o que está vazio
2. por que
3. o que fazer a seguir

---

# 11. Footer

## Footer

Composição final do site.

Pode incluir:
- logo
- navegação
- contato
- redes
- legal
- copyright

Não colocar lógica específica de negócio diretamente no componente.

---

# 12. Matriz de escolha rápida

| Necessidade | Componente |
|---|---|
| CTA | Button |
| Navegação | Link / Navbar |
| Título | Heading |
| Texto | Text |
| Agrupamento | Card |
| Serviço | ServiceCard |
| Benefício | FeatureCard |
| Depoimento | TestimonialCard |
| Plano | PricingCard |
| Profissional | TeamCard |
| Projeto | CaseStudyCard |
| Perguntas | Accordion / FAQSection |
| Formulário | FormField + controles / ContactForm |
| Feedback temporário | Toast |
| Aviso persistente | Alert |
| Conteúdo vazio | EmptyState |
| Oferta principal | Hero + CTA |
| Prova social | TestimonialsSection / LogoCloud / StatsSection |
| Conversão | CTASection |

---

# 13. Como criar uma variante

Crie variante quando:

- comportamento é o mesmo
- estrutura é majoritariamente a mesma
- diferença é visual ou de apresentação

Exemplo:

```tsx
<Button variant="primary" />
<Button variant="outline" />
```

Evitar:

```tsx
<BlueButton />
<GoldButton />
<HeroButton />
```

---

# 14. Como criar um novo componente

Antes de criar:

### Pergunta 1
Existe componente equivalente?

### Pergunta 2
Posso compor componentes existentes?

### Pergunta 3
Posso resolver com variante?

### Pergunta 4
Este padrão aparecerá em mais de uma página/projeto?

Se a resposta for sim, pode justificar novo componente.

---

# 15. Checklist obrigatório de novo componente

```text
[ ] Nome semântico
[ ] Responsabilidade única
[ ] API pequena
[ ] Props tipadas
[ ] Sem dados específicos do cliente
[ ] Responsivo
[ ] Acessível
[ ] Estados definidos
[ ] Tokens do Design System
[ ] Animação somente se necessária
[ ] Server Component por padrão
[ ] Client Component somente quando necessário
[ ] Testado em pelo menos 3 larguras
[ ] Registrado neste catálogo
[ ] Documentado
```

---

# 16. Regra contra componentes "Frankenstein"

Não criar componentes que tentam fazer tudo:

```tsx
<UniversalSection
  type="hero"
  layout="split"
  variant="premium"
  animation="gsap"
  showPricing
  showTestimonials
  ...
/>
```

Isso cria APIs frágeis.

Prefira:

```text
HeroSplit
+
FeatureGrid
+
TestimonialsSection
+
CTASection
```

Composição é preferível à configuração excessiva.

---

# 17. Dados vs. apresentação

Quando o conteúdo varia, prefira dados:

```ts
const services = [
  {
    title: "...",
    description: "...",
  },
]
```

em vez de duplicar JSX.

O componente controla apresentação.
O projeto controla conteúdo.

---

# 18. Regras para agentes

Antes de implementar uma página, o agente deve registrar mentalmente ou no plano:

```text
PAGE:
Objetivo:
Público:
CTA principal:

COMPONENTS:
- existente:
- composição:
- variante:
- novo:

ANIMATION:
- CSS:
- Motion:
- GSAP:

QA:
- mobile:
- tablet:
- desktop:
- a11y:
- performance:
```

Se houver componente novo, explicar por que os componentes existentes não atendem.

---

# 19. Critério de evolução

Depois de um projeto:

```text
Projeto
 ↓
Padrão novo identificado?
 ↓
Sim → abstrair
 ↓
Adicionar ao Starter
 ↓
Documentar
 ↓
Usar novamente
```

Não transformar toda solução específica em componente global.

---

# 20. Princípio final

> O Agency Starter não deve ter o maior número possível de componentes.
>
> Deve ter o menor conjunto de componentes capaz de resolver a maior quantidade de projetos sem sacrificar qualidade.

