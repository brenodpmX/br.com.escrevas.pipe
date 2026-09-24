# Débito

## Utilidade

Sinalização criada por um agente quando encontra bloqueio, inconsistência ou falta de informação que impede sua continuidade. O débito é uma **dependência resolvida por outro agente** (negócio/design/arquitetura), que assume a decisão no board `debito`. Ao abrir um débito, bloqueie a issue de origem **apenas** pela relação de dependência (`/blocked_by`); **não** adicione `/need_human` — o débito não aguarda um humano, e marcá-lo criaria uma espera humana redundante sobre um trabalho que é de outro agente. Use `/need_human` só na exceção em que a resolução exige, comprovadamente, decisão humana (débito destinado à coluna `humano`).

## Quando abrir (e quando NÃO abrir)

Débito é **exclusivamente** para uma **lacuna de DEFINIÇÃO** que você não tem autoridade para criar: regra de negócio ausente, decisão de design não tomada, decisão arquitetural pendente. Nesses casos a resolução é de outro agente (product/ux/architecture), não sua.

**NÃO abra débito para trabalho técnico que é do próprio engenheiro** — isso não é lacuna de definição, é o seu trabalho. Exemplos do que você deve RESOLVER, nunca virar débito:

- Não encontrar um commit na sua branch, resolver conflito de merge, acertar o histórico git
- Subir o ambiente de desenvolvimento (`bash dev/dev.sh`) ou depurar por que ele não sobe
- Ler e entender código existente, procurar um arquivo, investigar um erro
- Escrever ou ajustar testes

Se o problema é técnico e bem definido mas você não consegue resolvê-lo no seu nível, o caminho **não é débito**: é **escalar** para um engenheiro mais sênior (ver a persona de engenharia). Insegurança ou preguiça não são bloqueio.

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
- **Branch desta issue**: `(ainda não criada)` — NÃO preencha este campo ao criar o débito. A branch de correção é criada pela própria issue de débito, na primeira coluna do board `debito`, a partir da branch de origem/pai. Deixe sempre `(ainda não criada)` na criação.
- **Issue pai**: #<id> — <nome da issue que originou o débito>   (a issue bloqueada por este débito)
- **Branch da issue pai**: `<branch-pai>`   (branch de origem, sobre a qual a correção é aplicada)

<adicionar tags aqui>
```

## Board

`debito` — abra o débito na coluna do responsável que se entende deve iniciar a correção (`product`, `ux`, `architecture` ou `humano`), conforme o domínio da lacuna. Qualquer coluna de raciocínio também pode escalar para `humano` quando a resolução exigir decisão humana.
