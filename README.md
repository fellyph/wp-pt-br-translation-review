# Skill de tradução para conteúdo WordPress(wp-pt-br-translation-review)

Skill para traduzir e revisar conteúdo do ecossistema WordPress para português do Brasil, com foco em posts do Make WordPress, WordPress Core, Docs, AI, strings de plugins e temas, GlotPress, PO/POT, handbooks, releases e comunicados da comunidade.

Ela orienta o agente a:

* Buscar a URL informada e extrair apenas o corpo editorial do post.
* Traduzir strings de plugins/temas, sugestões do GlotPress e trechos `.po`/`.pot`.
* Traduzir o conteúdo para pt-BR com tom claro, natural e adequado à comunidade brasileira.
* Conferir terminologia com o glossário pt-BR e boas práticas brasileiras de tradução.
* Preservar links, comandos, código, placeholders, plurais, contexto, versões, identificadores técnicos, handles e hashtags.
* Revisar riscos de i18n em strings de plugins, como placeholders quebrados, text domain, contexto, plurais e HTML.
* Produzir uma revisão com glossário, estilo, sugestões e bloqueios.

## Estrutura

```text
wp-pt-br-translation-review/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── evals/
│   └── evals.json
└── references/
    ├── pt-br-glossary.csv
    ├── pt-br-glossary.md
    ├── wordpress-plugin-i18n.md
    └── wordpress-pt-br-translation.md
```

## Instalação local

Para usar no Codex:

```bash
cp -R wp-pt-br-translation-review ~/.codex/skills/wp-pt-br-translation-review
```

Para usar no diretório de skills de agentes:

```bash
cp -R wp-pt-br-translation-review ~/.agents/skills/wp-pt-br-translation-review
```

## Uso

Exemplo de prompt:

```text
Use $wp-pt-br-translation-review para traduzir e revisar este post Make WordPress para pt-BR: https://make.wordpress.org/core/example/
```

```text
Use $wp-pt-br-translation-review para traduzir estas strings de plugin para pt-BR e verificar placeholders:
msgid "Save settings"
msgstr ""
```

## Fontes de referência

A skill usa fontes ao vivo quando disponíveis e mantém um resumo compacto em `references/wordpress-pt-br-translation.md` para fallback:

* WordPress Documentation Style Guide
* Writing Tips do time de documentação
* Relatório do projeto GSoD 2020 sobre o style guide
* Glossário pt-BR do translate.wordpress.org
* Snapshot CSV do glossário pt-BR em `references/pt-br-glossary.csv`
* Boas práticas brasileiras de tradução
* Plugin Internationalization Handbook
