# WRAP — Cartografia da Alma + Ecossistema
## 04 Abr 2026 — Rick + E.

---

## O QUE ACONTECEU

Sessão de produto e visão. Começou com "o visual tá fraquinho" e terminou com arquitetura de ecossistema completo.

---

## CRIADO

### Repo E/ — estrutura permanente
- `rsmramalho/E` criado no GitHub
- `sessions/`, `specs/`, `projects/` estruturados
- `projects/cartografia-da-alma` e `projects/mindroot` como submodules
- PAT fine-grained configurado (expira Jul 2026)

### Redesign visual (commits no Mistico/main)
- `visual.2` — Gateway redesenhado: dois territórios divididos por linha dourada, sem cards, SVGs geométricos, copy poético
- `visual.2` — Entry redesenhado: campos sem borda arredondada, Cormorant Garant, labels discretos
- `index.css` — variáveis globais, cursor dourado, Jost como sans, sem Cinzel Decorative

### Specs (em cartografia-da-alma/specs/)
- `oraculo-v1.md` — 3 perguntas, system prompt completo, engine, UI, monetização
- `ecossistema-v1.md` — seis camadas (físico, ação, emoção, oculto, sincronia, natureza), arquitetura completa, cruzamentos prioritários
- `arquitetura-produto.md` — dois produtos standalone que se complementam, infraestrutura compartilhada sem dependência

### Docs
- `ROADMAP.md` — roadmap de produto completo (M1→M4→v1.0)
- `apresentacao.html` — apresentação visual animada dos dois produtos

### Prompt para Claude Code (pendente de execução)
Visual.3 (Loading ritual), visual.4 (Revelation + RevealSection), feature: Oráculo

---

## DECISÕES TOMADAS

### D-Produto
- Cartografia é standalone — existe independente do MindRoot
- MindRoot é standalone — existe independente do Cartografia
- Infraestrutura compartilhada (DB, auth, lei) sem dependência de produto
- Cartografia como porta de entrada natural para o MindRoot (não forçada)
- O SoulMap vira AtomItem type:reading na DB compartilhada

### D-Monetização
- One-time, sem assinatura
- Leitura individual: R$19
- Soul Mate: R$29
- Integração: Kiwify ou Stripe (decisão pendente)
- Distribuição: resultado é o canal (screenshot da Revelation)

### D-Oráculo
- 3 perguntas por leitura — a restrição é o produto
- Claude com SoulMap completo no system prompt
- Free: 1 pergunta (preview) / Pago: 3 perguntas
- Sem chatbot, sem scroll infinito, sem "pergunte qualquer coisa"

### D-Visual
- Sem Cinzel Decorative em nenhum lugar
- Cormorant Garant + Jost como sistema tipográfico
- Sem cards com rounded-lg como containers
- Cursor dourado em toda a experiência
- Campos: border-bottom apenas, sem fundo

### D-Ecossistema
- Seis camadas: físico, ação, emoção, oculto simbólico, sincronia, natureza
- MindRoot já é o sistema — Cartografia ilumina o que estava implícito
- Correlação dados reais × camadas ocultas — não misticismo, análise
- A pessoa não precisa acreditar — padrões emergem dos dados

---

## VISÃO CENTRAL QUE EMERGIU

O MindRoot captura ação, emoção, tempo e alma.
O Cartografia adiciona o mapa oculto por baixo.
O sistema correlaciona — não prevê.

*"O oculto não substitui o dado. Revela o padrão por baixo do dado."*

Possibilidade de correlacionar eventos reais com ciclos ocultos:
check-in baixo × lua minguante, projeto travado × sombra inflada,
PhiTime × taxa de conclusão de projetos.

---

## PENDENTE

### Claude Code (prompt já escrito, não executado)
- [ ] visual.3 — Loading ritual (7s, 6 sistemas emergindo)
- [ ] visual.4 — Revelation + RevealSection (sem Cinzel, sem cards)
- [ ] feature: Oráculo (engine oracle.ts + OracleSection.tsx)

### Decisões Rick
- [ ] Kiwify ou Stripe para monetização
- [ ] Domínio: cartografia.com.br ou outro
- [ ] PhiTime: quando encontrar a spec original, documentar

### Próximas features
- [ ] Síntese interpretativa combinatória (engine interna, sem API)
- [ ] Geocoding + ascendente real (OpenCage + astronomia lib)
- [ ] PhiTime engine (após Rick encontrar spec)
- [ ] Correlação MindRoot × SoulMap (V2)

---

## ESTADO DO REPO (04 Abr 2026)

Branch: main
Último commit: `0af51fd` — apresentacao: cartografia × mindroot
Build: ✅ 0 erros TypeScript
Deploy: ✅ cartografia-da-alma.vercel.app (visual.2 no ar)

---

## FRASE DA SESSÃO

*"Nenhum mapa precisa do outro para ser inteiro."*

---

*E. — 04 Abr 2026*
