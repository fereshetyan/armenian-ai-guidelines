# Armenian Writing Guidelines for AI Agents (Հայերեն Գրագրության Ուղեցույցներ AI Համակարգերի Համար)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status: Experimental](https://img.shields.io/badge/Status-Experimental%20%2F%20Community%20Review-orange.svg)]()
[![Compatible with: Claude Code | Codex | Cursor | OpenCode](https://img.shields.io/badge/Compatible%20with-Claude%20Code%20%7C%20Codex%20%7C%20Cursor%20%7C%20OpenCode-blueviolet.svg)]()

> **Նախագծի նպատակը.** Բաց համայնքային նախաձեռնություն՝ ուղղված ժամանակակից AI գործակալների և LLM-ների (**Claude Code, OpenAI / Codex, Cursor, OpenCode**) կողմից հայերենի (հատկապես արևելահայերենի) գեներացման որակի, բնականության և տեխնիկական/պաշտոնական ճշգրտության բարելավմանը։

---

## ⚠️ Կարգավիճակը և Լեզվաբանական Փորձաքննությունը (Project Status & Disclaimer)

**Հայերեն**  
Սույն նախագիծը փորձարարական համայնքային նախաձեռնություն է (AI-assisted research)։ Ստեղծողը (maintainer) չի հանդիսանում մասնագետ-լեզվաբան կամ հայոց լեզվի ակադեմիական ուսուցիչ։ Ուղեցույցները մշակվել են AI գործիքների և գոյություն ունեցող հետազոտությունների համադրմամբ և չեն հավակնում լինել պաշտոնական ակադեմիական կանոններ։

Նախաձեռնությունը **բաց է համագործակցության համար**․ ողջունվում են հայերենի մասնագետների, ուսուցիչների, խմբագիրների, թարգմանիչների և լեզվաբանների (ներառյալ ՀՀ ԳԱԱ Հ. Աճառյանի անվան լեզվի ինստիտուտի և Լեզվի կոմիտեի ներկայացուցիչների) դիտարկումները, ուղղումները և առաջարկությունները (Pull Requests & Issues)։

**English**  
This project is an **experimental, AI-assisted community initiative** aimed at improving the quality of Eastern Armenian language generation across modern AI coding assistants and LLMs (**Claude Code, OpenAI/Codex, Cursor, OpenCode**).

The maintainer is not a professional linguist, and the guidelines have not yet undergone exhaustive academic review by institutional Armenian language authorities. Contributions, corrections, and reviews from Armenian linguists, teachers, editors, and native speakers are warmly welcome.

---

## 📌 Ինչ խնդիր է լուծում նախագիծը

Շատ AI մոդելներ (Claude, GPT-4o / Codex, Gemini) հայերեն գեներացնելիս հաճախ ստեղծում են անբնական տեքստեր՝
1. **Կաղապարային մեխանիկական թարգմանություն** ռուսերենից կամ անգլերենից։
2. **Արհեստական շարադասություն** (բայի/ստորոգյալի մեխանիկական տեղադրում նախադասության վերջում)։
3. **Կանցելյարային ավելորդ կլիշեներ** («տեղի է ունեցել իրականում», ռուսերեն «является»-ի կույր պատճենում)։
4. **Ոչ հարմար տերմինաբանություն** տեխնիկական և կիբեռանվտանգության ոլորտներում։

---

## 🚀 Ինտեգրումը տարբեր AI գործիքներում (Integration Guide)

Ուղեցույցները համատեղելի են բոլոր հիմնական AI գործակալների և զարգացման միջավայրերի հետ․

### 1. Claude Code / Anthropic
Ավելացրեք հղումը կամ տեքստը ձեր նախագծի `CLAUDE.md` ֆայլում կամ տեղադրեք Agent Skill ֆորմատով․
```sh
# Տեղադրում որպես Claude Code Skill
mkdir -p .claude/skills/
cp -r skills/armenian-writing .claude/skills/
```
Կամ պարզապես ձեր `CLAUDE.md` ֆայլում ներառեք հետևյալ տողը․
```markdown
## Armenian Writing Guidelines
Always follow the natural syntax, terminology, and tone rules defined in:
https://github.com/fereshetyan/armenian-ai-guidelines/blob/main/skills/armenian-writing/SKILL.md
```

### 2. OpenAI / Codex / ChatGPT (Custom Instructions & System Prompt)
Եթե աշխատում եք ChatGPT-ի, OpenAI API-ի կամ Codex-ի հետ, պատճենեք [`skills/armenian-writing/SKILL.md`](skills/armenian-writing/SKILL.md) ֆայլի հիմնական բովանդակությունը ձեր **Custom Instructions**-ում կամ System Prompt-ում։

### 3. Cursor
Ավելացրեք կանոնները ձեր նախագծի `.cursor/rules/armenian-writing.mdc` ֆայլում կամ `.cursorrules`․
```sh
mkdir -p .cursor/rules/
cp skills/armenian-writing/SKILL.md .cursor/rules/armenian-writing.mdc
```

### 4. OpenCode / Agentic Harnesses
```sh
# Գլոբալ կարգավորումներում
mkdir -p ~/.config/opencode/skills/
cp -r skills/armenian-writing ~/.config/opencode/skills/

# Կամ տեղային նախագծում
mkdir -p .opencode/skills/
cp -r skills/armenian-writing .opencode/skills/
```

---

## 📂 Պահոցի կառուցվածքը

- [`skills/armenian-writing/SKILL.md`](skills/armenian-writing/SKILL.md) — Ունիվերսալ համակարգային հրահանգ (Canonical System Prompt / Agent Skill):
- [`REVIEW.md`](REVIEW.md) — Կանոնների և առաջարկությունների ստուգման մատրիցա (`Research-supported`, `Normative-source-backed`, `Grammar-reference-backed`, `Editorial-guideline`):
- [`examples/`](examples/) — Կաղապարային vs բնական հայերենի օրինակներ և պաշտոնական ձևանմուշներ։
- [`fonts/`](fonts/) — ՀՀ Կառավարության N 1259-Ն որոշմամբ հաստատված պետական տառատեսակների տեղեկատվական ուղեցույց։

---

## 🤝 Ինչպե՞ս աջակցել (How to Contribute)

Եթե դուք լեզվաբան եք, ուսուցիչ, տեխնիկական խմբագիր կամ պարզապես նկատել եք սխալ կամ անբնական ձևակերպում՝
1. Բացեք **Issue**՝ նշելով խնդրահարույց արտահայտությունը և ձեր առաջարկած ճիշտ տարբերակը։
2. Ուղարկեք **Pull Request** [`skills/armenian-writing/SKILL.md`](skills/armenian-writing/SKILL.md) կամ [`examples/`](examples/) բաժիններում։
3. Օգնեք լրացնել կանոնների գիտական կամ բառարանային հիմնավորումները [`REVIEW.md`](REVIEW.md) ֆայլում։
