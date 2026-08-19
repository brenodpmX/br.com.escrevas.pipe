# Débito

## Utilidade

Sinalização criada por um agente quando encontra bloqueio, inconsistência ou falta de informação que impede sua continuidade. Quando requer ação humana, deve conter a tag `/need_human` no final do arquivo.

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

<adicionar tags aqui>
```

## Board

`debito` — abra o débito na coluna do responsável que se entende deve iniciar a correção (`product`, `ux`, `architecture` ou `humano`), conforme o domínio da lacuna. Qualquer coluna de raciocínio também pode escalar para `humano` quando a resolução exigir decisão humana.

## Tags a serem adicionadas na issue

```
/blocked_by <issue-id>     # opcional — id das issues que bloqueiam a execução desta
/need_human                # opcional — indica que necessita intervenção humana
/branch <nome>             # branch de execução da issue atual
/parent_branch <nome>      # condicional — branch da issue pai (quando originada de outra issue)
/effort [ low | medium | high ]  # opcional — sobrescreve model/effort (requer allow-overwrite na coluna)
```
