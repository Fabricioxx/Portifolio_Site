<div align="center">
  <h1>🌐 Portfólio Pessoal – Fabrício</h1>
  <p>Site estático moderno, responsivo e otimizado com foco em desenvolvimento Mobile (Kotlin / Jetpack Compose) e Web Fullstack.</p>
  <a href="https://fabricioxx.github.io/Portifolio_Site/" target="_blank"><strong>👉 Acessar versão publicada (GitHub Pages)</strong></a>
  <br><br>
  <!-- (Opcional) Adicione aqui um screenshot do portfólio: 
	  <img src="./screenshot.png" alt="Preview do Portfólio" width="820" /> -->
</div>

---

## ✨ Destaques do Projeto

- Layout responsivo (CSS moderno + grid flexível)
- Navegação sticky com menu mobile (hambúrguer)
- Seção Sobre com habilidades destacadas em chips
- Cards de projetos com hover e estrutura semântica (`<article>`)
- Formulário integrado preparado para Formspree (envio assíncrono + validação + honeypot anti-spam)
- Lazy loading + imagens progressivas com efeito blur (IntersectionObserver)
- Acessibilidade: landmarks, `aria-label`, foco visível, contraste adequado
- Ano dinâmico no rodapé via JavaScript
- Código único (todo o CSS incorporado em `index.html` para facilitar deploy simples)

---

## 🧱 Estrutura do Repositório

```
Portifolio_Site/
├── index.html          # Página principal (HTML + CSS inline + JS)
├── README.md           # Este arquivo
└── img/                # Ícones sociais ou futuros assets
```

> Observação: A folha de estilos externa (`css/style.css`) foi removida após a incorporação do CSS diretamente no `index.html`.
> Screenshot removido (arquivo `img_exemplo.png` não faz mais parte do repositório). Se quiser adicionar um preview, salve uma imagem (ex: `screenshot.png`) e insira a tag `<img>` no topo.

---

## 🛠 Tecnologias e Recursos Utilizados

| Área | Tecnologias / Recursos |
|------|------------------------|
| Layout / Estilo | HTML5 semântico, CSS moderno (grid/flex, variáveis CSS, gradients, chips), animações suaves |
| Tipografia | Google Fonts (Open Sans) |
| Ícones | Font Awesome (CDN) |
| Imagens | `data-src` + `data-srcset` + progressive blur-up |
| Acessibilidade | `aria-label`, foco visível, estrutura semântica |
| Formulário | Formulário custom + integração assíncrona com Formspree (substituir endpoint) |
| Otimização | Lazy loading, `decoding="async"`, tamanhos responsivos |
| JavaScript | Navegação ativa, menu mobile, envio AJAX, Observer de imagens |

---

## 🚀 Como Executar Localmente

1. Clone ou baixe este repositório.
2. Abra o arquivo `index.html` diretamente no navegador (duplo clique) OU use uma extensão como “Live Server” no VS Code.
3. Alterações podem ser feitas diretamente em `index.html` e recarregadas.

> Não há dependências, build ou bundlers. É totalmente estático.

---

## 📬 Configurando o Formulário (Formspree)

1. Crie uma conta em https://formspree.io/
2. Gere um formulário e copie o endpoint (ex: `https://formspree.io/f/mxyzabcd`).
3. No `index.html`, localize:
	```html
	<form id="contact-form" action="https://formspree.io/f/SEU_ID" method="POST" novalidate>
	```
4. Substitua `SEU_ID` pelo ID real.
5. (Opcional) Adicione assunto padrão:
	```html
	<input type="hidden" name="_subject" value="Novo contato via Portfólio" />
	```
6. Teste enviando uma mensagem real.

### Sobre o Honeypot
Campo escondido `_gotcha` ajuda a reduzir spam. Bots tendem a preenchê-lo → submissão descartada.

---

## 🖼 Personalizando Imagens

As imagens usam placeholders com blur inicial. Para trocar:

1. Gere versões em múltiplas resoluções (ex: 320, 480, 640, 800).
2. Substitua `data-src` e `data-srcset` mantendo o padrão:
	```html
	<img
	  src="mini-blur-32x20.webp"
	  data-src="imagem-640.webp"
	  data-srcset="imagem-320.webp 320w, imagem-480.webp 480w, imagem-640.webp 640w, imagem-800.webp 800w"
	  sizes="(max-width: 640px) 100vw, (max-width: 1024px) 50vw, 320px"
	  alt="Descrição do projeto"
	  class="project-thumb blur-up progressive-img"
	  loading="lazy"
	  decoding="async" />
	```
