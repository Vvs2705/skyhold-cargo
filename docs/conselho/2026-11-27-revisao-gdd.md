# Ata do Conselho — Skyhold Cargo: revisão do GDD (2026-11-27)

> Aberta por: producer · Estado: DECIDIDA · Rodadas simuladas inline (um executor seguindo os papéis do `Vvs2705/time-jogos`), não são opiniões independentes.

## 0. Entrada
- **Pedido:** "trabalhe em cima dos GDDs, analise se o jogo faz sentido, as stacks, mecânicas, veja o que funcionou nos outros jogos e pode ser aplicado. Pode melhorar, criar, adicionar, mexer no que for necessário."
- **Jogo:** Skyhold Cargo (`Vvs2705/skyhold-cargo`) · branch `docs/conselho-2026-11-27`

## 1. Triagem (7 eixos)
| Eixo | Leitura | Evidência |
|---|---|---|
| Utilidade | Alta: 2º puzzle, plano B do Rune Relay, cobre o gênero que falta | veredito 2026-10-06 (3º no ranking, 7,61) |
| Funcionalidade | Core com falha justa (doca cheia) e sem RNG; 5 exploits já catalogados | GDD §2.1, §6.1 |
| Viabilidade | 2–3 semanas até o APK com reuso; Gate 0 em 5 dias; 0 crédito de arte | GDD §23, seção de lições |
| Aplicação | Fila + doca + porta colorida; o jogador decide "guardo ou encaixo" | GDD §2.1 |
| Necessidade | Não antes da Camada 0 do Rune Relay; sim logo depois | ordem do portfólio |
| Ajustes | Núcleo em C#, WebGL para a Camada 0; conflitos da seção de lições resolvidos; nome trocado antes | §29 |
| Melhorias | Nenhum protótipo descartável (TS); o mesmo projeto vai do Gate 0 ao produto | decisão técnica do §29.2 |

**Veredito: SEGUIR COM AJUSTES.**

## 2. Rodada 1
- **creative-director:** o gancho tem que ser "a doca encheu" e "cada cor na sua porta", não o encaixe sozinho, senão vira "mais um block" (§25). Veto: timer, vidas ou pontuação infinita no MVP.
- **technical-director:** o solver com doca é o único risco algorítmico; limitar o porão a 64 células (bitmask) e provar no CI. Veto: protótipo em outra linguagem que não vire produto.
- **producer:** Gate 0 de 5 dias com critério por dia; arte zero até a Camada 0. Veto: começar antes da Camada 0 do Rune Relay.

## 3. Rodada 2
O CD pediu porta colorida já no Gate 0 (é o diferencial S6); o TD aceitou, porque é só uma máscara a mais no `HoldGrid`. O producer manteve o Diário de Bordo (S3) fora do Gate 0.

## 4. Decisão
Consenso. Plano no GDD §29. Nome escala ao Vinicius (§29.4), por ser irreversível depois de publicado.

## 5. Despacho (quando o Vinicius liberar o projeto)
| # | Raia | Entrega | Depende de |
|---|---|---|---|
| 1 | ip-originality-reviewer | checagem dos 3 nomes | — |
| 2 | lead-programmer | dias 1–3 do Gate 0 | nome decidido |
| 3 | gameplay/ux | dias 4–5 | 2 |
| 4 | qa-lead | Camada 0 | 3 + Camada 0 do Rune Relay lida |
