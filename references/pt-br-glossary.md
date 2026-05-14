# pt-BR WordPress Glossary

Bundled fallback reference for the Portuguese (Brazil) locale glossary.

## Authority

The live glossary remains authoritative:

- View: https://translate.wordpress.org/locale/pt-br/default/glossary/
- CSV export: https://translate.wordpress.org/locale/pt-br/default/glossary/-export/

Use `pt-br-glossary.csv` as an offline snapshot only when live lookup is unavailable, when a quick local search is enough, or when the user explicitly asks to use bundled references.

Snapshot details:

- Source: official GlotPress CSV export from translate.wordpress.org.
- Locale: `pt-br`
- Project scope: default locale glossary.
- Snapshot date: 2026-05-14.
- Columns: `en`, `pt-br`, `pos`, `description`.

## Lookup Workflow

1. Prefer the live glossary URL when web access is available and terminology accuracy matters.
2. For offline lookup, search `references/pt-br-glossary.csv` case-insensitively for the English term.
3. Check part of speech and description before applying a translation.
4. If multiple rows exist for the same English term, choose by context and mention the decision in `Termos verificados no glossário`.
5. If no bundled row exists, mark the term as missing or unchecked and use the best contextual WordPress translation.
6. If a plugin/theme has a project glossary, check it in addition to the locale glossary.

## Useful Local Searches

```bash
rg -i '^plugin,' references/pt-br-glossary.csv
rg -i '^settings,' references/pt-br-glossary.csv
rg -i 'placeholder|plural|text domain' references/pt-br-glossary.csv
```

For terms with commas or quotes in CSV fields, prefer a CSV-aware parser if exact extraction is needed. `rg` is enough for quick human-readable lookup.
