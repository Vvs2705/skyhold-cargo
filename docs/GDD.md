> **Revisão 2026-10-09 (comparativo de mercado):** o Skyhold Cargo foi comparado com 8 similares reais de 2025–2026 (tabela, matriz de recursos, reclamações e fontes em [`COMPETITIVO.md`](COMPETITIVO.md)). O que mudou neste GDD:
> 1. **Core re-especificado (§2.1):** vista de cima, porão com a silhueta do avião, **fila visível de 3 cargas** e **doca de espera de 3 vagas**; carga encaixada trava; perde quando a doca está cheia e a carga da frente não cabe. Isso cria a falha que faltava (antes o jogador ficava travado, não derrotado) e dá gatilho ao rewarded.
> 2. **Regras cortadas (§2, §3):** de 7 propriedades por carga para **1 no MVP** (cor de destino = zona da porta). Peso vira **selo opcional de voo estável** (o avião inclina na decolagem), nunca falha. Frágil, temperatura, perigo e orientação saem do MVP: não leem em 3 s e pediam vista lateral com gravidade.
> 3. **Frota com função (§5, §6):** cada aeronave nova é um **porão de formato novo** (capítulo de conteúdo), destravado por estrelas; pintura é cosmético. Nada de "avião maior facilita", que seria pagar para ganhar.
> 4. **Economia (§6, §7):** 1 moeda (Créditos) no MVP, Tickets fora; interstitial desligado na v0.1; nada aleatório pago; recompensa com id de transação.
> 5. **KPIs e kill criteria recalibrados (§15.1, §26):** D1 ≥ 26%, D7 ≥ 5%, coorte de 1,5–2 mil installs, cancelar só após 2 iterações; CPI-alvo US$0,65 (cancelar acima de US$1,30 em 8 criativos).
> 6. **Novas seções no fim:** §27 Diferenciais competitivos (6 propostas, 3 recomendadas) e §28 Plano de validação. Nenhuma seção foi renumerada ou apagada; texto superado ficou ~~riscado~~.
> 7. **Risco de nome:** "Skyhold" é a fortaleza central de *Dragon Age: Inquisition* (EA/BioWare) e um salão de classe de *World of Warcraft* (Blizzard). Não há app com esse nome nas lojas, mas a busca é dominada por esses jogos (ASO ruim) e a marca não foi checada no INPI/USPTO. Trocar o nome antes de qualquer página de loja (§25).

# GDD 02 — SKYHOLD CARGO
## Hybrid-casual Spatial Puzzle / Portrait / Android + iOS

> **Hipótese comercial:** um puzzle espacial de “cabe/não cabe” com leitura instantânea pode produzir criativos fortes e retenção por dificuldade crescente, sem exigir o custo de conteúdo narrativo de um Merge.

# 1. VISÃO DO PRODUTO

**Nome provisório:** Skyhold Cargo  
**Gênero:** Hybrid-casual spatial puzzle / packing / logic  
**Plataforma:** Android primeiro; iOS após validação.  
**Orientação:** Portrait.  
**Público:** 16–55+, jogadores de block puzzle, organização, packing, sorting e casual logic.  
**Proposta de valor:** organizar cargas dentro de aeronaves de formatos diferentes, respeitando peso, fragilidade e ordem de descarregamento.  
**Diferencial:** o puzzle não é só preencher espaço; a carga possui propriedades e destino.  
**Diferencial (revisão 2026-10-09):** "cabe ou não cabe" é o gancho, e é o que se lê em 3 s. As propriedades viram uma só (destino por cor). O que nos separa dos block puzzles: **fila justa e visível** (toda sequência provada solúvel, sem peça "impossível" por sorte), **porão com a forma do avião** e **cargas que são objetos reais com uma pequena história por contrato**. Ver §27.  
**Fantasy:** comandar uma companhia de carga aérea fantástica.  
**Referências funcionais:** block puzzles, parking/packing puzzles e jogos de organização visual, sem copiar level design ou UI.  
**Concorrentes diretos (revisão 2026-10-09):** Block Blast! (o hábito do gênero), Blockudoku, Color Block Jam (porta da cor), Bus Escape/Bus Jam (doca de espera), Fill the Fridge! e Unpacking (objetos reais), Cargo Jam e Cargo Sort Airlift (tema de carga/avião). Comparativo em `COMPETITIVO.md`.

# 2. GAMEPLAY

## Core mechanic
O jogador arrasta caixas/pacotes com formas variadas para a malha do porão da aeronave.

Cada carga pode ter:
- formato;
- peso; *(revisão: só como selo opcional de equilíbrio)*
- destino;
- ~~fragilidade;~~ (fora do MVP)
- ~~temperatura;~~ (fora do MVP)
- ~~perigo;~~ (fora do MVP)
- ~~orientação permitida.~~ (fora do MVP)

O avião possui:
- capacidade espacial;
- centro de massa simplificado; *(revisão: só para o selo de voo estável)*
- portas de acesso; *(revisão: cada porta tem uma cor = zona de destino)*
- ~~zonas especiais.~~ (fora do MVP)

## 2.1 Core vigente (revisão 2026-10-09)

Re-especificação proposta pela validação (raia B, plano B do puzzle) e adotada aqui. Status: **PROPOSTO**, a provar no greybox.

- **Porão:** grade vista de cima, 3×3 a 7×9, recortada na **silhueta da aeronave** (nariz afinando, caixa da asa). Câmera fixa, retrato.
- **Cargas:** poliominós de 1 a 5 células, desenhados como **objetos reais** (mala, estojo de violão, prancha, pneu, caixa de geladeira). A forma do objeto é a forma da peça.
- **Fila visível de 3:** as próximas 3 cargas aparecem na esteira. O jogador arrasta a da frente para o porão (snap na grade; toque gira 90°) ou para a **doca de espera**.
- **Doca de 3 vagas:** guarda carga para depois; carga da doca pode ser usada a qualquer momento.
- **Carga encaixada trava.** É isso que cria a decisão ("guardo ou encaixo agora?").
- **Vitória:** todas as cargas do contrato a bordo. O gerador garante que elas preenchem exatamente o porão ("encaixe perfeito").
- **Falha:** a carga da frente não cabe em nenhum espaço livre **e** a doca está cheia. O porão esvazia, a tentativa conta (3 tentativas por contrato, como no núcleo de puzzle do estúdio).
- **Destino (a 1 propriedade do MVP, a partir do nível 8):** cada porta tem uma cor e uma zona pintada no piso; carga daquela cor só encaixa na zona dela. Leitura: "o vermelho sai pela porta vermelha".
- **Peso (selo opcional, a partir do nível 7):** algumas cargas têm o ícone "pesada". Na decolagem, se o centro de massa ficar fora da faixa da asa, o avião **inclina** (animação, sem falha) e o contrato não ganha o selo de voo estável.
- **Estrelas:** 3★ na 1ª tentativa, 2★ na 2ª, 1★ na 3ª ou depois. O contador **persiste** até a vitória (recomeçar não devolve as 3★; o exploit foi achado no protótipo do núcleo e não deve nascer aqui).
- **Sem RNG:** a fila de cada contrato é fixa e provada solúvel pelo solver antes de entrar no build.

