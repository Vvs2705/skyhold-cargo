# Skyhold Cargo — Comparativo competitivo

**Data:** 2026-10-09 · **Status:** PROPOSTO (pesquisa de mesa; nenhum criativo, playtest ou coorte foi medido) · **GDD:** [`GDD.md`](GDD.md) (revisão 2026-10-09 no topo).

**Legenda:** FATO = número com fonte e data · INFERÊNCIA = deduzido de fatos · OPINIÃO = julgamento de design. O que não foi confirmado está escrito **não confirmado**. Downloads e notas da Google Play vêm do espelho androidrank.org (a página da Play não abriu pela ferramenta), consultado em 09/10/2026. As siglas das fontes estão no fim.

**Pergunta que este documento responde:** num mercado de block puzzle dominado por gigantes, o que o Skyhold pode ter que eles não têm, barato para o nosso time e difícil de copiar?

---

## 1. Os similares

| Jogo | Estúdio | Lançamento | Downloads (Play) | Nota (nº aval.) | Receita / escala | Mecânica | Monetização | Fontes |
|---|---|---|---|---|---|---|---|---|
| **Block Blast!** | Hungry Studio | abr/2022 | 1B+ | 4,85 (5,6M) | Jogo mais baixado de 2025 (M1). 70M DAU / 300M MAU em dez/2025, dado da empresa (BW). Ads ~US$584 mil/dia: estimativa de agregador, **não confirmado** (U) | Grade fixa, 3 peças por rodada, sem rotação, limpa linhas; infinito | Quase só anúncio (interstitial + rewarded para reviver) | A1, M1, BW, U |
| **Blockudoku** | Easybrain | 2019 | 100M+ | 4,63 (1,3M) | **não confirmado** | Block puzzle + sudoku (9×9) | Anúncio + "No Ads" US$9,99 | A2, AS1 |
| **Color Block Jam** | Rollic | nov/2024 | 10M+ | 4,07 (338 mil) | Q2/2025: US$42,0M e 21,8M installs (AppMagic; GDR). IAP acumulado > US$100M até jul/2025 (CN). ~75% da receita do subgênero block em 2025 (N) | Deslizar blocos até a porta da mesma cor, com timer; níveis desenhados | IAP de boosters + interstitial + rewarded | A8, GDR, CN, N |
| **Bus Escape: Traffic Jam** | ABI Games | set/2024 | 10M+ | 4,42 (399 mil) | EUA Q1/2025: de ~US$101 mil a ~US$230 mil por semana (blog do Sensor Tower redigido por IA: fonte fraca) | Tirar ônibus do pátio; passageiros por cor numa **doca de espera** | IAP + anúncio | A12, ST |
| **Fill The Fridge!** | Rollic | 2022 | 50M+ | 4,17 (620 mil) | **não confirmado** | Arrastar objetos reais para as prateleiras da geladeira | IAP US$1,99–9,99 (inclui Remove Ads); anúncio para liberar itens | A5, AL |
| **Unpacking** (mobile) | Witch Beam / Humble | PC 2021; mobile ago/2023 | 50K+ | 4,2 (766) | > 1M de cópias somando plataformas até nov/2022 (NL); BAFTA 2022 de Narrativa (W) | Desempacotar objetos em casas sucessivas; a história é contada pelos objetos | Premium US$9,99 | A4, W, NL, TA |
| **Cargo Jam** | Go Game (Turquia) | mai/2025 | **não confirmado** | **não confirmado** | **não confirmado** | Encaixar peças 3D numa grade 3×3×6 | **não confirmado** | CS1, APK |
| **Cargo Sort Airlift** | Cui Yong Game | v1.0.8, jul/2026 | **não confirmado** | **não confirmado** | **não confirmado** | Único com **tema de avião**: levar cada item da fila à baia certa do avião, com movimentos e vidas; **sem grade de encaixe** | **não confirmado** | CS2 |

