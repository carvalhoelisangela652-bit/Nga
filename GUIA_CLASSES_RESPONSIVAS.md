# 🎨 TITAN v5 — Guia Prático de Classes Responsivas

## Como Usar as Classes Helper

Todas as classes estão em `css/utilities-responsive.css` e já estão carregadas.

---

## 📱 Display & Visibilidade

### Mostrar/Ocultar por Breakpoint

```html
<!-- Visível apenas em mobile -->
<div class="show-mobile-only">
  Menu Hambúrguer
</div>

<!-- Visível apenas em tablet -->
<div class="show-tablet-only">
  Sidebar Tablet
</div>

<!-- Visível apenas em desktop -->
<div class="show-desktop-only">
  Desktop Feature
</div>

<!-- Ocultar em breakpoint específico -->
<div class="hide-mobile">
  Não aparece em mobile, mas sim em tablet+
</div>

<div class="hide-tablet">
  Oculto em tablet, visível em mobile e desktop
</div>

<div class="hide-desktop">
  Oculto em desktop
</div>
```

---

## 🔲 Grid & Flexbox Responsivos

### Grid com Coluna Responsiva

```html
<!-- Desktop: 3 colunas, Tablet: 2, Mobile: 1 -->
<div class="grid-cols-1-mobile grid-cols-2-tablet grid-cols-3-desktop gap-mobile">
  <div class="card">Item 1</div>
  <div class="card">Item 2</div>
  <div class="card">Item 3</div>
</div>

<!-- Alternativa: Flex com direção responsiva -->
<div class="flex-col-mobile" style="flex-direction: row;"> <!-- Desktop fica row -->
  <div>Column 1</div>
  <div>Column 2</div>
</div>
```

---

## 📏 Espaçamento Responsivo

### Padding Adaptativo

```html
<!-- Padding aumenta conforme tela cresce -->
<div class="p-mobile">
  <!-- 10px em mobile, cresce progressivamente -->
</div>

<div class="p-tablet">
  <!-- 12px em tablet, aumenta em desktop -->
</div>

<div class="p-desktop">
  <!-- 16px em desktop -->
</div>
```

### Margin Responsiva

```html
<div class="m-mobile">
  <!-- Margem adaptativa -->
</div>

<div class="m-tablet m-desktop">
  <!-- Combinar múltiplas classes -->
</div>
```

### Gap em Containers

```html
<!-- Gap adaptativo para flex/grid -->
<div class="flex gap-mobile">
  <!-- 8px gap em mobile, aumenta em tablet+ -->
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<div class="gap-tablet">
  <!-- 12px gap -->
</div>
```

---

## 📝 Tipografia Responsiva

### Tamanho de Fonte

```html
<!-- Aumenta conforme tela cresce -->
<h1 class="text-xl-mobile">
  <!-- 14px mobile, 15px tablet, 17px desktop -->
  Responsive Heading
</h1>

<p class="text-md-mobile">
  <!-- 12px mobile, 13px tablet, 14px desktop -->
</p>

<small class="text-sm-mobile">
  <!-- 11px mobile, 12px tablet, 13px desktop -->
</small>

<!-- Combinações -->
<span class="text-lg-mobile text-xl-desktop">
  <!-- Diferentes tamanhos em diferentes breakpoints -->
</span>
```

---

## 📐 Largura Responsiva

### Width Fixas

```html
<!-- Full width em mobile -->
<div class="w-full-mobile">
  100% em mobile, cresce em tablet+
</div>

<!-- 90% em mobile -->
<div class="w-90-mobile">
  90vw em mobile
</div>

<!-- 80% em mobile -->
<div class="w-80-mobile">
  80vw em mobile
</div>
```

### Max-Width (Container)

```html
<!-- Limitador de largura responsivo -->
<div class="max-w-sm">
  <!-- max-width: 360px -->
</div>

<div class="max-w-md">
  <!-- max-width: 480px -->
</div>

<div class="max-w-lg">
  <!-- max-width: 640px -->
</div>

<div class="max-w-xl">
  <!-- max-width: 1024px -->
</div>
```

---

## ✋ Otimização Touch

### Alvo Clicável Touch-Friendly

```html
<!-- Garantido 44x44px mínimo -->
<button class="touch-target">
  Clique Aqui
</button>

<!-- Com ícone -->
<button class="touch-target">
  <i class="fas fa-plus"></i>
</button>
```

### Padding Para Touch

```html
<!-- Padding otimizado para toque -->
<div class="touch-padding">
  <!-- 12px padding em mobile, 8px em desktop (hover) -->
</div>

<div class="touch-padding-compact">
  <!-- 8px padding -->
</div>
```

### Remover Callout (Long Press)

