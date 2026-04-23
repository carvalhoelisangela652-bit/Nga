# 💻 TITAN v5 — Exemplos Práticos Responsivos

## Snippets Prontos Para Usar

Copie e cole os exemplos abaixo para seus components HTML.

---

## 1️⃣ Card Responsivo

```html
<!-- Card que muda layout por breakpoint -->
<div class="card p-mobile gap-mobile rounded-md-mobile shadow-lg">
  <div class="card-title text-md-mobile">
    <i class="fas fa-chart-bar"></i> Métrica
  </div>
  
  <div style="display: grid; grid-template-columns: auto 1fr; gap: 10px; align-items: center;">
    <div style="font-size: 28px; color: var(--green);">87%</div>
    <div>
      <div class="text-sm-mobile" style="color: var(--text-dim);">Performance</div>
      <div class="text-xs-mobile" style="color: var(--text-mid);">Último mês</div>
    </div>
  </div>
</div>
```

---

## 2️⃣ Grid Responsivo (Métricas)

```html
<!-- Desktop: 4 colunas, Tablet: 3, Mobile: 2 -->
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: var(--sp-md, 12px); margin-bottom: var(--sp-lg, 16px);">
  <div class="card p-mobile rounded-md-mobile">
    <div class="metric-label">Requests</div>
    <div class="metric-value">1.2K</div>
  </div>
  
  <div class="card p-mobile rounded-md-mobile">
    <div class="metric-label">Latência</div>
    <div class="metric-value">45ms</div>
  </div>
  
  <div class="card p-mobile rounded-md-mobile">
    <div class="metric-label">Uptime</div>
    <div class="metric-value">99.9%</div>
  </div>
  
  <div class="card p-mobile rounded-md-mobile">
    <div class="metric-label">Errors</div>
    <div class="metric-value">2</div>
  </div>
</div>
```

---

## 3️⃣ Modal Responsivo

```html
<!-- Modal que é fullscreen em mobile, centered em desktop -->
<div id="responsive-modal" onclick="if(event.target===this)closeModal()">
  <style>
    @media (max-width: 767px) {
      #responsive-modal {
        align-items: flex-end;
        padding: 0;
      }
      #responsive-modal .modal-box {
        max-height: 90vh;
        border-radius: 16px 16px 0 0;
        width: 100%;
        max-width: none;
      }
    }
    
    @media (min-width: 768px) {
      #responsive-modal {
        align-items: center;
        padding: 20px;
      }
      #responsive-modal .modal-box {
        max-height: 85vh;
        border-radius: 12px;
        width: auto;
        max-width: 520px;
      }
    }
  </style>
  
  <div class="modal-box p-mobile rounded-md-mobile" style="background: rgba(11,17,26,.98); border: 1px solid var(--border2);">
    <div class="modal-handle" style="width: 36px; height: 4px; background: var(--border2); border-radius: 99px; margin: 12px auto;"></div>
    
    <div class="modal-header" style="padding: 16px 14px 10px; border-bottom: 1px solid var(--border);">
      <div class="modal-title text-md-mobile">Configure Algo</div>
      <button onclick="closeModal()" class="icon-btn" style="width: 32px; height: 32px;">
        <i class="fas fa-times"></i>
      </button>
    </div>
    
    <!-- Conteúdo aqui -->
  </div>
</div>
```

---

## 4️⃣ Header Responsivo com Menu

```html
<!-- Header que muda em mobile -->
<header id="header" style="display: flex; align-items: center; height: 48px; padding: 0 8px; gap: 8px;">
  <!-- Logo (menor em mobile) -->
  <div style="flex-shrink: 0;">
    <svg width="24" height="30" viewBox="0 0 40 50" xmlns="http://www.w3.org/2000/svg">
      <!-- SVG aqui -->
    </svg>
  </div>
  
  <!-- Titulo (responsive font) -->
  <div class="text-md-mobile" style="flex: 1; min-width: 0;">
    <strong>TITAN</strong>
    <span class="hide-mobile">v5 Super Agent</span>
  </div>
  
  <!-- Espaço flex -->
  <div style="flex: 1;"></div>
  
  <!-- Botões (adaptáveis) -->
  <div style="display: flex; gap: 6px; align-items: center;">
    <button class="icon-btn touch-target">
      <i class="fas fa-search"></i>
    </button>
    
    <button class="icon-btn touch-target show-mobile-only">
      <i class="fas fa-bars"></i>
    </button>
    
    <button class="hide-mobile icon-btn touch-target" style="padding: 0 8px;">
      <i class="fas fa-key"></i> KEYS
    </button>
  </div>
</header>
```

