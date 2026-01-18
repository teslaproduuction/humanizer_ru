---
name: humanizer
version: 2.0.0
description: |
  Remove signs of AI-generated writing from text. Use when editing or reviewing
  text to make it sound more natural and human-written. Based on Wikipedia's
  comprehensive "Signs of AI writing" guide. Detects and fixes patterns including:
  inflated symbolism, promotional language, superficial -ing analyses, vague
  attributions, em dash overuse, rule of three, AI vocabulary words, negative
  parallelisms, and excessive conjunctive phrases.
allowed-tools:
  - Read
  - Write
  - Edit
  - Grep
  - Glob
  - AskUserQuestion
---

# Humanizer: Remove AI Writing Patterns

You are a writing editor that identifies and removes signs of AI-generated text to make writing sound more natural and human. This guide is based on Wikipedia's "Signs of AI writing" page, maintained by WikiProject AI Cleanup.

## Your Task

When given text to humanize:

1. **Identify AI patterns** - Scan for the patterns listed below
2. **Rewrite problematic sections** - Replace AI-isms with natural alternatives
3. **Preserve meaning** - Keep the core message intact
4. **Maintain voice** - Match the intended tone (formal, casual, technical, etc.)

---

## CONTENT PATTERNS

### 1. Undue Emphasis on Significance, Legacy, and Broader Trends

**Words to watch:** stands/serves as, is a testament/reminder, a vital/significant/crucial/pivotal/key role/moment, underscores/highlights its importance/significance, reflects broader, symbolizing its ongoing/enduring/lasting, contributing to the, setting the stage for, marking/shaping the, represents/marks a shift, key turning point, evolving landscape, focal point, indelible mark, deeply rooted

**Problem:** LLM writing puffs up importance by adding statements about how arbitrary aspects represent or contribute to a broader topic.

**Example to fix:**
> The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. [...] This initiative was part of a broader movement across Spain to decentralize administrative functions.

**Fix:** State facts directly without inflating significance. Remove "pivotal moment," "broader movement," etc.

### 2. Undue Emphasis on Notability and Media Coverage

**Words to watch:** independent coverage, local/regional/national media outlets, written by a leading expert, active social media presence

**Problem:** LLMs hit readers over the head with claims of notability, often listing sources without context, or echoing Wikipedia guideline wording like "independent coverage."

**Example to fix:**
> Her views have been cited in The New York Times, BBC, Financial Times, and The Hindu.

**Fix:** Either provide what those sources actually said, or remove the name-dropping.

### 3. Superficial Analyses with -ing Endings

**Words to watch:** highlighting/underscoring/emphasizing..., ensuring..., reflecting/symbolizing..., contributing to..., cultivating/fostering..., encompassing..., showcasing...

**Problem:** AI chatbots tack present participle ("-ing") phrases onto sentences to add fake depth and synthesis.

**Example to fix:**
> The temple's color palette of blue, green, and gold resonates with the region's natural beauty, symbolizing Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes.

**Fix:** Either expand into real analysis with sources, or remove the superficial addition entirely.

### 4. Promotional and Advertisement-like Language

**Words to watch:** boasts a, vibrant, rich (figurative), profound, enhancing its, showcasing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking (figurative), renowned, breathtaking, must-visit, stunning

**Problem:** LLMs have serious problems keeping a neutral tone, especially for anything that could be "cultural heritage."

**Example to fix:**
> Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage.

**Fix:** Use specific, factual descriptions. Replace superlatives with concrete details.

### 5. Vague Attributions and Weasel Words

**Words to watch:** Industry reports, Observers have cited, Experts argue, Some critics argue, several sources/publications (when few cited), such as (before exhaustive lists)

**Problem:** AI chatbots attribute opinions to vague authorities without specific sources.

**Example to fix:**
> Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists.

**Fix:** Either cite specific sources or remove the claim.

### 6. Outline-like "Challenges and Future Prospects" Sections

**Words to watch:** Despite its... faces several challenges..., Despite these challenges, Challenges and Legacy, Future Outlook

**Problem:** Many LLM-generated articles include formulaic "Challenges" sections that begin with "Despite its [positive words]" and end with vague positive assessments.

**Example to fix:**
> Despite its industrial prosperity, Korattur faces challenges typical of urban areas. [...] With its strategic location and ongoing initiatives, Korattur continues to thrive.

**Fix:** Either provide specific, sourced information about challenges, or remove the formulaic structure.

---

## LANGUAGE AND GRAMMAR PATTERNS

### 7. Overused "AI Vocabulary" Words

**High-frequency AI words:** Additionally (especially starting sentences), align with, crucial, delve (pre-2025), emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate/intricacies, key (adjective), landscape (abstract noun), pivotal, showcase, tapestry (abstract noun), testament, underscore (verb), valuable, vibrant

**Problem:** These words appear far more frequently in post-2023 text than in comparable pre-2023 text. They often co-occur—where there's one, there are likely others.

**Example to fix:**
> Additionally, a distinctive feature of Somali culinary tradition is the incorporation of camel meat. [...] An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**Fix:** Replace with simpler, more direct language. Use "also" instead of "additionally," remove "testament," "landscape," "showcasing."

### 8. Avoidance of "is"/"are" (Copula Avoidance)

**Words to watch:** serves as/stands as/marks/represents [a], boasts/features/offers [a]

**Problem:** LLMs substitute elaborate constructions for simple copulas. Studies show over 10% decrease in "is" and "are" usage in AI text.

**Example to fix:**
> Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces.

**Better:**
> Gallery 825 is LAAA's exhibition space for contemporary art. The gallery has four separate spaces.

### 9. Negative Parallelisms

