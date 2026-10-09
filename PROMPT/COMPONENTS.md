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
