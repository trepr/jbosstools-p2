# jbosstools-p2

Repositório de publicação dos sites **p2** (Eclipse update sites) do fork interno
do TRE-PR do JBoss Tools, servidos via **GitHub Pages**.

> Fork de uso estritamente interno. O conteúdo p2 é gerado pelos builds Tycho dos
> componentes e publicado aqui automaticamente por CI.

## Como funciona

- O conteúdo servido pelo GitHub Pages fica no branch **`gh-pages`** (não em `main`).
- Cada componente/versão publica em um subdiretório próprio, por exemplo:
  - `base/4.41/` — site p2 do componente *base* para o alvo Eclipse 2026-09 (plataforma 4.41).
- O arquivo `.nojekyll` no `gh-pages` é obrigatório: sem ele o GitHub Pages processa o
  conteúdo com Jekyll e descarta diretórios iniciados por `_` e outros caminhos usados
  pelos repositórios p2.

## URLs publicadas

Com o GitHub Pages habilitado para o branch `gh-pages`:

- Base: `https://trepr.github.io/jbosstools-p2/base/4.41/`

Essa URL é consumida pela propriedade `jbosstools-base-site` no POM pai
(`jbosstools-build/parent/pom.xml`), que o build do `jbosstools-server` usa para
resolver os bundles do componente *base*.

## Publicação

A publicação é feita por workflows de CI dos repositórios de origem (por exemplo,
o workflow `publish_p2_site.yml` em `jbosstools-base`), que constroem o site p2 com
Tycho e enviam o resultado para o branch `gh-pages` deste repositório, no
subdiretório correspondente ao componente e à versão.

Não edite o branch `gh-pages` manualmente: ele é sobrescrito pela CI.
