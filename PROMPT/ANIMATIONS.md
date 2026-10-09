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
