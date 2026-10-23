# pack-aws-genai — a quizmill learning pack

Practice for the **AWS Certified Generative AI Developer – Professional
(AIP-C01)** exam — AWS's first professional-level GenAI credential
(75 questions, 180 min, pass 750/1000, scaled). This pack is a
**30-question sample** across foundation-model integration, RAG, agents,
prompt management, deployment, observability, and security: three questions
per category, spanning the Easy, Hard and Very hard tiers, and including ten
exam-style scenarios written for the pack.

The **full bank — 752 questions** in twelve categories and four tiers, 385
of them an **Exam-level** tier of paired scenario questions written against
the exam guide's 20 tasks — ships as a separate pack, `aws-genai-full`. The
app's upgrade card
(on Home, below the practice loop, and in Settings → Packs) links to it, and
the manifest names it (`upgrade.packId`, with `upgrade.unlockUrl` as the
service) so a licence key for it unlocks the full bank **in place**: paste
the key under **Packs → Have a licence key?**, or open the `/unlock#key=…`
link you were sent, and the full bank becomes the active pack next to the
sample — no file involved, and progress is kept per pack. A key for any
other pack is refused with the service's own words. The fallback still
works: insert the full bank's bundle file at `/packs` and tap **Make
active**. Engines older than the release that added the key entry ignore
the two fields and show the card alone.

> **Unofficial.** Not affiliated with or endorsed by AWS. This is community
> study material — treat every question as `draft` and cross-check against
> AWS docs and the official practice set.

## Where the questions come from