**Também observados** (menos próximos): Parking Jam 3D (Popcore, 100M+, 4,12 de 1,77M; A10), Tetris Block Party (PLAYSTUDIOS, dez/2025, 1M+; em ago/2026 a empresa disse estar "reavaliando a escala" do investimento, P2), Pack Master (Lion Studios, 1M+, **nota 2,49**; A6), Gecko Out (Rollic, 5M+, 9º do hybridcasual puzzle no H1/2026; G1), Hexa Away (GOODROID, 5M+, 10º; G1), Bus Jam (Rollic, 10M+; A11), Block Ready e Load It! (carga até o caminhão da cor certa, iOS 2025; BR, LI), Pack & Go! 3D (ACTIONFIT, jul/2026; PG3) e Truckful (Pocketpair/MythicOwl, chega à Play em 09/10/2026; HG).

### Mercado (FATO, com fonte)
- Puzzle fez US$4,9B no H1/2026, mais de 44% do gasto em casual; os lançamentos de block puzzle passaram de 2.000 (+89%). O hybridcasual puzzle fez quase US$600M no semestre (G2, PGB, 27/07/2026). *Outro recorte da mesma AppMagic, com o gênero puzzle inteiro, dá US$7,6B; não comparar os dois.*
- Top-10 hybridcasual puzzle do H1/2026: Pixel Flow 23%, Screwdom 10%, Color Block Jam 9% (30% do subgênero block); Gecko Out e Hexa Away em 9º e 10º (G1, 06/08/2026).
- Subgênero block em 2025: o menor do puzzle (~US$183M), com receita +2.900% e downloads +39,4%; o próprio texto cita depois US$280M, então o tamanho exato fica **não confirmado** (N, 22/02/2026).
- Tipos de hybrid-puzzle por receita, jan–fev/2026: Sort/Screw lidera (US$72M); **Dock é o 4º e Dock+Conveyor o 5º** (G3, 25/03/2026). INFERÊNCIA: a doca de espera do core revisado está num formato que já paga.

---

## 2. Matriz de recursos

`sim` / `não` = confirmado na pesquisa ou na descrição da loja · `?` = não verificado nesta rodada · `n/a` = não se aplica. A última coluna é o GDD revisado (PROPOSTO, nada implementado).

| Recurso | Block Blast | Blockudoku | Color Block Jam | Bus Escape | Fill the Fridge | Unpacking | Cargo Sort Airlift | **Skyhold (GDD rev.)** |
|---|---|---|---|---|---|---|---|---|
| Níveis desenhados (não infinito) | ? | ? | sim | sim | sim | sim | sim | **sim (gerados com prova)** |
| Próximas peças visíveis | 3 por rodada | 3 por rodada | n/a (tabuleiro todo visível) | ? | n/a | n/a | sim (fila) | **sim, fila de 3** |
| Doca/área de espera | não | não | não | sim | não | não | baias | **sim, 3 vagas** |
| Rotação da peça | não | não | não | não | ? | sim | não | **sim (toque)** |
| Sorte na ordem das peças | sim (reclamada) | sim | não | ? | não | não | não ("sempre resolvível") | **não (fila fixa e provada)** |
| Falha clara | sim | sim | sim (timer) | sim | ? | não | sim (movimentos/vidas) | **sim (doca cheia)** |
| Timer | não | não | sim (reclamado) | ? | ? | não | ? | **não** |
| Vidas/energia | ? | ? | ? | ? | ? | não | sim | **não no MVP** |
| Cor de destino / porta | não | não | sim (porta da cor) | sim (passageiro por cor) | não | não | sim (baia certa) | **sim (zona da porta)** |
| Formato do tabuleiro muda | não | não (9×9) | sim | sim | sim | sim | ? | **sim (silhueta do avião)** |
| Objetos reais / história | não | não | não | não | objetos, sem história | **sim (história pelos objetos)** | objetos | **sim (Diário de Bordo)** |
| Selo/estrela de maestria | pontuação | pontuação | ? | ? | ? | não | ? | **sim (voo estável)** |
| Desafio diário compartilhável | ? | ? | ? | ? | ? | não | ? | **sim (texto, sem backend)** |
| Pagar para tirar anúncios | **não** (reclamado) | sim (US$9,99) | ? | ? | sim | n/a (premium) | ? | **sim (v0.2)** |

