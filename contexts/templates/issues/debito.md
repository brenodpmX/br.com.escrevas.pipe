# Débito

## Utilidade

Sinalização criada por um agente quando encontra bloqueio, inconsistência ou falta de informação que impede sua continuidade. O débito é uma **dependência resolvida por outro agente** (negócio/design/arquitetura), que assume a decisão no board `debito`. Ao abrir um débito, bloqueie a issue de origem **apenas** pela relação de dependência (`/blocked_by`); **não** adicione `/need_human` — o débito não aguarda um humano, e marcá-lo criaria uma espera humana redundante sobre um trabalho que é de outro agente. Use `/need_human` só na exceção em que a resolução exige, comprovadamente, decisão humana (débito destinado à coluna `humano`).

## Layout de Issue

```markdown
# <título do débito>

## Descrição
<o que está inconsistente, faltando ou bloqueando>

## Impacto
<o que fica bloqueado por este débito>

## Origem
<agente e etapa que detectou>

## Resolução sugerida
<ação necessária para resolver>

## Referências (obrigatório)
- **Branch desta issue**: `<branch>` — branch de correção do débito. Todo agente que atuar nesta issue DEVE trabalhar nesta branch; não crie nem use outra.
- **Issue pai**: #<id> — <nome da issue que originou o débito>   (a issue bloqueada por este débito)
- **Branch da issue pai**: `<branch-pai>`   (branch de origem, sobre a qual a correção é aplicada)

<adicionar tags aqui>
```

## Board

`debito` — abra o débito na coluna do responsável que se entende deve iniciar a correção (`product`, `ux`, `architecture` ou `humano`), conforme o domínio da lacuna. Qualquer coluna de raciocínio também pode escalar para `humano` quando a resolução exigir decisão humana.
