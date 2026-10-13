# Memory of Truth

**After decades of conversations, will an AI remember what you actually said—or only what it guessed you meant?**

Over years of conversations, you may tell AI systems about decisions, work, relationships, changing beliefs, and moments you want to remember. That history can end up scattered across chats and reduced to summaries that are useful today but leave out what you actually said, where a claim came from, or how your thinking changed. If you move to another AI, you may have to rebuild that context again.

Memory of Truth is being developed around one principle: **the owner decides what becomes a lasting record.** An AI may propose a memory. The owner reviews and approves the accepted version. The record should preserve its source, attribution, time context, and revisions, so a later AI can distinguish the owner's words from an inference and a current fact from an older one.

## Why build another kind of memory?

Products such as [ChatGPT Memory](https://help.openai.com/en/articles/8590148-memory-in-chatgpt), [Claude Memory](https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context), and [Gemini's memory of past chats](https://support.google.com/gemini/answer/16598469?hl=en) already help people continue conversations. They have different controls; Claude also offers [memory import and export](https://support.claude.com/en/articles/12123587-import-and-export-your-memory-from-claude). These are useful features, but they are built around each service's own personalization experience. ChatGPT says it does not retain every detail from every conversation and may change what it derives from chat history. Gemini's past-chat memory draws on Gemini activity. Claude describes its memory as focused on work-related context and notes that imported personal details may not all be retained.

**For a memory meant to last decades, convenience inside one assistant is not enough.** The project aims for a separate, owner-controlled source of truth that can be used with different models and agents. It should let the owner see what was recorded, why, and from where; correct a mistake without erasing the history; and export and restore the record. That is the standard we are building toward, not a claim that the current development build already meets it.

## A digital companion over many years

The long-term idea is a digital companion that can keep useful context as the person and the AI tools around them change. It should remember **with evidence and with the owner's consent**, rather than gradually turning guesses or convenient summaries into supposed facts.

These situations show why that matters:

- **An AI gets something wrong.** It infers a lasting preference from one conversation. The owner can reject the proposed memory instead of letting the inference quietly become part of their history.
- **A person's view changes.** Years later, the assistant should be able to show both an earlier decision and a later revision, with their time and sources, instead of treating one as though the other never existed.
- **The person changes AI services.** Their approved record should remain theirs and be usable with another model or agent without starting their story from zero.
- **Someone asks where a memory came from.** The answer should lead back to the original source and identify what the owner said, what an AI inferred, and what was subsequently approved or corrected.

There is a further, deeply personal purpose: **a digital legacy for loved ones, in a truthful form.** If the owner chooses to preserve and share parts of their history, the hope is that those closest to them could one day receive the person's own words and context, with a clear record of where each part came from, rather than an AI's invented certainty about who that person was. How access and sharing would work has not been defined; this is a long-term goal, not a feature available today.

## Where the project stands

Memory of Truth is in development and under test. **There is no public download or open test enrollment yet.** We will announce a working test release, supported environments, and installation instructions when it is ready. No release date has been announced.

The memory engine's source code is private at this stage. This repository is the public home for the project's description, plans, progress updates, questions, and community feedback. Publishing these documents does not make the engine open source.

## Help shape the first test

**Are you interested in following or eventually testing this idea?** Tell us what long-term memory would need to get right for you. Which AI models or applications would you want it to work with? Would you run it on your own computer or VPS? Which matters most: reliable recall, the original source, the history of changes, portability, or something we have missed?

Join [GitHub Discussions](https://github.com/Vanjaus/Memory-of-truth/discussions) with questions, examples, criticism, or an expression of interest. Please use hypothetical or synthetic examples; do not post private memories, personal data, credentials, or API keys. A comment is not test enrollment or a promise of access. We will publish test terms before enrollment opens.

## Planned path

1. Explain the project and listen to potential users.
2. Continue development and verify the complete memory cycle, including recall, owner approval, history, and recovery.
3. Announce a controlled test release with installation and testing instructions when it is ready.
4. Use real tester feedback to shape a stable V1.

Read [the roadmap](ROADMAP.md), [future tester plans](FOUNDING_TESTERS.md), and [licensing direction](LICENSING.md). They describe the current plan and do not claim that unreleased features are available today.
