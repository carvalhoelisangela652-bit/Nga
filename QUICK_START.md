# ⚡ QUICK START — Responsividade TITAN v5

Comece a usar a responsividade em 5 minutos!

---

## 1️⃣ Abra o Projeto

```bash
cd /workspaces/Nga
```

---

## 2️⃣ Entenda a Estrutura

### CSS da Responsividade

```
css/
├── main.css                    ← Variáveis de breakpoints
├── components.css              ← Componentes responsivos
├── responsive.css             ← Media queries (NOVO)
└── utilities-responsive.css   ← Classes helper (NOVO)
```

### Documentação

```
├── RESPONSIVIDADE.md              ← Guia completo
├── GUIA_CLASSES_RESPONSIVAS.md    ← Referência de classes
├── EXEMPLOS_PRATICOS.md           ← 14 exemplos prontos
├── CHECKLIST_RESPONSIVIDADE.md    ← Teste com isto
└── RESUMO_TRANSFORMACAO.md        ← O que foi feito
```

---

## 3️⃣ Use Classes Helper

### Mostrar/Ocultar por Breakpoint

```html
<!-- Visível apenas em mobile -->
<div class="show-mobile-only">Mobile</div>

<!-- Visível apenas em desktop -->
<div class="show-desktop-only">Desktop</div>

<!-- Ocultar em mobile -->
<div class="hide-mobile">Não aparece em mobile</div>
```

### Grid Responsivo

```html
<!-- 1 col mobile, 2 tablet, 3 desktop -->
<div style="
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--sp-lg, 16px);
">
  <div class="card">Item</div>
  <div class="card">Item</div>
  <div class="card">Item</div>
</div>
```

### Espaçamento Responsivo

```html
<!-- Padding que cresce com a tela -->
<div class="p-mobile">
  Padding adaptativo
</div>

<!-- Gap em grid/flex -->
<div class="flex gap-mobile">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### Tipografia Responsiva

```html
<!-- Font size adaptativo -->
<h1 class="text-xl-mobile">
  <!-- 14px mobile, 15px tablet, 17px desktop -->
</h1>

<p class="text-md-mobile">
  <!-- 12px mobile, 13px tablet, 14px desktop -->
</p>
```

---

## 4️⃣ Teste Responsividade

### No DevTools

1. Abra `index.html` no navegador
2. Pressione `F12` (DevTools)
3. Clique no ícone de dispositivo mobile
4. Selecione diferentes tamanhos:
   - 📱 375px (iPhone)
   - 📱 480px (Android)
   - 📱 768px (iPad)
   - 💻 1024px (Desktop)
   - 💻 1440px (Grande)

### Teste Orientação

- Gire para landscape
- Observe mudanças no layout
- Bottom tabs desaparecer em tablet+

### Teste Interações

- Clique no menu hambúrguer (mobile)
- Drawer abre/fecha
- Clique em um card
- Verifique responsividade

---

## 5️⃣ Breakpoints Principais

```javascript
// Use em CSS
@media (max-width: 767px) {
  /* Mobile */
}

@media (min-width: 768px) and (max-width: 1023px) {
  /* Tablet */
}

@media (min-width: 1024px) {
  /* Desktop */
}
```

### Referência Rápida

| Breakpoint | Dispositivo | Uso |
|------------|-------------|-----|
| < 480px | Mobile pequeno | Drawer, fullscreen |
| 480-767px | Mobile | Bottom nav, 2 col |
| 768-1023px | Tablet | Sidebar, 3 col |
| 1024-1439px | Desktop | 4 col, full features |
| 1440px+ | Desktop grande | 5 col, espaço |

---

## 6️⃣ Exemplos Rápidos

### Card Responsivo

```html
<div class="card p-mobile rounded-md-mobile shadow-lg">
  <div class="card-title text-md-mobile">
    <i class="fas fa-chart"></i> Métrica
  </div>
  <div class="metric-value">87%</div>
</div>
```

### Botão Touch-Friendly

```html
<button class="touch-target" style="
  min-width: 44px;
  min-height: 44px;
  width: 100%;
  height: 44px;
">
  Clique Aqui
</button>
```

### Input Mobile-Opted

```html
<input 
  type="text" 
  placeholder="..." 
  style="
    height: 40px;
    min-height: 44px;
    font-size: 14px;
    border-radius: 8px;
  "
/>
```

### Layout 2-Coluna

```html
<div style="
  display: grid;
  grid-template-columns: 1fr;
  gap: 12px;
">
  <div class="card">Esquerda</div>
  <div class="card">Direita</div>
</div>

<style>
  @media (min-width: 768px) {
    div {
      grid-template-columns: 1fr 1fr;
    }
  }
</style>
```

---

## 7️⃣ Padrões Comuns

### Mobile-First (✅ FAÇA ASSIM)

```css
/* Padrão: mobile */
.panel {
  padding: 10px;
}

