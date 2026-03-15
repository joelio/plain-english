<p align="center">
  <img src="logo.svg" alt="Plain English" width="400">
</p>

# Plain English — Claude Code Writing Skills

Three [Claude Code skills](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills/overview) that help Claude write clearly, consistently, and naturally.

They stack together: **plain-english** for clarity, **british-english** for consistency, and **natural-writing** to strip out the AI slop.

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

### `natural-writing`

Removes AI writing patterns that make text sound machine-generated. Covers em dash elimination, banned words (delve, leverage, robust, crucial, and 30+ more), banned phrases ("In today's fast-paced world", "It's worth noting", "Great question!"), structural de-AIification (no bold-colon-explanation bullets, no sycophantic openings, no formulaic enumeration), and tone rules (have an opinion, be specific, vary rhythm).

Based on research from:
- [Max Planck Institute study on AI word frequency](https://futurism.com/the-byte/ai-overuses-specific-words) (2025)
- Community consensus from writing and copywriting forums
- [Blake Stockton's Red Flag Words analysis](https://www.blakestockton.com/red-flag-words/)
- [Plagiarism Today's em dash analysis](https://www.plagiarismtoday.com/2025/06/26/em-dashes-hyphens-and-spotting-ai-writing/)

## Installation

Copy the skill directories into your Claude Code skills folder:

```bash
# Clone
git clone https://github.com/joelio/plain-english.git

# Copy all skills
cp -r plain-english/skills/plain-english ~/.claude/skills/
cp -r plain-english/skills/british-english ~/.claude/skills/
cp -r plain-english/skills/natural-writing ~/.claude/skills/
```

Or symlink them:

```bash
cd plain-english
for skill in skills/*/; do
  ln -s "$(pwd)/$skill" ~/.claude/skills/"$(basename $skill)"
done
```

## Usage

Once installed, Claude Code will automatically discover and use these skills when relevant:

- **plain-english** triggers when writing or editing prose, documentation, policies, or user-facing content
- **british-english** triggers when writing for British audiences, UK organisations, or when British English is requested
- **natural-writing** triggers when writing any content that should sound human-written, or when asked to remove AI-sounding language

You can also invoke them explicitly:

```
/plain-english
/british-english
/natural-writing
```

## Testing

The `tests/` directory contains application scenarios that verify Claude can find and correctly apply the guidance from each skill. These are reference skills (lookup tables and conventions), not discipline-enforcing skills, so they use retrieval and application tests rather than pressure scenarios.

Run manually by providing the test prompts to a Claude Code session with the skills installed.

## Research

The word lists, rules, and conventions in these skills were synthesised from research across 11 LLMs (via [Parliament of Owls](https://github.com/joelio/owl)) plus direct consultation of the GOV.UK Content Design Guide, Oxford International English spelling guides, the Plain English Campaign's published materials, and AI writing pattern research.

## Licence

MIT. See [LICENSE](LICENSE).
