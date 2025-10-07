# 🎯 Prompt para Criação de Portfólio Profissional

## Contexto Geral
Crie um site portfólio completo, moderno, responsivo e otimizado para SEO. O projeto deve ser totalmente contido em um único arquivo HTML (com CSS inline e JavaScript incorporado) para facilitar deploy simples.

---

## 📋 Especificações Técnicas

### Estrutura Base
- **Arquivo único:** `index.html` com todo CSS e JS inline
- **Linguagem:** pt-BR
- **Semântica HTML5:** uso correto de `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`
- **Acessibilidade:** aria-labels, alt em imagens, foco visível, navegação por teclado

### Design System (Variáveis CSS)
```css
:root {
  --color-bg: #020528;
  --color-gradient-start: #000033;
  --color-gradient-end: #04154f;
  --color-primary: #3399ff;
  --color-primary-accent: #4db2ff;
  --color-accent: #ffd447;
  --color-text: #ffffff;
  --color-text-soft: #d2d7e2;
  --radius-sm: 4px;
  --radius-md: 10px;
  --radius-full: 999px;
  --shadow-sm: 0 2px 4px rgba(0,0,0,.2);
  --shadow-md: 0 4px 12px -2px rgba(0,0,0,.4);
  --shadow-glow: 0 0 0 1px rgba(255,255,255,.05), 0 4px 22px -4px rgba(51,153,255,.55);
  --max-width: 1180px;
  --transition: .25s cubic-bezier(.4,.2,.2,1);
}
```

### Background Principal
- Gradiente radial partindo do canto superior esquerdo
- Cores: `#000033` → `#04154f`

---

## 🎨 Seções do Site

### 1. **HEADER (Navegação Fixa)**

**Características:**
- Posição `sticky` no topo
- Backdrop filter com blur (14px) e fundo semi-transparente
- Borda inferior sutil
- Altura mínima: 70px

**Conteúdo:**
- Logo/Brand à esquerda: `<i class="fas fa-code"></i> Nome Dev`
- Navegação à direita com links: Sobre | Projetos | Contato
- Menu mobile (hambúrguer) para telas < 820px

**Comportamento:**
- Links com border-radius completo e fundo ao hover
- Menu mobile dropdown animado (translateY + opacity)
- Botão hambúrguer vira X quando aberto
- Link ativo destacado conforme scroll (JavaScript)

---

### 2. **SEÇÃO SOBRE** (`#about`)

**Layout:**
- Grid responsivo 2 colunas (foto | texto)
- Gap: 3rem entre colunas
- Padding da section: 6rem top, 4rem bottom

**Coluna 1 - Foto:**
- Imagem circular (220px, aspect-ratio 1:1)
- Borda: 3px solid da cor primária
- Box-shadow com glow azul
- Implementar lazy loading progressivo (blur-up):
  - `src`: placeholder 40x40px com blur
  - `data-src`: imagem final 400x400px
  - `data-srcset`: múltiplas resoluções (320w, 400w, 600w, 800w)
  - IntersectionObserver para trocar ao entrar no viewport

**Coluna 2 - Texto:**
- **3 parágrafos** com classe `.intro`:
  - Parágrafo 1: Apresentação (nome, formação, foco técnico)
  - Parágrafo 2: Experiência e áreas de atuação
  - Parágrafo 3: Objetivo profissional
  - Font-size: 1.05rem, color suave, margin-bottom: 1.25em
  - Último parágrafo sem margem inferior

- **Ícones Sociais:**
  - 3 botões circulares (42x42px) com ícones Font Awesome
  - GitHub, LinkedIn, Facebook
  - Fundo com gradient, hover com transform translateY(-3px) e glow
  - Margin: 2rem top, 1.5rem bottom

- **Habilidades:**
  - Título `<h3>` (1.3rem, cor primária)
  - Lista horizontal de chips (pills):
    - 9 tecnologias: Kotlin, Jetpack Compose, JavaScript, Node.js, Next.js, React, Java, C#, Python
    - Padding: .65rem .95rem
    - Gap: .7rem
    - Border-radius completo
    - Fundo gradient sutil, borda ao hover

**Responsividade Mobile (<640px):**
- Padding section reduzido: 4rem top
- Texto: 1rem
- Ícones e chips centralizados
- Título habilidades centralizado

---

### 3. **SEÇÃO PROJETOS** (`#projects`)

**Layout:**
- Grid responsivo: `repeat(auto-fill, minmax(250px, 1fr))`
- Gap: 1.8rem
- Margin-top do grid: 3rem