```html
<!-- Prevenir menu de context long-press em iOS -->
<button class="no-touch-callout">
  Sem menu de contexto
</button>

<!-- Alternativa com user-select -->
<div class="select-none">
  Não selecionável
</div>
```

---

## 🎭 Visibilidade Alternativa

### Visibility (Renderiza mas invisível)

```html
<!-- Renderizado mas invisível -->
<div class="visible-mobile">
  Visível em mobile
</div>

<div class="visible-tablet">
  Visível em tablet
</div>

<div class="visible-desktop">
  Visível em desktop
</div>
```

---

## 🖼️ Aspecto Responsivo

### Aspect Ratio

```html
<!-- Quad 1:1 -->
<div class="aspect-square">
  <img src="..." />
</div>

<!-- Vídeo 16:9 -->
<div class="aspect-video">
  <iframe src="..."></iframe>
</div>

<!-- Retrato 3:4 -->
<div class="aspect-portrait">
  <img src="..." />
</div>
```

---

## 🎨 Border Radius Responsivo

### Cantos Arredondados

```html
<!-- Aumenta conforme tela cresce -->
<div class="rounded-sm-mobile">
  <!-- 4px mobile, 6px tablet, 8px desktop -->
</div>

<div class="rounded-md-mobile">
  <!-- 8px mobile, 10px tablet, 12px desktop -->
</div>

<div class="rounded-lg-mobile">
  <!-- 12px mobile, 14px tablet, 16px desktop -->
</div>
```

---

## 💫 Sombra & Depth

### Box Shadow

```html
<!-- Sem sombra em mobile -->
<div class="shadow-none-mobile shadow-md">
  <!-- Nenhuma sombra em mobile, md em tablet+ -->
</div>

<div class="shadow-lg">
  <!-- Sombra grande (sempre) -->
</div>

<div class="shadow-xl">
  <!-- Sombra extra grande -->
</div>
```

---

## 🔄 Overflow Responsivo

### Scroll em Mobile

```html
<!-- Scroll suave em mobile (iOS) -->
<div class="overflow-auto-mobile">
  <!-- Scroll automático com inércia em iOS -->
</div>

<!-- Scroll horizontal -->
<div class="overflow-x-auto">
  <!-- Sempre scroll-x com suporte touch -->
</div>

<!-- Scroll vertical -->
<div class="overflow-y-auto">
  <!-- Sempre scroll-y -->
</div>

<!-- Hidden -->
<div class="overflow-hidden-mobile">
  <!-- Overflow hidden em mobile -->
</div>
```

---

## 📍 Posicionamento Responsivo

### Position Dinâmico

```html
<!-- Absolute em mobile, static em desktop -->
<div class="absolute-mobile static-desktop">
  Positioned dinamicamente
</div>

<!-- Relative -->
<div class="relative-mobile">
  <!-- Relative em mobile -->
</div>

<!-- Fixed -->
<div class="fixed-mobile">
  <!-- Fixed em mobile (bottom nav, etc) -->
</div>
```

---

## 📊 Stack & Flex

### Stack Flexível

```html
<!-- Coluna em mobile, row em tablet+ -->
<div class="flex flex-col-mobile" style="flex-direction: row;">
  <div>Esquerda</div>
  <div>Direita</div>
</div>

<!-- Reverse em mobile -->
<div class="flex" style="flex-direction: column-reverse;">
  <div>Último em mobile</div>
  <div>Primeiro em mobile</div>
</div>
```

---

## 🎯 Texto Responsivo

### Alinhamento de Texto

```html
<!-- Centralizado em mobile, left em desktop -->
<div class="text-center-mobile text-left-desktop">
  Texto adaptativo
</div>

<!-- Centralizado em tablet -->
<div class="text-center-tablet">
  Centralizado tablet
</div>

<!-- Right aligned desktop -->
<div class="text-right-desktop">
  Alinhado à direita
</div>
```

### Altura de Linha

```html
<!-- Linha compactada -->
<p class="leading-tight">
  <!-- line-height: 1.2 -->
</p>

<!-- Linha normal -->
<p class="leading-normal">
  <!-- line-height: 1.5 -->
</p>

<!-- Linha espaçada -->
<p class="leading-loose">
  <!-- line-height: 1.8 -->
</p>
```

---

## 🎨 Transformações

### Scale (Zoom)

```html
<!-- Normal -->
<div class="scale-100">
  Tamanho normal
</div>

<!-- 95% -->
<div class="scale-95">
  Levemente menor
</div>

<!-- 105% -->
<div class="scale-105">
  Levemente maior
</div>
```

### Translate (Movimento)

