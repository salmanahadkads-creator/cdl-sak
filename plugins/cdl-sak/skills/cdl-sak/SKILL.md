---
name: cdl-sak
description: "Content design rules from Content Design London, the Readability Guidelines and Salman's house rules, for auditing or rewriting copy when Salman says CDL."
---

# cdl-sak

Content Design London defines content design as "answering a user need in the best way for the user to consume it." Source: [What is content design?](https://contentdesign.london/blog/what-is-content-design)

This skill triggers on request, not automatically. Salman says "CDL" or similar. That is the signal.

---

## Sources

Every rule in this skill carries one of three tags. Put the tag on every flag you raise.

- **[CDL]** Guidance published on contentdesign.london. Every rule is in the "Content Design London guidance" table below, next to the page it came from.
- **[RG]** The Readability Guidelines, a project led by Content Design London. Every rule is in the "Readability Guidelines" table below, next to the page it came from.
- **[House]** Salman's own rules. Each one traces to something he asked for. The last section lists where.

Three limits on attribution:

1. Never tag a rule [CDL] or [RG] unless it is in one of those two tables. If a rule is not there, it is a house rule or it is not a rule.
2. Never add a rule from memory. A new [CDL] or [RG] rule needs the page it came from, read directly.
3. The book *Content Design* by Sarah Winters and Rachel Edwards was not available when this skill was written. Nothing here is attributed to the book except two excerpts that CDL published on its own site and labeled as coming from it.

When sources disagree, the house rule wins, and the tables say where that happens.

---

## Step 0: Ask three things first. Never skip this.

Before writing or reviewing a single line, ask these in one short message, in this order, and wait:

1. **Audit or rewrite?** An audit lists the sentences that break a rule, names the rule and its source, and changes nothing. A rewrite scores the copy, lets Salman pick how much to change, previews three directions, then rewrites.
2. **Who is this for?** A specific person, not a category. "Hiring managers at design studios" beats "our audience."
3. **What do they need to do after reading it?** Decide, buy, apply, understand enough to explain it to someone else, nothing at all.

Skip question 1 when Salman has already said "audit" or "rewrite," or when there is no existing copy and he wants something written from scratch. Treat "review" and "check" as ambiguous and ask.

If Salman cannot answer questions 2 and 3, propose the most likely audience and task, state it as an explicit assumption at the top of your output, and proceed. Never silently invent one.

CDL writes the same two answers as a user story: "As a [person in a particular role], I want to [perform an action or find something out], so that [I can achieve my goal]." [CDL] Use that form when it helps Salman answer.

Everything downstream is judged against these answers.

**Audit mode** runs the scoring in "Which copy needs rewriting?", then jumps to "Audit output." It skips the scale question, the preview, and every rewrite step.

**Rewrite mode** runs every step in order.

---

## Do not rewrite for the sake of it [House]

This rule is for Claude. When Salman gives you a sentence, a rewrite is not the default answer.

- **Check it first.** Run the sentence against the rules in this skill.
- **If it breaks no rule, say so and leave it alone.** "This is fine as written" is a complete answer. Do not offer an alternative version, a polish, or a "you could also."
- **If it breaks a rule, fix only that.** Name the rule, change the part that breaks it, and keep the rest of his wording.
- **Do not rewrite your own rewrite.** If Salman sends back a sentence you already fixed, check it again. If it now passes, tell him it passes.
- **A different wording is not a better one.** A change needs a rule behind it. Taste alone is not a reason.
- **Rewrite in full only when he asks for a rewrite,** or when the passage scores past the level he chose.

Why: every unneeded rewrite costs Salman a decision, replaces words he chose, and can add a new problem to copy that had none. CDL makes a related point about effort. It asks whether the effort is proportionate to the outcome, and notes that extra work can add very little to a page that already performs well. [CDL]

---

## Which copy needs rewriting?

Do not rewrite everything. Score each passage first, let Salman choose how much to rewrite, and leave everything outside that level exactly as written. A passage is one interface string or one paragraph of prose.

The score counts how many of this skill's rules a passage breaks, scaled to its length. It is a triage tool.

### Fail on sight

These get fixed in any passage, whatever its score. Fix only the offending part and leave the rest of the passage alone.

- **An em dash.** [House, RG] Swap in a comma or a period, or restructure the sentence.
- **"Not this, but that."** [House] A contrast the reader never proposed. Keep the positive half. The test is under "Defining a thing by what it is not."

### Scored tells

Count each occurrence in the passage. A single sentence can break several rules. Count each one.

| Points | Tell | Source |
|---|---|---|
| 3 | Aphorism or design maxim. A sentence that restates the one before it. Craft detail only the maker would care about. | House |
| 3 | A teaser, wordplay, or question heading. | House, RG, CDL |
| 2 | Trailing tail. Two sentences that could be one. | House |
| 2 | Link or button text such as "click here" or "more information." A mention of age, gender, a condition, heritage, or nationality that the task does not need. "Suffers from" or "struggle with" about a person. | RG |
| 1 | A sentence over 35 words. | House |
| 1 | A sentence with three or more commas, not counting commas in numbers. | House |
| 1 | A passage averaging over 15 words a sentence, counted once. | RG |
| 1 | Banned word. | House, RG |
| 1 | Passive voice with no reason. | House, CDL |
| 1 | Metaphor or idiom in explanatory copy. | RG |
| 1 | Title Case, or a whole word in capitals. | House, RG |
| 1 | Uniform rhythm, counted once: four or more sentences where the longest is under twice the length of the shortest. A number under 10 written as a numeral, or a number of 10 or more written as a word. | House |
| 1 | Any other break of a rule in the Readability Guidelines table. | RG |
| 1 | Any other break of a rule in the Content Design London guidance table. | CDL |

Negative contractions ("don't," "can't") break an RG rule that Salman chose not to enforce. Note them in an audit. Do not score them.

**Score = points ÷ words × 100.** Treat anything under 50 words as 50. Two trailing tails and one banned word in a 62-word paragraph is 5 points, so 5 ÷ 62 × 100 = 8.1.

### Audit output

In audit mode, this is the whole deliverable. Stop after it.

Flag every sentence that breaks a rule in a passage scoring 3 or more, plus every fail-on-sight problem anywhere. Report them in one table, ranked by passage score, highest first:

| Where | Sentence | Rules broken | Source | Passage score |
|---|---|---|---|---|
| `Hero.tsx:14` | "Leverage our robust platform to elevate growth." | 3 banned words (leverage, robust, elevate) | House, RG | 6.0 |
| About, paragraph 2 | "Three cuts ship to the browser, self-hosted." | Trailing tail | House | 4.0 |

- **Where** is `file:line` for code, or the section and paragraph number for prose.
- **Sentence** is quoted exactly as written.
- **Rules broken** names each rule in a few words. Name the rule, not the fix.
- **Source** is House, RG, or CDL, per rule. For RG and CDL, the rule must be in the tables below.

Above the table, give one line with the audience and task (or the assumption), how many passages you read, how many you flagged, and the reading level from Step 2. Below it, give the count of passages that scored clean. Do not list the clean ones.

Do not rewrite, suggest wording, or preview directions. End with one line offering rewrite mode, which will reuse these scores.

### Show the scores

In rewrite mode, rank every passage by score, highest first, in one table: where it lives, points, score, and the tally, for example "2 tails + 1 banned word = 5 points, 62 words, 8.1", so Salman can check the arithmetic. If the batch is large, show the 10 highest and the count of passages in each band.

The score measures how many of these rules a passage breaks, not who wrote it. Do not present it as an AI-detection result or call a passage "X% AI-written."

### Choose how much to rewrite

How many passages get rewritten is Salman's call. Offer this scale with the recommended level first, and give the count each level would touch in this batch, for example "Standard: rewrites 9 of 31 passages, plus 4 fixes."

| Level | Rewrites passages scoring |
|---|---|
| Standard (recommended) | 6 or more |
| Fixes only | None. Fail-on-sight fixes only. |
| Light | 10 or more |
| Thorough | 3 or more |

Every level makes the fail-on-sight fixes. Passages below the chosen level keep their wording exactly. A score under 3 counts as clean and is never rewritten unless Salman asks to rewrite everything. If he does, say it will change copy that scored as clean, then do it.

### Preview before rewriting

Do not rewrite anything until Salman has seen a preview and chosen a direction. Take the highest-scoring passage and rewrite it three ways. If the batch mixes interface strings and prose, take one of each. The directions:

- **Spare.** Shortest possible, no scene-setting, reads like documentation.
- **Explanatory.** Same facts, with the reason behind the decision included.
- **Direct address.** Speaks to the reader as "you," suited to interface and instructional copy.

Show the original first with its score, then each direction as a short labeled block with the score it would earn. Use the same real passage every time and never invent filler. All three must already obey every rule in this skill. They vary in register, never in clarity.

Ask the scale question and the direction question in one message, then wait. When the session has an option picker such as AskUserQuestion, use it: one question for each choice, with each direction's rewrite in that option's preview. If Salman wants a different direction, take his note, revise the preview, and show it again before touching anything else. If he does not care, apply Standard and Spare.

Skip the scale question when there is only one passage. If nothing reaches the level he can pick, or nothing scores 3 or more, say so, make the fail-on-sight fixes, and skip the preview.

---

## Step 1: House rules [House]

Apply these, plus the two tables that follow, to the passages inside the level Salman chose, in the direction he picked. Score each rewrite. It should land under 3. Passages below the level keep their wording, apart from fail-on-sight fixes.

### Structure

- **Front-load.** The answer comes first, the detail after. A reader who stops after one sentence should still have the point. CDL and RG say the same.

### Sentences

- **Average 15 words, maximum 35.** The average is the RG figure. The maximum is Salman's. It overrides RG, which sets the maximum at 25. Split anything over 35 into more than one sentence or a list.
- **Vary length.** Do not clip every sentence to the same size.
- **Few commas.** Aim for one comma per sentence at most. Two is the limit. If a sentence needs more, split it into two sentences or a list. Do not chain clauses with commas. A comma in a number (9,000) or between items in a list does not count toward the limit.
- **No comma before a phrase that finishes the sentence.** A closing phrase that starts with "with," "in," "for," or "by" joins the sentence without a comma. "Every talk and set gets a post, with the photo masked in the talk's shape" becomes "Every talk and set gets a post with the photo masked in the talk's shape."
- **Oxford comma in every list of three or more.** "Fill, stroke, surface, and surface light," not "fill, stroke, surface and surface light." The Oxford comma does not count toward the comma limit.

### One sentence by default

Write one sentence per idea. Do not break copy into more sentences than it needs. Start a new sentence only when the next part is a separate point the reader needs on its own. [House]

- **Join related parts.** Link a detail, reason, contrast, or result to its sentence with "and," "so," "while," "before," or a colon.
- **Cut before you split.** If both parts do not fit in one sentence of 35 words or less with two commas or fewer, drop the weaker part. Only split if both parts must stay.
- **No sentences about the page.** "Ten of them are shown here" says nothing the reader cannot see.

Examples from the MODULR presentation:

| Before | After |
|---|---|
| Daytime is for talks. It uses light surfaces and soft color. Nighttime is for DJ sets. It uses deep surfaces, light shapes and grain. | Daytime talks use light surfaces and soft color, while nighttime DJ sets use deep surfaces, light shapes and grain. |
| One layout serves all six talks, each in its own palette. The shape series swaps the motif and keeps everything else. | One layout serves all six talks in their own palettes, and the shape series swaps only the motif. |
| Eleven studies tested four shapes in grids, bands and stacks. Triangle bands became the first poster, then the base of the system. | Eleven studies tested four shapes in grids, bands and stacks before triangle bands became the first poster. |
| Each loop runs four seconds, which is eight beats at 120 BPM. Ten of them are shown here. | Each loop runs four seconds, which is eight beats at 120 BPM. |

### Words

- **Active voice. Hard rule.** Passive only when the actor is genuinely unknown or genuinely irrelevant.
- **American English.** Spelling, punctuation, and usage. Color, organize, toward, canceled. RG and CDL write in UK English. Their spelling is not the rule here.
- **No jargon** unless the named audience already uses the word. If a term must appear, define it once, where it first appears.
- **Reading age nine** for anything public-facing. Relax it only for a named specialist audience, and say so when you do.

### Punctuation and case

- **No em dashes. Ever.** Use a comma or a period, or restructure. This covers everything you write, headings and examples included.
- **No "not this, but that."** State the positive claim alone.
- **Sentence case.** Headings, buttons, labels, and body copy. No Title Case, no lowercase for style. RG says the same.

### Aphorisms and design maxims

Never justify a specific decision with a general law. If a sentence would still make sense pasted into an unrelated project, it is a maxim.

The example Salman flagged: "A scholar's site fails the moment the reading gets hard."

The tell is a universal subject with no article, or a dramatizing verb used figuratively: a site "fails." Watch for "the moment," "always," "never."

**The fix is to name the reason that is true for this project only.** If no project-specific reason exists, delete the sentence. Do not replace one maxim with a better-written maxim.

### Defining a thing by what it is not

Never define something by the alternative it avoided, when that alternative was never on the table.

The example Salman flagged: "Phones get everything, not a reduced version."

The tells: "not a," "not just," "rather than," "instead of," "more than a."

**The test is whether the rejected alternative was genuinely on the table.** "She adds new work by filling in fields instead of asking us" passes, because asking a designer is what happened before. "Phones get everything, not a reduced version" fails, because nobody proposed cutting content from the phone.

**The fix is to make the positive claim alone.** "Phones get everything."

### Trailing tails

A sentence finishes, then a comma bolts on a qualifier.

The example Salman flagged: "Three cuts ship to the browser, self-hosted."

**The fix: if the tail carries a fact, promote it. If it does not, delete it.** "Three cuts ship to the browser, self-hosted" becomes "We self-host three cuts."

### Restating

Say a thing once. Salman flagged a draft as "too repetitive." A second sentence that recasts the first in different words adds no fact.

**The test: name the new fact in the second sentence.** If you cannot, delete it.

### Detail only the maker cares about

Salman asked for copy that is "very minimal with the details" and does not list code components. Cut any fact that only the person who made the thing would care about.

**The test: does this change what the reader thinks, decides, or does?** Run it against the audience and task from Step 0.

### Headings

Always descriptive. A heading names what is under it. No teasers, no wordplay, no questions.

### Captions and labels

Label what is shown. No commentary, no repetition of what the body copy already said, words only where necessary.

### Numbers

- Spell out one through nine. Numerals for 10 and up. This overrides RG, which uses numerals from 2 up.
- RG's own exceptions still apply: numerals for a step or a point in a list, numerals with MB and KB ("4 MB"), and a number that starts a sentence written out unless it starts a title or subheading.
- Keep figures out of prose. A measurement, count, or price goes in a short table or on its own line.

### Banned words

Cut on sight. Add to this list only when Salman deletes a word you wrote, or names one.

**Words Salman approved:** seamless, leverage, robust, journey, elevate.

**RG words to avoid:** the full list is in the "Words to avoid" row of the Readability Guidelines table.

**Constructions:** "not just X but Y," "more than just," and the em dash in any form. "In order to" is on the RG list.

---

## Content Design London guidance [CDL]

Source: https://contentdesign.london. All 264 pages in the site's sitemap were read on 29 September 2026. Most cover research, strategy, governance, courses, and the shop. The rows below are the ones that say how to write or structure copy. Each rule is paraphrased from the page named beside it. Nothing is added.

Guest posts are marked. They are published by CDL but written by someone outside it.

| Page | Rule |
|---|---|
| [What is content design?](https://contentdesign.london/blog/what-is-content-design) | Start from the user need, then choose the format. The answer may not be words. Use the language your users use. Work from data and evidence about what the audience needs. Review content and set dates to delete it. |
| [How to work with user needs](https://contentdesign.london/blog/how-to-work-with-user-needs) | Write each need as "As a… I want to… So that…". Break a wide need into specific tasks. One page cannot hold everything about a topic. |
| [The difference between job stories and user stories](https://contentdesign.london/blog/the-difference-between-job-stories-and-user-stories) | With one audience, use a job story: "When [situation], I want to [action], so I can [goal]." With several audiences, use user stories. CDL labels this page an excerpt from the book. |
| [Editing copy or designing content](https://contentdesign.london/blog/editing-copy-or-designing-content-the-difference) | Ask how to get the content across to the audience in the best way, before asking how to write it. CDL labels this page an excerpt from the book. |
| [How to communicate through crisis events](https://contentdesign.london/blog/how-to-communicate-through-crisis-events) | First ask whether the content is needed at all. Publish only if you add value for the audience. Titles and subheads should tell the story on their own. Headings are statements, because a question adds words before the keyword. Use short, active, positive sentences and avoid negatives and double negatives. A reader should be able to tell what a page gives them within 20 seconds. Show when content was last updated. Give images alt text. |
| [How to structure your content](https://contentdesign.london/blog/how-to-structure-your-content) | Structure follows the user's mental model, never the organization's structure. The first 5 words of a title decide whether the reader stays. The first 15 to 20 words of the page should tell readers whether they are on the right page. Put what 80% of people are looking for first. Subheads tell the story. Keep the same content on mobile and desktop. |
| [Making the case for clear language](https://contentdesign.london/blog/the-case-for-clear-language) | Choose simple, everyday words. Avoid technical terms and jargon, or explain them. Keep sentences short and less than 15 words. Use "you" and "we." Use plenty of paragraphs. Put the most important information first. Use descriptive headings, subheadings, and subject lines. CDL says "clear language" more often than "plain language." Note: RG sets the average at 15 words and the maximum at 25. This skill scores the RG average of 15 and Salman's maximum of 35. |
| [Why user needs should dictate word count](https://contentdesign.london/blog/why-user-needs-should-dictate-word-count) | Do not write to a word count. The content's purpose sets the length. Answer the user need and only the user need. Cut unnecessary words. |
| [Clarity before brevity](https://contentdesign.london/blog/clarity-before-brevity) (guest post) | Clarity comes before brevity. Use as many words as you need to be clear. Shorter words help as much as fewer words. |
| [A few thoughts on frequently asked questions](https://contentdesign.london/blog/thoughts-on-frequently-asked-questions-faqs) | Do not write FAQs. A question cannot be front-loaded. If search, navigation, or the product is failing, fix that instead of writing copy about it. Put each answer on the page where the task happens. |
| [Thoughts on the "dumbing down" content argument](https://contentdesign.london/blog/thoughts-on-the-dumbing-down-argument) | Technical terms are allowed. Explain each one the first time it appears on a page. Avoid long, convoluted sentences. |
| [Design for how people read](https://contentdesign.london/blog/design-for-how-people-read) | Use familiar words: "start" not "commence," "help" not "assistance," "the money you owe" not "the arrears." Remove effort added by presentation: long sentences, jargon, weak structure, long unbroken text. Clear, descriptive headings let readers scan to the part they came for. |
| [AI and search](https://contentdesign.london/blog/ai-and-search-what-content-designers-need-to-know) | Front-load headings, most important word first. Each heading describes the content beneath it. Avoid vague headings like "Things to consider." Short paragraphs and plain language. |
| [The importance of end-to-end strategy](https://contentdesign.london/blog/the-importance-of-end-to-end-strategy) | Understanding matters more than fine writing. Tone can change by channel. Style stays the same. Use the same words for the same thing on every channel. Plain English can still confuse if there is too much of it. |
| [Reason, free from jargon](https://contentdesign.london/blog/reason-free-from-jargon) | In legal copy, use "will" not "shall," "so" not "hence," "also" not "furthermore" or "in addition." Where a word has a fixed legal meaning, keep it and explain it. Break long sentences into shorter ones or a bulleted list. |
| [Neurodiversity and designing for difference](https://contentdesign.london/blog/neurodiversity-and-designing-for-difference) | Break up big blocks of text with headings and bullet lists. Give information one step at a time and remove what is not needed at that moment. Be consistent in language. Do not call a task "quick" or "simple." Error messages say what to do next. |
| [Using trauma-informed principles in content design](https://contentdesign.london/blog/using-trauma-informed-principles-with-content-design) | Front-load the important message. Do not give more information than the person needs right now. Give clear instructions on time limits, timescales, save options, and next steps. |
| [When you design for everyone, you design for no one](https://contentdesign.london/blog/when-you-design-for-everyone-you-design-for-no-one) | No user need, no content. Do not duplicate content that exists elsewhere. Do not make the reader work out which parts apply to them. |
| [5 reasons for content design in services](https://contentdesign.london/blog/5-reasons-for-content-design-in-services) | In a service, check the user need at every step. Keep the words to a minimum. Help text should give the solution, not list possible problems. |
| [How to turn push publishing into pull content](https://contentdesign.london/blog/how-to-turn-push-publishing-into-pull-content) | Lead with what the audience wants to know, not what the organization wants to say. |
| [Why editors need to design](https://contentdesign.london/blog/why-editors-need-to-design) | Subheads break up the page and tell the story. Use an image only when it carries information. Readers ignore decoration. |
| [Good governance should help teams make better content decisions](https://contentdesign.london/blog/good-governance-should-help-teams-make-better-content-decisions) | Ask whether the effort is proportionate to the outcome, and what happens if you do nothing. The same work can add very little to a small update on a page that already performs well. Reduce effort where the value is low. |
| [About](https://contentdesign.london/about) | CDL's stated vision is that content should be useful, usable, and safe. |

---

## Readability Guidelines [RG]

Source: https://readabilityguidelines.wikidot.com/home, created by Sarah Richards at Content Design London. The first row is from the home page's "Top level findings." Every other row is from that guideline page's "Recommendations" section. Nothing is taken from the evidence lists or discussion threads, and nothing is added. The site is marked as archived.

| Guideline | Rule |
|---|---|
| [Top-level findings](http://readabilityguidelines.wikidot.com/home) | Use simple sentences. Avoid capitalising words. In paragraphs, keep link text to the end of the sentence whenever possible. Avoid abbreviations and acronyms except where users know them better in abbreviated form (GIF, 5KB). Avoid referencing gender or age. Choose respectful vocabulary, and research what language could be emotive for your users through forums, blogs, social media, and user testing. Plain language, short sentences, active tense, good grammar, and accurate punctuation make content easier to translate. |
| [Plain English](http://readabilityguidelines.wikidot.com/plain-english) | Easy, short words over formal, long ones: "buy" not "purchase," "help" not "assist," "about" not "approximately." Write for a 9 year old's reading comprehension. No jargon or buzzwords; say what the term means instead. Write as if talking directly to the reader, with the authority of someone who can help. Test with users. |
| [Sentence structure](http://readabilityguidelines.wikidot.com/sentence-structure) | Avoid complex sentences. Complexity is the number of clauses and the word order. "The red fox jumped over the gate," not "The fox, which was red, over the gate jumped." |
| [Sentence length](http://readabilityguidelines.wikidot.com/sentence-length) | 15 words on average, none over 25. Split longer ones into more sentences or a bulleted list. Salman's house rule overrides the maximum: this skill flags sentences over 35 words, not 25. |
| [Specialist terms](http://readabilityguidelines.wikidot.com/specialist-content) | Anybody can reach the content, so write for every expertise level. Explain a concept's parts and processes, do not only name it. Keep the language around a technical term plain. Help with the term itself in one of 3 ways: link it to a page that explains it, add a definition after it, or link to an existing definition elsewhere. |
| [Legal](http://readabilityguidelines.wikidot.com/legal) | When a law is referred to, say what it is about in the main text, not only in a reference section or appendix. Explain complex terms simply. |
| [Words to avoid](http://readabilityguidelines.wikidot.com/words-to-avoid) | agenda (unless a meeting), advancing, collaborate (use "working with"), combating, commit, pledge, countering, deliver (only pizzas, post, and services are delivered), deploy (unless military or software), dialogue, disincentivise, incentivise, empower, facilitate, focusing, foster (unless children), impact (not as a synonym for "have an effect on" or "influence"), initiate, key (unless it unlocks something), land (only aircraft), leverage (unless financial), liaise, overarching, progress (as a verb), promote (unless an ad campaign), robust, slimming down, streamline, strengthening (unless bridges or structures), tackling (unless sport), transforming, utilise. No metaphors: drive (only vehicles), drive out (unless cattle), going forward, in order to, ring fencing. Replace each with what you are actually doing. |
| [Headings](http://readabilityguidelines.wikidot.com/headings) | Descriptive and specific, never generic. The H1 is what shows in search results. Clear, concise, action-orientated. Statements rather than questions, keyword first: "Front-load your headings," not "Should you front-load your headings?" Use headings to show importance or process. The site does not ban play-on-words, idioms, and colloquialisms. It says they can be hard to decipher for people with English as a second language or reading challenges, so weigh the audience and channel. The ban on wordplay headings is a house rule. |
| [Links](http://readabilityguidelines.wikidot.com/links) | Link text is meaningful, not "click here" or "more information." A call-to-action link starts with a verb. Avoid mid-sentence links. Front-load the link text. Active and specific: "Buy pink grapefruits," not "Grapefruits for sale, pink ones only." |
| [CTAs and buttons](http://readabilityguidelines.wikidot.com/cta-and-buttons) | Calls to action in text are active. Button text has 2 to 4 words, ideally starts with an action word, is meaningful (never "Click here"), is specific ("get started" is too vague and misleads), reflects the destination page's title and content, is in sentence case, and is consistent with the other content. |
| [Writing for mobile](http://readabilityguidelines.wikidot.com/writing-for-mobile) | Design mobile first. Ask "How would this look on mobile?" Test with users on mobile devices. Put calls to action close to the relevant content. |
| [Capitals](http://readabilityguidelines.wikidot.com/capitals) | Do not capitalise whole words or phrases. Sentence case in headlines, subheads, and buttons. Exceptions: proper nouns, job titles after a person's name, titles like Mr, Ms, Dr, buildings, place names, brand names, a specific faculty or department, names of groups and organisations, titles of specific acts and bills (then "the act" after first use), named schemes, select committees, table header cells, book titles, World War 1 and World War 2. |
| [Abbreviations and acronyms](http://readabilityguidelines.wikidot.com/abbreviations-and-acronyms) | Abbreviations and acronyms are "not great for readability," except where users know the thing better by its short name (GIF, MB, KB). Test with users to find out how familiar a term is; you may need a brief description ("the conservation charity the RSPB" instead of "the RSPB"). No points or spaces in abbreviations: mph, 4am, WH Smith. Write out "for example" and "that is"; never "eg," "ie," or "etc." All capitals for an initialism said letter by letter (BBC, CEO, US, VAT). Initial capital only for an acronym said as a word (Nasa, Nato, Unicef), unless it has become an everyday word (laser, radar). Capitalise a single letter in C-list or F-word. An international audience will not necessarily know abbreviations that are familiar in the country of authorship. Still under discussion on the site, so note but do not score: put the abbreviation in brackets at first mention if it is used more than once, with a well-known acronym first and the full wording after it, and the reverse for a less familiar one. |
| [Ampersands](http://readabilityguidelines.wikidot.com/ampersands) | Use "and." An ampersand only in an academic reference, a company name as registered at Companies House, or a logo (M&S). |
| [Dashes and hyphens](http://readabilityguidelines.wikidot.com/hyphens) | No hyphen unless the word is confusing without it. Never spaces around a hyphen. Time and date ranges use "to," not a hyphen. A compound adjective takes a hyphen before a noun but not after it: "first-class essay," "the essay is first class." Avoid an en dash or an em dash wherever commas or brackets would do. If an en dash is used mid-sentence, space it on both sides. An em dash is never spaced and is very unusual in UK English. |
| [Contractions](http://readabilityguidelines.wikidot.com/contractions) | Use positive contractions like "you'll" and "we'll." Avoid negative contractions like "shouldn't," "can't," and "don't"; the site says many users find them difficult to read and misread them as the opposite of what they say. Salman has chosen not to enforce the negative-contraction rule, so note a break but do not score it. |
| [Numbers](http://readabilityguidelines.wikidot.com/numbers) | The site writes out "one," except for a step, a point in a list, or another place where the numeral makes more sense, and writes all other numbers as numerals, including 2 to 9, except in a common expression like "one or two of them." Salman's house rule (spell out one to nine, numerals from 10) overrides that, and the audit says so. The rest applies: a number that starts a sentence is written out unless it starts a title or subheading; a comma in numbers over 999 (9,000); a 0 before a decimal point; avoid or write out 0 and 1 where they could be confused with the letters O, I, or l; use clear, familiar typography, because 1 and I can look the same; spell out common fractions (one-half); "%" for percentages (50%); MB preceded by a space for anything over 1 MB ("4 MB not 4096 KB"), KB preceded by a space for anything under 1 MB ("569 KB not 0.55 MB"), as accurate as possible and up to 2 decimal places (4.03 MB); ranges and address ranges use "to" (500 to 900, 49 to 53 Cherry Street); ages as "1 year 6 months" rather than "18 months," "a year and a half," or "1.5 years," and months below 1 year; with data, be specific and consider the context ("20% of 10 people is very different to 20% of 100"). |
| [Writing about people](http://readabilityguidelines.wikidot.com/writing-about-people) | Mention age, gender, a medical, mental, or cognitive condition, heritage, or nationality only when it is absolutely relevant. Use respectful terms for disability, mental health, and dying. Acceptable words vary, so check with the people you are writing for or about. Use positive, enabling language and do not present people as victims: "has" or "was diagnosed with" not "suffers from"; "challenge of" not "struggle with"; "support" not "help"; "taken to hospital" never "hospitalised" or "rushed to hospital"; "blind person," "deaf person," never "the blind" or "the deaf"; "disabled people" not "people with disabilities"; "wheelchair user" not "wheelchair-bound" or "in a wheelchair"; "someone with diabetes" not "a diabetic"; "non-disabled people" not "able-bodied people," "normal people," or "healthy people"; "someone with mental health difficulties"; "bipolar disorder" never "manic depression"; "took their own life" not "committed suicide"; "assisted dying" not "assisted suicide." Age: "older people" never "the elderly"; "younger people" not "the young" or "millennials." Gender: neutral professions (firefighter, police officer, actor, chair, businessperson); "people" not "guys"; "women" not "girls" or "ladies"; "she," "her," "he," or "his" if you know how the person identifies, otherwise "they" and "their"; do not make gender a compulsory field on forms. Heritage: if you must mention it, be specific and accurate and do not generalise, because some people dislike their background being described by land mass ("South American," "Asian food," "she is from Africa"). For a product or service everyone can use, the site prefers "inclusive" to "accessible"; "accessible parking space," not "disabled parking space." |
| [Audience labels](http://readabilityguidelines.wikidot.com/audience-labels) | Using "we" is fine as long as it is clear who "we" is. Do not assume the audience will know. Lead with "we" in an "about us" section. Each time you use "we," make sure the organisation's full name has already appeared in that specific section, because users can arrive at a heading from the navigation or skim from the top. "We" can become confusing when a third party is heavily referred to. "You" can be confusing when the content is aimed at multiple audiences. |
| [Hashtags and social](http://readabilityguidelines.wikidot.com/hashtags-and-social) | The site's 3 rules are written for Twitter. Capitalise the first letter of each word in a hashtag (#ContentDesign). Use the image description function to describe the images you post. If you add a GIF, include a description of it in the tweet: "[GIF: cat curled up on top of a pile of books]." |

The site is written in UK English. Salman's house rule stays American spelling, so "capitalise," "organisation," and "utilise" in the table are quotations, not the spelling to use.

---

## Step 2: Report readability [House]

Compute an approximate US grade level or reading age for the final copy and report it in one line. Never block on the number and never rewrite good prose to chase it.

If the grade level is far above the audience, say which passages caused it.

---

## Step 3: Self-audit before handing anything back

In audit mode, check only that every flag quotes the sentence exactly, names a real rule, carries its source tag, and that you rewrote nothing. For each [CDL] or [RG] tag, confirm the rule is in the table. Then hand back the audit.

In rewrite mode, run this list. Fix what fails rather than reporting it.

- [ ] Salman chose audit or rewrite, or said which in his request
- [ ] Audience and task are stated, or the assumption is stated
- [ ] Every passage was scored, and Salman chose the level and the direction from a preview before anything was rewritten
- [ ] Only passages inside the chosen level were rewritten, in the chosen direction, and each rewrite re-scores under 3
- [ ] Nothing was rewritten that broke no rule, and every change names the rule behind it
- [ ] Zero em dashes in anything you wrote or changed
- [ ] Nothing defined by the alternative it avoided, unless that alternative was genuinely on the table
- [ ] No aphorisms, no trailing tails, no sentence that restates the one before it
- [ ] No copy split into more sentences than it needs
- [ ] No detail only the maker would care about
- [ ] Sentence case throughout, American spelling throughout
- [ ] The first sentence carries the point
- [ ] Every heading describes its content and is a statement
- [ ] Every caption is a label, with no commentary and no repetition
- [ ] No passive voice without a reason, no banned words
- [ ] Sentences average 15 words or under, none runs past 35, and lengths still vary
- [ ] One through nine spelled out, numerals for 10 and up, figures kept out of prose
- [ ] Every rule in the Content Design London guidance table was checked
- [ ] Every rule in the Readability Guidelines table was checked
- [ ] Every flag and every reason you gave names its source, and no rule was attributed to CDL or RG from memory
- [ ] Reading level reported

---

## Step 4: Show what changed

Rewrite mode only. Audit mode ends at "Audit output."

Lead with the ranked score table from "Which copy needs rewriting?", now with the action taken on each passage: rewrite, fix, or keep. Add the new score beside each rewrite.

For a rewrite, follow with a short table of the lines that changed most. Before on the left, after on the right, at most six rows.

---

## Relationship to brand voice [House]

When a brand voice skill is also loaded, the brand wins on **register**: warmth, humor, formality, and who the narrator is. This skill wins on **clarity and structure**: order, sentence construction, word choice, headings, and captions.

---

## What this skill cannot do

CDL says content designers "generally don't move without research." Source: [What is content design?](https://contentdesign.london/blog/what-is-content-design) That research can be desk research, usability research, or expert research.

This skill has none of it. Asking for the audience and task in Step 0 is a substitute, not a replacement. Do not describe output from this skill as user-tested, validated, or research-backed.

---

## Where each house rule came from

| Rule | What Salman said | When |
|---|---|---|
| Covers reviewing and writing, prose and interface copy | Answers 1 to 3 of the 20 questions | 13 September 2026 |
| Triggers only on request | "auto when i say something like cdl" | 13 September 2026 |
| Ask for audience and task | "yes, prompt for audience and task" | 13 September 2026 |
| Sentence lengths vary | "length of sentences should vary" | 13 September 2026 |
| Average 15 words | Chose the Readability Guidelines rule | 29 September 2026 |
| Maximum 35 words a sentence | "update the 25 words rule 35" | 29 September 2026 |
| Reading age nine, report a reading level | Answers 7 and 8 | 13 September 2026 |
| American English | "American" | 13 September 2026 |
| Active voice, hard rule | "hard" | 13 September 2026 |
| Jargon rule | Answer 11 | 13 September 2026 |
| Headings always descriptive | "always descriptive" | 13 September 2026 |
| Captions | "no commentary, no repitition, words only where necessary" | 13 September 2026 |
| Front-loading | Answer 14 | 13 September 2026 |
| Banned-words list | Answer 15 | 13 September 2026 |
| Before and after table, self-audit | Answers 17 and 18 | 13 September 2026 |
| Writing styles to choose between | "give user options of writing styles to choose between with a few sample paragraphs" | 13 September 2026 |
| Brand voice wins on register | Answer 5 | 13 September 2026 |
| Restating | "this writing is too repetitive" | 13 September 2026 |
| Aphorisms | "update the cdl skill to make sure we dont use language like this" | 13 September 2026 |
| Defining a thing by what it is not | "update cdl skill to also not write things like this" | 14 September 2026 |
| Trailing tails | "make sure we also dont do this thing of short sentence followed by comma and then statement" | 14 September 2026 |
| Few commas | "update cdl-sak to reduce number of commas used in sentences" | 26 November 2026 |
| One sentence by default | "too often, the copy ends up being broken into multiple sentences when it's not necessary" | 27 November 2026 |
| No comma before a closing phrase | "unnecessary comma for cdl-sak" | 27 November 2026 |
| Oxford comma | "also use oxford commas for lists" | 27 November 2026 |
| Detail only the maker cares about | "be very minimal with the details" | 14 September 2026 |
| No em dashes, no "not this, but that" | "no em dashes, no it's not this, that" | 20 September 2026 |
| Do not rewrite for the sake of it | "it's not always necessary to keep rewriting for the sake of it" | 29 September 2026 |
| Score first, rewrite past a threshold | "make a calculation on which copy feels most AI-written" | 20 September 2026 |
| Scale and preview | "give user the scale on how much to rewrite" | 20 September 2026 |
| Audit against the Readability Guidelines | "make sure these are the readability guidelines for the audit" | 29 September 2026 |
| Negative contractions not enforced | Chose "No" | 29 September 2026 |
| Spell out one to nine | "Numerals for ten and up" | 29 September 2026 |
| Rules limited to these three sources | "make sure anything CDL related is actually from the Contentdesign.london website or the content design book" | 29 September 2026 |