# Contributing

Thanks for helping other testers prepare. The most valuable contributions are **your own interview experiences**, corrections to wrong or outdated answers, and new questions on topics the repo doesn't cover yet.

## Adding questions

1. All new question files use the canonical format in **[docs/question-schema.md](docs/question-schema.md)**. Copy [docs/templates/question-file-template.md](docs/templates/question-file-template.md) as a starting point.
2. Put company interviews in `CompanyName/role-name.md`, using kebab-case file names with no spaces or `&`.
3. Pick an `id_prefix`, register it in the [ID prefix table](docs/question-schema.md#5-id-prefixes), and give each question a unique `id`. Never reuse or renumber IDs.
4. Hide every answer in a `<details>` block. Put code in fenced blocks with a language tag.
5. Leave out interviewer names, candidate details, and anything covered by an NDA.
6. Set `source` honestly (`interview`, `original`, `ai-generated` or `collected`) and set `last_verified` to the date you checked the content.

When you edit an **existing** file that hasn't been migrated to the schema yet, keep the format that file already uses. Migration is tracked as roadmap item C-04.

## AWS AIF-C01 content

- Before adding a question to Question Bank 1 (`ch*.md`) or Question Bank 2 (`question-bank-2.md`), check that the other bank doesn't already ask it.
- Update every count that depends on the questions (summary tables, ranges, answer keys, score trackers, `README.md`).
- After reviewing a file, update its **Last reviewed** line and add an entry to [AWS-AI-Practitioner/review-log.md](AWS-AI-Practitioner/review-log.md).

## Checks

Every pull request runs the [Docs quality](.github/workflows/docs-quality.yml) workflow: Markdown lint, spell check and link check. You can also start it by hand from the **Actions** tab. To run the same checks locally (Node.js 22+):

```bash
npx markdownlint-cli2@0.18.1                       # rules: .markdownlint-cli2.jsonc
npx cspell@9.1.3 lint --no-progress "**/*.md"      # config: cspell.json
lychee --config lychee.toml "./**/*.md"            # needs lychee: https://lychee.cli.rs
```

If the spell checker flags a real technical term, add it to [.cspell/tech-words.txt](.cspell/tech-words.txt) (one word per line, kept sorted). Fix genuine typos instead of adding them.

## Reporting a wrong answer

Open an issue that names the file and question number, says what's wrong, and links a source (official docs preferred).