---

## 3. O que os jogadores reclamam nos líderes (oportunidades)

| # | Reclamação recorrente | Onde | Fonte | Oportunidade para nós |
|---|---|---|---|---|
| 1 | Anúncio depois de **toda** partida, alguns com mais de 30 s sem pular, e **sem opção paga** para remover | Block Blast; também Color Block Jam e Parking Jam 3D | J1, CS3, J3 | Interstitial desligado na v0.1; na v0.2 só depois do contrato 12–15, com intervalo ≥ 90 s; Remove Ads desde o 1º IAP |
| 2 | **Peças "absurdas"** que não cabem; suspeita de RNG viciado conforme a ocupação do tabuleiro | Block Blast | J1, PL | **S1:** fila fixa, visível e provada solúvel; perder é sempre consequência de escolha |
| 3 | **Paywall de dificuldade**: timer apertado, boosters raros, "tentar de novo só vendo anúncio", movimentos limitados, muro por volta do nível 250 | Color Block Jam, Parking Jam 3D | CS3, GS, J3 | Sem timer; recomeçar é grátis; todo contrato é solúvel sem booster (o solver prova) |
| 4 | Bugs e travamentos com **perda de progresso** | Block Blast, Blockudoku, Color Block Jam | J1, J2, CS3 | Save atômico + núcleo testado fora do Unity (pipeline que o estúdio já tem) |
| 5 | **Repetitivo** | Fill the Fridge, Color Block Jam | GS-F, CS3 | **S3:** cada contrato é um cliente com objetos próprios; **S2:** o porão muda de forma por capítulo |
| 6 | Controle de toque **desajeitado** em tela pequena | Unpacking mobile | TA | A peça sobe ~1,5 célula acima do dedo, snap generoso, alvo de toque ≥ 48 dp |
| 7 | Undo vendido como poder/booster | jogos tipo Wood Block | WB | Não vender undo; a dica do solver é o único ralo (e ensina, não resolve tudo) |

INFERÊNCIA: as reclamações 1–3 não são falha de quem não sabe fazer. São a monetização desses jogos. Não repeti-las é barato para nós e caro para eles, porque eles perderiam receita.

---

## 4. Diferenciais propostos

Régua de custo para o nosso time (1 dev + Claude Code, Unity 6, sem backend): **P** ≤ 1 semana · **M** 2–4 semanas · **G** ≥ 1 mês. Status de todos: **PROPOSTO**.

### S1 — Fila justa e provada (a culpa nunca é da sorte)
- **Por que importa:** a reclamação mais emocional do maior block puzzle do mundo é a peça "impossível" que parece sorteada contra o jogador (J1, PL). E a doca de espera é um formato que paga: Dock é o 4º tipo de hybrid-puzzle em receita no início de 2026 (G3).
- **Como funciona:** as 3 próximas cargas estão sempre à vista; cada contrato tem fila fixa e foi provado solúvel pelo solver antes de entrar no build. Com a doca de 3 vagas, perder é sempre consequência de uma escolha ("guardei a peça errada"), nunca de um sorteio. A tela de falha mostra "ainda dava: veja onde a carga entraria" (1 dica grátis por falha).
- **Custo:** **M** (gerador por partição + solver com doca + portão de conteúdo no CI; o método vem pronto do pipeline de puzzle do estúdio).
- **Risco:** fila fixa reduz a rejogabilidade infinita dos block puzzles de pontuação; compensar com volume de contratos gerados.
- **Validar barato:** criativo #11 "A doca encheu" × #5 "time-lapse satisfatório"; no playtest, perguntar "por que você perdeu?" (meta: ≥ 70% citam a própria escolha).

