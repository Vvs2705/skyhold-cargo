# Skyhold Cargo

**Estilo:** puzzle espacial de encaixe ("cabe ou não cabe"), hybrid-casual, retrato.

**O que é:** você carrega o porão de um avião de carga antes da decolagem.

**Como funciona:** as cargas chegam numa fila visível; você arrasta cada uma para a grade do porão, respeitando o formato, a porta do destino (cor) e as zonas especiais. Quando a carga não cabe, ela vai para uma doca de espera com 3 vagas; doca cheia e nada cabe = falha. Encaixou tudo: valida e decola. Cada avião novo da frota é um porão de formato diferente.

**Como vai ser jogar:** arrumar a mala perfeita com regras que vão se somando a cada fase, com a tensão da fila e da doca.

## Situação
Plano B do slot puzzle (reaproveita o gerador e o solver do Rune Relay). O nome "Skyhold" colide com Dragon Age/World of Warcraft: trocar antes da loja. Ainda não há código: este repositório guarda o GDD e a estrutura do projeto, pronta para o desenvolvimento começar.

- **GDD:** [`docs/GDD.md`](docs/GDD.md) (revisão competitiva de 2026-10-09 no topo).
- **Comparativo com jogos similares e diferenciais:** [`docs/COMPETITIVO.md`](docs/COMPETITIVO.md).

## Estrutura do repositório
| Pasta | Para quê |
|---|---|
| `docs/` | GDD, comparativo e, depois, balance, validações e contratos de cada fase |
| `client/` | projeto Unity 6 (6000.3.x), Android primeiro, retrato; código do jogo em `client/Assets/_SC/` |
| `client/Assets/_SC/Scripts/Core/` | núcleo em C# puro (regras, simulação, save), testável fora do Unity |
| `client/Assets/_SC/Scripts/View/` | MonoBehaviours, UI, câmera, entrada |
| `client/Assets/_SC/Editor/` | setup do projeto e builds por linha de comando |
| `client/Assets/_SC/Tests/EditMode/` | testes NUnit do núcleo |
| `client/Assets/_SC/Resources/` | sprites e dados carregados em tempo de execução |
| `client/tools/` | ferramentas fora do Unity (testes `dotnet`, scripts de arte, relatório de playtest) |
| `arte/` | arte-fonte; `arte/tripo/` e `arte/mixamo/` ficam fora do git |

Como contribuir: [`CONTRIBUTING.md`](CONTRIBUTING.md). Histórico: [`CHANGELOG.md`](CHANGELOG.md).

## Repositório e licença
© V-STACK / Vinicius Souza. **Todos os direitos reservados.** Código, documentos e arte visíveis para acompanhamento, sem licença de uso, cópia ou redistribuição.
