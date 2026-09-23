# Task

## Utilidade

Define uma unidade mínima de trabalho executável pela engenharia. Contém escopo, critério de aceite e classificação de effort para determinar o nível de modelo a ser utilizado na implementação.

## Layout de Issue

```markdown
# <título da task>

effort: low | medium | high

## User Story
<referência à story relacionada>

## Descrição
<o que deve ser feito — objetivo e direto>

## Escopo técnico
<o que está incluso>

## Fora de escopo
<limites claros>

## Critério de aceite
- Implementação segue arquitetura
- Código cobre cenário descrito
- Testes unitários criados
- Sem quebra de funcionalidades existentes

## Referências (obrigatório)
- **Branch desta issue**: `(ainda não criada)` — NÃO preencha este campo ao criar a task. A branch de trabalho própria da task é criada pela própria task, na primeira coluna do board `task`, a partir da branch da issue pai. Deixe sempre `(ainda não criada)` na criação.
- **Issue pai**: #<id> — <nome da story>   (a story que originou esta task)
- **Branch da issue pai**: `<branch-pai>`   (branch de trabalho da story — origem de onde a branch da task nasce e para onde volta)

<adicionar tags aqui>
```

## Board

`task` — coluna `backlog`
