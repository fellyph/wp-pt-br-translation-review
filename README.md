# wp-pt-br-translation-review

Skill para traduzir e revisar posts do ecossistema WordPress para português do Brasil, com foco em posts do Make WordPress, WordPress Core, Docs, AI, plugins, temas, handbooks, releases e comunicados da comunidade.

Ela orienta o agente a:

* Buscar a URL informada e extrair apenas o corpo editorial do post.
* Traduzir o conteúdo para pt-BR com tom claro, natural e adequado à comunidade brasileira.
* Conferir terminologia com o glossário pt-BR e boas práticas brasileiras de tradução.
* Preservar links, comandos, código, placeholders, versões, identificadores técnicos, handles e hashtags.
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

## Fontes de referência

A skill usa fontes ao vivo quando disponíveis e mantém um resumo compacto em `references/wordpress-pt-br-translation.md` para fallback:

* WordPress Documentation Style Guide
* Writing Tips do time de documentação
* Relatório do projeto GSoD 2020 sobre o style guide
* Glossário pt-BR do translate.wordpress.org
* Boas práticas brasileiras de tradução

## Evals

Os prompts de avaliação ficam em `evals/evals.json` e cobrem três posts reais do Make WordPress:

* AI 0.9.0
* Extensão do ciclo da versão 7.0
* Fluxo responsável de IA para documentação do WordPress 6.9
