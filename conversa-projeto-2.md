# Conversa — Projeto 2: TransLogística Brasil S.A.

> Histórico da sessão de desenvolvimento do **mapa mental interativo** do estudo de caso TransLogística.

---

## Resumo do projeto

Site single-page (HTML + CSS + JS puro) apresentando um **mapa mental interativo** do estudo de caso "TransLogística Brasil S.A." — empresa brasileira de logística e distribuição.

**Estrutura:**
- Header com h1 + subtítulo
- **Visão geral**: 4 stat-cards (22 anos, 1.800 clientes, 2.200 pedidos/dia, 15.000 t/mês)
- **Mapa mental**: nó central "TransLogística Brasil S.A." + 6 ramificações clicáveis
- **Painéis de detalhes** expansíveis (accordion) com conteúdo de cada tópico
- **Fluxo de processos** horizontal com 8 etapas + setas
- Footer com créditos

**As 6 ramificações:**
1. **Empresa e Unidades** — Matriz SP + Recife + Uberlândia + Joinville
2. **Estratégia** — Missão, Visão, Valores
3. **Infraestrutura de TI** — Data center, servidores, VPN, links, backups
4. **Sistemas** — ERP LogSys v4.2, WMS (3 diferentes), SFA
5. **Processos** — Fluxo do pedido em 8 etapas
6. **Problemas** — Gargalos identificados (WMS isolado, processos manuais, etc.)

---

## Stack

- HTML estático + CSS inline + JS vanilla
- Fontes: Inter (texto) + JetBrains Mono (técnico) via Google Fonts
- Sem dependências externas
- Responsivo (desktop + mobile)
- Zoom desativado (viewport)

---

## Arquivos

- `index.html` — aplicação completa
- `conversa.md` — este arquivo

---

## Estado final

### Visual
- **Tema dark** (background `#0e1014`, off-white escuro)
- **Accent âmbar** `#fbbf24` (substituiu indigo no redesign final)
- Tons neutros: cinza-azulado escuro, off-white
- Tipografia: Inter 500/600 (títulos) + JetBrains Mono (técnico)
- Border-radius: 6-8px (clean)
- Sombras sutis, sem glow/gradientes
- Espaçamento generoso (sections com 72px)

### Interatividade
- **Click em cada card** expande painel de detalhes logo abaixo
- Painel é movido dinamicamente no DOM (`insertAfter` no card clicado)
- Ao fechar, painel volta pro container original
- Scroll suave até o painel aberto
- Hover: borda mais forte + sombra leve
- No mobile: grid vira lista vertical, fluxo vira empilhado, SVG das conexões some

### Estrutura HTML
```
header (h1 + subtitle)
section#overview (4 stat-cards)
section#mindmap
  .container
    .section-header
    h2
    .mindmap-wrapper
      .mindmap-svg (linhas decorativas - some no mobile)
      .mindmap-grid (3x3 com nó central)
        6 .branch-node (cards)
        1 .center-node
      .details-panel (display: contents)
        6 .detail-card (movidos dinamicamente)
section#fluxo (8 etapas do pedido)
footer
```

### Mudanças cronológicas nesta sessão

1. **Criação do projeto 2** — mapa mental completo, paleta azul-petróleo + dourado (era serifa)
2. **Redesign 1** — off-white + azul-petróleo sóbrio, removida Source Serif
3. **Redesign 2** — mais clean, pesos de fonte mais contidos
4. **Header centralizado** — badges viraram texto mono (depois removidas)
5. **Troca de paleta** — dark + indigo
6. **Troca de accent** — indigo → âmbar
7. **Header final** — só h1 + subtítulo, sem metadados
8. **Expansão do mapa** — painéis agora aparecem logo abaixo do card clicado (via JS DOM move)

---

## Issues conhecidos

- O `.details-panel` tem `display: contents` — funciona, mas é um pouco não-ortodoxo
- O SVG das conexões tem viewBox `0 0 1200 640` hard-coded — funciona com `preserveAspectRatio="none"` mas não é responsivo perfeito
- No mobile extremo (< 480px) o grid 1-coluna fica bom mas pode ter altura desigual

---

## Próximos passos sugeridos

- [ ] Subir pro GitHub
- [ ] Adicionar atalho de teclado (Esc fecha painel)
- [ ] Adicionar indicador visual de "qual card está aberto" no mapa mesmo (linha destacada)

---

## Créditos

- Roberivan Santos
- Leonardo Mello
- Vinícius Baron
- Victor Hugo
- Cristiano Silva
- Kevin (Xuewei Zhan)