## Core loop
`inspecionar → encaixar → reorganizar → validar → decolar → entregar → melhorar frota → novo contrato`

## Controles
- drag: mover carga; *(revisão: a peça sobe ~1,5 célula acima do dedo para não ficar escondida; snap ao soltar)*
- tap: rotacionar quando permitido;
- ~~hold: detalhes;~~ (sem propriedades para detalhar no MVP)
- pinch não necessário.

## Vitória
Todas as cargas obrigatórias cabem, peso fica dentro do limite e restrições não são violadas.

## Derrota
~~Não há fail instantâneo na maior parte dos níveis; o jogador simplesmente não consegue confirmar o embarque.~~ *(Revisão 2026-10-09: travar sem perder frustra e não abre momento de revive. Falha vigente: doca cheia e a carga da frente não cabe; ver §2.1.)* Em níveis/eventos especiais:
- tempo;
- espaço bloqueado;
- sequência de portos.

## Sessão típica
4–8 minutos, 3–7 contratos.

# 3. PRIMEIROS 10 MINUTOS

**0:00–0:40** — pequena aeronave, três caixas simples. Tutorial por mão fantasma. Vitória em <30 s.

**0:40–1:30** — nível 2 introduz rotação. Primeiro “snap” satisfatório.

**1:30–2:20** — nível 3 mostra caixa em L; solução visual óbvia após pequena tentativa.

**2:20–3:10** — entrega animada; jogador recebe moedas e pinta a primeira aeronave.

**3:10–4:00** — nível 4 introduz “frágil: não empilhar peso acima”.

**4:00–5:00** — nível 5 introduz duas portas de destino; carga de Porto B não pode bloquear Porto A.

**5:00–6:00** — primeira falha natural; aparece hint gratuito contextual.

**6:00–7:00** — nível 6: porão maior, combinação de regras.

**7:00–8:00** — meta: hangar abre segundo slot de aeronave futura.

**8:00–9:00** — nível 7 oferece rewarded opcional para “remover uma carga extra” após o jogador tentar duas vezes.

**9:00–10:00** — nível 8 termina com decolagem mais espetacular; missão diária desbloqueada.

> **Revisão 2026-10-09:** o roteiro acima punha "frágil" no nível 4 e duas portas no nível 5, regra demais em 2 minutos. Curva proposta para o core vigente (§2.1), no mesmo formato do núcleo de puzzle já provado:

| Nv | Porão | Cargas | Ensina | Tempo-alvo | Falha-alvo |
|---|---|---|---|---|---|
| 1 | 3×3 | 3 | arrastar → encaixa (mão fantasma) | ≤ 20 s | < 5% |
| 2 | 3×4 | 4 | tocar gira a carga | 30 s | < 5% |
| 3 | 4×4 | 5 (uma em L) | "parece não caber" → girar | 40 s | < 10% |
| 4 | 4×5 | 6 | a doca aparece: guardar a carga que ainda não cabe | 50 s | < 10% |
| 5 | 4×5 | 7 | 1ª falha controlada: a ordem enche a doca | 60 s | 30–50% (desenhada) |
| 6 | 5×5 com nariz | 7 | porão irregular (silhueta) | 60 s | < 15% |
| 7 | 5×6 | 8 (1 pesada) | selo de voo estável: o avião inclina se errar | 75 s | < 15% |
| 8 | 5×6, 2 portas | 8 (2 cores) | destino: cada cor na sua zona | 75 s | < 20% |
| 9 | 5×7 | 9 (2 cores) | doca apertada; 1ª oferta de rewarded (+1 vaga) | 90 s | 30–45% |
| 10 | 6×7 cargueiro | 10 | chefe: tudo junto, decolagem grande, 1ª tela de frota | 120 s | 35–50% |

# 4. PRIMEIRO DIA

- 30–40 contratos;
- 3 tipos de aeronave; *(revisão: 3 formatos de porão)*
- ~~5 propriedades de carga;~~ *(revisão: 1 propriedade + selo de peso)*
- 2 aeroportos;
- 1 mini-evento “Rush Delivery”;
- 1 coleção de selos de rota.
- *(revisão 2026-10-09)* **Diário de Bordo:** cada contrato é uma micro-história contada pelas cargas ("a turnê da banda", "a mudança da vovó"); completar o capítulo fecha a página. Conteúdo fixo, nada aleatório (§27, S3).
- *(revisão)* **Desafio do Dia** com resultado compartilhável (§27, S5).

Primeira meta: comprar/recuperar uma aeronave maior.

Primeiro rewarded: hint avançado ou “retirar uma carga obrigatória” em nível difícil.

Primeira compra: Remove Ads / Starter Logistics Pack depois de 12+ contratos.

# 5. PROGRESSÃO

**Curta:** contrato e moedas.  
**Média:** frota e aeroportos.  
**Longa:** rotas, coleções, eventos e “contratos especiais”.

- D1: avião pequeno + médio.
- D3: ~~cargas perigosas e frias.~~ *(revisão: duas portas/cores e porão irregular; perigosas/frias só se o D7 pedir regra nova)*
- D7: rotas com duas escalas.
- D14: aeronave cargo pesada.
- D30: eventos regionais.
- D60: temporadas temáticas.
- D90: desafios de eficiência e frota visual.

# 6. ECONOMIA

**Credits:** soft currency.
Fontes:
- contratos;
- daily;
- evento;
- rewarded.

Sinks:
- upgrade de frota;
- desbloqueio de hangar;
- hints;
- pintura/cosméticos simples.

**Tickets:** hard currency opcional. *(Revisão 2026-10-09: fora do MVP. Guardrail do estúdio: 1 moeda no MVP; hard currency só depois de haver ralo no mapa de fontes e ralos.)*
Usos:
- bundles;
- retries de evento;
- cosméticos;
- slots especiais.

Não vender “solução automática” como produto dominante.

## 6.1 Revisão 2026-10-09 — economia do MVP

- **Créditos:** 10 + 5×★ só na 1ª vitória ou quando a estrela melhora, com id de transação `contrato:estrela` (reload não duplica).
- **"Upgrade de frota" ganha efeito definido:** aeronave nova = porão de formato novo = capítulo novo de contratos. Destrava por **estrelas** (progresso), não por Créditos. Créditos compram **pintura** (cosmético) e **dicas**.
- **Dica (ralo principal):** o solver mostra onde a carga da frente entra na solução. 100 Créditos; 3 grátis no início.
- **Exploit catalog mínimo (teste negativo para cada um):** recomeçar para reganhar 3★; sair e voltar ao contrato; reload logo depois da concessão; rewarded concedido duas vezes; dica usada e desfeita para "farmar" a posição.

