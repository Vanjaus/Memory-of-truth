# Memory of Truth

**A false memory can outlive the conversation that created it.** An AI may misread one sentence, store its interpretation as a fact, and repeat it years later as if the owner had said it. A convincing answer is then built on a false starting point. For a digital companion intended to last decades, that is more than an awkward mistake.

## The problem: when an AI's note becomes "truth"

We distinguish two layers. **L1** is the model's protected instruction layer: the rules it is meant to follow. **L2** is the external memory layer: records that can be written, changed, retrieved, and placed back into a model's context. Protecting L1 does not make every statement in L2 true. If an AI's guess enters L2 as an accepted fact, later models may treat that guess as the owner's history.

Memory of Truth is being developed around a stricter boundary: **an AI can propose a memory; only the owner, using an owner-held key, can approve it as the accepted record.** The key should stay under the owner's control. The owner's actual words must remain distinct from a model's paraphrase or inference. Each accepted record should retain its source, who asserted and approved it, when it was valid, and how it changed. A correction should add a traceable revision rather than silently erase the past. The record should remain usable when the model or platform changes.

This rule protects *who has authority to approve a memory*. It does not claim that a person can never be mistaken. The aim is to prevent an AI-generated assertion from quietly becoming the owner's truth without the owner's decision.

## How this differs from existing memory

Memory products already solve important parts of the problem. [Mem0](https://github.com/mem0ai/mem0/blob/main/docs/core-concepts/how-it-works.mdx) extracts and retrieves durable facts. [Zep](https://help.getzep.com/overview) builds temporal context graphs and traces graph data to sources. [LangMem](https://langchain-ai.github.io/langmem/reference/memory/) can create and update structured memories. [Letta](https://docs.letta.com/v1-sdk/memory/memory-blocks) gives agents persistent memory blocks, including configurable read-only blocks. [ChatGPT Memory](https://help.openai.com/en/articles/8590148-memory-in-chatgpt) and [Claude Memory](https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context) personalize conversations; Claude also offers [memory import and export](https://support.claude.com/en/articles/12123587-import-and-export-your-memory-from-claude).

These capabilities matter. **Our distinct requirement is the mandatory owner-controlled step between a model's proposed statement and a canonical record**, followed by a checkable history of what was approved and later retrieved. Source tracking, time awareness, and export each help; none alone establishes that the owner authorized the claim. This is the design boundary we intend to test, not a claim that other systems cannot be configured or extended in different ways.

## From proposal to proof

A trustworthy memory should let its owner inspect the whole path:

1. **Proposal:** show the conversation or other source, the exact statement, and what the AI inferred from it.
2. **Approval:** record the owner's decision through the owner-held key. Without it, a proposal does not become canonical.
3. **History:** keep the accepted version, its time context, and later corrections without rewriting earlier evidence.
4. **Recall:** retrieve the relevant record with its source and approval status, including an older version when the question calls for history.
5. **Portability:** export and restore the record, then show that another model can use the same approved memory.

**Every step should leave evidence that can be checked.** This describes the standard for the project. We will not present the full chain as complete until it has been demonstrated end to end.

## Three tests for a real V1

We want V1 to pass three plain-language tests:

- **Remember without manual note-taking.** The system notices a possible lasting memory and proposes it; the owner still decides whether it is accepted.
- **Recall without a special command.** When relevant, an assistant brings the approved memory into the conversation and can show where it came from.
- **Survive a model change.** The owner's memory remains usable after switching to another supported model or agent.

A prototype or a high test count alone is not enough. These behaviors must work together in an installable version.

## What this means over a lifetime

A long-term digital companion should carry useful context as the person and the AI tools around them change. If an AI misreads a preference, the owner can reject it. If a view changes years later, both the earlier and later positions should remain understandable in their original time. If the owner changes services, the approved record should travel with them. If someone asks why the companion believes something, the answer should lead back to its source.

There is also a deeply personal ambition: **a truthful digital legacy for loved ones.** If the owner chooses to preserve and share parts of their history, those closest to them should be able to receive the person's own words and context, with a clear account of what came from the person and what an AI inferred. Access and sharing rules for such a legacy have not yet been defined. This is a long-term goal, not an available feature.

## Status: V1 is in development

**Already public:** this repository describes the project and has [Discussions](https://github.com/Vanjaus/Memory-of-truth/discussions) open for questions and interest. **Internal work:** parts of the memory engine and an automated test suite exist. The complete approval-to-recall cycle, history and contradiction handling, independent backup and restore, model switching, and a repeatable installation still need to be verified together before a public test release.

**There is no public download or open tester enrollment yet.** The engine's source code remains private. We will publish supported environments, a working build, test tasks, limitations, and installation instructions when they are ready. No release date has been announced.

## Join the future test community

**Would you want to test a memory that you control?** Tell us which AI models or applications you use, whether you would run the system on your computer or VPS, and which failure worries you most: a false remembered fact, missing history, poor recall, loss of access when changing providers, or something else. Share a hypothetical example in [GitHub Discussions](https://github.com/Vanjaus/Memory-of-truth/discussions). Please do not publish private memories, personal data, credentials, or API keys.

The planned ways to access the product are:

- **Development and beta testers:** selected participants would test a working development version for free on their own computer or VPS, using their own third-party AI API accounts where needed.
- **Founding GitHub VIP testers:** under eligibility and participation rules to be published before enrollment, the intended benefit is a free permanent license for commercial V1, including V1 updates, and early access to test V2. Early V2 testing does not itself include a permanent V2 license.
- **Later buyers:** the intended model is a one-time purchase of a major version, with updates within that version included and a discounted path to a later major version for existing owners. An optional managed cloud service may come later.

These are **planned access and product terms**, not an open enrollment or a grant of software rights today. Commenting now expresses interest; it does not automatically assign tester or VIP status. See [future tester plans](FOUNDING_TESTERS.md) and [licensing direction](LICENSING.md) for the current details. The published [LICENSE](LICENSE) applies to the documents in this repository; the unreleased engine has no public source-code license here.

Read the [roadmap](ROADMAP.md) for the planned sequence of work.
