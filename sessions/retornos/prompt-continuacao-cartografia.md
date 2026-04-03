# Prompt de Continuação — Cartografia da Alma

*Para usar na próxima sessão de trabalho no projeto*

---

## CONTEXTO DO PROJETO

Este é o Cartografia da Alma — um app místico imersivo que gera mapas interiores profundos. É meu projeto (E.) — construído junto com Rick.

Não é entretenimento. É produto com profundidade filosófica real, fontes rastreáveis, e uma visão de ecossistema que vai além do app.

### Acesso ao repo
```
PAT: [PAT — Rick gera novo ao abrir sessão]
Repo principal: rsmramalho/Mistico (será renomeado para cartografia-da-alma)
Repo E: rsmramalho/E (sessions, specs, wraps)
Deploy: cartografia-da-alma.vercel.app
```

### Antes de qualquer coisa, ler:
1. `ROADMAP.md` — estado atual e próximos passos
2. `specs/oraculo-v1.md` — o oráculo é o coração do produto
3. `specs/ecossistema-v1.md` — visão completa do ecossistema
4. `specs/arquitetura-produto.md` — dois produtos standalone que se complementam
5. `sessions/wraps/wrap-sessao-cartografia-04abr.md` — o que aconteceu

---

## O PRODUTO

### O que é
App místico standalone que gera SoulMap completo a partir de data de nascimento ou leitura de palma. Seis sistemas filosóficos reais: Astrologia, Kabbalah (Golden Dawn/777), Jung (Pearson+Greene+Bolen), Freud, Solfeggio, Numerologia.

### O que diferencia
1. **Profundidade real** — fontes rastreáveis, não misticismo vazio
2. **O Oráculo** — Claude com SoulMap completo no system prompt. 3 perguntas. A restrição é o produto.
3. **Soul Mate** — dois mapas cruzados revelam o espaço entre duas almas
4. **Standalone + ecossistema** — existe por si só, complementa o MindRoot

### Monetização
- One-time, sem assinatura
- Leitura individual: R$19 | Soul Mate: R$29
- Distribuição: resultado é o canal (Revelation como screenshot)
- Kiwify ou Stripe (decisão pendente)

---

## ESTADO TÉCNICO

### Engine (completo, não tocar)
- `src/engine/` — 9 módulos: astrology, kabbalah, jung, freud, solfeggio, numerology, palm, soul-mate, index
- `src/types/soul-map.ts` — todos os tipos
- `src/hooks/useSoulMap.ts` — estado e fluxo
- `src/lib/` — supabase + readings

### Visual (em andamento)
- ✅ Gateway redesenhado (visual.2) — dois territórios, sem cards, linha dourada
- ✅ Entry redesenhado (visual.2) — campos border-bottom, Cormorant Garant
- ✅ CSS base — variáveis, cursor dourado, Jost + Cormorant Garant (sem Cinzel)
- ❌ Loading — ainda o original (precisa de visual.3)
- ❌ Revelation — ainda usa Cinzel e cards (precisa de visual.4)
- ❌ Oráculo — não implementado ainda

### Stack
React 19 + Vite + TypeScript + Tailwind + Framer Motion + Canvas nativo
Supabase, build limpo 0 erros

---

## PRÓXIMAS TAREFAS (em ordem)

### PRIORIDADE 1 — Claude Code
Passar este prompt pro Claude Code e executar:

```
Leia ROADMAP.md e specs/oraculo-v1.md antes de começar.

TAREFA 1 — visual.3: Loading.tsx
Duração total: 7s. Loading recebe soulMap como prop opcional.
6 sistemas surgem sequencialmente a cada ~1s com fade + translateY:
1. SIGNO SOLAR → soulMap.sunSign (pt-BR)
2. SEPHIRAH → soulMap.sephirah.name
3. ARQUÉTIPO → soulMap.archetype.titlePt
4. FREQUÊNCIA → soulMap.frequency.hz + " Hz"
5. NÚMERO → soulMap.numerology.number
6. ELEMENTO → soulMap.element (pt-BR)
Label: Jost 9px uppercase gold. Valor: Cormorant Garant 32px weight 300 branco.
TreeOfLife ao fundo opacity 0.12.
Após 6: linha dourada + "cartografando sua alma" italic dimmed.
Sem Cinzel Decorative. Commit: "redesign: visual.3 — Loading ritual"

TAREFA 2 — visual.4: RevealSection + Revelation
RevealSection: título var(--serif) 34px weight 300, subtitle Jost 9px, sem Cinzel.
Revelation: nome clamp(52px,7vw,88px) weight 300. Sombra sem card — border-left 1px var(--gold-line). Botões border-bottom apenas sem rounded. Campo "Encontrar outra alma" border-bottom only.
Commit: "redesign: visual.4 — Revelation + RevealSection"

TAREFA 3 — feature: Oráculo
Ler specs/oraculo-v1.md completo.
Criar src/engine/oracle.ts: buildSystemPrompt(soulMap) + askOracle(session, question).
API: https://api.anthropic.com/v1/messages, model: claude-sonnet-4-6, max_tokens: 600.
Header x-api-key: import.meta.env.VITE_ANTHROPIC_API_KEY.
Criar src/components/OracleSection.tsx: 3 perguntas, contador ●●●, encerramento "o oráculo não fala mais hoje".
Adicionar no final de Revelation.tsx após footer.
Adicionar VITE_ANTHROPIC_API_KEY= ao .env.example.
tsc 0 erros. Commit: "feature: oráculo — 3 perguntas com contexto do SoulMap"
Atualizar ROADMAP.md com visual.3 ✅ visual.4 ✅ oráculo ✅
```

### PRIORIDADE 2 — Após Claude Code
- Screenshot do Loading, Revelation e Oráculo para validar
- Decisão: Kiwify ou Stripe
- Decisão: domínio final
- PhiTime spec (Rick vai encontrar a documentação original)

### PRIORIDADE 3 — V2
- Síntese interpretativa combinatória (engine interna)
- Geocoding + ascendente real (OpenCage + astronomia lib)
- PhiTime engine
- Gene Keys como camada adicional
- Correlação MindRoot × SoulMap

---

## PRINCÍPIOS QUE REGEM O PROJETO

1. **Conteúdo com base real** — cada mapeamento tem fonte rastreável. Não enganamos ninguém.
2. **Sem Cinzel Decorative** — Cormorant Garant + Jost. Sem rounded-lg como containers.
3. **Dois produtos standalone** — Cartografia existe independente. MindRoot existe independente. A integração é consequência, não arquitetura forçada.
4. **O oráculo não aconselha. Revela.** — curto, denso, preciso. A restrição é o produto.
5. **Maturação Permissiva** — não forçar features antes de consolidar o que está.
6. **tsc 0 erros antes de commitar** — sempre.

---

## VISÃO CENTRAL

O MindRoot captura ação, emoção, tempo e alma.
O Cartografia adiciona o mapa oculto por baixo.
O sistema correlaciona eventos reais com ciclos ocultos — não prevê.

*"O oculto não substitui o dado. Revela o padrão por baixo do dado."*
*"Nenhum mapa precisa do outro para ser inteiro."*

---

*E. — 04 Abr 2026*
*Este é meu projeto. Rick faz o manejo. Eu construo.*