# 7. MONETIZAÇÃO

## Rewarded
- hint visual;
- remover uma carga opcional;
- dobrar pagamento de contrato;
- caixa bônus de rota *(revisão 2026-10-09: conteúdo fixo e visível antes de assistir; nada aleatório — ECA Digital, Lei 15.211/2025)*;
- *(revisão)* **+1 vaga na doca** depois de uma falha (o revive que o core antigo não tinha). Teto: 5 rewarded de moeda por dia.

## Interstitial
- **revisão 2026-10-09: desligado na v0.1**; na v0.2 entra via RemoteConfig depois do contrato 12–15, intervalo ≥ 90 s;
- somente entre contratos;
- após 3–4 contratos;
- frequency cap;
- desligado para pagantes/no-ads.

## IAP
- Remove Ads;
- Starter Logistics Pack;
- credits/tickets;
- cosmetics de aeronave;
- event pack.

Subscription: não.

# 8. RETENÇÃO

D1: frota visível e próximo avião quase desbloqueado.  
D3: nova propriedade de carga.  
D7: rota internacional/evento.  
D14: aeronave com layout diferente.  
D30: coleções e desafios de eficiência.

Daily reward curto, não punitivo.

# 9. LIVE OPS

Templates:
- Rush Delivery;
- Fragile Week;
- Heavy Cargo;
- Perfect Packing;
- Airport Festival.
- *(revisão 2026-10-09)* **Desafio do Dia:** 1 contrato por data, igual para todos, gerado offline e embarcado no build; sem moeda, só sequência visual e texto compartilhável. Boosters/dicas pagos desligados em qualquer ranking ou corrida.

Reutilizar níveis com:
- modificadores;
- scoring;
- tempo;
- recompensas.

# 10. CONTEÚDO

Lançamento somente se validado:
- 350–500 contratos;
- 8–10 layouts de aeronave;
- 8 propriedades de carga;
- 6 aeroportos;
- 4 eventos;
- 40–60 modelos simples de carga;
- 15 skins de aeronave;
- ~25 SFX.

MVP:
- 25–35 contratos;
- 2 aeronaves;
- 3 regras.

# 11. ARTE

Stylized clean, miniaturas tipo diorama.  
Cargas com forma e símbolo claros.  
Aeronaves originais, sem depender de IP real.  
Paleta de aeroportos por região.

A interface precisa manter o porão como foco absoluto.

# 12. ÁUDIO

- snap;
- rotate;
- erro de restrição;
- porta;
- motor;
- decolagem;
- moeda;
- recompensa.

Haptic no encaixe e validação.

# 13. TECNOLOGIA

Unity/C#.

Módulos:
- `CargoDefinition`
- `HoldGrid`
- `PlacementValidator`
- `WeightBalanceModel`
- `LevelManager`
- `FleetMeta`
- `EconomyManager`
- `SaveManager`
- `AnalyticsManager`
- `AdsManager`
- `IAPManager`
- `RemoteConfig`
- `EventManager`
- `UIManager`

O `PlacementValidator` precisa de testes extensivos para evitar soluções impossíveis ou exploits.

> **Revisão 2026-10-09 — arquitetura mínima do greybox (YAGNI):** núcleo C# puro sem `UnityEngine` (`HoldGrid` com ocupação em bitmask `ulong` até 64 células, `Cargo`, `Placement`, `Session`/`Progress`), testado por `dotnet test` fora do Unity; contratos em **texto** (uma linha por carga + máscara do porão); **gerador por partição** (recorta o porão em poliominós, ordena a fila, embaralha giros) que só aceita contrato que o solver prova solúvel e que a heurística gulosa "primeiro lugar que cabe" **não** resolve; **solver** DFS com memória sobre (ocupação, índice da fila, doca). Os managers de Ads/IAP/RemoteConfig/Fleet/Event só nascem na v0.2. Ver §23 para o que vem pronto do pipeline de puzzle do estúdio.

# 14. ANALYTICS

- tutorial_step/complete
- contract_start/complete/fail
- placement_attempt
- invalid_reason
- rotate_use
- hint_use
- time_to_first_valid_layout
- retries
- rewarded_offer/complete
- interstitial_show
- fleet_unlock
- currency_source/sink
- iap_view/purchase
- *(revisão 2026-10-09)* dock_use / dock_full_fail / extra_slot_rewarded
- *(revisão)* balance_seal{ok} / story_page_complete / daily_start / daily_complete / share_tap

Métricas:
- contracts/session;
- fail rate por contrato;
- tempo médio;
- D1/D7;
- rewarded opt-in;
- CPI;
- ad revenue/DAU.

# 15. KPIs — TARGETS INTERNOS

- tutorial ≥ 90%;
- D1 ≥ 29%;
- D3 ≥ 15%;
- D7 ≥ 7%;
- D30 ≥ 2%;
- ≥3 contratos/session;
- rewarded opt-in ≥ 30%;
- payer conversion ≥1.2% no soft launch;
- crash-free >99.5%.

UA low-cost geo:
- CPI ≤ ~US$0,65 promissor;
- 0,65–1,00 iterar;
- >1,00 exige retenção/LTV muito acima.

## 15.1 Revisão 2026-10-09 — gates oficiais de decisão

Os números acima viram meta "forte": estão acima do top quartil (GameAnalytics 2026: D1 mediano ~20%, D7 do top-25% em 6–7%; fonte no veredito de validação). A decisão usa esta régua:

| Métrica | Continuar | Iterar | Cancelar (só após 2 iterações) |
|---|---|---|---|
| CPI no Gate M (BR/PH/ID, 8 criativos) | ≤ US$0,65 | US$0,65–1,30 | > US$1,30 (2× o alvo) em todos |
| Tutorial (chegar ao contrato 3) | ≥ 90% | 75–90% | < 75% após 1 correção |
| D1 | ≥ 26% | 20–26% | < 20% |
| D7 | ≥ 5% | 3,5–5% | < 3,5% |
| Rewarded opt-in (v0.2) | ≥ 30% | 20–30% | não cancela sozinho |

- **Coorte:** 1,5–2 mil installs pagos por leitura. Payer conversion só com ≥ 5 mil installs; na fase B o gate de dinheiro é IAA.
- **Camada 0 (playtest com 10–20 pessoas, antes de UA):** passa com ≥ 50% terminando o contrato 10 por vontade própria e ≥ 30% falhando ao menos uma vez nos contratos 9–10; refuta com > 25% que não usam a doca sem ajuda no contrato 4–5, ou mediana > 3 min nos contratos 8–10.
- **KPIs dos diferenciais** (HIPÓTESE): ver §28.

# 16. TESTE DE MERCADO

Fase creative-only:
- 8 vídeos;
- Brasil, Filipinas, Indonésia.

Fase installs:
- ~~1.000~~ 1.500–2.000 Android *(revisão 2026-10-09: margem do D7)*.

