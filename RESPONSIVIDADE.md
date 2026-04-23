# 📱 TITAN v5 — Guia de Responsividade Mobile-First Avançado

## 🎯 Visão Geral

O projeto foi transformado em uma **arquitetura responsiva ultra-avançada** com **Mobile-First** completo, suportando todos os dispositivos modernos.

---

## 📐 Breakpoints Definidos

```css
--bp-xs:   320px   /* Mobile Extra Pequeno */
--bp-sm:   480px   /* Mobile Pequeno */
--bp-md:   768px   /* Tablet */
--bp-lg:   1024px  /* Desktop Pequeno */
--bp-xl:   1440px  /* Desktop Grande */
--bp-2xl:  1920px  /* Ultrawide */
```

---

## 🔄 Estratégia Mobile-First

### Estrutura do CSS

1. **`main.css`** — Estilos base e variáveis (mobile-first)
2. **`components.css`** — Componentes responsivos (modal, API, etc)
3. **`responsive.css`** — Arquivo dedicado para media queries (NOVO)
4. **`utilities-responsive.css`** — Classes helper responsivas (NOVO)

### Como Funciona

```css
/* PADRÃO: Mobile (< 768px) */
.panel {
  padding: 12px 10px;  /* Compacto para mobile */
}

/* TABLET: 768px - 1023px */
@media (min-width: 768px) {
  .panel {
    padding: 16px 20px;  /* Aumentado para tablet */
  }
}

/* DESKTOP: 1024px+ */
@media (min-width: 1024px) {
  .panel {
    padding: 20px 24px;  /* Espaçamento completo */
  }
}
```

---

## 📱 Layout por Dispositivo

### Mobile (< 768px)

```
┌──────────────────┐
│    Header (48px) │
├──────────────────┤
│                  │
│    Main Panel    │
│                  │
├──────────────────┤
│  Bottom Tabs     │
│  (60px)          │
└──────────────────┘

Sidebar: Drawer overlay (#sidebar-overlay)
```

**Características:**
- ✅ Drawer sidebar que desliza
- ✅ Bottom navigation bar
- ✅ Modal em fullscreen bottom sheet
- ✅ Touch-friendly (min 44px)
- ✅ Dinâmico viewport (100dvh)

### Tablet (768px - 1023px)

```
┌────────────────────────────────┐
│        Header (56px)           │
├─────────┬──────────────────────┤
│ Sidebar │                      │
│ (240px) │    Main Panel        │
│         │                      │
│         │                      │
└─────────┴──────────────────────┘
```

**Características:**
- ✅ Sidebar fixo e visível
- ✅ Sem bottom nav
- ✅ 2 colunas em grids
- ✅ Modal em modal box

### Desktop (1024px+)

```
┌─────────────────────────────────────┐
│           Header (56px)             │
├───────────┬─────────────────────────┤
│ Sidebar   │                         │
│ (260-280) │    Main Panel           │
│           │                         │
│           │                         │
└───────────┴─────────────────────────┘
```

**Características:**
- ✅ Sidebar sempre visível
- ✅ 4-5 colunas em grids
- ✅ Full-featured layout
- ✅ Modal centrado

---

## 🎨 Componentes Responsivos

### Header

| Mobile | Tablet | Desktop |
|--------|--------|---------|
| 48px | 56px | 56px |
| Logo reduzido | Logo completo | Logo completo |
| Menu hambúrguer | Menu oculto | Menu oculto |
| Compact | Normal | Normal |

### Sidebar

| Mobile | Tablet | Desktop |
|--------|--------|---------|
| Drawer overlay | Fixo 240px | Fixo 260px |
| Visível ao clicar | Sempre visível | Sempre visível |
| Full height | Scrollável | Scrollável |

### Grids

| Mobile | Tablet | Desktop | XL |
|--------|--------|---------|-----|
| 2 colunas | 3 colunas | 4 colunas | 5 colunas |

### Modais

| Mobile | Tablet+ |
|--------|---------|
| Bottom sheet fullscreen | Centered modal box |
| Draggable handle | Fixed position |
| Swipe to close | Click overlay to close |

---

## 🚀 Otimizações Touch

### Áreas Touch-Friendly

```css
--touch-min: 44px;  /* Mínimo recomendado */
```

Todos os botões, inputs e áreas clicáveis têm **mínimo 44x44px** em mobile.

### Tipos de Input

```html
<!-- Font size de 14px+ previne zoom iOS -->
<input type="text" placeholder="..." /> <!-- 14px em mobile -->

<!-- Select também otimizado -->
<select class="api-input">
  <option>...</option>
</select>

<!-- Textarea -->
<textarea placeholder="..."></textarea>
```

### Scroll Performance

```css
-webkit-overflow-scrolling: touch;  /* Scroll suave em iOS */
overflow: auto;                      /* Overflow otimizado */
```

---

## 📊 Classes Helper Responsivas

Use as classes em `utilities-responsive.css`:

### Display

