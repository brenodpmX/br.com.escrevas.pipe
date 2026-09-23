# Bug

## Utilidade

Documenta um defeito encontrado durante execução de testes ou code review, com reprodução clara e classificação de severidade. Serve como issue de movimentação no board bug.

## Layout de Issue

```markdown
# <título do bug>

## Descrição
<problema objetivo>

## Passos para reproduzir
1. ...

## Resultado esperado
...

## Resultado obtido
...

## Severidade
critical | high | medium | low

## Tipo de violação
requisito | arquitetura | regressão

## Referências (obrigatório)
- **Branch desta issue**: `(ainda não criada)` — NÃO preencha este campo ao criar o bug. A branch de correção é criada pela própria issue de bug, na primeira coluna do board `bug`, a partir da branch de origem/pai (Branch original). Deixe sempre `(ainda não criada)` na criação.
- **Issue pai (Issue original)**: #<id> — <nome da issue que originou o bug>
- **Branch da issue pai (Branch original)**: `<branch-pai>` — branch de origem sobre a qual a correção é aplicada e para a qual o MR será aberto.

<adicionar tags aqui>
```

## Board

`bug` — coluna `backlog`