3. Atualize o `alt` para algo descritivo (bom para SEO e acessibilidade).

---

## 💡 Editando a Seção Sobre

Busque no `index.html` pela classe `intro`. São parágrafos independentes — você pode adicionar:
* Semestre ou instituição (ex: “7º semestre em Ciência da Computação – Universidade X”) 
* Interesses atuais (ex: “Estudando IA aplicada a automação de pipelines”) 
* Links para CV ou LinkedIn.

Exemplo de botão (adicione abaixo dos parágrafos):
```html
<p><a href="link-do-cv.pdf" class="btn-icon" style="max-width:200px;">Download CV</a></p>
```

---

## 🧩 Adicionando Novos Projetos

Copie um bloco `<article class="project-card">` dentro da seção de projetos e ajuste:
* Título (`<h3>`)
* Descrição (`.project-desc`)
* Links (GitHub, deploy, build mobile, etc.)
* Imagem (`img` com novos `data-src` / `data-srcset`)

Sugestões de novos botões:
```html
<a class="btn-icon" href="#" aria-label="Demo online"><i class="fas fa-external-link-alt"></i> Demo</a>
<a class="btn-icon" href="#" aria-label="Documentação"><i class="fas fa-book"></i> Docs</a>
```

---

## 🔒 Acessibilidade e Boas Práticas

Implementado:
* Uso de `aria-label` em navegação e áreas funcionais.
* Botões com `aria-expanded` no menu mobile.
* Texto alternativo em imagens.
* Foco visível e contraste adequado.

Possíveis incrementos futuros:
* `prefers-reduced-motion` para reduzir animações.
* Tema claro/escuro automático.
* Skip link (pular para conteúdo principal).

---

## 🌍 Deploy com GitHub Pages

1. Vá em Settings > Pages.
2. Selecione a branch `main` e root (`/`).
3. Salve e aguarde a publicação em: `https://<seu-usuario>.github.io/Portifolio_Site/`

> Se mudar o nome do repositório, o link também muda.

### Deploy alternativo
Pode ser hospedado em: Netlify, Vercel, Cloudflare Pages ou qualquer serviço de host estático.

---

## 🧪 Testes Básicos Manuais

Checklist rápido após editar:
| Item | Verificar |
|------|-----------|
| Navegação | Menu mobile abre/fecha? Links rolam corretamente? |
| Formulário | Envia e mostra mensagem de sucesso/erro? |
| Imagens | Trocam do blur para versão final ao rolar? |
| Acessibilidade | Tab navega em ordem lógica? Foco visível? |
| Responsividade | Testar em 360px, 768px, 1024px e >1280px |

---

## 🗺 Roadmap (Ideias Futuras)

- [ ] Multi-idioma (pt-BR / en-US)
- [ ] Dark/Light mode com toggle
- [ ] Animações de entrada (IntersectionObserver + classes)
- [ ] Consumir lista de projetos via JSON externo ou GitHub API
- [ ] Adicionar badge de status de build (caso futuramente use pipeline)
- [ ] Integração com serviço de analytics leve (ex: Plausible)

---

## 🙋🏻‍♂️ Sobre

Desenvolvido por Fabrício – estudante de Ciência da Computação e desenvolvedor mobile/web. Focado em Kotlin, Jetpack Compose, Node.js, Next.js e integração de soluções com IA.

Se este template ajudou você, considere deixar uma estrela ⭐ no repositório.

---

## 📄 Licença

Você pode usar este código livremente para estudo e personalização do seu próprio portfólio. (Se quiser adotar uma licença formal, adicione um arquivo `LICENSE` — ex: MIT.)

---

### 🔗 Links Relacionados

- GitHub Pages: https://pages.github.com/
- Formspree: https://formspree.io/
- Font Awesome: https://fontawesome.com/
- Google Fonts: https://fonts.google.com/

---

> Última atualização: automatizada via assistente em {{DATA_ATUALIZE_MANUALMENTE}}

