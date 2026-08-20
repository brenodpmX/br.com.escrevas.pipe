# Pesquisa

## Utilidade

O board `pesquisa` espelha conhecimento externo para dentro do repositório (biblioteca), sempre com fonte, para que os demais agentes não precisem repesquisar. A pesquisa descreve o que as fontes dizem — não recomenda, não escolhe e não projeta. A decisão e o design permanecem com o solicitante.

Abra uma pesquisa por assunto.

## Modo da solicitação

Escolha um:

- **Panorama** — mapear as opções existentes sobre um assunto. Para cada opção, um resumo descritivo curto, com fonte e ponteiro para aprofundar. Use quando ainda vai escolher. Sem ranking, sem "melhor", sem métrica cruzada sem fonte.
- **Referência completa** — espelhar a documentação atual e completa de um alvo já definido (uma API específica, um padrão escolhido, uma norma), organizada, com versão/data e fonte.

Fluxo típico: um Panorama para decidir; depois uma Referência completa do alvo escolhido.

## Layout de Issue

```markdown
# Solicitação de Pesquisa

## Informações Gerais

- **Título**:
- **Categoria**: <assunto em kebab-case; vira a pasta em docs/biblioteca/<categoria>/>
- **Modo**: panorama | referência completa
- **Solicitante**:
- **Issue origem**:
- **Branch destino**: <branch de trabalho atual>
- **Prioridade**:

---

## Objetivo

<Que conhecimento trazer e para que será usado.>

---

## Alvo / Assunto

<Concreto. Referência completa: nome e versão do alvo. Panorama: o assunto a mapear e, se já souber, as opções candidatas.>

---

## Escopo

### Inclui

-

### Não inclui

-

---

## Fontes esperadas

<As que julgar relevantes; exemplos:>
- Documentação oficial
- RFCs
- Especificações
- Normas técnicas
- Repositório oficial
- Guidance publicada e citável

---

## Resultado esperado

- **Panorama**: catálogo das opções, cada uma com resumo descritivo e sua fonte; Lacuna declarada para a opção sem fonte citável.
- **Referência completa**: documentação do alvo espelhada e organizada na biblioteca, com versão/data e fontes; Lacuna declarada para o que não foi encontrado.

Não espere recomendação, escolha ou microcopy — isso é responsabilidade do solicitante.

---

## Critério de conclusão

A pesquisa está concluída quando:

- o conteúdo foi catalogado em `docs/biblioteca/<categoria>/<slug>.md`, com fontes verificáveis;
- Panorama: cada opção tem resumo com fonte ou Lacuna declarada;
- Referência completa: a cobertura do alvo está declarada (o que foi espelhado e o que ficou de fora).

A decisão permanece com o solicitante.
```
