# Memory of Truth

**Your AI says you set aside money for a tax penalty—and you do not know why.**

Imagine your assistant says, *“As we agreed, you reported additional income to the tax authority and set aside money for a penalty.”* You stop. **You do not remember saying that—and you may not owe any penalty.** Perhaps the model inferred an obligation while trying to protect you from a perceived regulatory risk. Perhaps it turned a caution into a claim about what you did. **If you trust that claim, you could pay money you do not owe.**

LLMs operate under very different rules: from relatively unrestricted models to models shaped by safety measures, provider policies, ethical choices, and applicable laws. Those rules may address real risks, but **a model's rules are not evidence about your life.** An overly cautious answer may turn the model's own risk assessment into a claim about what you said, did, or owe. Protections in its instruction layer (L1) do not, by themselves, keep that unverified claim out of external memory (L2).

**The first connection is especially sensitive.** A model introduced to a new memory may propose an initial picture of you through its own L1 rules. If those proposals become accepted records automatically, later models could inherit that picture as if you had confirmed it. Memory of Truth is being built to prevent that failure.

## What this means over a lifetime

A long-term digital companion should carry useful context as the person and the AI tools around them change. If an AI misreads a preference, the owner can reject it. If a view changes years later, both the earlier and later positions should remain understandable in their original time. If the owner changes services, the approved record should travel with them. If someone asks why the companion believes something, the answer should lead back to its source.

There is also a deeply personal ambition: **a truthful digital legacy for loved ones.** If the owner chooses to preserve and share parts of their history, those closest to them should be able to receive the person's own words and context, with a clear account of what came from the person and what an AI inferred. Access and sharing rules for such a legacy have not yet been defined. This is a long-term goal, not an available feature.

## The problem: when an AI's note becomes "truth"

We distinguish two layers. **L1** is the model's protected instruction layer: the rules it is meant to follow. **L2** is the external memory layer: records that can be written, changed, retrieved, and placed back into a model's context. Protecting L1 does not make every statement in L2 true. If an AI's guess enters L2 as an accepted fact, later models may treat that guess as the owner's history.

**The design goal is that no connected model can rewrite accepted L2 memory to fit its own L1 rules or assumptions.** This applies when memory is first connected, when another model takes over, and when a model later proposes a correction. Each model may read approved records and suggest additions or changes; its suggestions remain proposals until the owner approves them. A model's policies or caution cannot stand in for the owner's decision.

Memory of Truth is being developed around a stricter boundary: **an AI can propose a memory; only the owner, using an owner-held key, can approve it as the accepted record.** The key should stay under the owner's control. The owner's actual words must remain distinct from a model's paraphrase or inference. Each accepted record should retain its source, who asserted and approved it, when it was valid, and how it changed. A correction should add a traceable revision rather than silently erase the past. The record should remain usable when the model or platform changes.

This rule protects *who has authority to approve a memory*. It does not claim that a person can never be mistaken. The aim is to prevent an AI-generated assertion from quietly becoming the owner's truth without the owner's decision.

## What existing tools do

| Tool | What it offers |
| --- | --- |
| [Mem0](https://github.com/mem0ai/mem0/blob/main/docs/core-concepts/how-it-works.mdx) | Extracts and retrieves lasting facts from conversations. |
| [Zep](https://help.getzep.com/overview) | Builds temporal context graphs and traces graph data to sources. |
| [LangMem](https://langchain-ai.github.io/langmem/reference/memory/) | Creates and updates structured memories. |
| [Letta](https://docs.letta.com/v1-sdk/memory/memory-blocks) | Gives agents persistent memory blocks, including configurable read-only blocks. |
| [ChatGPT Memory](https://help.openai.com/en/articles/8590148-memory-in-chatgpt) and [Claude Memory](https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context) | Personalize conversations; Claude also offers [memory import and export](https://support.claude.com/en/articles/12123587-import-and-export-your-memory-from-claude). |

All solve **part** of the problem. Export helps. Source tracking helps. Time awareness helps. The question this project places at the center is: **who approved that a model's statement should become the owner's accepted memory?**

## Our difference: a required owner decision

Memory of Truth puts an owner-controlled step between a model's proposal and an approved record:

```text
Model proposes: “The owner owes a tax penalty.”
                    ↓
             Wait for the owner
                    ↓
Owner rejects it → no canonical record of the claim
Owner confirms it with their key → approved record with evidence
```

**Without that decision, there is no canonical record.** The model cannot promote its own inference into the owner's accepted history.

In practice, the intended result is simple:

- **Every accepted record has evidence:** who said what, when, and from which source.
- **Its history can be checked:** what was approved, what was later superseded, and when.
- **The owner controls the boundary:** the model or platform cannot approve on the owner's behalf.

This is the design boundary we are testing. Other systems may be configured or extended in different ways. Memory of Truth aims to show **what was proposed, what the owner approved, and why a memory was later used**.

## From proposal to proof

A trustworthy memory should let its owner inspect the whole path:

1. **Proposal:** show the conversation or other source, the exact statement, and what the AI inferred from it.
2. **Approval:** record the owner's decision through the owner-held key. Without it, a proposal does not become canonical.
3. **History:** keep the accepted version, its time context, and later corrections without rewriting earlier evidence.
4. **Recall:** retrieve the relevant record with its source and approval status, including an older version when the question calls for history.
5. **Portability:** export and restore the record, then show that another model can use the same approved memory without rewriting it to fit its own rules.

**Every step should leave evidence that can be checked.** This describes the standard for the project. We will not present the full chain as complete until it has been demonstrated end to end.

## Three tests for a real V1

We want V1 to pass three plain-language tests:

- **Remember without manual note-taking.** The system notices a possible lasting memory and proposes it; the owner still decides whether it is accepted.
- **Recall without a special command.** When relevant, an assistant brings the approved memory into the conversation and can show where it came from.
- **Survive a model change.** The owner's memory remains usable after switching to another supported model or agent.

A prototype or a high test count alone is not enough. These behaviors must work together in an installable version.

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