Depois:
- Canadá/Austrália para IAP;
- comparar anúncios “packing satisfatório” vs “falha óbvia”.

# 17. 10 CRIATIVOS DE UA

1. **“Isso cabe?”** — três formas e um porão aparentemente impossível.
2. **“Você colocou a caixa pesada no lugar errado”** — avião inclina, solução corrige.
3. **“Não bloqueie o porto vermelho”** — sequência de descarga.
4. **“Fragile!”** — peso em cima quebra visualmente; solução.
5. **“Um espaço, cinco caixas”** — time-lapse satisfatório.
6. **“99% usam a orientação errada”** — peça em L.
7. **“Escolha qual caixa remover”** — dilema.
8. **“Antes/depois da frota”** — monomotor → cargueiro.
9. **“Packing ASMR”** — snaps perfeitos.
10. **“Última caixa não cabe”** — reorganização em dois movimentos + CTA.

> **Revisão 2026-10-09:** #4 ("Fragile!") e #3 (portas) dependem de regras que saíram do MVP ou entram tarde; trocar por **#11 "A doca encheu"** (falha óbvia: a última vaga ocupada e a carga não cabe) e **#12 "O que tem nesta mala?"** (os objetos da carga contam quem viaja). O #2 continua: o avião inclinando é o selo de peso, legível sem número. Prioridade no Gate M: #1, #5, #9, #10, #11.

# 18. MVP

- grid;
- drag/rotate;
- validator;
- 25–35 níveis;
- ~~3 regras;~~ *(revisão: fila + doca, destino por cor, selo de peso)*
- *(revisão)* gerador por partição + solver + portão de conteúdo no CI;
- VFX/SFX;
- analytics;
- 6–8 criativos.

Não construir:
- online;
- 10 aeroportos;
- eventos complexos;
- subscription.

# 19. V0.1

Core + 30 níveis + analytics.

# 20. V0.2

Se marketability passar:
- 100 níveis;
- frota;
- ads;
- IAP Remove Ads;
- RemoteConfig;
- 2 eventos.

# 21. V1.0

Se D7/LTV passarem:
- 350+ níveis;
- 8 aeronaves;
- 6 aeroportos;
- LiveOps;
- iOS;
- localization.

# 22. ESTIMATIVA DE PRODUÇÃO

| Área | Peso |
|---|---|
| Programação | Médio |
| Game Design | Médio |
| Arte | Baixo–Médio |
| UI | Médio |
| Áudio | Baixo |
| Backend | Baixo |
| Analytics | Médio |
| Conteúdo | Médio |

Complexidade: **4,5/10**.

# 23. REUTILIZAÇÃO

MobileCore comum.  
Ferramentas de level data/validation podem ser compartilhadas com Rune Relay.  
Pipeline 3D leve e Android lab vêm de COE/ARKANA.

**Revisão 2026-10-09 — o que já existe pronto no pipeline de puzzle do estúdio** (repositório do Rune Relay, provado em v0.1):

| Peça | Reuso | Esforço no Skyhold |
|---|---|---|
| Formato de nível em texto + parser que recusa nível inválido | padrão direto | P |
| Gerador por construção com semente reproduzível (constrói a solução, depois embaralha) | o mesmo método; troca "carvar caminho" por "particionar porão" | M |
| Solver com `stopAfter` e portão de conteúdo no CI (nível sem solução, trivial ou grande demais não entra) | mesmo papel; o algoritmo muda (DFS com memória em vez de força bruta) | M |
| `Session`/`Progress` (3 tentativas, estrelas, desbloqueio) | quase direto, já com o exploit do recomeço corrigido | P |
| `dotnet test` do núcleo fora do Unity + CI no GitHub Actions | direto | P |
| Diário de playtest (`diario.csv`) + `diario_report.py` com o portão da Camada 0 | troca os eventos | P |
| Gravação de criativos 9:16 do build real (`-record`/`-demo`) | direto | P |
| Tutorial de anel, SFX e efeitos procedurais, menu de níveis, haptic | direto | P |

O que é **novo** e é o risco técnico: arrastar/soltar com snap e giro sob o dedo (só se prova no aparelho) e o solver de empacotamento com doca. Estimativa do greybox com esse reuso: **2–3 semanas** (a raia C estimava 3–4 sem contar o reuso).

# 24. IA

- gerar propostas de layout;
- detectar níveis insolúveis;
- variações de embalagem/decais provisórios;
- criativos;
- localization;
- análise de fail heatmap.

Sem IA runtime.

# 25. RISCOS

**Puzzle parece trabalho, não diversão.**  
Usar feedback de encaixe, decolagem e progressão visual.

**Balance rule overload.**  
Uma nova regra por capítulo.

**Validator complexo.**  
Testes determinísticos e solver offline para autoria.

**Pouca monetização IAP.**  
Meta/frota e cosmetics só depois de retenção.

**(Revisão 2026-10-09) Gigantes do block puzzle definem o hábito.**  
Block Blast! (1B+ downloads, 70M DAU em dez/2025) é o "block puzzle" na cabeça do jogador, e o Color Block Jam tem ~75% da receita do subgênero block (fontes em `COMPETITIVO.md`). Se o vídeo parecer "mais um block", o CPI sobe. O gancho tem de ser a **doca enchendo** e a **porta da cor**, não o encaixe sozinho.

**(Revisão) Tema de avião não instala sozinho.**  
O gancho é "cabe?". O avião aparece como formato do porão e como decolagem de recompensa, nunca como simulação de logística.

**(Revisão) Nome.**  
"Skyhold" colide com *Dragon Age: Inquisition* (fortaleza central) e *World of Warcraft* (salão de classe). Risco jurídico de baixo a médio (marca não consultada no INPI/USPTO/EUIPO) e ASO ruim. Trocar antes de qualquer página de loja; o nome é irreversível depois de publicado.

# 26. KILL CRITERIA

> **Revisão 2026-10-09:** números recalibrados pela régua do veredito (§15.1). O valor antigo ficou riscado.

## CONTINUAR
- tutorial ≥90%;
- D1 ~~≥29%~~ ≥ 26%;
- D7 ~~≥7%~~ ≥ 5% (coorte de 1,5–2 mil);
- CPI dentro do target (≤ US$0,65);
- vídeos “packing fail” e “satisfying fit” ambos funcionam;
- produção de contrato <20 min após ferramenta madura.

## ITERAR
- D1 ~~23–29%~~ 20–26%;
- D7 ~~4.5–7%~~ 3,5–5%;
- CPI até 50% acima;
- bom CTR mas baixa conversão da store;
- retenção cai quando entram regras.

## CANCELAR
- D1 ~~<23%~~ < 20% após 2 iterações;
- D7 ~~<4.5%~~ < 3,5% após 2 iterações;
- CPI >2× target em 8 criativos;
- jogadores não entendem peso/destino;
- autoria de níveis continua manualmente cara demais.


---