---

## 5️⃣ Sidebar Drawer (Mobile)

```html
<!-- Sidebar que vira drawer em mobile -->
<nav id="sidebar" style="
  position: fixed;
  inset: 48px 0 60px 0;
  width: 280px;
  background: rgba(8,12,18,.98);
  border-right: 1px solid var(--border);
  transform: translateX(-100%);
  transition: transform 0.3s ease;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
">
  <!-- Backdrop overlay para fechar -->
  <div onclick="closeSidebar()" style="
    position: fixed;
    inset: 48px 0 60px 280px;
    background: rgba(0,0,0,.4);
    display: none;
  " id="sidebar-overlay"></div>
  
  <style>
    #sidebar.open {
      transform: translateX(0);
    }
    
    #sidebar.open ~ #sidebar-overlay {
      display: block;
    }
    
    @media (min-width: 768px) {
      #sidebar {
        position: relative;
        inset: auto;
        width: 240px;
        transform: translateX(0);
      }
      #sidebar-overlay {
        display: none !important;
      }
    }
  </style>
  
  <!-- Conteúdo -->
  <div style="padding: 12px; border-bottom: 1px solid var(--border);">
    <div class="text-xs-mobile" style="color: var(--text-dim); font-weight: 700; letter-spacing: 1px;">
      NAVEGAÇÃO
    </div>
  </div>
  
  <!-- Items -->
</nav>
```

---

## 6️⃣ Bottom Navigation (Mobile)

```html
<!-- Bottom nav que desaparece em tablet+ -->
<div id="bottom-tabs" style="
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 60px;
  background: rgba(8,12,18,.95);
  border-top: 1px solid var(--border);
  display: flex;
  z-index: 300;
">
  <button class="bottom-tab active" onclick="switchTab('dashboard')" style="
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: var(--accent);
    background: rgba(47,120,240,.1);
    border: none;
    font-size: 8px;
    cursor: pointer;
  ">
    <i class="fas fa-chart-bar" style="font-size: 18px; margin-bottom: 4px;"></i>
    Dashboard
  </button>
  
  <button class="bottom-tab" onclick="switchTab('github')" style="
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: var(--text-dim);
    border: none;
    font-size: 8px;
    cursor: pointer;
  ">
    <i class="fab fa-github" style="font-size: 18px; margin-bottom: 4px;"></i>
    GitHub
  </button>

  <!-- Mais tabs... -->
</div>

<style>
  @media (min-width: 768px) {
    #bottom-tabs {
      display: none;
    }
  }
</style>
```

---

## 7️⃣ Layout Responsivo 2-Coluna

```html
<!-- 1 coluna mobile, 2 colunas tablet/desktop -->
<div style="
  display: grid;
  grid-template-columns: 1fr;
  gap: 12px;
">
  <!-- Mobile: coloca um abaixo do outro -->
  
  <div class="card p-mobile rounded-md-mobile">
    <div class="card-title">Left Panel</div>
    <!-- Conteúdo -->
  </div>
  
  <div class="card p-mobile rounded-md-mobile">
    <div class="card-title">Right Panel</div>
    <!-- Conteúdo -->
  </div>
</div>

<style>
  @media (min-width: 768px) {
    /* Tablet+ fica 2 colunas */
    div {
      grid-template-columns: 1fr 1fr;
    }
  }
</style>
```

---

## 8️⃣ Input Responsivo Touch-Friendly

