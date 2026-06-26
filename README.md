<div align="center">

# 🫀 Humanizer

**Claude Code плагин для удаления признаков ИИ-генерации из текста**

**Claude Code plugin to remove signs of AI-generated writing from text**

[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-2-blue?style=for-the-badge&logo=anthropic&logoColor=white)](skills/)
[![Patterns EN](https://img.shields.io/badge/patterns_EN-24-orange?style=for-the-badge)](skills/humanizer/SKILL.md)
[![Patterns RU](https://img.shields.io/badge/patterns_RU-25-red?style=for-the-badge)](skills/humanizer-ru/SKILL.md)

</div>

---

<details open>
<summary><strong>🇷🇺 Русский</strong></summary>

Плагин для Claude Code, который очищает тексты от характерных паттернов ИИ-генерации. Поддерживает английский и русский языки. Основан на руководстве [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) от WikiProject AI Cleanup.

> «LLM использует статистические алгоритмы, чтобы угадать, что должно идти дальше. Результат стремится к наиболее статистически вероятному варианту, подходящему для максимально широкого круга случаев.»

### Установка

```bash
claude plugin add github:teslaproduuction/humanizer_ru
```

<details>
<summary>Ручная установка (legacy)</summary>

```bash
mkdir -p ~/.claude/skills/humanizer-ru
git clone https://github.com/teslaproduuction/humanizer_ru.git /tmp/humanizer_ru
cp /tmp/humanizer_ru/skills/humanizer-ru/SKILL.md ~/.claude/skills/humanizer-ru/
```

</details>

### Использование

```
/humanizer-ru [вставьте ваш текст]
```

Или спросите Claude напрямую:

```
Очеловечь этот текст: [текст]
Убери следы ИИ: [текст]
Перепиши по-человечески: [текст]
```

### Пример

**До:**
> Следует отметить, что в современных условиях цифровизации бизнеса наблюдается устойчивая тенденция к повышению эффективности взаимодействия между участниками рынка. Данный подход является ключевым фактором успешного развития.

**После:**
> Бизнес автоматизирует процессы. По данным за 2025 год, компании, внедрившие CRM, сократили время обработки заявок на 30%. Большинство из них окупили затраты за год.

### 25 паттернов AI-текста на русском

#### Содержание (1–6)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 1 | **Преувеличенная значимость** | «переломный момент» | «появился» |
| 2 | **Расплывчатые слова** | «в настоящее время» | «сейчас», «сегодня» |
| 3 | **Поверхностный анализ** | «символизируя развитие отношений...» | конкретная формулировка |
| 4 | **Избегание «есть/является»** | «выступает, представляет собой» | «есть», «—» |
| 5 | **Туманные ссылки** | «эксперты утверждают» | «по данным [источник]» |
| 6 | **Шаблонные противопоставления** | «несмотря на трудности, продолжает» | конкретные факты |

#### AI-лексика и канцеляризмы (7–13)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 7 | **Отглагольные существительные** | «осуществление деятельности» | «работа» |
| 8 | **Генитивные цепочки** | «повышение уровня качества обслуживания» | «лучше обслуживать» |
| 9 | **Пассивные конструкции** | «было принято решение о проведении» | «решили провести» |
| 10 | **Слова-паразиты** | «данный, осуществлять, являться» | «этот, делать, быть» |
| 11 | **Weasel Words** | «по мнению некоторых» | «по мнению [источник]» |
| 12 | **Шаблонные переходы** | «следует отметить, что...» | убрать вводную |
| 13 | **Лишние иностранные слова** | «имплементация» | «внедрение» |

#### Структура (14–17)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 14 | **Отрицательный параллелизм** | «не просто X, а Y» | сформулируй прямо |
| 15 | **Правило трёх** | «инновации, вдохновение и идеи» | естественное число |
| 16 | **Synonym Cycling** | «исследователь... главный персонаж... протагонист» | одно слово |
| 17 | **Ложные диапазоны** | «от Пушкина до нейросетей» | перечисли напрямую |

#### Стиль (18–20)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 18 | **Злоупотребление тире** | «учреждения — не люди — однако —» | запятые или точки |
| 19 | **Жирный + список + жирный** | **«Производительность:** улучшилась» | просто текст |
| 20 | **Кавычки** | `сказал «проект»` | `сказал "проект"` |

#### Чат и маркетинг (21–22)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 21 | **Артефакты чат-бота** | «Надеюсь, помог! Дайте знать!» | убрать полностью |
| 22 | **Подхалимский тон** | «Отличный вопрос! Совершенно верно!» | ответить напрямую |

#### Вода и перестраховка (23–25)

| # | Паттерн | До | После |
|---|---------|-----|-------|
| 23 | **Слова-наполнители** | «в целях того», «в связи с тем что» | «чтобы», «потому что» |
| 24 | **Перестраховка** | «может потенциально, возможно» | «может» |
| 25 | **Общий вывод** | «будущее выглядит светлым» | конкретный прогноз |

#### Жёсткие запреты

- «не просто X, а Y» / «не только X, но и Y»
- Длинное тире «—» (используй короткое «–»)
- Риторические вопросы
- Подхалимские вступления

</details>

---

<details>
<summary><strong>🇬🇧 English</strong></summary>

Plugin for Claude Code that removes AI writing patterns from text. Supports English and Russian. Based on [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide by WikiProject AI Cleanup.

> "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."

### Install

```bash
claude plugin add github:teslaproduuction/humanizer_ru
```

<details>
<summary>Manual install (legacy)</summary>

```bash
mkdir -p ~/.claude/skills/humanizer
git clone https://github.com/teslaproduuction/humanizer_ru.git /tmp/humanizer_ru
cp /tmp/humanizer_ru/skills/humanizer/SKILL.md ~/.claude/skills/humanizer/
```

</details>

### Usage

```
/humanizer [paste your text here]
```

Or ask Claude directly:

```
Please humanize this text: [your text]
Remove AI signs from: [your text]
```

### 24 Patterns (English)

#### Content patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 1 | **Significance inflation** | "marking a pivotal moment in the evolution of..." | "was established in 1989 to collect regional statistics" |
| 2 | **Notability name-dropping** | "cited in NYT, BBC, FT, and The Hindu" | "In a 2024 NYT interview, she argued..." |
| 3 | **Superficial -ing analyses** | "symbolizing... reflecting... showcasing..." | Remove or expand with actual sources |
| 4 | **Promotional language** | "nestled within the breathtaking region" | "is a town in the Gonder region" |
| 5 | **Vague attributions** | "Experts believe it plays a crucial role" | "according to a 2019 survey by..." |
| 6 | **Formulaic challenges** | "Despite challenges... continues to thrive" | Specific facts about actual challenges |

#### Language patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 7 | **AI vocabulary** | "Additionally... testament... landscape... showcasing" | "also... remain common" |
| 8 | **Copula avoidance** | "serves as... features... boasts" | "is... has" |
| 9 | **Negative parallelisms** | "It's not just X, it's Y" | State the point directly |
| 10 | **Rule of three** | "innovation, inspiration, and insights" | Use natural number of items |
| 11 | **Synonym cycling** | "protagonist... main character... central figure... hero" | "protagonist" (repeat when clearest) |
| 12 | **False ranges** | "from the Big Bang to dark matter" | List topics directly |

#### Style patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 13 | **Em dash overuse** | "institutions--not the people--yet this continues--" | Use commas or periods |
| 14 | **Boldface overuse** | `**OKRs**, **KPIs**, **BMC**` | "OKRs, KPIs, BMC" |
| 15 | **Inline-header lists** | `**Performance:** Performance improved` | Convert to prose |
| 16 | **Title Case Headings** | "Strategic Negotiations And Partnerships" | "Strategic negotiations and partnerships" |
| 17 | **Emojis** | "Launch Phase: Key Insight:" | Remove emojis |
| 18 | **Curly quotes** | `said "the project"` | `said "the project"` |

#### Communication patterns

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 19 | **Chatbot artifacts** | "I hope this helps! Let me know if..." | Remove entirely |
| 20 | **Cutoff disclaimers** | "While details are limited in available sources..." | Find sources or remove |
| 21 | **Sycophantic tone** | "Great question! You're absolutely right!" | Respond directly |

#### Filler and hedging

| # | Pattern | Before | After |
|---|---------|--------|-------|
| 22 | **Filler phrases** | "In order to", "Due to the fact that" | "To", "Because" |
| 23 | **Excessive hedging** | "could potentially possibly" | "may" |
| 24 | **Generic conclusions** | "The future looks bright" | Specific plans or facts |

</details>

---

## Структура / Structure

```
.claude-plugin/plugin.json    Plugin manifest
skills/humanizer/SKILL.md     English skill (24 patterns)
skills/humanizer-ru/SKILL.md  Russian skill (25 patterns)
commands/humanizer.md          /humanizer command
commands/humanizer-ru.md       /humanizer-ru command
```

## Источники / References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup)
- [smixs/humanizer-ru](https://github.com/smixs/humanizer-ru) — дополнительные русские паттерны
- [blader/humanizer](https://github.com/blader/humanizer) — оригинальный проект

## История версий / Changelog

- **3.0.0** — Конвертация в Claude Desktop plugin, улучшения из smixs/humanizer-ru (генитивные цепочки, пассивный залог, иностранные слова, шаблонные переходы, жёсткие запреты)
- **2.1.1** — Исправлен пример паттерна #18
- **2.1.0** — Before/after примеры для всех 24 паттернов
- **2.0.0** — Полная переработка на основе Wikipedia
- **1.0.0** — Первый релиз

## Лицензия / License

MIT
