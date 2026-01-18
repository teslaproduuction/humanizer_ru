# Humanizer

A Claude Code skill that removes signs of AI-generated writing from text, making it sound more natural and human.

## Overview

Based on [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide, maintained by WikiProject AI Cleanup. This comprehensive guide comes from observations of thousands of instances of AI-generated text.

### Key Insight from Wikipedia

> "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases. It can simultaneously be a strength and a 'tell' for detecting AI-generated content."

## Patterns Detected

### Content Patterns
1. **Undue emphasis on significance** - "pivotal moment," "broader movement," "serves as a testament"
2. **Notability name-dropping** - Listing media outlets without context
3. **Superficial -ing analyses** - "highlighting," "ensuring," "showcasing" tacked onto sentences
4. **Promotional language** - "vibrant," "nestled," "breathtaking," "rich cultural heritage"
5. **Vague attributions** - "Industry experts believe," "Observers have cited"
6. **Formulaic challenges sections** - "Despite its... faces challenges..."

### Language Patterns
7. **AI vocabulary words** - Additionally, crucial, delve, enhance, fostering, garner, interplay, intricate, landscape, pivotal, showcase, tapestry, testament, underscore, vibrant
8. **Copula avoidance** - "serves as" instead of "is," "features" instead of "has"
9. **Negative parallelisms** - "It's not just X, it's Y"
10. **Rule of three** - Forcing everything into groups of three
11. **Elegant variation** - Excessive synonym cycling
12. **False ranges** - "from X to Y" where X and Y aren't on a scale

### Style Patterns
13. **Em dash overuse** - Multiple em dashes per paragraph
14. **Boldface overuse** - Mechanical emphasis of key terms
15. **Inline-header lists** - "**Topic:** Description of topic..."
16. **Title Case Headings** - Capitalizing All Main Words
17. **Emojis** - Decorating bullets and headings
18. **Curly quotation marks** - "..." instead of "..."

### Communication Patterns
19. **Chatbot artifacts** - "I hope this helps!", "Certainly!"
20. **Knowledge-cutoff disclaimers** - "While details are limited..."
21. **Sycophantic tone** - "Great question!", "You're absolutely right!"

### Filler and Hedging
22. **Filler phrases** - "In order to," "Due to the fact that"
23. **Excessive hedging** - "It could potentially possibly"
24. **Generic conclusions** - "The future looks bright"

## Installation

Copy the `SKILL.md` file to your Claude Code skills directory:

```bash
# Create skills directory if it doesn't exist
mkdir -p ~/.claude/skills/humanizer

# Copy the skill
cp SKILL.md ~/.claude/skills/humanizer/
```

## Usage

In Claude Code, invoke the skill:

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
> The new software update serves as a testament to the company's commitment to innovation. Moreover, it provides a seamless, intuitive, and powerful user experience—ensuring that users can accomplish their goals efficiently. It's not just an update, it's a revolution in how we think about productivity. Industry experts believe this will have a lasting impact on the entire sector, highlighting the company's pivotal role in the evolving technological landscape.

**After (Humanized):**
> The software update adds batch processing, keyboard shortcuts, and offline mode. Early feedback from beta testers has been positive, with most reporting faster task completion.

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) - The primary source for all patterns
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) - The Wikipedia project maintaining the guide

## Version History

- **2.0.0** - Complete rewrite based on raw Wikipedia article content with 24 pattern categories
- **1.0.0** - Initial release with 14 patterns from secondary sources

## License

MIT