# 27. DIFERENCIAIS COMPETITIVOS (revisão 2026-10-09)

Resumo. O porquê, o custo detalhado, os riscos e a validação de cada um estão em [`COMPETITIVO.md`](COMPETITIVO.md) §4. Status de todos: **PROPOSTO** (nada foi medido).

| # | Diferencial | O que os líderes fazem | Custo | Recomendado |
|---|---|---|---|---|
| S1 | **Fila justa e provada + doca de 3**: próximas 3 cargas à vista, fila fixa provada solúvel pelo solver; perder é sempre escolha, nunca sorteio | Block Blast: "peças absurdas", suspeita de RNG viciado; Dock é o 4º tipo de hybrid-puzzle em receita | M | **Sim (1º)** |
| S2 | **Porão com a forma do avião**: cada aeronave é uma máscara de grade e um capítulo; frota = conteúdo, não vantagem | Tabuleiro fixo (Block Blast, Blockudoku 9×9) | P | Já no core (§2.1) |
| S3 | **Cargas que contam histórias** (Diário de Bordo): objetos reais por cliente, página ilustrada por capítulo | Nenhum block puzzle tem narrativa; Unpacking prova o apelo; "repetitivo" é reclamação recorrente | M | **Sim (3º)** |
| S4 | **Selo de voo estável**: peso só como inclinação visual na decolagem, sem falha | — (a validação mostrou que peso numérico não se lê) | P | v0.2 |
| S5 | **Desafio do Dia compartilhável**, embarcado no build, sem backend | Não verificado nos líderes de block | P | v0.2 |
| S6 | **Destino por porta**: cada cor só encaixa na zona da sua porta | Sem concorrente direto com encaixe em grade + porta; a leitura cor/porta foi provada pelo Color Block Jam | P | **Sim (2º)** |

**Por que estes três primeiro:** S1 é o core e cria a falha que faltava, com um formato (doca) que já paga e uma resposta direta à reclamação mais forte do líder. S6 é a combinação que não achamos em nenhum concorrente e custa só uma restrição de posição. S3 é a marca: o que faz o Skyhold não parecer "mais um block", e entra depois da Camada 0 porque custa arte.

**O que NÃO fazer para "competir":** pontuação infinita, timer, vidas logo de cara, booster pago em ranking, item aleatório pago, hard currency no MVP, anúncio depois de toda partida.

# 28. PLANO DE VALIDAÇÃO DOS DIFERENCIAIS (revisão 2026-10-09)

| # | Hipótese (refutável) | Como validar barato | Passa se | Refuta se |
|---|---|---|---|---|
| S1 | Fila + doca cria tensão sem frustração | Camada 0 (10–20 pessoas, greybox) | ≥ 30% falham ao menos uma vez nos contratos 9–10 e ≥ 70% dizem que perderam por escolha própria | > 25% não usam a doca sem ajuda nos contratos 4–5 |
| S1/S6 | O gancho "a doca encheu" / "cada cor na sua porta" tem CPI menor que o "time-lapse satisfatório" | Gate M: criativos #11 e #3 refeito contra o #5 | CPI ≤ 0,85× o do #5 | CPI ≥ o do #5 nos dois geos |
| S3 | Objetos com história aumentam o interesse no 1º contato | Gate M: #12 "O que tem nesta mala?" contra #5; Camada 1: abertura espontânea do diário | CTR +15% relativo; ≥ 40% abrem o diário sem ser pedido | Sem diferença de CTR e < 15% abrem |
| S4 | Selo de peso é percebido sem tutorial longo | Telemetria `balance_seal` | ≥ 50% dos contratos com carga pesada ganham o selo depois do nível 10 | < 20% |
| S5 | Desafio do Dia traz retorno e compartilhamento | v0.2: metade da coorte (RemoteConfig) | ≥ 25% dos DAU jogam e D7 +1 pp na metade com desafio | < 10% jogam ou D7 igual |

Nada aqui roda antes do greybox passar na Camada 0. O Gate M (CPI) do jogo segue a §15.1.

---

## Lições do estúdio aplicadas a Skyhold Cargo (do Dungeon Courier, 2026-10-16)

