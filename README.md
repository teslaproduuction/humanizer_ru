# Humanizer

A Claude Code skill that removes signs of AI-generated writing from text, making it sound more natural and human.

## Overview

Based on Wikipedia's "[Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)" guide, this skill identifies and fixes common patterns that make text sound AI-generated:

- Inflated symbolism ("serves as a testament to", "watershed moment")
- Promotional language ("breathtaking", "cutting-edge", "game-changing")
- Overused conjunctive phrases ("Moreover", "Furthermore", "Additionally")
- Em dash overuse
- Rule of three forcing
- Superficial -ing endings ("...ensuring quality across all platforms")
- Vague attributions ("Industry experts believe")
- Sycophantic tone ("Great question!", "Absolutely!")
- And more...

## Installation

Copy the `SKILL.md` file to your Claude Code skills directory:

```bash
# Create skills directory if it doesn't exist
mkdir -p ~/.claude/skills/humanizer

# Copy the skill
cp SKILL.md ~/.claude/skills/humanizer/
```

## Usage

In Claude Code, you can invoke the skill directly:

```
/humanizer

[paste your text here]
```

Or reference it when asking Claude to edit text:

```
Please humanize this text: [your text]
```

## Example

**Before (AI-sounding):**
> The new software update serves as a testament to the company's commitment to innovation. Moreover, it provides a seamless, intuitive, and powerful user experience—ensuring that users can accomplish their goals efficiently. It's not just an update, it's a revolution in how we think about productivity.

**After (Humanized):**
> The software update adds three features users requested: batch processing, keyboard shortcuts, and offline mode. Early feedback from the beta group has been positive, with most users reporting faster task completion.

## Patterns Detected

| Pattern | Example | Problem |
|---------|---------|---------|
| Inflated Symbolism | "plays a vital role" | Overstates importance |
| Promotional Language | "stunning natural beauty" | Sales-pitch tone |
| Editorializing | "It's important to note" | Unnecessary commentary |
| Conjunctive Overuse | "Moreover", "Furthermore" | Padding |
| Em Dash Overuse | Multiple — per paragraph | Mimics "punchy" copywriting |
| Rule of Three | "fast, efficient, and reliable" | Forced structure |
| -ing Endings | "...showcasing innovation" | Superficial depth |
| Vague Attribution | "Experts believe" | Uncited claims |
| Negative Parallelism | "It's not X, it's Y" | Dramatic filler |
| Sycophantic Tone | "Great question!" | Over-affirmation |

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [The best guide to spotting AI writing comes from Wikipedia - TechCrunch](https://techcrunch.com/2025/11/20/the-best-guide-to-spotting-ai-writing-comes-from-wikipedia/)
- [Don't Write Like AI: 10 Takeaways from Wikipedia's Signs of AI Writing](https://www.blakestockton.com/takeaways-from-wikipedias-signs-of-ai-writing-2/)
- [Here's a handy guide to help you spot AI writing - Literary Hub](https://lithub.com/heres-a-handy-guide-to-help-you-spot-ai-writing/)

## License

MIT
