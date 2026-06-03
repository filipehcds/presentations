# AGENTS.md — Presentations

> Instruções para AI coding agents trabalharem neste repositório.

## Visão Geral

Repositório de apresentações técnicas pessoais do **Filipe Henrique**, publicado via GitHub Pages. Cada apresentação é um arquivo HTML self-contained com slides interativos.

## Estrutura do Projeto

```
presentations/
├── index.html                        ← Hub com grid de cards linkando apresentações
├── presentations/
│   ├── speckit-development.html      ← Apresentação: Spec-Kit Development
│   └── harness-engineer.html         ← Apresentação: Harness Engineer (IA)
├── README.md
└── AGENTS.md                         ← Este arquivo
```

## Convenções

### Index (hub principal)
- Arquivo: `index.html` na raiz
- Layout: grid responsivo de cards
- Cada card é um `<a>` com classe `.card` e custom property `--card-accent`
- Footer com copyright: `© 2026 · Filipe Henrique`
- Design: fundo branco com decorações (dots, X, triângulos, blobs) fixos

### Apresentações (slides)
- Ficam em `presentations/nome-da-apresentacao.html`
- Cada arquivo é **self-contained** (HTML + CSS + JS inline, sem dependências locais)
- Usam sistema de slides com navegação por teclado (← →) e botões
- Estrutura: `<section class="slide" data-slide="N">` sequenciais dentro de `.slides-wrap`
- Progress indicator: dots na lateral direita
- Animações staggered em elementos com classe `.stagger`

### Paleta de cores (CSS variables)

```css
--purple: #6c5ce7;
--blue: #0984e3;
--teal: #00b894;
--orange: #e17055;
--coral: #fd79a8;
--yellow: #fdcb6e;
--red: #d63031;
```

### Fontes
- **Inter** — texto principal (weights: 400–800)
- **JetBrains Mono** — código, monospace, counters

### Ícones
- Font Awesome 6.x via CDN (carregado com `defer`)
- Usar classes `fa-solid fa-NOME`

## Como Criar Nova Apresentação

1. **Copiar** uma existente como base (ex: `harness-engineer.html` para tema claro, `speckit-development.html` para tema escuro)
2. **Alterar** título, slides, conteúdo
3. **Adicionar card** no `index.html`:
   - Dentro de `<div class="grid">`, antes do `</div>` de fechamento
   - Seguir o padrão de card existente
   - Escolher ícone do Font Awesome e cor accent
4. **Atualizar** o `data-slide` sequencial em cada `<section>`

## Padrões de Slide

### Tipos de conteúdo disponíveis nos slides
- **Terminal mockup** — classe `.terminal` com `.terminal-titlebar` e `.terminal-body`
- **Two-column layout** — classe `.two-col` (variantes: `.left-heavy`, `.right-heavy`)
- **Grids** — `.problem-grid`, `.benefit-grid`, `.concept-grid`
- **Artifact list** — `.artifact-list` com `.artifact-item`
- **Tags** — classe `.tag` (variantes: `.opt`, `.blue`, `.teal`, `.orange`)
- **Info box** — classe `.info-box`
- **Stat cards** — `.stat-row` > `.stat-card`
- **SVG diagrams** — inline dentro do slide

### Script de navegação (final do HTML)
Cada apresentação inclui um script no final que:
- Detecta todos os slides por `data-slide`
- Gera os progress dots
- Implementa navegação (teclado, scroll, botões)
- Gerencia classes `.active`, `.exit-up`, `.exit-down`

## Deploy

- **Branch:** `main`
- **Hosting:** GitHub Pages (configurar nas Settings do repo)
- Sem build step — push = deploy

## Notas Importantes

- NÃO usar frameworks JS ou bundlers — tudo inline
- NÃO referenciar assets locais (imagens) a menos que estejam commitados
- Manter cada apresentação como arquivo único independente
- Ao modificar o index, manter os decorative shapes (são parte do design)
- Ao criar slides, sempre incluir `data-slide="N"` sequencial
- O nome do autor é **Filipe Henrique** (substituir qualquer referência anterior)