### S2 — O porão tem a forma do avião (frota = conteúdo, não vantagem)
- **Por que importa:** os líderes de block usam tabuleiro fixo (Blockudoku 9×9; Block Blast sempre a mesma grade). O único jogo com tema de avião que achamos (Cargo Sort Airlift, CS2) não tem grade de encaixe. E a validação apontou que "upgrade de frota" não tinha efeito de jogo definido.
- **Como funciona:** cada aeronave é uma máscara de grade: monomotor 3×4, turbo-hélice com nariz, cargueiro com caixa da asa, jumbo com dois decks (capítulo tardio). Nova aeronave = capítulo novo, destravado por estrelas. A pintura é o único item comprável com Créditos.
- **Custo:** **P** (a máscara é um campo do nível; a silhueta 2D é um sprite por aeronave).
- **Risco:** porões irregulares ficam difíceis cedo; introduzir só no nível 6.
- **Validar barato:** criativo #8 "Antes/depois da frota" mostrando porões de formatos diferentes; tempo por nível no playtest.

### S3 — Cargas que contam histórias (Diário de Bordo)
- **Por que importa:** o Unpacking provou que objetos contam história sem nenhuma palavra (BAFTA de Narrativa 2022, mais de 1M de cópias; W, NL), e o Fill the Fridge provou que organizar objetos reais atrai em massa (50M+; A5). Nenhum dos líderes de block tem narrativa, e "repetitivo" é reclamação recorrente (GS-F, CS3).
- **Como funciona:** cada contrato é de um cliente: "a turnê da banda" (estojo de violão, bumbo, amplificador), "a mudança da vovó" (poltrona, caixa de fotos, gaiola). As peças são silhuetas desses objetos sobre o poliominó. Ao fim do capítulo, o Diário de Bordo fecha uma página ilustrada (conteúdo fixo, nada aleatório).
- **Custo:** **M** (40–60 ícones 2D por IA com revisão humana + 1 tela de diário; a forma da peça continua sendo dado).
- **Risco:** arte por IA inconsistente; texto demais para o casual (no máximo 1 linha por contrato).
- **Validar barato:** criativo #12 "O que tem nesta mala?" × #5; no playtest, ver se o jogador abre o diário sem ser pedido.

### S4 — Selo de voo estável (peso sem conta)
- **Por que importa:** a validação concluiu que peso numérico vira conta e não se lê em 2 s, e que "frágil/centro de massa" pediam vista lateral. Transformar o peso numa consequência visual mantém a fantasia do avião sem sobrecarregar a regra.
- **Como funciona:** algumas cargas têm o ícone "pesada". Na decolagem, centro de massa fora da faixa da asa faz o avião inclinar e perder o selo, sem falhar o contrato. Camada de maestria opcional.
- **Custo:** **P** (centro de massa de células ponderadas + 1 animação).
- **Risco:** o jogador não percebe a regra; mostrar a faixa da asa no piso a partir do nível 7.
- **Validar barato:** criativo #2 "avião inclina"; taxa de selo por contrato na telemetria (`balance_seal`).

### S5 — Desafio do Dia compartilhável (sem backend)
- **Por que importa:** dá um motivo diário de voltar sem LiveOps e sem servidor, e um texto curto em grupo de WhatsApp é aquisição de graça. Não verificamos se os líderes de block têm desafio diário (`?` na matriz); o que seria nosso é o **resultado compartilhável**, com o mesmo contrato para todos.
- **Como funciona:** 365 contratos gerados offline e embarcados no build; a data escolhe o do dia; o resultado vira texto (estrelas, selo de voo, sequência). Sem moeda, então mudar o relógio não rende nada.
- **Custo:** **P** (com o gerador pronto).
- **Risco:** pouca gente compartilha.
- **Validar barato:** desafio ligado para metade da coorte na v0.2 (`daily_start`, `share_tap`).