```html
<!-- Input otimizado para touch em mobile -->
<div style="display: flex; flex-direction: column; gap: 6px;">
  <label class="text-xs-mobile" style="color: var(--text-dim); font-weight: 700; letter-spacing: 1px;">
    API KEY
  </label>
  
  <div style="display: flex; gap: 6px; align-items: stretch;">
    <input 
      type="password" 
      placeholder="sk-..." 
      class="api-input touch-target"
      style="
        flex: 1;
        height: 40px;
        min-height: 44px;
        padding: 8px 10px;
        font-size: 14px;
        border-radius: 6px;
        background: var(--bg3);
        border: 1px solid var(--border);
        color: var(--text);
      "
    />
    
    <button class="icon-btn touch-target" style="min-width: 44px; min-height: 44px;">
      <i class="fas fa-eye"></i>
    </button>
    
    <button class="touch-target" style="
      height: 40px;
      min-height: 44px;
      padding: 0 10px;
      background: var(--accent-dim);
      border: 1px solid rgba(47,120,240,.3);
      border-radius: 6px;
      color: var(--accent);
      font-size: 10px;
      font-weight: 700;
      white-space: nowrap;
      flex-shrink: 0;
    ">
      TEST
    </button>
  </div>
  
  <div class="text-xs-mobile" style="color: var(--text-dim); line-height: 1.5;">
    Obtenha em <a href="..." style="color: var(--accent);">console.example.com</a>
  </div>
</div>
```

---

## 9️⃣ Tabbed Interface Responsivo

```html
<!-- Tabs com scroll horizontal em mobile -->
<div style="overflow-x: auto; -webkit-overflow-scrolling: touch; border-bottom: 1px solid var(--border);">
  <div style="display: flex; gap: 3px; padding: 10px 12px; white-space: nowrap;">
    <button class="modal-tab active" style="
      padding: 6px 10px;
      background: var(--accent-dim);
      border: 1px solid rgba(47,120,240,.25);
      border-radius: 5px;
      color: var(--accent);
      font-size: 9px;
      font-weight: 700;
      cursor: pointer;
      transition: var(--transition);
    ">✦ Claude</button>
    
    <button class="modal-tab" style="
      padding: 6px 10px;
      background: transparent;
      border: 1px solid transparent;
      border-radius: 5px;
      color: var(--text-dim);
      font-size: 9px;
      font-weight: 700;
      cursor: pointer;
      transition: var(--transition);
    ">◈ GitHub</button>
    
    <button class="modal-tab" style="
      padding: 6px 10px;
      background: transparent;
      border: 1px solid transparent;
      border-radius: 5px;
      color: var(--text-dim);
      font-size: 9px;
      font-weight: 700;
      cursor: pointer;
      transition: var(--transition);
    ">◉ Render</button>
  </div>
</div>

<!-- Tab content -->
<div style="padding: 12px 14px;">
  <!-- Conteúdo da tab Claude -->
</div>
```

---

## 🔟 Buttons Responsivos

```html
<!-- Botões que adaptam tamanho -->
<div style="display: flex; flex-direction: column; gap: 8px;">
  <!-- Primary Button -->
  <button class="touch-target" style="
    width: 100%;
    height: 44px;
    min-height: 44px;
    background: linear-gradient(135deg, var(--accent) 0%, var(--copper) 100%);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 11px;
    font-weight: 900;
    letter-spacing: 0.5px;
    cursor: pointer;
    transition: var(--transition);
  ">
    <i class="fas fa-key" style="margin-right: 6px;"></i>
    CONFIGURAR
  </button>
  
  <!-- Secondary Button -->
  <button class="touch-target" style="
    width: 100%;
    height: 44px;
    min-height: 44px;
    background: var(--bg3);
    color: var(--text);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 11px;
    font-weight: 800;
    cursor: pointer;
    transition: var(--transition);
  ">
    <i class="fab fa-github" style="margin-right: 6px;"></i>
    LOGIN COM GITHUB
  </button>
</div>

<style>
  /* Em desktop, lado a lado */
  @media (min-width: 768px) {
    div {
      flex-direction: row;
    }
    button {
      width: auto;
      flex: 1;
    }
  }
</style>
```

---

## 1️⃣1️⃣ Breadcrumb Responsivo

```html
<!-- Breadcrumb que trunca em mobile -->
<div style="
  display: flex;
  gap: 6px;
  align-items: center;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  padding: 8px 0;
  font-size: 9px;
">
  <span style="color: var(--accent); cursor: pointer;">Home</span>
  <i class="fas fa-chevron-right" style="color: var(--text-dim); font-size: 7px;"></i>
  
  <span class="hide-mobile" style="color: var(--text-mid);">Projects</span>
  <i class="fas fa-chevron-right hide-mobile" style="color: var(--text-dim); font-size: 7px;"></i>
  
  <span style="color: var(--text); font-weight: 700; white-space: nowrap;">Current Page</span>
</div>
```

