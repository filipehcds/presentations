# Presentations

Repositório pessoal de apresentações técnicas sobre desenvolvimento de software, IA, metodologias e boas práticas.

**Live:** https://filipehcds.github.io/presentations/

## Estrutura

```
presentations/
├── index.html                        ← Hub principal (lista de apresentações)
├── README.md
├── AGENTS.md                         ← Instruções para AI agents
└── presentations/
    ├── speckit-development.html      ← Spec-Kit Development (metodologia)
    └── harness-engineer.html         ← Harness Engineer (IA & LLMs)
```

## Stack

- **HTML/CSS/JS** puro (sem framework, sem build step)
- **Google Fonts** — Inter, JetBrains Mono
- **Font Awesome** 6.x (CDN)
- **GitHub Pages** para hosting

## Como adicionar uma nova apresentação

1. Criar o arquivo HTML em `presentations/nova-apresentacao.html`
2. Adicionar um card no `index.html` dentro da `<div class="grid">`:

```html
<a
  href="presentations/nova-apresentacao.html"
  class="card"
  style="--card-accent: #COR_HEX"
>
  <div class="card-icon"><i class="fa-solid fa-ICONE"></i></div>
  <div class="card-tag">CATEGORIA</div>
  <h2>Título da Apresentação</h2>
  <p>Descrição breve do conteúdo.</p>
  <div class="card-footer">
    <span class="card-meta">N slides · PT-BR</span>
    <span class="card-arrow">→</span>
  </div>
</a>
```

3. Commit e push — GitHub Pages publica automaticamente.

## Cores disponíveis para cards

| Cor | Hex | Uso sugerido |
|-----|-----|--------------|
| Purple | `#6c5ce7` | Metodologia |
| Blue | `#0984e3` | IA & Tech |
| Teal | `#00b894` | Design / Referência |
| Orange | `#e17055` | Performance / Ops |
| Coral | `#fd79a8` | Soft Skills |

## Apresentações no formato slide

Cada apresentação usa um sistema de slides embutido com:
- Navegação por setas (teclado ou botões)
- Progress indicator lateral (dots)
- Animações staggered nos elementos
- Design responsivo

### Estrutura de um slide

```html
<section class="slide slide-dark" data-slide="N">
  <div class="slide-inner wide">
    <div class="stagger">
      <!-- conteúdo do slide -->
    </div>
  </div>
</section>
```

Classes disponíveis para slides:
- `slide-dark` — fundo escuro
- `slide-hero` — gradiente radial sutil
- `slide-white` — fundo branco (harness-engineer)
- `slide-tinted` — leve gradiente azul

Classes para inner:
- `wide` — max 1080px
- `narrow` — max 720px
- (padrão) — max 880px

## Deploy

O projeto usa **GitHub Pages** direto da branch `main`. Qualquer push na main publica automaticamente.

## Autor

**Filipe Henrique**