**Cards de Projeto (6 cards):**
- Background: gradient diagonal (#081238 → #041025)
- Border-radius: 16px
- Padding: 1.4rem 1.35rem 1.5rem
- Gap interno: .9rem
- Estrutura flexbox vertical

**Elementos do Card:**
1. **Imagem (thumb):**
   - Aspect-ratio: 16/10
   - Border-radius: 10px
   - Lazy loading com blur-up (placeholder 32x20, final 640x400 + srcset)

2. **Título:**
   - Font-size: 1.05rem
   - Margin: .4rem 0 .35rem

3. **Descrição:**
   - Font-size: .85rem, color suave
   - Line-height: 1.5
   - Margin-bottom: .6rem

4. **Links (2 botões):**
   - Flex horizontal com gap .75rem
   - Botões com ícones: GitHub | Android/App
   - Padding: .65rem .8rem
   - Text-transform uppercase, letra-spacing .8px

**Hover Card:**
- TranslateY(-6px)
- Border mais clara
- Box-shadow glow
- Overlay radial gradient (opacity 0 → 1)

---

### 4. **SEÇÃO CONTATO** (`#contact`)

**Layout:**
- Grid 2 colunas responsivo: `repeat(auto-fit, minmax(320px, 1fr))`
- Gap: 2.5rem
- Margin-top: 2.8rem

**Coluna 1 - Informações:**
- Background gradient diagonal
- Border-radius: 18px, padding: 2rem 2.2rem 2.4rem
- Efeito radial gradient decorativo (pseudo-elemento :after)

**Conteúdo:**
- Título `<h3>`: "Fale comigo"
- Parágrafo breve (ex: "Aberto a oportunidades...")
- 4 links de contato verticais:
  - WhatsApp (com link `api.whatsapp.com/send?phone=...`)
  - E-mail (`mailto:...`)
  - LinkedIn
  - GitHub
  - Padding: .7rem 1rem, gap .95rem
  - Ícone + texto, hover com fundo e borda primária

**Coluna 2 - Formulário:**
- Background gradient diferente
- Border-radius: 18px, padding: 2rem

**Campos do Formulário:**
- Grid 2 colunas (nome | email)
- Campo assunto (full-width)
- Campo mensagem/textarea (full-width, min-height 160px)
- Honeypot escondido (`_gotcha`) para anti-spam
- Labels uppercase, pequenas (.68rem)
- Inputs com padding: .85rem 1rem
- Focus: borda primária + box-shadow glow

**Botão Enviar:**
- Border-radius completo
- Padding: .85rem 1.4rem
- Gradient background
- Ícone "paper-plane"
- Hover: glow + translateY(-2px)
- Estado disabled: opacity reduzida

**Integração Formspree:**
- Action: `https://formspree.io/f/SEU_ID`
- Method: POST
- JavaScript para envio assíncrono (fetch):
  - Validação de campos obrigatórios
  - Desabilita botão durante envio
  - Texto "Enviando..."
  - Mensagens de sucesso/erro abaixo do botão
  - Reset do form ao sucesso

---

### 5. **FOOTER**

**Estrutura:**
- Background: #030a25
- Border-top sutil
- Padding: 2.5rem 0 2.2rem
- Margin-top: 4rem
- Efeito radial gradient decorativo

**Conteúdo Centralizado:**
- Links de navegação horizontais:
  - Sobre | Projetos | Contato
  - Padding: .65rem 1rem
  - Border-radius completo
  - Gap: 1rem
- Copyright:
  - Font-size: .7rem
  - Ano dinâmico via JavaScript: `new Date().getFullYear()`
  - Margin-top: .4rem

---

## ⚡ JavaScript Funcionalidades

### 1. Ano Dinâmico
```javascript
document.getElementById('year').textContent = new Date().getFullYear();
```

### 2. Menu Mobile
- Toggle classe `.open` na `<ul>`
- Atualizar `aria-expanded`
- Trocar ícone hambúrguer ↔ X
- Fechar menu ao clicar em link interno

### 3. Link Ativo na Navegação
- Observar scroll position
- Detectar seção visível (offset + 140px para compensar header)
- Adicionar classe `.active` no link correspondente

### 4. Lazy Loading Progressivo de Imagens
- Selecionar todas `img[data-src]`
- Criar IntersectionObserver com `rootMargin: 120px`
- Ao entrar no viewport:
  - Trocar `src` por `data-src`
  - Trocar `srcset` por `data-srcset`
  - Adicionar classe `.lazy-loaded` (remove blur)
  - Adicionar classe `.loaded` no wrapper (efeito overlay)
- Fallback para navegadores sem IntersectionObserver

### 5. Formulário Assíncrono
- Prevenir submit padrão
- Validar campos obrigatórios
- Fetch com FormData para endpoint Formspree
- Tratamento de resposta (ok → reset + mensagem sucesso | erro → exibir mensagem)
- Loading state no botão

---

## 🎨 Estilos CSS Detalhados

### Scrollbar Customizada (WebKit)
```css
::-webkit-scrollbar { width: 10px; }
::-webkit-scrollbar-track { background: #060b3d; }
::-webkit-scrollbar-thumb { background: linear-gradient(#3399ff, #1d71b8); border-radius: 8px; }
```

### Efeito Blur-Up (Lazy Images)
```css
.blur-up { filter: blur(18px); transform: scale(1.02); transition: filter .8s, transform .8s; }
.blur-up.lazy-loaded { filter: blur(0); transform: scale(1); }
```

### Navegação Ativa
```css
nav a.active { background: rgba(255,255,255,.08); color: var(--color-text); }
```

### Focus States (Acessibilidade)
```css
a:focus { outline: 2px solid var(--color-primary); outline-offset: 3px; }
```

---

## 📦 Recursos Externos (CDN)

### Fontes
```html
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap" rel="stylesheet" />
```

### Ícones
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" />
```

---

## 🔧 Meta Tags Essenciais

```html
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="Portfólio de [Nome] - Desenvolvimento Mobile e Web (Android, APIs REST, SPA)." />
<title>Portfólio | [Nome]</title>
```

---

## 📱 Breakpoints Responsivos

### Mobile (< 640px)
- Seção Sobre: padding reduzido, texto menor, elementos centralizados
- Formulário: padding reduzido

### Tablet (< 820px)
- Header: menu hambúrguer ativado
- Grid ajusta automaticamente (auto-fit/auto-fill)

### Desktop (> 1180px)
- Container limitado ao max-width
- Layout otimizado

---

## ✅ Checklist de Implementação

### Estrutura
- [ ] DOCTYPE, lang="pt-BR", meta tags
- [ ] Google Fonts e Font Awesome via CDN
- [ ] CSS inline completo com variáveis
- [ ] Semântica HTML5 correta

### Seções
- [ ] Header sticky com navegação
- [ ] Seção Sobre (foto + 3 parágrafos + social + skills)
- [ ] Seção Projetos (6 cards com lazy loading)
- [ ] Seção Contato (info + formulário Formspree)
- [ ] Footer (links + copyright dinâmico)

### Funcionalidades JS
- [ ] Menu mobile toggle
- [ ] Link ativo por scroll
- [ ] Lazy loading de imagens com blur-up
- [ ] Formulário assíncrono com validação
- [ ] Ano dinâmico no footer

### Acessibilidade
- [ ] aria-label, aria-labelledby, aria-expanded
- [ ] Textos alternativos em imagens
- [ ] Focus visível
- [ ] Navegação por teclado funcional

### Performance
- [ ] CSS inline (reduz requisições)
- [ ] Lazy loading com IntersectionObserver
- [ ] `loading="lazy"` e `decoding="async"`
- [ ] Imagens responsivas (srcset + sizes)

### SEO Básico
- [ ] Meta description relevante
- [ ] Headings hierárquicos (h1 > h2 > h3)
- [ ] URLs semânticas (#about, #projects, #contact)
- [ ] Scroll-behavior smooth

---

## 🎯 Conteúdo Placeholder

### Seção Sobre - Exemplo de Texto
```
Sou [Nome], estudante de Ciência da Computação e desenvolvedor mobile nativo e web fullstack. 
Tenho foco em aplicativos Android utilizando Kotlin e Jetpack Compose, além de atuar no 
ecossistema JavaScript/Node.js desenvolvendo APIs, trabalhando com Docker e explorando a 
criação de bots com inteligência artificial.

Tenho experiência com integrações, automações e criação de conteúdo para redes sociais, 
com destaque para plataformas como o Facebook. Atualmente, estou aprofundando estudos 
sobre aplicação de IA no ciclo de desenvolvimento para acelerar processos — inclusive 
este site foi criado com apoio de ferramentas de inteligência artificial.

Meu objetivo é unir criatividade e inovação para transformar ideias em soluções digitais 
práticas, escaláveis e de impacto.
```

### Imagens Placeholder
- Foto perfil: `https://placehold.co/400x400/0b1a4d/ffffff?text=Nome`
- Projetos: `https://placehold.co/640x400/081238/ffffff?text=Projeto+1`

---

## 📝 Observações Finais

1. **Único arquivo:** Todo CSS e JS devem estar inline no `<head>` e antes do `</body>`
2. **Formspree:** Substituir `SEU_ID` por endpoint real após criar conta
3. **Links sociais:** Trocar `href="#"` por URLs reais
4. **Imagens:** Substituir placeholders por assets reais em múltiplas resoluções
5. **Projetos:** Atualizar títulos, descrições e links quando tiver conteúdo
6. **Deploy:** Site funciona abrindo index.html direto no navegador (sem build)

---

## 🚀 Como Usar Este Prompt

**Passo 1:** Copie todo este prompt  
**Passo 2:** Cole em um assistente de IA (ChatGPT, Claude, Copilot, etc.)  
**Passo 3:** Peça: "Crie o arquivo index.html completo seguindo estas especificações"  
**Passo 4:** Revise o código gerado e ajuste conforme necessário  
**Passo 5:** Teste localmente e faça deploy (GitHub Pages, Netlify, Vercel, etc.)

---

**Autor:** Fabrício  
**Data:** 07/10/2025  
**Versão:** 1.0  
**Licença:** Livre para uso e modificação