```html
<!-- Mostrar/ocultar por breakpoint -->
<div class="show-mobile-only">Visível apenas em mobile</div>
<div class="show-tablet-only">Visível apenas em tablet</div>
<div class="show-desktop-only">Visível apenas em desktop</div>

<div class="hide-mobile">Oculto em mobile</div>
<div class="hide-tablet">Oculto em tablet</div>
<div class="hide-desktop">Oculto em desktop</div>
```

### Grid Responsivo

```html
<div class="grid-cols-1-mobile">
  <!-- 1 coluna em mobile -->
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### Spacing Responsivo

```html
<!-- Espaçamento dinâmico -->
<div class="p-mobile gap-mobile">
  <!-- 10px padding + 8px gap em mobile -->
  <!-- Aumenta em tablet/desktop -->
</div>
```

### Tipografia Responsiva

```html
<h1 class="text-xl-mobile">
  <!-- 14px em mobile, 15px tablet, 17px desktop -->
</h1>
```

### Touch Optimization

```html
<button class="touch-target">
  <!-- Garantido mín 44x44px -->
  Click me
</button>
```

---

## 🔧 Implementação no Código

### JavaScript para Mobile

```javascript
// Detectar mudança de tamanho
window.addEventListener('resize', () => {
  const isMobile = window.innerWidth < 768;
  if (!isMobile) {
    closeSidebar();  // Fechar drawer em tablet+
  }
});

// Viewport mobile otimizado
const isMobileViewport = window.innerWidth < 768;
const isLandscape = window.innerHeight < window.innerWidth;
```

### Melhorias Adicionadas

✅ **100dvh** — Dynamic Viewport Height (ignora barra do navegador)
✅ **viewport-fit=cover** — Notch awareness
✅ **-webkit-overflow-scrolling: touch** — Inércia scroll iOS
✅ **touch-action: manipulation** — Remove delay de 300ms
✅ **user-select: none** — Previne seleção acidental

---

## 📋 Checklist de Responsividade

- [x] Mobile-first architecture
- [x] Touch-friendly (44x44px minimum)
- [x] Flexible typography
- [x] Responsive images/SVGs
- [x] Flexible layouts (flexbox/grid)
- [x] Optimized performance
- [x] Cross-browser support
- [x] High DPI displays
- [x] Landscape support
- [x] Keyboard accessibility
- [x] Screen reader support
- [x] Reduced motion support
- [x] Dark mode support
- [x] Print styles

---

## 🎯 Casos de Uso

### Mobile Pequeno (320px - 479px)
- Stack vertical completo
- Drawer sidebar
- Bottom navigation
- Botões grandes
- Modalss em fullscreen

### Mobile Médio (480px - 639px)
- Stack vertical com ajustes
- Slightly larger spacing
- Bottom navigation
- Modais otimizadas

### Tablet (768px - 1023px)
- 2-3 colunas
- Sidebar visível
- Sem bottom nav
- Layouts em grid

### Desktop (1024px - 1439px)
- 3-4 colunas
- Sidebar permanente
- Full-featured UI
- Hover effects

### Desktop Grande (1440px+)
- 4-5 colunas
- Sidebar expandido
- Espaçamento luxurioso

---

## 🛠️ Debug & Troubleshooting

### Ativar Debug de Breakpoints

Descomente em `utilities-responsive.css`:

```css
@media (max-width: 767px) {
  body::before { content: 'MOBILE'; }
}
@media (min-width: 768px) and (max-width: 1023px) {
  body::before { content: 'TABLET'; }
}
@media (min-width: 1024px) {
  body::before { content: 'DESKTOP'; }
}
```

### Testar Responsividade

1. **DevTools** — F12 → Toggle Device Toolbar
2. **Breakpoints:**
   - 375px (iPhone)
   - 480px (Android)
   - 768px (iPad)
   - 1024px (Laptop)
   - 1440px (Desktop)
3. **Orientação** — Portrait/Landscape

---

## 📚 Referências

- [MDN Mobile First](https://developer.mozilla.org/en-US/docs/Mobile)
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/ios)
- [Material Design Responsive](https://material.io/design/layout/responsive-layout-grid.html)
- [CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)

---

## ✨ Features Implementadas

### Responsivity

✅ 6 breakpoints com fallbacks
✅ Dynamic viewport height (100dvh)
✅ Fluid typography
✅ Flexible spacing
✅ Touch optimization

### Performance

✅ Minimal media queries
✅ CSS-only (sem JS)
✅ Optimized animations
✅ Efficient layouts

### Accessibility

✅ WCAG 2.1 AA compliant
✅ Keyboard navigation
✅ Screen reader support
✅ High contrast support
✅ Reduced motion support

### Compatibility

✅ iOS 12+
✅ Android 5+
✅ Chrome (latest)
✅ Firefox (latest)
✅ Safari (latest)
✅ Edge (latest)

---

**Última atualização:** Abril 2026
**TITAN v5** — Ultra Responsive Mobile-First Architecture
