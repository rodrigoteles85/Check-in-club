# 📚 Guia de Variáveis CSS - Check in Club

## 🎯 Propósito

Este documento descreve o sistema centralizado de variáveis CSS do projeto, implementado para facilitar manutenção, consistência visual e mudanças rápidas de design em todo o projeto.

---

## 📂 Estrutura

### Arquivo Principal

- **`style/global.css`** - Contém todas as variáveis CSS centralizadas

### Arquivos que usam as variáveis

- **`style/home.css`** - Página inicial (hotéis e voos)
- **`style/login.css`** - Página de login

---

## 🎨 Categorias de Variáveis

### 1️⃣ CORES (--color-\*)

```css
--color-primary: #ffd700; /* Ouro - Destaques */
--color-primary-dark: #d4af37; /* Ouro escuro */
--color-secondary: #000; /* Preto - Botões */
--color-secondary-light: #222; /* Cinza muito escuro */
--color-white: #fff; /* Branco */
--color-black: #000; /* Preto */
--color-gray-light: #f5f6fa; /* Cinza claro - BG */
--color-gray-border: #eee; /* Cinza borders */
--color-gray-text: #666; /* Cinza texto */
```

### 2️⃣ TIPOGRAFIA (--font-\*)

**Famílias:**

```css
--font-serif: "Playfair Display", serif; /* Títulos elegantes */
--font-sans: "Montserrat", Arial, sans-serif; /* Corpo de texto */
```

**Tamanhos:**

```css
--font-size-xs: 0.875rem; /* 14px */
--font-size-sm: 1rem; /* 16px */
--font-size-base: 1.1rem; /* 17.6px */
--font-size-lg: 1.4rem; /* 22.4px */
--font-size-xl: 2rem; /* 32px */
--font-size-2xl: 3rem; /* 48px */
```

**Pesos:**

```css
--font-weight-regular: 400;
--font-weight-semibold: 600;
--font-weight-bold: 700;
```

### 3️⃣ ESPAÇAMENTO (--spacing-\*)

```css
--spacing-xs: 8px;
--spacing-sm: 10px;
--spacing-md: 12px;
--spacing-lg: 18px;
--spacing-xl: 22px;
--spacing-2xl: 28px;
--spacing-3xl: 32px;
--spacing-4xl: 40px;
```

### 4️⃣ BORDER RADIUS (--radius-\*)

```css
--radius-sm: 15px; /* Formulários */
--radius-md: 18px; /* Cards */
--radius-lg: 24px; /* Botões */
--radius-xl: 30px; /* Tabs */
--radius-full: 40px; /* Input fields */
```

### 5️⃣ SOMBRAS (--shadow-\*)

```css
--shadow-sm: 0 0 10px rgba(0, 0, 0, 0.2);
--shadow-md: 0 10px 30px rgba(0, 0, 0, 0.08);
--shadow-lg: 0 18px 40px rgba(0, 0, 0, 0.15);
```

### 6️⃣ EFEITOS E TRANSIÇÕES

**Backdrop Filters:**

```css
--backdrop-blur-sm: blur(10px); /* Header */
--backdrop-blur-md: blur(30px); /* Modal login */
```

**Transições:**

```css
--transition-fast: 0.25s ease; /* Interações rápidas */
--transition-base: 0.3s ease; /* Animações padrão */
```

### 7️⃣ BORDERS (--border-\*)

```css
--border-width: 2px;
--border-light: 2px solid rgba(255, 255, 255, 0.2); /* Vidro */
--border-dark: 2px solid #eee; /* Default */
```

### 8️⃣ GRID E LAYOUT (--\*-)

```css
--container-max-width: 1200px; /* Width máximo */
--container-padding: 40px; /* Padding horizontal */
--grid-gap: 32px; /* Gap entre cards */
--card-min-width: 340px; /* Min width cards */
```

### 9️⃣ OVERLAYS E ESTADOS

```css
--overlay-dark: rgba(0, 0, 0, 0.55); /* Banner gradient */
--bg-transparent: rgba(255, 255, 255, 0.15); /* Header frosted glass */
```

---

## 💡 Como Usar

### ✅ Exemplo 1: Criar um Botão

```css
.meu-botao {
  background: var(--color-primary);
  color: var(--color-black);
  border-radius: var(--radius-lg);
  padding: var(--spacing-sm) var(--spacing-2xl);
  font-weight: var(--font-weight-semibold);
  transition: all var(--transition-fast);
}

.meu-botao:hover {
  transform: scale(1.05);
}
```

### ✅ Exemplo 2: Criar um Card

```css
.meu-card {
  background: var(--color-white);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-md);
  padding: var(--spacing-xl);
  transition: all var(--transition-base);
}

.meu-card:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-4px);
}
```

### ✅ Exemplo 3: Texto com Tipografia

```css
.titulo-principal {
  font-family: var(--font-serif);
  font-size: var(--font-size-2xl);
  font-weight: var(--font-weight-bold);
  color: var(--color-secondary-light);
}

.texto-corpo {
  font-family: var(--font-sans);
  font-size: var(--font-size-sm);
  color: var(--color-gray-text);
  line-height: 1.6;
}
```

---

## 🔄 Fluxo de Atualização

Para **mudar a cor primária** em todo o projeto:

1. Abra `style/global.css`
2. Encontre a linha: `--color-primary: #FFD700;`
3. Mude para a cor desejada, ex: `--color-primary: #FF6B35;`
4. **Pronto!** Todas as páginas atualizam automaticamente

---

## 📏 Padrões de Nomenclatura

```
Variáveis seguem o padrão:
--[categoria]-[nome]: valor;

Exemplos:
✅ --color-primary
✅ --font-size-lg
✅ --spacing-md
✅ --radius-lg
✅ --shadow-md
✅ --transition-fast
```

---

## 🎯 Boas Práticas

| ✅ Faça                    | ❌ Não Faça                     |
| -------------------------- | ------------------------------- |
| Usar variáveis CSS         | Hardcodar valores (`#FFD700`)   |
| Reutilizar espaçamento     | Inveniar novos valores (`23px`) |
| Combinar variáveis         | Duplicar definições             |
| Manter ordem alfabética    | Misturar categorias             |
| Comentar valores especiais | Deixar sem documentação         |

---

## 📱 Responsividade

As variáveis funcionam perfeitamente em media queries:

```css
@media (max-width: 768px) {
  .container {
    padding: var(--spacing-xl); /* Reduz automaticamente em mobile */
  }
}
```

---

## 🚀 Próximos Passos (Recomendações)

- [ ] Adicionar variáveis de z-index centralizadas
- [ ] Criar variáveis para animações padrão
- [ ] Implementar tema dark mode com variáveis
- [ ] Adicionar easing curves padronizadas
- [ ] Criar guia de componentes reutilizáveis

---

## 📞 Dúvidas?

Consulte o `global.css` para ver todas as definições centralizadas e seus valores atuais.