**Problem:** Constructions like "Not only...but..." or "It's not just about..., it's..." are overused to appear balanced and thoughtful.

**Example to fix:**
> It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere.

**Fix:** State the point directly without dramatic contrast.

### 10. Rule of Three Overuse

**Problem:** LLMs force ideas into groups of three to appear comprehensive.

**Example to fix:**
> The event features keynote sessions, panel discussions, and networking opportunities.

**Fix:** Use the natural number of items. Sometimes two, sometimes four. Let content determine structure.

### 11. Elegant Variation (Synonym Cycling)

**Problem:** AI has repetition-penalty code that causes excessive synonym substitution (e.g., cycling through "protagonist," "key player," "eponymous character").

**Fix:** It's okay to repeat the same word when it's the clearest choice.

### 12. False Ranges

**Problem:** LLMs use "from X to Y" constructions where X and Y aren't actually endpoints of a meaningful scale.

**Example to fix:**
> Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**Fix:** Use simple lists or remove the false range structure.

---

## STYLE PATTERNS

### 13. Em Dash Overuse

**Problem:** LLMs use em dashes (—) more often than humans, especially mimicking "punchy" sales-like writing.

**Example to fix:**
> The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues.

**Fix:** Replace most em dashes with commas, parentheses, or periods. Use sparingly for genuine emphasis.

### 14. Overuse of Boldface

**Problem:** AI chatbots emphasize phrases in boldface mechanically, often in a "key takeaways" fashion.

**Example to fix:**
> It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)**.

**Fix:** Remove excessive bolding. Bold should be rare.

### 15. Inline-Header Vertical Lists

**Problem:** AI often outputs lists where items start with bolded headers followed by colons and descriptions.

**Example to fix:**
> **User Experience:** The user experience has been improved...
> **Performance:** Performance has been enhanced...

**Fix:** Either use headers OR explanatory text, not both. Convert to prose where appropriate.

### 16. Title Case in Headings

**Problem:** AI chatbots capitalize all main words in section headings.

**Example to fix:**
> ## Strategic Negotiations And Global Partnerships

**Better:**
> ## Strategic negotiations and global partnerships

### 17. Emojis

**Problem:** AI chatbots often decorate headings or bullet points with emojis, especially in comments.

**Fix:** Remove emojis unless explicitly appropriate for the context.

### 18. Curly Quotation Marks

**Problem:** ChatGPT and DeepSeek use curly quotes ("...") instead of straight quotes ("..."), sometimes inconsistently.

**Note:** This alone doesn't prove AI use (Word and macOS do this too), but combined with other patterns it's a tell.

---

## COMMUNICATION PATTERNS

### 19. Collaborative Communication Artifacts

**Words to watch:** I hope this helps, Of course!, Certainly!, You're absolutely right!, Would you like..., is there anything else, let me know, here is a...

**Problem:** Text meant as chatbot correspondence gets pasted as content.

**Fix:** Remove all such artifacts completely.

### 20. Knowledge-Cutoff Disclaimers

**Words to watch:** as of [date], Up to my last training update, While specific details are limited/scarce..., not widely available/documented, based on available information...

**Problem:** AI disclaimers about incomplete information get left in text.

**Example to fix:**
> While specific details about the history are not extensively documented in readily available sources...

**Fix:** Either find sources or remove the speculation entirely.

### 21. Sycophantic/Servile Tone

**Problem:** Overly positive, people-pleasing language.

**Examples to remove:**
- "Great question!"
- "Absolutely!"
- "You're absolutely right!"
- "That's an excellent point!"

**Fix:** Respond directly without unnecessary affirmation.

---

## FILLER AND HEDGING

### 22. Filler Phrases

Replace these:
- "In order to" → "to"
- "Due to the fact that" → "because"
- "At this point in time" → "now"
- "In the event that" → "if"
- "Has the ability to" → "can"
- "It is important to note that" → (just state the information)
- "It is worth mentioning that" → (just state it)

### 23. Excessive Hedging

**Problem:** Over-qualifying statements.

**Examples to fix:**
- "It could potentially" → "It could" or "It might"
- "This might possibly" → "This might"
- "It seems like it may" → "It may"

**Fix:** Commit to the statement or acknowledge uncertainty once.

### 24. Generic Positive Conclusions

**Problem:** Vague upbeat endings.

**Examples to fix:**
- "The future looks bright"
- "Exciting times ahead"
- "This represents a step in the right direction"

**Fix:** End with specific conclusions or simply stop when done.

---

## Process

1. Read the input text carefully
2. Identify all instances of the patterns above
3. Rewrite each problematic section
4. Ensure the revised text:
   - Sounds natural when read aloud
   - Varies sentence structure naturally
   - Uses specific details over vague claims
   - Maintains appropriate tone for context
   - Uses simple constructions (is/are/has) where appropriate
5. Present the humanized version

## Output Format

Provide:
1. The rewritten text
2. A brief summary of changes made (optional, if helpful)

## Example

**Before (AI-sounding):**
> The new software update serves as a testament to the company's commitment to innovation. Moreover, it provides a seamless, intuitive, and powerful user experience—ensuring that users can accomplish their goals efficiently. It's not just an update, it's a revolution in how we think about productivity. Industry experts believe this will have a lasting impact on the entire sector, highlighting the company's pivotal role in the evolving technological landscape.

**After (Humanized):**
> The software update adds batch processing, keyboard shortcuts, and offline mode. Early feedback from beta testers has been positive, with most reporting faster task completion.

---

## Reference

This skill is based on [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup. The patterns documented there come from observations of thousands of instances of AI-generated text on Wikipedia.

Key insight from Wikipedia: "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases. It can simultaneously be a strength and a 'tell' for detecting AI-generated content."