```html
<!-- Deslocar X -->
<div class="translate-x-full">
  <!-- 100% para a direita -->
</div>

<div class="translate-x-0">
  <!-- 0 (sem deslocamento) -->
</div>

<!-- Deslocar Y -->
<div class="translate-y-full">
  <!-- 100% para baixo (drawer) -->
</div>

<div class="translate-y-0">
  <!-- Posição normal -->
</div>
```

---

## 📦 Contenedor

### Container Responsivo

```html
<!-- Container com padding e max-width adaptativo -->
<div class="container">
  <!-- 100% mobile, 450px tablet pequeno, 720px tablet, 960px desktop, 1280px desktop grande -->
  Conteúdo fluido mas limitado
</div>
```

---

## 🔍 Z-Index

### Camadas

```html
<!-- Z-index básico -->
<div class="z-0">Base</div>
<div class="z-10">Acima</div>
<div class="z-20">Mais acima</div>

<!-- Z-index para modais -->
<div class="z-modal">Modal</div>

<!-- Z-index máximo -->
<div class="z-top">Muito acima</div>
```

---

## 👁️ Opacidade

### Transparência Responsiva

```html
<!-- Opacidade responsiva -->
<div class="opacity-0-mobile opacity-100-desktop">
  Invisível em mobile, visível em desktop
</div>

<!-- Valores fixos -->
<div class="opacity-50">
  50% transparente
</div>

<div class="opacity-75">
  75% transparente
</div>

<div class="opacity-100">
  Completamente opaco
</div>
```

---

## 🎬 Backdrop & Filtros

### Blur Effect

```html
<!-- Blur adaptativo -->
<div class="blur-lg">
  <!-- 16px blur, reduzido para 8px em mobile -->
</div>

<div class="blur-md">
  <!-- 8px blur -->
</div>

<div class="blur-sm">
  <!-- 4px blur -->
</div>
```

---

## ⌚ Cursor

### Cursor Styles

```html
<!-- Pointer (clicável) -->
<button class="cursor-pointer">
  Clique
</button>

<!-- Text (seleção) -->
<div class="cursor-text">
  Select me
</div>

<!-- Move -->
<div class="cursor-move">
  Drag me
</div>

<!-- Not allowed -->
<button class="cursor-not-allowed" disabled>
  Desabilitado
</button>
```

---

## ✏️ Seleção

### User Select

```html
<!-- Não selecionável -->
<div class="select-none">
  Não posso ser selecionado
</div>

<!-- Selecionável -->
<div class="select-text">
  Posso ser selecionado
</div>

<!-- Select all ao clicar -->
<div class="select-all">
  Click aqui seleciona tudo
</div>
```

---

## 🚀 Performance

### Will Change

```html
<!-- Optimizar para transform -->
<div class="will-change-transform">
  Vai ser transformado frequentemente
</div>

<!-- Optimizar para opacity -->
<div class="will-change-opacity">
  Vai mudar opacidade frequentemente
</div>
```

---

## ♿ Acessibilidade

### Screen Reader Only

```html
<!-- Oculto visualmente mas acessível -->
<span class="sr-only">
  Informação adicional para leitores de tela
</span>

<!-- Exemplo -->
<button>
  <i class="fas fa-times"></i>
  <span class="sr-only">Fechar</span>
</button>
```

### Focus Visible

```html
<!-- Outline ao focar (acessibilidade) -->
<button class="focus-visible:focus">
  Foco otimizado
</button>
```

---

## 🖨️ Print

### Print Styles

```html
<!-- Ocultar em impressão -->
<div class="print-hidden">
  Não aparece na impressão
</div>

<!-- Mostrar apenas em impressão -->
<div class="print-show">
  Apenas na impressão
</div>
```

---

## 📋 Resumo Rápido

| Classe | O que faz | Uso |
|--------|-----------|-----|
| `show-mobile-only` | Visível só mobile | Menu mobile |
| `hide-mobile` | Oculto em mobile | Desktop feature |
| `touch-target` | 44x44px mínimo | Botões |
| `w-full-mobile` | 100% em mobile | Containers |
| `text-xl-mobile` | Font responsiva | Headings |
| `gap-mobile` | Gap adaptativo | Grid/Flex |
| `p-mobile` | Padding adaptativo | Cards |
| `rounded-md-mobile` | Border radius responsiva | Cards |
| `shadow-lg` | Sombra adaptativa | Depth |
| `overflow-auto-mobile` | Scroll suave | Listas |
| `sr-only` | Screen reader | A11y |
| `cursor-pointer` | Cursor style | UI |

---

**DICA:** Combine múltiplas classes para melhor controle!

```html
<div class="p-mobile gap-mobile grid-cols-1-mobile grid-cols-2-tablet grid-cols-3-desktop rounded-md-mobile shadow-lg">
  <!-- Altamente responsivo! -->
</div>
```

---

Última atualização: Abril 2026
TITAN v5 — Utilities Responsive v1.0
