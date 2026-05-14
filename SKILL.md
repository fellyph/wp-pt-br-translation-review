---
name: wp-pt-br-translation-review
description: Use this skill whenever the user asks to translate, localize, review, revise, QA, or improve Make WordPress, WordPress Core, Docs, AI, plugin, theme, handbook, release, or community posts for Brazilian Portuguese. It translates English WordPress posts into pt-BR and reviews drafts against the Brazilian glossary, translation best practices, and WordPress documentation style guidance, even if the user only says "translate this URL", "review this pt-BR draft", or "check style/glossary".
metadata:
  short-description: Tradução e revisão pt-BR para WordPress
---

# WordPress pt-BR Translation Review

Use this skill to translate English WordPress community posts into Brazilian Portuguese and to review existing pt-BR drafts for terminology, tone, style, and formatting quality.

## Reference Sources

Use live sources whenever web access is available. Do not rely only on memory for current posts or glossary entries.

- WordPress Documentation Style Guide: https://make.wordpress.org/docs/style-guide/
- Style guide source on GitHub: https://github.com/WordPress/WordPress-Documentation-Style-Guide/blob/main/docs/1-introduction/index.md
- Writing Tips: https://make.wordpress.org/docs/handbook/get-involved/writing-tips/
- GSoD style guide project report: https://make.wordpress.org/docs/2021/03/07/wordpress-documentation-style-guide-google-season-of-docs-2020-project-report-tacitonic/
- pt-BR glossary: https://translate.wordpress.org/locale/pt-br/default/glossary/
- Brazilian translation best practices: https://br.wordpress.org/team/handbook/traducao/boas-praticas/

Read `references/wordpress-pt-br-translation.md` when you need a compact checklist of the source guidance, when browsing is unavailable, or before making nuanced glossary/style decisions.

## Source Authority

Resolve decisions in this order:

1. The English source post for facts, structure, links, version numbers, code, dates, and names.
2. The live pt-BR glossary and Brazilian translation best practices for terminology and localization choices.
3. The WordPress Documentation Style Guide and Writing Tips for clarity, style, voice, tone, and global-audience guidance.
4. External references only when the WordPress sources do not answer the issue.

If the glossary conflicts with the local context, use the contextually correct translation and explain the exception in `Observações ou bloqueios`.

## Workflow

1. Fetch the submitted URL with available web or browser tools.
2. Extract only the article content: title, author/date if relevant, article body, headings, lists, images with alt/captions when useful, inline links, code, tags, and props.
3. Exclude page chrome: navigation, sidebars, subscription boxes, share widgets, comments, post navigation, footers, and site resource lists unless the user explicitly asks for them.
4. If a URL redirects or resolves to an index page, locate the intended post by title, date, author, and visible permalink. State the fallback used.
5. Identify source terms that need glossary verification before translating: WordPress product terms, UI terms, developer/API terms, release terms, acronyms, feature names, experiment names, and recurring nouns.
6. Check relevant terms against the live pt-BR glossary first. Record the checked terms and any missing or context-sensitive terms.
7. Translate into Brazilian Portuguese with clear, concise, informal-but-polite wording. Translate meaning organically rather than word by word.
8. Review the result against glossary, style, tone, inclusivity, formatting, and source fidelity.

## Translation Rules

- Preserve source meaning. Do not add facts, status, dates, interpretation, or links that are not in the source.
- Preserve product names, project names, team names, plugin/theme names, handles, hashtags, version numbers, issue/PR numbers, commands, code identifiers, placeholders, and URLs unless the source itself translates them.
- Preserve Markdown/HTML structure when the user needs a publishable draft. Keep headings, lists, tables, code fences, inline code, links, emphasis, image references, and block quotes intact.
- Preserve placeholders and code-like tokens exactly, including `%s`, `%d`, `%1$s`, `%2$d`, `%%`, `%@`, `===TOKEN===`, `###TOKEN###`, HTML tags, shortcode syntax, REST routes, package names, and CLI commands.
- Keep links semantically equivalent. Do not replace official links with unrelated or commercial links.
- Use the glossary consistently across the whole translation. If a term appears many times, use one translation unless context requires a different one.
- Avoid raw machine-translation artifacts: unnatural cognates, literal English syntax, unnecessary gerunds, excessive "de" chains, and inflated formal words.
- Avoid slang, regional jokes, idioms, culturally specific references, unnecessary humor, exclamation points, and ableist or exclusionary language.
- Prefer concise sentences and short paragraphs. Use active voice, present tense, and second person when the source is procedural or user-facing.
- Keep the source level of formality. For WordPress community content, prefer natural, polite pt-BR over either overly formal or overly casual phrasing.

## Review Focus

When reviewing a draft, compare it against the English source and report concrete changes. Do not rewrite the whole draft unless the user requests it or the draft is too inconsistent to review locally.

Check for:

- Glossary adherence and consistent recurring terms.
- Untranslated English where translation is expected.
- Terms that should stay in English, such as plugin names, package names, commands, code, and proper nouns.
- Source fidelity, including preserved meaning, scope, and caveats.
- Tone aligned with WordPress guidance: succinct, natural, friendly, clear, and not condescending.
- Global-audience and inclusivity issues.
- Broken Markdown, malformed links, changed code snippets, altered placeholders, or lost headings.
- Page chrome accidentally translated as article content.

## Output Format

Respond in Brazilian Portuguese by default. Use this structure unless the user asks for a different format:

```markdown
## Tradução sugerida
[Tradução completa ou trecho revisado em pt-BR.]

## Revisão de qualidade
[Resumo objetivo do alinhamento com fonte, glossário, estilo e tom.]

## Termos verificados no glossário
| Termo original | Tradução usada | Observação |
| --- | --- | --- |
| ... | ... | ... |

## Sugestões de melhoria
- [Sugestões concretas, com trechos antes/depois quando útil.]

## Observações ou bloqueios
- [Limitações, termos ausentes no glossário, URLs que redirecionaram, ou decisões contextuais.]
```

If there are no issues in a section, say that clearly and briefly. If live browsing or glossary lookup is unavailable, disclose that limitation in `Observações ou bloqueios` and use the bundled reference as a fallback.
