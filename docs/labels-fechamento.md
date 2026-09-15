# Labels de fechamento de issue (`completed` / `not_planned`)

> **Documentação pública, voltada a pessoas.** Este documento explica um
> comportamento observável da esteira para quem acompanha as issues no GitHub.
> **Não é steering**: os agentes da esteira **não** aplicam nem leem essas
> labels diretamente. Elas são um efeito das transições de coluna, tratado pelo
> adapter do GitHub.

## O que são

Quando uma issue chega às colunas terminais do board, a esteira aplica uma label
que sinaliza o motivo do encerramento. O adapter do GitHub interpreta essa label
e **fecha a issue** com o `state_reason` correspondente:

| Label         | Coluna terminal | `state_reason` no GitHub | Significado                              |
|---------------|-----------------|--------------------------|------------------------------------------|
| `completed`   | `concluido`     | `completed`              | Trabalho entregue e concluído com êxito. |
| `not_planned` | `cancelado`     | `not_planned`            | Encerrada sem execução (cancelada).      |

## Como funciona

- A label é posta pela **coluna terminal**, por meio dos gatilhos
  `on_in`/`on_out` definidos no board — não por decisão de um agente.
  - `concluido` → `on_out: [completed]`
  - `cancelado` → `on_out: [not_planned]`
  - `encerrado` → `on_in: [archive]` (arquivamento; não fecha por motivo)
- O **adapter do GitHub** observa a presença dessas labels e traduz cada uma no
  fechamento da issue com o `state_reason` da tabela acima.
- O efeito é **determinístico**: a mesma label sempre leva ao mesmo motivo de
  fechamento.

## Reabertura

Reabrir uma issue fechada por essas labels é uma **ação humana**. A esteira não
reabre automaticamente; se você precisar retomar o trabalho, reabra a issue
manualmente no GitHub (e, se aplicável, reposicione-a no board).

## Por que isto está documentado aqui

Para que qualquer pessoa que veja uma issue fechada com `completed` ou
`not_planned` entenda **por que** ela fechou e **quem** a fechou (a automação da
esteira, via transição de coluna), sem precisar inspecionar a configuração
interna do pipeline.

Reforçando: este é um documento **público e explicativo**. As labels descritas
aqui são um contrato entre as colunas terminais e o adapter do GitHub — os
agentes não as manipulam.
