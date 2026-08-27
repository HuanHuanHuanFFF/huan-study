---
name: huan-study-summary
description: Turn the current learning conversation into a downloadable full, incremental, or revised Markdown knowledge summary.
---

# Huan Study: Summary

Turn the conversation into a Markdown file suitable for a knowledge base, follow-up work by another agent, review, and interview preparation. Reconstruct the knowledge structure instead of copying the transcript or expanding it into an encyclopedia.

## Determine the scope

First identify the summary type:

- **Full**: The user asks for everything from the beginning, the entire conversation, a complete review, or a full summary. Cover the conversation from its beginning through the current message.
- **Incremental**: The user asks for everything since the previous summary, the latest discussion, new material, or an incremental summary. Cover the messages after the most recent summary boundary through the current message.
- **Revised**: The user identifies an omission, error, or imprecision and asks to supplement, rewrite, or update an existing summary. Use the original summary and the subsequent corrections as inputs.

If the type is unclear but the most recent summary boundary can be located reliably, create an incremental summary and state that decision at the beginning of the file. If the boundary cannot be located, ask one scope question. If the original file for a revision is inaccessible, ask the user to provide or select it again. Begin writing only after the scope and inputs are known.

## Extract conclusions

Read the conversation within scope; for a revision, also read the original summary. Extract:

- the knowledge modules discussed and their main causal chains;
- the user's follow-up questions, doubts, corrections, and points of confusion;
- the final confirmed conclusions and any unresolved conflicts;
- what has been explained clearly and what still needs work.

For an explicitly corrected claim, use the final confirmed version and briefly retain the original misconception and why it was corrected. For an unresolved conflict, preserve each position, its evidence, and the current uncertainty; do not treat the last claim in the conversation as automatically correct.

Avoid introducing substantial knowledge from outside the conversation. Add only the small amount of background needed to prevent a broken causal chain, and label it "Supplementary context."

## Reorganize the knowledge

Organize by knowledge module, not message chronology. Cover the following path as needed for each important module:

> problem -> motivation or core tension -> design and mechanism -> effect -> cost and boundary

Also preserve confusing points, corrections made during the conversation, key follow-up questions and final answers, and concise interview answers that can be spoken directly. Merge small points into sections such as "Miscellaneous notes" or "Corrections to common confusions" when useful, but do not omit them merely because they are brief.

Let the content determine the structure. Do not create empty sections or mechanically apply every heading. Consider, in order: scope, problem overview, knowledge modules, corrections to common confusions, interview answers, and open items. Keep only sections that have content.

## Generate the file

Create a standard Markdown file and do not paste the full body into the chat. Write in the user's language unless the user requests another language.

Before generating the file, check the current project or workspace for established destination, naming, and revision conventions, and follow them when present. If no convention exists, or if it is unclear whether a revision should overwrite the original or create a new file, ask the user first.

- State the scope, summary type, and purpose in the title and introduction.
- Use only English letters, digits, and hyphens in the filename. Use `YYYY-MM-DD-topic-full-summary.md`, `YYYY-MM-DD-topic-incremental-summary.md`, or `YYYY-MM-DD-topic-revised-summary.md`.
- Put code and commands in fenced code blocks. Format formulas with Markdown or LaTeX math.
- Keep interview answers concise, causal, and easy to say aloud.
- List only unresolved material under open items; do not repeat completed material.

## Delivery checks

Before delivery, confirm that:

- the summary type and source scope are accurate;
- none of the user's key follow-up questions, confusions, or corrections are missing;
- completed material, open items, and unresolved conflicts are distinguished;
- the main conclusions are connected by causal reasoning rather than stacked definitions and conclusions;
- the Markdown file exists and its download link works.

Keep the checking process out of the summary itself. After completion, reply briefly in the user's language and include the file link.