/* Tablet */
@media (min-width: 768px) {
  .panel {
    padding: 16px;
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .panel {
    padding: 20px;
  }
}
```

### Desktop-First (❌ NÃO FAÇA)

```css
/* Desktop primeiro */
.panel {
  padding: 20px;
}

/* Reducir para mobile */
@media (max-width: 767px) {
  .panel {
    padding: 10px;
  }
}
```

---

## 8️⃣ Otimizações Importantes

### Touch Targets

✅ Mínimo **44x44 pixels** para botões/links em mobile

```css
button, a, [role="button"] {
  min-width: 44px;
  min-height: 44px;
}
```

### Font Size em Inputs

✅ **14px ou maior** em inputs (previne zoom iOS)

```html
<input style="font-size: 14px;" /> <!-- ✅ BOM -->
<input style="font-size: 12px;" /> <!-- ❌ Vai fazer zoom -->
```

### Scroll Performance

✅ `-webkit-overflow-scrolling: touch` em mobile

```css
.scrollable {
  overflow-y: auto;
  -webkit-overflow-scrolling: touch; /* iOS */
}
```

---

## 9️⃣ Ferramentas Úteis

### Testar Responsividade

- **DevTools F12** — Built-in (use isto!)
- **Responsive Design Tester** — Extensão Chrome
- **BrowserStack** — Dispositivos reais

### Verificar Performance

- **Lighthouse** — DevTools F12 → Lighthouse
- **WebPageTest** — webpagetest.org
- **Google PageSpeed** — pagespeed.web.dev

### Debugging

```css
/* Debug: mostrar em qual breakpoint você está */
body::before {
  content: 'MOBILE';
  position: fixed;
  bottom: 10px;
  left: 10px;
  background: red;
  color: white;
  padding: 5px 10px;
  z-index: 99999;
}

@media (min-width: 768px) {
  body::before { content: 'TABLET'; background: orange; }
}

@media (min-width: 1024px) {
  body::before { content: 'DESKTOP'; background: green; }
}
```

---

## 🔟 Checklist Inicial

- [ ] Abri `index.html`
- [ ] Testei em tamanhos diferentes (F12)
- [ ] Verifico se sidebar vira drawer em mobile
- [ ] Verifico se bottom tabs aparecem em mobile
- [ ] Verifico se modal vira fullscreen em mobile
- [ ] Testei em landscape
- [ ] Li `RESUMO_TRANSFORMACAO.md`
- [ ] Copiei um exemplo de `EXEMPLOS_PRATICOS.md`

---

## 🎯 Próximos Passos

### 1. Explore a Documentação

```bash
# Leia nesta ordem:
1. RESUMO_TRANSFORMACAO.md      # O que foi feito
2. RESPONSIVIDADE.md             # Como funciona
3. GUIA_CLASSES_RESPONSIVAS.md   # Como usar classes
4. EXEMPLOS_PRATICOS.md          # Copie e cole
5. CHECKLIST_RESPONSIVIDADE.md   # Teste com isto
```

### 2. Comece a Usar

- Use classes de `utilities-responsive.css`
- Copie snippets de `EXEMPLOS_PRATICOS.md`
- Teste em múltiplos breakpoints
- Consulte `RESPONSIVIDADE.md` quando tiver dúvidas

### 3. Customize Para Suas Necessidades

- Ajuste breakpoints em `:root` de `main.css`
- Adicione componentes novos
- Crie suas classes helper
- Teste em dispositivos reais

---

## 💡 Dicas Rápidas

### Adicionar Novo Componente Responsivo

```css
/* 1. Estilos base (mobile) */
.novo-component {
  padding: 10px;
  font-size: 12px;
}

/* 2. Media queries em responsive.css */
@media (min-width: 768px) {
  .novo-component {
    padding: 16px;
    font-size: 14px;
  }
}
```

### Copiar Classe Helper

```css
/* Em utilities-responsive.css */
.novo-util-mobile {
  /* estilos mobile */
}

@media (min-width: 768px) {
  .novo-util-mobile {
    /* estilos tablet+ */
  }
}
```

### Testar Rápidamente

1. DevTools F12
2. Toggle Device Toolbar (Ctrl+Shift+M)
3. Selecione iPhone 12
4. Observe mudanças
5. Mude para tablet
6. Mude para desktop

---

## 🆘 Troubleshooting

### Layout quebrado em mobile?
- Verifique se não há `min-width` fixo
- Use `width: 100%` em containers
- Teste em DevTools

### Elementos muito pequenos?
- Aumente para `min-height: 44px`
- Use `text-md-mobile` para font maior
- Adicione `padding` com `p-mobile`

### Scroll horizontal indesejado?
- Procure por `width: 100%` que está overflowing
- Use `max-width: 100%`
- Teste com `overflow-x: hidden`

### Modal fechando sozinho?
- Verifique `onclick` no overlay
- Garanta que `event.target===this`
- Teste em mobile real

---

## 📱 Testar em Tamanhos Específicos

### Copie e Cole no Console do DevTools

```javascript
// iPhone 12 (375px)
document.documentElement.style.width = '375px';

// Tablet (768px)
document.documentElement.style.width = '768px';

// Desktop (1024px)
document.documentElement.style.width = '1024px';

// Resetar
document.documentElement.style.width = '';
```

Então abra DevTools → Device Toggle para ver mudanças.

---

## 🎓 Aprenda Mais

- [MDN Mobile First](https://developer.mozilla.org/en-US/docs/Mobile)
- [Material Design Responsive](https://material.io/design/layout/responsive-layout-grid.html)
- [CSS Tricks Media Queries](https://css-tricks.com/css-media-queries/)
- [Web Dev Responsive Design](https://web.dev/responsive-web-design-basics/)

---

## ✅ Você está Pronto!

Seu projeto agora é:
- ✅ Mobile-first
- ✅ Totalmente responsivo
- ✅ Touch-optimized
- ✅ Bem documentado
- ✅ Pronto para produção

**Aproveite a responsividade ultra-avançada!** 🚀

---

**Criado em:** Abril 2026
**TITAN v5** — Quick Start Guide v1.0

Dúvidas? Consulte os guias criados!