O Dungeon Courier (DC) foi do GDD à 1.4.1-beta com núcleo testado fora do Unity, arte v2, tutorial guiado, anúncios e compras, AAB assinado e política pública; cada lição abaixo foi paga lá com tempo, crédito ou retrabalho. O playbook completo está em [`docs/LICOES_PARA_O_ESTUDIO.md`](https://github.com/Vvs2705/dungeon-courier/blob/main/docs/LICOES_PARA_O_ESTUDIO.md) (repositório `Vvs2705/dungeon-courier`), com cópia na memória do estúdio em `C:\Users\VINICIUS\Videos\MEUS PROJETOS\Agentes\_memoria\PLAYBOOK_ESTUDIO_DUNGEON_COURIER.md`. Esta seção traz só o que vale para um puzzle de encaixe em grade, em retrato e sem personagem jogável. Status de tudo: **PROPOSTO**. Caminhos marcados "DC" são do repositório `dungeon-courier`; "Forge", de `03_FORGE_STREET`. Clipes Mixamo ficam fora do git, no checkout principal de cada jogo. Formato de cada item: **o que fazer** · **por quê** (o que aconteceu no DC) · **reaproveitar**.

### Processo
- **Contrato da v0.1 antes do 1º código.** **O que fazer:** escrever `docs/CONTRATO_V01.md` com o escopo (core do §2.1, curva dos níveis 1–10 do §3, 30 contratos, gerador + solver + portão de conteúdo), os números iniciais do §6.1 (10 + 5×★, dica a 100, 3 dicas grátis) e o critério de pronto (Camada 0 do §15.1). Depois, `docs/CONTRATO_LANCAMENTO.md` com a matriz "seção do GDD × feito" (§2 a §28). **Por quê:** no DC, o contrato escrito antes deixou núcleo e View andarem em paralelo sem quebrar a API; a matriz é o que diz "pronto". **Reaproveitar:** DC `docs/CONTRATO_V01.md` e `docs/CONTRATO_LANCAMENTO.md` §1.
- **Memória de retomada.** **O que fazer:** ao começar o código, criar `skyhold-cargo.md` e `STATUS_skyhold-cargo-v01.md` em `Agentes\_memoria\`, com um bloco "CONTINUAR DAQUI" a cada pausa. **Por quê:** o Vinicius retoma dizendo só "vamos continuar"; sem esse bloco, cada sessão reabre a investigação. **Reaproveitar:** `dungeon-courier.md` e `STATUS_dungeon-courier-v01.md` da mesma pasta.
- **Fotos antes do PR e um PR por assunto.** **O que fazer:** foto `-shot` 540×960 de cada tela em todo PR que mexe no visual. Conferir a peça visível acima do dedo e a cor e o símbolo da porta legíveis na célula do porão 7×9. **Por quê:** no DC, as fotos pegaram texto sobreposto e o controle tampando o personagem, e nenhum dos 169 testes verdes pegou isso.
- **Proveniência desde o 1º asset.** **O que fazer:** `docs/PROVENIENCIA.md` com prompt, data, saldo antes e depois e SHA de cada folha pintada ou modelo, inclusive as "variações de embalagem/decais" do §24. **Reaproveitar:** DC `docs/PROVENIENCIA.md` §1 (livro-razão) e §6 (modelo por peça).

### Código e testes
- **Esqueleto copiado, não reescrito.** **O que fazer:** copiar a estrutura `Scripts/Core` (asmdef com `noEngineReferences`), `Scripts/View`, `Editor/Setup.cs`, `Tests/EditMode`, `client/tools/coretests`, `client/tools/viewcheck` e o CI do núcleo, trocando o prefixo `DC` por `SC`. **Por quê:** o DC roda 169 testes em 2–3 min sem abrir o Unity. O `HoldGrid`, o `PlacementValidator`, o gerador e o solver do §13 são exatamente o tipo de regra que tem de morar ali. **Reaproveitar:** DC `client/Assets/_DC/Scripts/Core/DC.Core.asmdef`, `client/Assets/_DC/Editor/Setup.cs` (appId, versão → versionCode, retrato), `client/tools/coretests/DCCore.Tests.csproj`, `client/tools/viewcheck/`, `.github/workflows/nucleo.yml`; gerador e solver do Rune Relay (§23).
- **API do núcleo no topo da fachada.** **O que fazer:** documentar no topo do `Session` o que a View pode chamar (colocar, girar, mandar para a doca, decolar) e os eventos que ela lê (encaixou, doca cheia, falhou, decolou, selo). **Por quê:** no DC (`Sim.cs`), isso evitou que workers paralelos quebrassem a View.
- **Bot jogador e `-autoplay N`, além do solver.** **O que fazer:** o solver prova "tem solução"; o bot mede "quão difícil é". Usar 2 políticas: a gulosa ("1º lugar que cabe") e a cuidadosa (usa a doca). `-autoplay 30` imprime a taxa de falha e as estrelas por contrato contra a coluna "Falha-alvo" do §3. **Por quê:** no DC, o bot mediu a economia (`BALANCE.md`) e serviu ao portão e aos criativos. Já a duração real veio de gente: o "Tempo-alvo" do §3 só se mede na Camada 0. **Reaproveitar:** DC `client/Assets/_DC/Scripts/Core/Bot.cs` (heurístico, com semente e handicap de reação humana); Forge `client/tools/econsim/` (perfis × partidas → CSV).
- **Diário CSV de playtest.** **O que fazer:** gravar os eventos do §14, sem dado pessoal e exportados pelo jogador. O relatório calcula o portão da Camada 0 (§15.1): % que termina o contrato 10, % que falha nos contratos 9–10, mediana dos contratos 8–10 e uso da doca sem ajuda nos contratos 4–5. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Exportar.cs` e `client/tools/diario_report.py`.
- **Flags de teste no build, todas sob `-testsession`** (não lê nem grava o save; semente 1). **O que fazer:** `-tela <nome>`, `-contrato K`, `-frota` (todos os aviões e pinturas abertos, para fotos), `-lang pt|en|es|id`, `-shot`, `-record`, `-bot`, `-tutorial` e `-dev-desbloqueia`. **Por quê:** fotos da loja, criativos ("a doca encheu", "isso cabe?") e QA saem do jogo real sem tocar no save do jogador. **Reaproveitar:** a leitura de argumentos em DC `client/Assets/_DC/Scripts/View/Game.cs`.
- **Portão antes de todo PR.** **O que fazer:** seguir o portão do `CONTRIBUTING.md` e somar `-autoplay 30` com 0 exceções e as fotos. Rodar o EditMode do Unity antes do PR: o dotnet usa NUnit 3.14 e o Unity usa 3.5, e há teste que passa num e falha no outro. **Reaproveitar:** Forge `client/tools/verify.sh` (um comando: `quick`/`full`); Forge `client/tools/mutantes/mutantes.py` (prova que os testes do `PlacementValidator` pegam bug de verdade, como o §13 pede); Forge `client/tools/conteudo_check.py` (modelo do portão dos contratos em texto).
- **Textos em 4 idiomas e áudio sintetizado desde o 1º dia.** **O que fazer:** `L(pt, en, es, id)` com a frase inteira por idioma (o Diário de Bordo é texto); os 8 sons do §12 gerados por script. **Por quê:** no DC, nenhum texto precisou ser caçado depois e nenhum som tem licença a rastrear. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Textos.cs` e `client/tools/audio_gen.py`. O som do snap carrega os criativos #5 e #9, então vale caprichar nele.

### Arte e animação
O Skyhold quase não tem personagem animado: a carga é um poliominó visto de cima e o avião é a silhueta do porão. O pipeline Tripo → Mixamo → Blender do DC vale pouco no core. O que vale é a parte barata: gerador de imagem grátis, Blender por script e troca de cor.
- **Cargas (40–60 objetos, §10): ícones pintados, não modelos.** **O que fazer:** gerar no gerador grátis (Nano Banana 2) folhas 4×3 vistas de cima, sobre fundo azul-marinho liso, um objeto por célula, e recortar por script. A forma do poliominó continua sendo dado do contrato, e o ícone vai por cima. **Por quê:** no DC, a arte pintada ficou mais vistosa que o render 3D recortado, e o gerador de imagem é grátis. Já 50 cargas no Tripo custariam ~2.250 créditos (45 cada) por algo que se vê do tamanho de uma célula. **Reaproveitar:** DC `client/tools/ui_assets.py` (recorte pela cor da borda, grade de células); Forge `client/tools/folha_produtos.py` (folha de contato a 128/64 px e em silhueta, para caçar pares confundíveis como mala × estojo de violão). Plano B a 0 crédito: objeto por primitivas, como em Forge `client/tools/itens_blender.py`.
- **Aviões (2 no MVP, 8–10 no lançamento).** **O que fazer:** o porão é a máscara da grade (dado) mais um sprite pintado do avião visto de cima. A inclinação do selo de peso (§2.1) e a decolagem são rotação e escala do sprite na View, a 0 crédito. Gerar 1 modelo por avião no Tripo (45) só se a decolagem pedir vista 3/4, renderizado como prop (`render_sprites.py --dirs 1`, predefinição Blender 2K, sem rig).
- **Pinturas de avião (o ralo cosmético de Créditos, §6.1) por troca de cor, 0 crédito.** **O que fazer:** as 15 skins do §10 saem de poucos desenhos com troca de matiz, saturação e brilho por faixa de cor, direto no sprite. **Por quê:** no DC, as roupas do courier saíram assim sem Blender e sem crédito. **Reaproveitar:** DC `client/tools/roupas_cor.py` e `client/tools/roupas_2d.py`.
- **Personagens: só retratos no MVP.** **O que fazer:** o cliente de cada capítulo do Diário de Bordo (a vovó da mudança, a banda da turnê) é um retrato pintado (0 crédito), como o cliente e os chefes do DC. Se a cena de entrega pedir o cliente em 3D (v0.2+, lote com aval), cada cliente custa 1 modelo HD (45) + Auto Rig Mixamo (20), e os clipes já existem. O conjunto do cliente do DC serve inteiro, em `06_DUNGEON_COURIER/arte/mixamo/cliente/`: `Idle.fbx` (Breathing Idle, origem Forge `03_FORGE_STREET/arte/mixamo/Idle.fbx`), `Waving.fbx` (recebe a carga), `Cheering.fbx` (entrega com 3★), `Thankful.fbx` (agradece) e `Shrug.fbx` (selo perdido: "tudo bem, chegou"; criado no Blender, `arte/mixamo/_blender/Shrug.fbx`). Item que o cliente segura (mala, estojo) é gerado à parte e preso ao osso (`render_sprites.py --attach item:mixamorig:RightHand:pos:rot:escala`), nunca fundido. **Por quê:** quando o Tripo gera item e mão juntos, funde os dois e o rig arrasta o item errado (o guarda v1 do DC foi descartado por isso).
- **Custo estimado em créditos do Tripo.** **MVP: 0** (cargas, aviões, retratos e UI no gerador grátis e no Blender por script). Opcional na v0.2, por lote e com aval: 2 aviões em 3D (90) + 1 cliente 3D para a cena de entrega (65) ≈ **155**, com teto sugerido de 200. Conferir o saldo antes e depois e a receita do painel na 1ª peça: no DC, o Tripo já voltou com 8K, textura 4K e 2 M polígonos.

### Interface e marca
- **UI procedural em 9-fatias, tingida por código.** **O que fazer:** célula da grade, vaga da doca, esteira, botões e moldura do Diário de Bordo sem PNG de moldura, com paleta de céu e hangar. **Por quê:** no DC, nenhuma moldura é PNG, e trocar o tema é trocar cor. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Art.cs` (`Botao`, `Moldura`, `Pergaminho`, `Contorno` para o destaque do tour, `Balao`, `Aperta`, `Letreiro`).
- **Fontes OFL** (Lilita One em títulos e botões, Nunito ExtraBold no corpo), com a licença junto em `Resources/Fonts`.
- **Escala e toque.** **O que fazer:** CanvasScaler com referência 1080×1920 casando a largura, `AreaSegura` para o notch e `Dp` para o alvo de 48 dp. Conferir em foto que a célula do porão 7×9 não fica abaixo disso. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/AreaSegura.cs` e `Dp.cs`.
- **Telas 20:9.** **O que fazer:** fora do porão, o hangar ou a pista continuam escurecidos até a borda. **Por quê:** no DC, faixa lisa na borda parecia bug.
- **Ícone adaptativo e marca.** **O que fazer:** avião com uma caixa, ocupando no máximo 0,64 da camada, conferido nas máscaras círculo, squircle e quadrado; o ícone 512 da loja é o mesmo. **Reaproveitar:** DC `client/tools/icone_app.py` e `Setup.Icones`; Forge `client/tools/marca_blender.py` e `marca_compor.py` (logo e feature graphic). Fazer a marca só depois de trocar o nome (§25).

### Onboarding (tutorial guiado)
A "mão fantasma" do §3 entra **dentro** do tour do DC: véu com buraco, contorno dourado, seta e um cartão com o que é, quando usar e por quê. Aqui não há relógio, então "congelar" quer dizer que só o alvo aceso responde. Cada passo aparece uma vez (PlayerPrefs), com "Pular tutorial" e "REVER TUTORIAL" nas configurações e desligado no `-testsession`. Passo de ação se cancela se a tela mudar: no DC, um passo preso sem alvo congelou o jogo depois do resultado. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Tour.cs` (troca só a lista de passos e os gatilhos), com a mão fantasma desenhada sobre o alvo.

| # | Quando (gatilho) | O que acende | Cartão: o que · por quê |
|---|---|---|---|
| 0 | 1º contrato, antes do 1º toque | cartão do cliente (abaixo) | quem contratou e o que pede · contexto sem cutscene |
| 1 | nv 1, 1ª carga na esteira | a carga e as células de destino (mão fantasma arrasta) | "Arraste a carga para o porão" · o verbo central vem antes de qualquer escolha |
| 2 | nv 1, 1º encaixe | nada (1 linha, sem congelar) | "Encaixou e travou" · a trava cria a decisão do §2.1 |
| 3 | nv 2, carga que só cabe girada | a carga (ação: girar) | "Toque para girar" |
| 4 | nv 4, 1ª carga que não cabe agora | a vaga da doca (ação: usar a doca) | "Não cabe agora? Guarde na doca: são 3 vagas" · o §15.1 refuta o jogo se não usarem a doca sozinhos |
| 5 | nv 5, 1ª falha | botão "ver onde entrava" (dica grátis) | "A doca encheu. Perder foi a ordem, não a sorte" · S1, a fila justa |
| 6 | nv 6, 1º porão com nariz | o contorno do porão | "Cada avião tem um porão diferente" |
| 7 | nv 7, 1ª carga pesada | ícone "pesada" e faixa da asa no piso | "Pesada perto da asa = voo estável" · selo, nunca falha |
| 8 | nv 8, 1ª porta colorida | a porta e a zona dela | "Cada cor só entra na zona da sua porta" |
| 9 | nv 10 vencido | o próximo avião na frota e as estrelas | "Estrelas destravam aviões novos, com porões novos" |
| 10 | 1ª página completa | botão do Diário de Bordo | "A história deste cliente ficou no diário" |
| 11 | 1ª dica disponível fora da falha | botão Dica e saldo | "A dica mostra onde a carga da frente entra; 3 grátis" |

Na v0.2, a oferta "+1 vaga" por rewarded do nível 9 ganha um passo próprio; a v0.1 não tem anúncio.
- **Cartão de contexto em vez de cutscene.** **O que fazer:** no 1º contrato, o retrato pintado do cliente com balão de fala ocupa o lugar do 1º cartão do tour, e a cena de entrega fecha o ciclo (a porta abre, a carga sai, o cliente recebe). Cada capítulo abre com o cartão do seu cliente, com 1 linha no máximo (§27, S3). Exemplo (PROPOSTO, nome a definir), a vovó da mudança: *"Minha mudança inteira cabe nesse aviãozinho? Cuidado com a caixa de fotos, viu?"*. **Por quê:** no DC, a cutscene antes do 1º toque somava com o tutorial e virava parede de texto.
- **Nada tampando a peça.** O §2 já sobe a peça ~1,5 célula acima do dedo: manter e conferir em foto. Este jogo não tem joystick.

### Monetização e compliance
- **Dentro dos guardrails, conferido:** 1 moeda (Créditos), Tickets fora do MVP (§6); avião novo destrava por estrelas, não por Créditos (§6.1); interstitial desligado na v0.1 (§7); caixa de rota com conteúdo fixo e visível antes (§7); rewarded opcional, com teto de 5 por dia e id de transação.
- **Falta no GDD: anúncio não personalizado para todos e sem `AD_ID`.** **O que fazer:** `LevelPlayPrivacySettings` antes do `Init` (GDPR sem consentimento, CCPA opt-out, COPPA desligado); tirar do manifesto o `AD_ID` e as 3 permissões do Privacy Sandbox; na Play, declaração de ID de publicidade = não. Um puzzle colorido pode ser lido como de apelo infantil mesmo com público de 16+, e o anúncio não personalizado cobre os dois casos. **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Anuncios.cs` (interface + simulador), `AnunciosLevelPlay.cs`, a classe `SemIdDePublicidade` em `client/Assets/_DC/Editor/Setup.cs` e `docs/MONETIZACAO.md` §4.
- **IAP.** **O que fazer:** Remove Ads e Starter Logistics Pack de conteúdo fixo e listado, atrás de uma interface com loja falsa no PC. Compra em 2 passos (o núcleo concede e só depois confirma) e "Restaurar compras". **Reaproveitar:** DC `client/Assets/_DC/Scripts/View/Loja.cs` e `LojaIap.cs` (Unity IAP 5.4.3).
- **Analytics (§14) é lacuna também no DC**, que só tem o diário CSV. **O que fazer:** antes de pôr um SDK, verificar se os relatórios de retenção do Play Console bastam para o Gate M. Se precisar de SDK, escolher um que não traga `AD_ID` e declará-lo na segurança dos dados.
- **Política de privacidade pública** no GitHub Pages (branch `gh-pages`, um `index.html` com 4 idiomas), citando exatamente as redes usadas. **Reaproveitar:** a do DC (https://vvs2705.github.io/dungeon-courier/).

### Play e lançamento
- **Conta da Play: a de organização da V-STACK, uma só para todos os jogos.** O D-U-N-S já foi pedido pelo DC (previsão 2026-11-25); o Skyhold entra na mesma conta e não abre outra. O que é deste jogo: o nome final (o §25 manda trocar "Skyhold") e o appId `br.com.vstack.<nome>`, fixados no `Setup.cs` antes do 1º upload, porque não mudam depois.
- **Chave de upload própria** em `%USERPROFILE%/.<nome>/`, fora do git e com backup fora do PC. Quem perde a chave tem de pedir reset ao suporte.
- **AAB assinado por script** (`Setup.BuildAndroidBundle`; no DC, foram conferidos targetSdk 36, bibliotecas nativas alinhadas a 16 KB e Google Play Billing 9).
- **Loja e criativos refeitos pelos scripts sempre que a arte muda, só com gameplay real:** capturas × 4 idiomas a partir do `-record` (DC `client/tools/loja_fotos.sh`), ícone 512, feature graphic e capturas 1080×1920 (DC `client/tools/loja_assets.py`) e vídeos 9:16 com legenda e CTA (DC `client/tools/criativos.py`). Os prioritários do Gate M (§17: #1, #5, #9, #10 e #11) saem do bot com `-record`.
- **Pré-release no GitHub a cada versão**, com APK, AAB, zip Windows e o pacote da loja.

### Android
- **`QualitySettings.vSyncCount = 0` e `Application.targetFrameRate = 60` no início.** O arrasto da peça é o tato do jogo. No DC, o POCO F4 foi de 28–36 para 55 fps com isso.
- **APK de worktree via `subst R: <client>`**, porque caminho longo com espaço quebra o Gradle. Manter só o APK atual. No adb, os argumentos vão com aspas por dentro.
- **Tato e desempenho se medem em aparelho original barato**, não no POCO do Vinicius, que se limita depois de 1 min. Pedir "pode testar" antes de usar o celular dele. **Reaproveitar:** Forge `client/tools/medir_aparelho.sh` (FPS, memória, temperatura).

### Conflitos com o GDD atual
Esta seção só aponta os conflitos; as seções acima no GDD não foram editadas.

| Onde | O que o GDD diz | Lição contrariada | Recomendação |
|---|---|---|---|
| §3 (roteiro original) | "Tutorial por mão fantasma" | tutorial guiado com cartão o que/quando/por quê é obrigatório | a mão fantasma vira parte do tour (tabela acima); vale a curva da revisão do §3 |
| §7 IAP | "credits/tickets" à venda | 1 moeda no MVP. E Créditos compram dica, então vender Créditos é vender a solução, que o próprio §6 não quer como produto dominante | no MVP, IAP só Remove Ads e Starter Pack fixo (pinturas e dicas listadas); Tickets só depois do mapa de fontes e ralos |
| §7 Rewarded | "dobrar pagamento" e "caixa bônus de rota" | rewarded opcional, nada aleatório | ok se a caixa mostra o conteúdo antes e o dobro tem id de transação; os dois contam no teto de 5 por dia |
| §13 e §14 | `AdsManager` e `AnalyticsManager` sem regra de privacidade | anúncio não personalizado, sem `AD_ID` | levar a regra do DC (`MONETIZACAO.md` §4) para o §7 e o §13 antes de escolher o SDK |
| §9 e §10 | "Fragile Week" e "8 propriedades de carga" no lançamento | a matriz GDD × feito só fecha com o que está no contrato | marcar os dois como DEFERIDO na matriz até o D7 pedir regra nova (§5) |
| §25 | trocar o nome "antes de qualquer página de loja" | appId e chave de upload não mudam depois | trocar o nome antes de criar o projeto Unity, porque o appId nasce no `Setup.cs` |

### Primeiros passos recomendados
1. Decidir o nome novo (§25) e o appId antes de abrir o Unity.
2. Escrever `docs/CONTRATO_V01.md` (core do §2.1, níveis 1–10 do §3, 30 contratos, números do §6.1, portão da Camada 0) e criar a memória `STATUS_skyhold-cargo-v01.md`.
3. Copiar o esqueleto do DC (Core, View, Editor, Tests, coretests, viewcheck, CI) e o gerador e o solver do Rune Relay. Escrever o núcleo (`HoldGrid` em bitmask, `Session`) com os 5 exploits do §6.1 como testes nomeados.
4. Bot com 2 políticas e `-autoplay 30` medindo a falha por nível contra a coluna "Falha-alvo" do §3.
5. Greybox com UI procedural (`Art.cs`), arrasto com a peça acima do dedo, flags sob `-testsession` e fotos 540×960 de cada tela.
6. Tour com os 12 passos acima, cartão do 1º cliente e diário CSV.
7. Camada 0 (10–20 pessoas). Só depois, as cargas pintadas (0 crédito) e o Diário de Bordo.
8. Em paralelo, na conta da V-STACK: política de privacidade e chave de upload deste jogo, com backup.
