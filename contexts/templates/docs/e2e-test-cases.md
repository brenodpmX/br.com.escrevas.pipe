# E2E Test Cases (nova estrutura)

## Utilidade

Casos de teste executáveis, dirigidos pelo frontend, versionados no repositório de
código em `qa/`. Substituem os antigos documentos de casos de teste em markdown.
São executados pelo modo QA (`bash qa/run.sh`) e servem de contrato do que será
validado após a implementação.

## Onde ficam

`qa/tests/specs/NNN-*.spec.ts` no repositório de código (br.com.escrevas). Um caso
por arquivo. O prefixo numérico define a ordem de execução (`010-`, `020-`, ...).
A execução é sequencial e para no primeiro erro (fail-stop).

## Princípios

- Interação EXCLUSIVAMENTE pelo frontend (Playwright). Nada de SQL nem chamada
  direta ao backend dentro do spec.
- Estado de exceção (só quando inevitável) via seeds, nunca dentro do spec:
  `qa/seeds/db/*.sql` (SQL) e `qa/seeds/backend/*.sh` (request à API), ordenados por
  prefixo. Ex.: aprovar um documento simulando o administrativo que ainda não tem tela.
- Ampliar o conjunto = adicionar novos specs numerados. Nada mais a configurar.

## Layout do spec

```ts
import { test, expect } from '@playwright/test';

// Caso NNN — <objetivo do caso, em uma linha>
test('<comportamento validado, na visão do usuário>', async ({ page }) => {
  await page.goto('/');
  // interaja como um usuário: navegue, preencha campos, clique em botões...
  await expect(page.getByRole('heading', { name: 'Escrevas' })).toBeVisible();
});
```

## Convenções

- Nome do arquivo: `NNN-<slug-curto>.spec.ts` (NNN ordena; agrupe assuntos por faixa).
- `baseURL` já vem da config (`qa/tests/playwright.config.ts`); use caminhos relativos.
- Sem dependência entre specs além da ordem; cada caso valida um comportamento.
- Prefira seletores acessíveis (`getByRole`, `getByLabel`) a seletores frágeis.

## Referência

`qa/README.md` no repositório de código (fluxo completo, fases e o `result.json`).
