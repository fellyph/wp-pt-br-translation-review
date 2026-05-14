# WordPress Plugin Translation and i18n Reference

This is a compact fallback reference for translating and reviewing plugin/theme strings for Brazilian Portuguese. Live WordPress sources remain authoritative.

## Live Sources

- Brazilian translation best practices: https://br.wordpress.org/team/handbook/traducao/boas-praticas/
- Plugin Internationalization Handbook: https://developer.wordpress.org/plugins/internationalization/
- How to Internationalize Your Plugin: https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/
- Internationalization Security: https://developer.wordpress.org/plugins/internationalization/security/
- Localization: https://developer.wordpress.org/plugins/internationalization/localization/
- pt-BR glossary: https://translate.wordpress.org/locale/pt-br/default/glossary/
- Bundled pt-BR glossary snapshot: `pt-br-glossary.csv` (see `pt-br-glossary.md`)

## When the Input is Plugin Translation Work

Treat these as plugin/theme translation tasks:

- A WordPress.org plugin URL or GlotPress project.
- A list of UI strings, errors, notices, button labels, settings labels, block labels, or readme sections.
- `.po` or `.pot` content with `msgid`, `msgid_plural`, `msgctxt`, and `msgstr`.
- A PHP/JS snippet using gettext functions such as `__()`, `_e()`, `_x()`, `_n()`, `_nx()`, `esc_html__()`, or `esc_attr__()`.
- Review requests for placeholders, text domain, translator comments, plurals, or i18n quality.

## Translation Rules for Plugin Strings

- Translate only user-facing text. Preserve technical identifiers and code.
- Do not translate plugin names, theme names, product names, brands, slugs, text domains, package names, hook/filter/action names, function names, class names, constants, file paths, block names, shortcode names, REST routes, option/meta keys, CSS selectors, or command names.
- Preserve placeholders exactly: `%s`, `%d`, `%1$s`, `%2$d`, `%f`, `%%`, `%@`, `{name}`, `{{ name }}`, `===TOKEN===`, `###TOKEN###`, and similar tokens.
- Preserve HTML tags, entities, Markdown syntax, shortcode syntax, newline escape sequences, and intentional whitespace unless the user asks to rewrite source code.
- Never add, remove, or alter URL parameters, HTML attributes, target behavior, or form behavior through translation.
- Keep translations concise for UI labels, buttons, menus, and notices. pt-BR can be longer than English, but menus and buttons should stay as short as practical.
- Use sentence case in pt-BR unless the string is a proper noun or the UI context requires another style.
- Action buttons and links usually use infinitive verbs: "Atualizar", "Salvar", "Excluir", "Ver detalhes".
- Avoid unnecessary "por favor" and "com sucesso" when they add no meaning. Example: "The plugin was installed successfully." -> "O plugin foi instalado."
- Avoid gerundism. Use gerund only for ongoing status labels such as "Imprimindo..." or "Atualizando...".
- Avoid gender-specific phrasing when a neutral construction is natural. Example: "Thank you for your help." -> "Agradecemos a ajuda."
- For dates in plugin/theme format strings, prefer Brazilian formats from the local guide when the source is a date format string, e.g. `j \d\e F \d\e Y`, `d/m/Y`, `H:i`, or `H:i:s` when appropriate.
- For numbers in visible text, use pt-BR punctuation conventions when translating examples: `1.500`, `1,5`.
- Use the live locale glossary and any project glossary. If live lookup is unavailable, use `pt-br-glossary.csv` as the fallback locale glossary. If context requires ignoring a glossary term, explain why.

## PO/POT Handling

- In `.po` work, translate only `msgstr` values unless explicitly asked to modify source metadata.
- Preserve `msgid`, `msgid_plural`, `msgctxt`, extracted comments, translator comments, source references, flags, and headers.
- Keep placeholder counts and types aligned between `msgid`/`msgid_plural` and `msgstr`.
- If a plural entry is provided, fill the available plural forms consistently and preserve any `msgstr[0]`, `msgstr[1]` structure.
- If the user asks for a compiled `.mo`, recommend generating it from the reviewed `.po` with `msgfmt`; do not trust an unrelated `.mo` binary as proof of content.
- For WordPress.org plugins, translations from translate.wordpress.org can take priority over bundled translations in modern WordPress versions. Do not tell users to bundle `.mo` files unless their distribution workflow requires it.

## i18n Code Review Signals

When reviewing source snippets, flag:

- Missing or inconsistent text domain.
- Text domain stored in a variable in gettext calls.
- Variables embedded directly in translatable strings instead of placeholders.
- Multiple placeholders without argument swapping when order may change.
- Concatenated strings that force word-by-word translation.
- Ambiguous words without context where `_x()`, `_ex()`, `_nx()`, or translator comments would help.
- Missing translator comments for placeholders, date/time formats, abbreviations, or unclear context.
- Missing plural handling with `_n()`, `_nx()`, `_n_noop()`, or `_nx_noop()`.
- URLs embedded directly in translatable strings rather than passed as placeholders.
- Unescaped output from translated strings, especially HTML or attribute contexts.
- Leading/trailing whitespace inside translatable strings.
- Unnecessary HTML markup inside translatable strings.
- Empty strings passed for translation.

## Output Patterns

For pasted plugin strings, prefer a compact table:

| Original | Tradução sugerida | Observação |
| --- | --- | --- |
| Save settings | Salvar configurações | Botão; verbo no infinitivo. |

For PO snippets, return valid PO-style entries when practical:

```po
#: includes/admin.php:42
msgid "Save settings"
msgstr "Salvar configurações"
```

For review-only tasks, report concrete issues with source references when available:

- Placeholder `%1$s` missing in `msgstr`.
- "Backup settings" is ambiguous without UI context.
- Plugin name translated; keep the original brand/name.