### S6 — Destino por porta (a única regra de logística)
- **Por que importa:** não achamos nenhum jogo que combine encaixe de poliominós em grade com zona de descarga por porta. As partes existem separadas (Bus Jam, Color Block Jam, Block Ready, Load It!). E a leitura "cada cor na sua porta" já foi provada em escala pelo Color Block Jam (~75% da receita do block em 2025; N).
- **Como funciona:** cada porta tem uma cor e uma zona no piso; carga daquela cor só encaixa na zona dela. Na animação de entrega, a porta abre e as cargas saem; a regra se explica sozinha.
- **Custo:** **P** (restrição de posição no validador e no gerador, que particiona por zona).
- **Risco:** com zonas pequenas, o puzzle fica óbvio; balancear pelo solver (número de becos sem saída).
- **Validar barato:** criativo #3 refeito ("o vermelho sai pela porta vermelha"); falha por nível no playtest.

---

## 5. Os 3 que eu faria primeiro

1. **S1 — Fila justa e provada + doca.** É o core: cria a falha que o GDD não tinha, dá gatilho ao rewarded (+1 vaga), responde à reclamação mais forte do Block Blast e usa um formato (Dock) que já paga. Sem ele não existe jogo.
2. **S6 — Destino por porta.** É a combinação sem concorrente direto que achamos, com uma leitura de cor/porta que o mercado já aprendeu. Custa P porque é só restrição de posição.
3. **S3 — Cargas com história.** É o diferencial emocional e de marca que nenhum block puzzle tem, e ataca o "repetitivo". Custa M, então entra depois de o greybox passar na Camada 0; os ícones podem começar como placeholders.

S2 (porão com forma de avião) já entrou no core revisado (GDD §2.1). S4 e S5 são baratos e ficam para a v0.2.

**Não competir em:** pontuação infinita (território do Block Blast), timer, vidas, booster pago em ranking, item aleatório pago.

---

## 6. Riscos de mercado e lacunas

- **Gigante no hábito:** Block Blast (1B+, 70M DAU) é o "block puzzle" na cabeça do jogador. Se o vídeo parecer "mais um block", o CPI sobe. O gancho tem de ser a **doca enchendo** e a **porta da cor**, não o encaixe sozinho.
- **Nome:** "Skyhold" é a fortaleza central de *Dragon Age: Inquisition* (BioWare/EA; FX) e o salão de classe dos Guerreiros em *World of Warcraft* (Blizzard; WW). Não há app com esse nome nas lojas (IT, AR-S), mas a busca por "Skyhold" é dominada por guias desses jogos: ASO ruim e risco jurídico de baixo a médio. Marca registrada **não confirmada** (USPTO/EUIPO/INPI não consultados). Recomendação: trocar o nome antes de qualquer página de loja.
- **Tema de avião já existe** (Cargo Sort Airlift), mas sem encaixe em grade e sem números confirmados.
- **Lacunas:** receita de Blockudoku, Fill the Fridge, Bus Jam, Gecko Out, Hexa Away, Cargo Jam e Cargo Sort Airlift **não confirmada**; reclamações de Gecko Out, Hexa Away, Bus Jam e Pack Master **não confirmadas**; o blog do Sensor Tower sobre ônibus e os agregadores (justuseapp, grand-screen, Udonis) são fontes fracas.

---

## Fontes (consultadas em 09/10/2026)

