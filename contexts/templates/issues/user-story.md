# User Story

## Utilidade

Define uma unidade de entrega de valor do ponto de vista do usuário. Contém regras de negócio e critérios de aceitação testáveis. Serve tanto como documentação de referência quanto como issue de movimentação no board story.

## Layout de Issue

```markdown
# <título da user story>

Como <tipo de usuário>
Quero <ação>
Para <objetivo>

## Regras de negócio
- ...

## Critérios de aceitação
- Dado <contexto>, quando <ação>, então <resultado>
- ...

## Não objetivos
- ...

## Referências (obrigatório)
- **Branch desta issue**: `(ainda não criada)` — NÃO preencha este campo ao criar a story. A branch de trabalho própria da story é criada pela própria story, na primeira coluna do board `story`, a partir da branch da issue pai. Deixe sempre `(ainda não criada)` na criação.
- **Issue pai**: #<id> — <nome do épico>   (o épico que originou esta story)
- **Branch da issue pai**: `<branch-pai>`   (branch de trabalho do épico — origem de onde a branch da story nasce e para onde volta)

<adicionar tags aqui>
```

## Caminho do Arquivo

`doc/product/<slug-epic>/stories/<slug-story>.md`

## Board

`story` — coluna `backlog`
