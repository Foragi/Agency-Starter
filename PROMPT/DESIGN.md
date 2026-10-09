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