- **Androidrank** (espelho da Google Play), prefixo `https://www.androidrank.org/application/`: A1 `block_blast/com.block.juggle` · A2 `blockudoku/com.easybrain.block.puzzle.games` · A4 `unpacking/com.humblebundle.unpacking` · A5 `fill_the_fridge/com.GybeGames.FillTheFridgeTest` · A6 `pack_master/com.dmg.packmaster` · A8 `color_block_jam/com.GybeGames.ColorBlockJam` · A10 `parking_jam_3d/com.lszenlamzr.parkingjam` · A11 `bus_jam/com.nt.games.busjam` · A12 `bus_escape_traffic_jam/com.abi.busjam.sortpuzzle` · AR-S https://www.androidrank.org/search?q=skyhold
- **Mercado e imprensa:** M1 https://mobilegamer.biz/the-top-mobile-game-downloads-of-2025/ (13/01/2026) · BW https://www.businesswire.com/news/home/20260108572322/en (08/01/2026) · U https://www.blog.udonis.co/statistics/block-blast (09/06/2026) · G1 https://www.gamigion.com/?p=34952 (06/08/2026) · G2 https://www.gamigion.com/mobile-casual-games-report-h1-2026-analysis/ (27/07/2026) · G3 https://www.gamigion.com/13-hybrid-puzzle-types-ranked-by-iap-iaa/ (25/03/2026) · PGB https://www.pocketgamer.biz/puzzle-accounts-for-44-of-casual-mobile-earnings-in-h1-2026/ (27/07/2026) · N https://naavik.co/digest/how-niche-subgenres-are-reshaping-the-mobile-puzzle-market/ (22/02/2026) · GDR https://gamedevreports.substack.com/p/appmagic-top-10-hybrid-casual-games (15/09/2025) · CN https://www.cnbce.com/teknoloji/istanbul-merkezli-studyo-rollicin-100-milyon-dolarlik-mobil-rekorunun-sirri-ne-h15218 (21/07/2025) · ST https://sensortower.com/blog/2025-q1-unified-top-5-bus%20games-revenue-us-60326d74241bc16eb8da0eed
- **PLAYSTUDIOS:** P2 https://secure.businesswire.com/news/home/20260811377645/en/PLAYSTUDIOS-Inc.-Announces-Second-Quarter-Results (11/08/2026)
- **Unpacking:** W https://en.wikipedia.org/wiki/Unpacking_(video_game) · NL https://nintendolife.com/news/2022/11/cosy-indie-darling-unpacking-has-sold-over-1-million-copies-since-launch · TA https://toucharcade.com/2023/08/24/unpacking-mobile-review-iphone-ipad-controller-support/ (24/08/2023)
- **Reviews e agregadores (fonte fraca, usar como sinal):** J1 https://justuseapp.com/en/app/1617391485/block-blast/reviews · J2 https://justuseapp.com/en/app/1452227871/blockudoku-block-puzzle-game/reviews · J3 https://justuseapp.com/en/app/1498229533/parking-jam-3d/reviews · CS1 https://chrome-stats.com/d/id6746150428 · CS2 https://chrome-stats.com/d/com.pilot.appcargosort · CS3 https://chrome-stats.com/d/id6504332779 · GS https://grand-screen.com/games/color-block-jam/ · GS-F https://grand-screen.com/games/fill-the-fridge/ · AL https://app-liv.jp/5343908/ · PL https://playgama.com/blog/game-faqs/why-does-block-blast-sometimes-give-impossible-blocks/ · APK https://apkpure.com/cargo-jam/com.gogames.gacargojam
- **Lojas:** AS1 https://apps.apple.com/KR/app/id1452227871 · WB https://apps.apple.com/app/id1602504786 · BR https://apps.apple.com/hr/app/block-ready/id6751489149 · LI https://apps.apple.com/mx/app/load-it/id6748239267 · PG3 https://appgoblin.info/apps/6788677604 · IT https://itunes.apple.com/search?term=skyhold&entity=software
- **Outros:** HG https://www.haveagood-holiday.com/en/articles/truckful-google-play-launch (10/09/2026) · FX https://dragonageinquisition.wiki.fextralife.com/Skyhold · WW https://warcraft.wiki.gg/wiki/Warrior_class_hall
