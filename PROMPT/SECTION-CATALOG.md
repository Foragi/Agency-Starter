# SECTION-CATALOG.md

## Agency Starter — Catálogo de Seções e Composição de Páginas

Este documento orienta Claude Code e Codex sobre **quais seções usar, em que ordem e por qual motivo**.

Uma página não deve ser montada pela estética disponível. Ela deve ser montada pela jornada do usuário.

---

# 1. Modelo mental

```text
Objetivo do negócio
        ↓
Intenção do usuário
        ↓
Mensagem
        ↓
Seções necessárias
        ↓
Componentes
        ↓
Animação
        ↓
QA
```

---

# 2. Funções das seções

| Seção | Função |
|---|---|
| Hero | Atenção + proposta |
| Proof | Confiança inicial |
| Features | Entendimento |
| Benefits | Desejo |
| Services | Oferta |
| Process | Redução de incerteza |
| Testimonials | Prova social |
| Case Studies | Evidência |
| Stats | Evidência quantitativa |
| Pricing | Decisão |
| FAQ | Remoção de objeções |
| CTA | Conversão |
| Footer | Navegação/fechamento |

---

# 3. Estruturas recomendadas

## Landing page de serviço

```text
Header
Hero
Proof / Trust
Problem
Benefits
Services
Process
Testimonials
FAQ
CTA
Footer
```

---

## Landing page premium

```text
Header
Editorial Hero
Brand/Proof
Signature Offering
Benefits
Visual Story
Testimonials
Process
CTA
Footer
```

---

## SaaS / produto

```text
Header
Hero
Product Proof
Features
Workflow
Integrations
Testimonials
Pricing
FAQ
CTA
Footer
```

---

## Clínica / profissional

```text
Header
Hero
Trust
Services
Benefits
Specialist / Team
Process
Testimonials
FAQ
Booking CTA
Footer
```

---

## Agência

```text
Header
Hero
Selected Work
Services
Process
Results
Testimonials
About
CTA
Footer
```

---

# 4. Regra de ordem

A ordem deve responder progressivamente:

```text
O que é?
↓
Por que importa?
↓
Por que acreditar?
↓
Como funciona?
↓
O que posso fazer?
↓
Por que agora?
↓
Como começo?
```

Nem toda página precisa de todas as respostas.

---

# 5. Regra de redução

Antes de adicionar uma seção, pergunte:

1. Qual pergunta do usuário ela responde?
2. Qual objeção ela remove?
3. Qual etapa da decisão ela melhora?

Se nenhuma:

**não adicionar.**

---

# 6. Regras de repetição

Evitar sequências como:

```text
FeatureSection
FeatureSection
FeatureSection
```

ou:

```text
CardGrid
CardGrid
CardGrid
CardGrid
```

Alternar ritmo visual:

```text
Texto
↓
Grid
↓
Imagem
↓
Prova
↓
CTA
```

---

# 7. Densidade

Uma seção deve ter uma função dominante.

Se uma seção possui:
- headline
- 12 cards
- vídeo
- depoimentos
- FAQ
- formulário

provavelmente ela deveria ser dividida.

---

# 8. Conteúdo real

Agentes não devem inventar:
- métricas
- clientes
- depoimentos
- certificações
- resultados
- logos
- preços

Quando o conteúdo não existir, usar placeholders explícitos e documentados.

Nunca mascarar conteúdo fictício como real.

---

# 9. Animação por intenção

Hero:
- reveal
- stagger
- entrada de mídia

Cards:
- hover leve
- reveal

Sections:
- scroll reveal moderado

Case studies:
- media transition
- parallax somente quando fizer sentido

CTA:
- entrada simples

Evitar animar tudo.

---

# 10. Mobile

A composição deve ser reavaliada no mobile.

Não basta reduzir:

```text
Desktop → menor
```

Pode ser necessário:

```text
Desktop:
2 colunas

Mobile:
1 coluna
```

ou:

```text
Desktop:
menu completo

Mobile:
menu compacto
```

---

# 11. Critério de página pronta

```text
[ ] Existe objetivo claro
[ ] CTA principal é evidente
[ ] Cada seção tem função
[ ] Ordem faz sentido
[ ] Não existem seções decorativas sem propósito
[ ] Componentes vêm do catálogo
[ ] Conteúdo é real ou explicitamente placeholder
[ ] Mobile foi pensado
[ ] Animações não competem com conteúdo
[ ] SEO está configurado
[ ] Acessibilidade validada
[ ] Performance validada
```