---

## 1️⃣2️⃣ Loading State Responsivo

```html
<!-- Loading spinner responsivo -->
<div style="
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  padding: 20px;
">
  <div style="
    width: 40px;
    height: 40px;
    border: 3px solid var(--border);
    border-top-color: var(--accent);
    border-radius: 50%;
    animation: spin 1s linear infinite;
  "></div>
  
  <div class="text-md-mobile" style="color: var(--text-mid);">
    Processando...
  </div>
</div>

<style>
  @keyframes spin {
    to { transform: rotate(360deg); }
  }
</style>
```

---

## 1️⃣3️⃣ Notification Toast

```html
<!-- Toast que aparece bottom-right, mobile-aware -->
<div style="
  position: fixed;
  bottom: 70px;
  left: 10px;
  right: 10px;
  background: rgba(11,17,26,.95);
  border: 1px solid var(--border2);
  border-radius: 8px;
  padding: 12px 14px;
  display: flex;
  align-items: center;
  gap: 8px;
  backdrop-filter: blur(10px);
  z-index: 10000;
  animation: slideUp 0.3s ease;
">
  <i class="fas fa-check-circle" style="color: var(--green); flex-shrink: 0;"></i>
  <span class="text-sm-mobile" style="color: var(--text);">
    Configuração salva com sucesso!
  </span>
  <button onclick="this.parentElement.remove()" style="
    background: transparent;
    border: none;
    color: var(--text-dim);
    cursor: pointer;
    margin-left: auto;
    flex-shrink: 0;
  ">
    <i class="fas fa-times"></i>
  </button>
</div>

<style>
  @keyframes slideUp {
    from { transform: translateY(100%); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
  }
  
  @media (min-width: 768px) {
    /* Desktop: canto inferior direito */
    div {
      bottom: 16px;
      right: 16px;
      left: auto;
    }
  }
</style>
```

---

## 1️⃣4️⃣ Full Page Layout

```html
<!-- Layout completo responsivo -->
<div id="app" style="
  display: flex;
  flex-direction: column;
  height: 100vh;
  overflow: hidden;
">
  <!-- Header -->
  <header id="header" style="
    height: 48px;
    background: rgba(8,12,18,.92);
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    padding: 0 8px;
    z-index: 100;
    flex-shrink: 0;
  ">
    <!-- Header content -->
  </header>
  
  <!-- Content area -->
  <div id="content" style="
    flex: 1;
    display: flex;
    overflow: hidden;
  ">
    <!-- Sidebar (modal em mobile) -->
    <nav id="sidebar" style="
      position: fixed;
      left: 0;
      top: 48px;
      width: 280px;
      height: calc(100vh - 48px - 60px);
      background: rgba(8,12,18,.95);
      transform: translateX(-100%);
      transition: transform 0.3s ease;
    "></nav>
    
    <!-- Main panels -->
    <main id="panels" style="
      flex: 1;
      overflow-y: auto;
      -webkit-overflow-scrolling: touch;
      padding-bottom: 60px;
    "></main>
  </div>
  
  <!-- Bottom navigation (mobile) -->
  <div id="bottom-tabs" style="
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    height: 60px;
    background: rgba(8,12,18,.95);
    border-top: 1px solid var(--border);
    display: flex;
    z-index: 300;
  "></div>
</div>

<style>
  @media (min-width: 768px) {
    #app {
      /* Remover bottom tabs */
    }
    
    #content {
      flex-direction: row;
    }
    
    #sidebar {
      position: relative;
      left: auto;
      transform: none;
      width: 240px;
    }
    
    #panels {
      padding-bottom: 0;
    }
    
    #bottom-tabs {
      display: none;
    }
  }
</style>
```

---

## Dicas Finais

✅ **Sempre use `min-height: 44px` para elementos clicáveis em mobile**
✅ **Use `font-size: 14px+` em inputs para evitar zoom iOS**
✅ **Aplique `-webkit-overflow-scrolling: touch` para melhor performance**
✅ **Combina classes do `utilities-responsive.css` para máxima eficiência**
✅ **Teste em múltiplos breakpoints: 375px, 768px, 1024px, 1440px**

---

Última atualização: Abril 2026
TITAN v5 — Exemplos Práticos v1.0
