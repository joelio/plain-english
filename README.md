# Plain English & British English — Claude Code Skills

Two [Claude Code skills](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills/overview) that help Claude write clearly and consistently.

## Skills

### `plain-english`

A reference guide for writing in plain English. Covers sentence length rules, word choice (use not utilise, start not commence), active voice, readability targets (Flesch 60-70), document structure, and common patterns to avoid (nominalisations, hidden verbs, hedging piles, double negatives).

Based on guidance from:
- [Plain English Campaign](https://www.plainenglish.co.uk/)
- [GOV.UK Content Design Guide](https://www.gov.uk/guidance/content-design/writing-for-gov-uk)
- US Federal Plain Language Guidelines (Plain Writing Act 2010)
- ISO 24495-1:2023 Plain language
- Martin Cutts, *Oxford Guide to Plain English*

### `british-english`

A reference guide for writing in British English conventions. Covers spelling (-ise not -ize, -our not -or, -re not -er), punctuation (single quotes, logical punctuation placement, Oxford comma policy), vocabulary differences (boot not trunk, flat not apartment), date formats (DD/MM/YYYY), grammar (collective nouns as plural, got not gotten, shall/will), and measurement conventions.

Based on guidance from:
- New Oxford Style Manual (Oxford University Press)
- Guardian and Observer Style Guide
- Cambridge Guide to English Usage
- Fowler's Modern English Usage
- GOV.UK Style Guide

## Installation

Copy the skill directories into your Claude Code skills folder:

```bash
# Clone
git clone https://github.com/joelio/plain-english.git

# Copy skills to your Claude Code skills directory
cp -r plain-english/skills/plain-english ~/.claude/skills/
cp -r plain-english/skills/british-english ~/.claude/skills/
```

Or symlink them:

```bash
ln -s "$(pwd)/plain-english/skills/plain-english" ~/.claude/skills/plain-english
ln -s "$(pwd)/plain-english/skills/british-english" ~/.claude/skills/british-english
```

## Usage

Once installed, Claude Code will automatically discover and use these skills when relevant:

- **plain-english** triggers when writing or editing prose, documentation, policies, or user-facing content
- **british-english** triggers when writing for British audiences, UK organisations, or when British English is requested

You can also invoke them explicitly:

```
/plain-english
/british-english
```

## Testing

The `tests/` directory contains application scenarios that verify Claude can find and correctly apply the guidance from each skill. These are reference skills (lookup tables and conventions), not discipline-enforcing skills, so they use retrieval and application tests rather than pressure scenarios.

Run manually by providing the test prompts to a Claude Code session with the skills installed.

## Research

The word lists, rules, and conventions in these skills were synthesised from research across 11 LLMs (via [Parliament of Owls](https://github.com/joelio/owl)) plus direct consultation of the GOV.UK Content Design Guide, Oxford International English spelling guides, and the Plain English Campaign's published materials.

## Licence

MIT. See [LICENSE](LICENSE).