Adapted (under MIT) from
[`JeremyEngineer/aws-aip-c01-practice-exam`](https://github.com/JeremyEngineer/aws-aip-c01-practice-exam)
— 462 community-authored questions with per-option explanations and AWS doc
links. See [`NOTICE.md`](NOTICE.md) for the license and exactly what was
changed. Options were reordered (upstream always lists the correct answer
first), per-option explanations were merged into one teaching explanation
with the source's AWS doc link appended, and **2 items flagged as imprecise
during review were dropped** (462 → 460). A further **141 were removed on
2026-10-13 as restatements** of other items in the bank (460 → 319): the
upstream Very hard tier repeated the Hard tier almost item for item, and the
`easy-off-N` items were condensed copies of the `hard-bp-N` items.
Since 2026-10-21 the per-option verdicts (why each rejected option is
wrong) sit on the option itself, as its `explanation`, and show under it
once the answer is checked; the question explanation keeps the lead
reasoning and the AWS doc link. On 2026-10-22 the **six `hard-bp-*` items
were removed**: upstream's `bp-N` questions are its copy of the AWS Skill
Builder Official Practice Question Set, which its MIT licence cannot cover
(see [`NOTICE.md`](NOTICE.md)); each slot went to one of the pack's own
scenarios in the same category.

**67 exam-style scenarios** (`source: "original"`, tag `scenario`, ids
`aws-genai-<tier>-d<domain>-<n>`) were written for the full bank in the
official exam's form — a multi-constraint scenario, full-sentence options,
"LEAST operational overhead" / "Select TWO" — and tagged with the official
domain (`domain-1` … `domain-5`). They concentrate on what the community
bank barely covers: testing, validation and troubleshooting, operational
efficiency, integration patterns, and governance. Each one's `sourceRef` is
the AWS doc page it is grounded in.

The sample here is 30 of the full bank's Easy, Hard and Very hard questions,
drawn by id. Three of them
(`easy-1-4-20`, `easy-2-1-14`, `veryhard-1-1-v1`) carry corrections made on
2026-10-22 against current AWS documentation (DynamoDB vector search, the
`agentcore` CLI, Provisioned Throughput's supported-model list).

### Verification

An independent adversarial pass checked a stratified sample of **48**
questions from the full bank (all task areas, all tiers) against AWS
documentation: **46 confirmed correct, 0 clearly wrong, 2 imprecise** (both
removed). The technical claims held up — including fast-moving 2025 services
(Bedrock AgentCore, Strands, application inference profiles, Guardrails).
That is a ~3% sample, so it is a strong signal, not a guarantee; everything
stays `reviewStatus: "draft"`.

On 2026-10-23 all 30 questions in this sample went through a three-pass
automated item review (solve without the key, guess from the options alone,
and a rubric review for the classic item-writing flaws). Every key was
confirmed, but 25 items were rated *major* for test-wiseness: distractors
nobody would pick and a key noticeably longer than the rest. The options
were rewritten so that each distractor is a real feature misapplied or a
near-miss, every option in an item is about the same length, and the "Read
more" link supports the claim it sits under. On re-review the same judge
rates 0 items fatal or major, 10 minor and 20 clean, still with every key
confirmed. The 30 ids are unchanged, so progress carries over, and the full
bank carries the same wording for them since 2026-10-23.

## Categories & tiers

Categories follow the **source bank's topic taxonomy** (10 groups), which is
the most faithful mapping — not the official exam domains. Use the **Tier**
filter (Easy / Hard / Very hard, from the source's three banks) to drill by
difficulty. The full bank adds two categories (Cost & Performance
Optimization; Evaluation, Testing & Troubleshooting) and a fourth tier,
**Exam-level**, which the sample does not draw from.

| Category | Sample (Easy / Hard / Very hard) | Full bank (Easy / Hard / Very hard / Exam-level) |
| --- | --- | --- |
| Foundation Models: Selection & Inference | 3 (1 / 1 / 1) | 86 (29 / 19 / 10 / 28) |
| RAG, Knowledge Bases & Vector Stores | 3 (1 / 2 / 0) | 84 (33 / 19 / 2 / 30) |
| Agents (Bedrock Agents, AgentCore, Strands) | 3 (1 / 1 / 1) | 82 (32 / 15 / 5 / 30) |
| Data Preparation | 3 (1 / 2 / 0) | 49 (25 / 10 / 2 / 12) |
| Security, Guardrails & Compliance | 3 (0 / 2 / 1) | 115 (0 / 27 / 7 / 81) |
| Prompt Management & Inference Control | 3 (1 / 1 / 1) | 47 (18 / 14 / 3 / 12) |
| Chunking, Embeddings & Retrieval | 3 (1 / 2 / 0) | 58 (22 / 12 / 0 / 24) |
| Model Deployment & Developer Tools (full bank: Deployment, Integration & Developer Tools) | 3 (0 / 2 / 1) | 110 (0 / 24 / 4 / 82) |
| Well-Architected GenAI Lens | 3 (1 / 1 / 1) | 34 (14 / 7 / 3 / 10) |
| Observability & Monitoring | 3 (0 / 2 / 1) | 29 (0 / 10 / 1 / 18) |
| Cost & Performance Optimization (full bank only) | — | 28 (0 / 0 / 0 / 28) |
| Evaluation, Testing & Troubleshooting (full bank only) | — | 30 (0 / 0 / 0 / 30) |

The Very hard tier is small on purpose: after the restatements were removed
it holds the 15 upstream items that ask something the Hard tier does not,
plus 22 of the exam-style scenarios. The full bank's Exam-level tier is 385
questions in pairs: the two share their options word for word but have
different scenarios and different keys, so only the stem decides; each is
tagged with the exam guide's task and skill, and the full bank's readiness
estimate and timed exam are computed from that tier alone.

### How the sample was chosen

Three questions per category, picked to look like the full bank in
miniature:

- **Every tier a category has is shown.** Each category with Easy items
  contributes one (seven of the ten; Security, Deployment and Observability
  have no Easy tier upstream), and every category with a Very hard item
  contributes one unless the slot was better spent on a scenario. The sample
  is 7 Easy, 16 Hard and 7 Very hard; the bank is Easy 173, Hard 157, Very
  hard 37, plus the 385 Exam-level questions the sample does not draw from.
- **Both kinds of question.** 14 are adapted from the community bank and 16
  are the pack's own exam-style scenarios — spread over nine of the ten
  categories and all five official domains — so the sample shows the
  scenario form the full bank is written in. (Until 2026-10-22 the split was
  20 / 10, the 20 including six of upstream's `hard-bp` items; see below.)
- **Both answer formats.** Six of the 30 are "Select TWO".
- **One concept per question**, across the whole sample, not just within a
  category: no two of the 30 ask the same scenario with the same key, and
  the richest explanations — the ones that say why each rejected option is
  wrong and link the AWS doc — were preferred.

Question ids are the full bank's own, so every id in the sample exists in
the full bank. The 14 ids the sample held before 2026-10-13 that were
removed from the bank as restatements (`easy-off-1`, `-3`, `-4`, `-6`,
`-13`, `-17` and `veryhard-1-3-v3`, `1-4-v1`, `1-5-v10`, `1-6-v6`, `2-1-v2`,
`2-2-v4`, `2-4-v5`, `3-1-v8`) were swapped out; progress recorded against
them is simply left behind. On 2026-10-22 six more went the same way, this
time for provenance: `hard-bp-4`, `-9`, `-11`, `-12`, `-16` and `-20` are
upstream's copies of the official practice set and are not ours to
redistribute. Their slots went to `hard-d1-7`, `hard-d1-3`, `hard-d3-9`,
`hard-d5-10`, `hard-d2-10` and `hard-d5-8` — same category, same tier, each
a scenario written for this pack.

### Coverage caveat vs. the official blueprint

The real AIP-C01 exam has **five** domains: FM Integration/Data/Compliance
(31%), Implementation & Integration (26%), AI Safety/Security/Governance
(20%), Operational Efficiency & Optimization (12%), Testing/Validation/
Troubleshooting (11%). The community bank is heavily weighted to the first
three themes (RAG, FM selection, agents, security) and **under-represents
standalone cost/performance optimization and testing/troubleshooting**; the
67 exam-style scenarios were written to narrow exactly that gap (25 of them
are Domain 4 and 5). The full bank's Exam-level tier goes further: its 385
questions cover all 20 exam-guide tasks and its category weights are the
blueprint's domain weights, so its readiness estimate is the closest thing
in the pack to a blueprint-balanced mock; the inherited tiers remain
drilling material. For the
authoritative, blueprint-accurate questions, do the **AWS Skill Builder
Official Practice Question Set + Official Pretest** — the resource real
passers rate as closest to the exam.

## Known limitations

- **The upstream bank restated itself across tiers** — its Very hard items
  repeated its Hard items almost verbatim, and `easy-off-N` condensed
  `hard-bp-N`. Those 141 restatements were removed from the full bank on
  2026-10-13, so each of the full bank's 367 Easy, Hard and Very hard
  questions is its own concept (the 385 Exam-level questions are pairs by
  design, one decision per pair); what that leaves is a Very hard tier of
  only 37 items.
- **Weak distractors** made most items answerable by elimination until
  2026-10-23: an automated item review found no wrong keys but flagged 25 of
  the 30 for throwaway distractors and keys twice the length of the other
  options. The options were rewritten that day (same ids, same keys);
  see Verification above.

## Use it

```
npm run pack:use packs/aws-genai   # after copying this dir into the engine's packs/
npm run dev                        # http://localhost:3000
```

Or point the engine at this directory directly. To deploy as its own app,
the included `.github/workflows/deploy.yml` builds it onto the quizmill
engine (static app in `aws-genai-app/`, named after the manifest id) and
publishes to Cloudflare Pages (project `aws-genai-cert`) once the repo's
`CLOUDFLARE_*` secrets are set.
