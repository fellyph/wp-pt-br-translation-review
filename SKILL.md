---
name: wp-pt-br-translation-review
description: Use this skill whenever the user asks to translate, localize, review, revise, QA, or improve WordPress content for Brazilian Portuguese, including Make WordPress posts, Core/Docs/AI posts, plugin or theme strings, GlotPress suggestions, PO/POT files, readme text, release notes, handbooks, and community posts. It translates English WordPress content into pt-BR and reviews drafts against the Brazilian glossary, Brazilian translation best practices, WordPress documentation style guidance, and plugin internationalization rules, even if the user only says "translate this URL", "translate these plugin strings", "review this pt-BR draft", or "check style/glossary".
metadata:
  short-description: Tradução e revisão pt-BR para WordPress
---

# WordPress pt-BR Translation Review

Use this skill to translate English WordPress community content and plugin/theme strings into Brazilian Portuguese and to review existing pt-BR drafts for terminology, tone, style, formatting, and i18n safety.

## Reference Sources

Use live sources whenever web access is available. Do not rely only on memory for current posts or glossary entries.

- WordPress Documentation Style Guide: https://make.wordpress.org/docs/style-guide/
- Style guide source on GitHub: https://github.com/WordPress/WordPress-Documentation-Style-Guide/blob/main/docs/1-introduction/index.md
- Writing Tips: https://make.wordpress.org/docs/handbook/get-involved/writing-tips/
- GSoD style guide project report: https://make.wordpress.org/docs/2021/03/07/wordpress-documentation-style-guide-google-season-of-docs-2020-project-report-tacitonic/
- pt-BR glossary: https://translate.wordpress.org/locale/pt-br/default/glossary/
- Brazilian translation best practices: https://br.wordpress.org/team/handbook/traducao/boas-praticas/
- Plugin Internationalization Handbook: https://developer.wordpress.org/plugins/internationalization/

Read `references/wordpress-pt-br-translation.md` when you need a compact checklist of the source guidance, when browsing is unavailable, or before making nuanced glossary/style decisions.
Read `references/pt-br-glossary.md` before using the bundled locale glossary snapshot. Use `references/pt-br-glossary.csv` as an offline fallback for terminology lookup when live glossary access is unavailable.
Read `references/wordpress-plugin-i18n.md` when translating plugin/theme UI strings, GlotPress suggestions, `.po`, `.pot`, `.mo`, or code-adjacent text, or when reviewing plugin internationalization quality.

## Source Authority

Resolve decisions in this order:

1. The English source content for facts, structure, links, version numbers, code, dates, names, source strings, and string context.
2. The live pt-BR glossary, project glossaries, and Brazilian translation best practices for terminology and localization choices. If live lookup is unavailable, use the bundled `references/pt-br-glossary.csv` snapshot as a fallback.
3. The WordPress Plugin Internationalization Handbook for gettext, text domains, placeholders, plurals, context, PO/POT/MO handling, and i18n security.
4. The WordPress Documentation Style Guide and Writing Tips for clarity, style, voice, tone, and global-audience guidance.
5. External references only when the WordPress sources do not answer the issue.

If the glossary conflicts with the local context, use the contextually correct translation and explain the exception in `Observações ou bloqueios`.

## Workflow

1. Identify the input type: article URL, copied draft, plugin/theme string list, GlotPress suggestions, `.po`/`.pot` file, readme text, code snippet, or mixed content.
2. For URLs, fetch the submitted URL with available web or browser tools.
3. For Make WordPress pages, extract only the article content: title, author/date if relevant, article body, headings, lists, images with alt/captions when useful, inline links, code, tags, and props.
4. For plugin/theme strings, preserve source identifiers and string structure: `msgid`, `msgid_plural`, `msgctxt`, `msgstr`, translator comments, references, text domains, placeholders, HTML tags, entities, line breaks, and escape-sensitive text.
5. Exclude page chrome from web pages: navigation, sidebars, subscription boxes, share widgets, comments, post navigation, footers, and site resource lists unless the user explicitly asks for them.
6. If a URL redirects or resolves to an index page, locate the intended post by title, date, author, and visible permalink. State the fallback used.
7. Identify source terms that need glossary verification before translating: WordPress product terms, UI terms, developer/API terms, release terms, acronyms, feature names, experiment names, recurring nouns, and plugin-specific terms.
8. Check relevant terms against the live pt-BR glossary first. For plugins/themes, also check any project glossary when available. If live lookup is unavailable, search the bundled glossary CSV. Record checked terms and any missing or context-sensitive terms.
9. Translate into Brazilian Portuguese with clear, concise, informal-but-polite wording. Translate meaning organically rather than word by word.
10. Review the result against glossary, style, tone, inclusivity, formatting, source fidelity, placeholders, plural behavior, context, and i18n safety.

## Translation Rules

- Preserve source meaning. Do not add facts, status, dates, interpretation, or links that are not in the source.
- Preserve product names, project names, team names, plugin/theme names, handles, hashtags, version numbers, issue/PR numbers, commands, code identifiers, placeholders, and URLs unless the source itself translates them.
- Preserve Markdown/HTML structure when the user needs a publishable draft. Keep headings, lists, tables, code fences, inline code, links, emphasis, image references, and block quotes intact.
- Preserve placeholders and code-like tokens exactly, including `%s`, `%d`, `%1$s`, `%2$d`, `%%`, `%@`, `===TOKEN===`, `###TOKEN###`, HTML tags, shortcode syntax, REST routes, package names, and CLI commands.
- For plugin/theme strings, never translate text domains, slugs, hook names, filter names, action names, option/meta keys, REST routes, block names, package names, class names, function names, constants, CSS selectors, file paths, or shortcode names.
- For PO/POT content, translate only `msgstr` values unless explicitly asked to fix source/i18n code. Preserve `msgid`, `msgid_plural`, `msgctxt`, comments, references, wrapping, and headers.
- For plural strings, preserve singular/plural intent and placeholder counts. If the format does not allow the correct pt-BR plural behavior, flag it in `Observações ou bloqueios` rather than silently changing structure.
- Use `msgctxt`, translator comments, source references, screenshots, or code context to resolve ambiguity. If context is missing and a string is ambiguous, provide the safest translation and flag the uncertainty.
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
- Broken PO syntax, modified `msgid`, mismatched placeholder counts, unsafe translated HTML, changed variables, changed shortcode syntax, or lost `msgctxt`.
- Missing translator context for ambiguous plugin strings, missing text domain in source snippets, concatenated translatable strings, or URLs embedded in translatable strings when reviewing i18n code.
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

For plugin/theme strings, use the same sections but choose the most useful artifact for `Tradução sugerida`: a table for pasted strings, completed `msgstr` entries for PO snippets, or a patch-style list for suggested replacements. Always include a placeholder/context audit in `Revisão de qualidade` or `Observações ou bloqueios`.
