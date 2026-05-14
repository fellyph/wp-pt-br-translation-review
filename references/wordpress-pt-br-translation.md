# WordPress pt-BR Translation Reference

This is a compact fallback reference. Live source links remain authoritative.

## Live Sources

- WordPress Documentation Style Guide: https://make.wordpress.org/docs/style-guide/
- GitHub style guide source: https://github.com/WordPress/WordPress-Documentation-Style-Guide/blob/main/docs/1-introduction/index.md
- Writing Tips: https://make.wordpress.org/docs/handbook/get-involved/writing-tips/
- GSoD 2020 style guide report: https://make.wordpress.org/docs/2021/03/07/wordpress-documentation-style-guide-google-season-of-docs-2020-project-report-tacitonic/
- pt-BR glossary: https://translate.wordpress.org/locale/pt-br/default/glossary/
- Brazilian translation best practices: https://br.wordpress.org/team/handbook/traducao/boas-praticas/

## Decision Hierarchy

1. Keep the source post authoritative for facts, structure, dates, links, code, names, and scope.
2. Use the pt-BR glossary and Brazilian translation best practices for terminology and localization.
3. Use the WordPress Documentation Style Guide for writing quality: clarity, consistency, style, tone, inclusivity, and global-audience guidance.
4. Use external style references only when the WordPress sources do not answer the issue.

## Brazilian Translation Best Practices

- Translate organically, not literally.
- Keep the same level of formality or informality. WordPress informational text tends to be informal and polite, not stiff.
- Prefer simple pt-BR wording. Examples from the Brazilian guide include using "use" instead of "utilize" when natural, and "tem/têm" instead of "possui/possuem" when it reads better.
- Do not add new meaning, commentary, emojis, jokes, ideology, or extra explanations that are not in the source.
- Avoid slang, audience-specific terms, and expressions that only a narrow group would understand.
- Maintain consistency across a post and across WordPress projects by checking the glossary.
- Do not alter behavior through translation, especially HTML, parameters, attributes, forms, links, placeholders, or commands.
- Do not submit or present raw machine translation without human review.
- Preserve placeholders and formatting tokens exactly.
- Keep links relevant to the original source and official WordPress/project domains.
- Respect brand spelling. Do not translate plugin names, theme names, project names, package names, handles, commands, or code identifiers.
- Be careful with capitalization, gendered language, punctuation in numbers, dates, time formats, ambiguity, and unnecessary words.
- The glossary is very important, but context can justify an exception. Explain exceptions.

## WordPress Documentation Style Guidance

- Write clearly and accurately for a global audience.
- Use a natural, succinct, friendly, conversational tone.
- Avoid being too pushy, robotic, overly formal, overly casual, or condescending.
- Avoid idioms, colloquialisms, cultural references, unnecessary humor, jargon, slang, exclamation points, ableist language, and long complicated sentences.
- Prefer active voice, present tense, concise sentences, short focused paragraphs, and consistent vocabulary.
- Define or clarify technical terms when the intended audience may not know them.
- Use second person for instructions when appropriate.
- For user documentation, get to the point quickly and explain technical terms without talking down to readers.
- For developer documentation, be direct and precise; assume more technical knowledge but still avoid needless complexity.
- For procedural content, prefer clear step-by-step instructions over personal narrative.
- Write timelessly where possible and avoid wording that will age quickly.

## Article Extraction Rules

For Make WordPress pages, translate the post, not the whole webpage.

Include:

- Post title.
- Publication date and author only if the user asks or if it matters for context.
- Article body.
- Headings, lists, tables, links, images with meaningful alt/captions, code, commands, tags, and props.

Exclude unless explicitly requested:

- Site navigation.
- Welcome boxes and team sidebars.
- Search, login, subscribe, and share UI.
- Comments and replies.
- Post navigation.
- Footer/site resource lists.

If a target URL is unavailable or resolves to an archive page, locate the matching post by title/date and report the fallback.

## Glossary Handling

Always check the live glossary when tools allow it. Use this fallback only when live lookup is unavailable.

Glossary entries observed in the source page snapshot:

| Original | Translation | Note |
| --- | --- | --- |
| ability | habilidade | Technical WordPress capability/ability contexts still need live/context check. |
| accordion | sanfona | Also "tipo sanfona" or "sanfonado" in adjective contexts. |
| activate | ativar | Verb. |
| add-on / addon | complemento | Noun. |
| address | corrige | Verb, as in a version addressing an issue. |
| address | endereço | Noun. |
| April | abril | Month names are lowercase except sentence starts or proper names. |
| are you sure you want | tem certeza de que deseja | Expression. |

For all other terms, especially terms such as "plugin", "theme", "block", "Core", "release", "feature", "experiment", "settings", "dashboard", "accessibility", "developer", "provider", "model", "comment", "moderation", "alt text", "media", "API", "REST API", "WP-CLI", and "Gutenberg", verify the live glossary or clearly mark the term as unchecked.

## Quality Review Checklist

- The translation covers only the article body and expected metadata.
- The translation preserves all source facts and caveats.
- The translation has no invented links, status updates, examples, or conclusions.
- Glossary terms are checked and used consistently.
- Proper nouns, code, commands, placeholders, issue numbers, PR numbers, versions, handles, and hashtags are preserved.
- Markdown and HTML remain valid.
- The tone is clear, concise, natural, polite, and suitable for the Brazilian WordPress community.
- The text avoids literal English structure and unnecessary formalism.
- Inclusive and global-audience guidance is followed.
- Any glossary exception or unavailable lookup is disclosed.
