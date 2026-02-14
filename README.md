# Humanizer

A Claude Desktop plugin that removes signs of AI-generated writing from text, making it sound more natural and human. Supports English and Russian.

**[Russian version / Русская версия](README_RU.md)**

## Installation

### As a Claude Desktop plugin (recommended)

```bash
claude plugin add github:teslaproduuction/humanizer_ru
```

### Manual installation (legacy Claude Code skills)

```bash
mkdir -p ~/.claude/skills/humanizer
git clone https://github.com/teslaproduuction/humanizer_ru.git /tmp/humanizer_ru
cp /tmp/humanizer_ru/skills/humanizer/SKILL.md ~/.claude/skills/humanizer/
cp -r /tmp/humanizer_ru/skills/humanizer-ru ~/.claude/skills/
```

## Usage

In Claude Desktop or Claude Code, invoke the commands:

```
/humanizer [paste your text here]
```

```
/humanizer-ru [вставьте ваш текст на русском]
```

Or ask Claude directly:

```
Please humanize this text: [your text]
Очеловечь этот текст: [ваш текст]
```

## Overview

Based on [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide, maintained by WikiProject AI Cleanup. This comprehensive guide comes from observations of thousands of instances of AI-generated text.

### Key insight

> "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."

## 24 Patterns detected (English)

### Content patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 1 | **Significance inflation** | "marking a pivotal moment in the evolution of..." | "was established in 1989 to collect regional statistics" |
| 2 | **Notability name-dropping** | "cited in NYT, BBC, FT, and The Hindu" | "In a 2024 NYT interview, she argued..." |
| 3 | **Superficial -ing analyses** | "symbolizing... reflecting... showcasing..." | Remove or expand with actual sources |
| 4 | **Promotional language** | "nestled within the breathtaking region" | "is a town in the Gonder region" |
| 5 | **Vague attributions** | "Experts believe it plays a crucial role" | "according to a 2019 survey by..." |
| 6 | **Formulaic challenges** | "Despite challenges... continues to thrive" | Specific facts about actual challenges |

### Language patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 7 | **AI vocabulary** | "Additionally... testament... landscape... showcasing" | "also... remain common" |
| 8 | **Copula avoidance** | "serves as... features... boasts" | "is... has" |
| 9 | **Negative parallelisms** | "It's not just X, it's Y" | State the point directly |
| 10 | **Rule of three** | "innovation, inspiration, and insights" | Use natural number of items |
| 11 | **Synonym cycling** | "protagonist... main character... central figure... hero" | "protagonist" (repeat when clearest) |
| 12 | **False ranges** | "from the Big Bang to dark matter" | List topics directly |

### Style patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 13 | **Em dash overuse** | "institutions--not the people--yet this continues--" | Use commas or periods |
| 14 | **Boldface overuse** | "**OKRs**, **KPIs**, **BMC**" | "OKRs, KPIs, BMC" |
| 15 | **Inline-header lists** | "**Performance:** Performance improved" | Convert to prose |
| 16 | **Title Case Headings** | "Strategic Negotiations And Partnerships" | "Strategic negotiations and partnerships" |
| 17 | **Emojis** | "Launch Phase: Key Insight:" | Remove emojis |
| 18 | **Curly quotes** | `said \u201cthe project\u201d` | `said "the project"` |

### Communication patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 19 | **Chatbot artifacts** | "I hope this helps! Let me know if..." | Remove entirely |
| 20 | **Cutoff disclaimers** | "While details are limited in available sources..." | Find sources or remove |
| 21 | **Sycophantic tone** | "Great question! You're absolutely right!" | Respond directly |

### Filler and hedging

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 22 | **Filler phrases** | "In order to", "Due to the fact that" | "To", "Because" |
| 23 | **Excessive hedging** | "could potentially possibly" | "may" |
| 24 | **Generic conclusions** | "The future looks bright" | Specific plans or facts |

## Russian language support (25 patterns)

The Russian skill includes all patterns above adapted for Russian, plus unique patterns:

- **Verbal nouns** - the primary marker of AI text in Russian
- **Bureaucratic cliches** - "in the present time", "within the framework of"
- **Genitive case chains** - uniquely Russian readability problem
- **Passive constructions** - hiding the actor
- **Unnecessary foreign words** - borrowings where Russian alternatives exist
- **Template transitions** - "It is important to note that..."
- **Hard prohibitions** - automatic rejection of negative parallelisms, long dashes, rhetorical questions

See [full Russian documentation](README_RU.md)

## Plugin structure

```
.claude-plugin/plugin.json    Plugin manifest
skills/humanizer/SKILL.md     English skill (24 patterns)
skills/humanizer-ru/SKILL.md  Russian skill (25 patterns)
commands/humanizer.md          /humanizer slash command
commands/humanizer-ru.md       /humanizer-ru slash command
```

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup)
- [smixs/humanizer-ru](https://github.com/smixs/humanizer-ru) - additional Russian patterns
- [blader/humanizer](https://github.com/blader/humanizer) - original project

## Version history

- **3.0.0** - Converted to Claude Desktop cowork plugin, incorporated improvements from smixs/humanizer-ru (genitive chains, passive voice, foreign words, template transitions, hard prohibitions, style rules)
- **2.1.1** - Fixed pattern #18 example (curly quotes vs straight quotes)
- **2.1.0** - Added before/after examples for all 24 patterns
- **2.0.0** - Complete rewrite based on raw Wikipedia article content
- **1.0.0** - Initial release

## License

MIT
