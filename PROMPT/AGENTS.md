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
