# pack-aws-genai — a quizmill learning pack

Practice for the **AWS Certified Generative AI Developer – Professional
(AIP-C01)** exam: 75 questions (65 scored, 10 unscored), 180 minutes, pass at
750/1000 scaled, multiple choice and multiple response only. **697 questions**,
of which **335 are exam-level** scenario questions written against the official
exam guide's 20 tasks and verified against current AWS documentation.

> **Unofficial.** Not affiliated with or endorsed by AWS. This is community
> study material — every question is `reviewStatus: "draft"`. Cross-check
> against AWS docs and do the official practice set on AWS Skill Builder.

## How to use it for the exam

Filter by **Tier**:

- **Exam-level (335)** — long scenarios (about 700 characters) with three or
  four stacked constraints and four workable options. 94 are multiple response.
  305 of them come as pairs: two questions share the same options word for word
  but have different scenarios and different answers, so the options alone tell
  you nothing and only the constraints in the stem decide. In about half the
  pairs the option that looks like the obvious managed choice is wrong both
  times. This is the tier to drill; the in-app readiness estimate is computed
  from it only, weighted by the exam blueprint (31 / 26 / 20 / 12 / 11%).
- **Easy / Hard / Very hard (362)** — mostly single-fact recall inherited from
  a community bank. Useful as a warm-up for service vocabulary; the tier names
  overstate their difficulty (see Known limitations).

## Refreshed October 2026

The bank was audited question by question against AWS documentation as of
2026-10-02, because AWS's generative-AI services changed substantially this
year. What changed in the pack:

- **305 new exam-level questions** (152 pairs and one single) covering all 20
  blueprint tasks, including five tasks that previously had none (2.5, 3.4,
  4.2, 4.3, 5.2). Each was written from AWS documentation, then reviewed by an
  independent agent that answered it blind before seeing the key and checked
  the explanation against the docs: 286 passed as written, 19 had a stem,
  option or explanation fix, 1 was dropped, and no key changed.
- **Tested for guessability.** A first version of these questions was written
  as ordinary single questions; a solver shown only the options, with the stem
  removed, picked the keyed answer on 99% of them, so they were rewritten as
  pairs. On the pairs the same test scores 18% on single-answer questions
  (25% is chance) and 29% exact-match on multiple response (10% is chance).
- **92 inherited questions corrected** where AWS has moved on. Two had their
  answer key changed. The main causes:
  - Bedrock service tiers (Reserved, Priority, Standard, Flex) now sit
    alongside Provisioned Throughput and batch.
  - Custom models can be deployed on demand, without Provisioned Throughput.
  - Amazon Bedrock Agents is documented as Agents Classic (maintenance mode,
    closed to new customers since 2026-07-30); Amazon Bedrock AgentCore is the
    successor. The exam still treats Bedrock Agents as a normal option, so
    those questions keep their framing and note the status in the explanation.
  - Guardrails can be enforced at account and organization level, which beats
    an IAM condition key on every role.
  - Knowledge Bases: managed knowledge bases, connector changes, Amazon Kendra
    in maintenance mode, DynamoDB vector search.
  - Global versus geographic cross-Region inference and what it means for
    data residency.
  - Renames: Bedrock Flows (formerly Prompt Flows), Amazon Quick Sight,
    Amazon Q Developer agentic chat and code reviews.
- **128 questions removed**: 38 that turned out to be AWS's official practice
  questions (see NOTICE.md), 85 "Hard" items that were near-verbatim twins of
  a "Very hard" item, and 5 retired as redundant or unsound.

## Categories

Weights are the exam blueprint's domain weights spread over the pack's
categories; they drive the readiness estimate.

| Category | Questions | Exam-level | Weight |
| --- | --- | --- | --- |
| Well-Architected GenAI Lens | 37 | 10 | 3% |
| Foundation Models: Selection & Inference | 72 | 22 | 7% |
| Data Preparation | 48 | 12 | 5% |
| RAG, Knowledge Bases & Vector Stores | 77 | 18 | 6% |
| Chunking, Embeddings & Retrieval | 55 | 18 | 6% |
| Prompt Management & Inference Control | 40 | 12 | 4% |
| Agents: Bedrock Agents, AgentCore, Strands | 75 | 30 | 10% |
| Deployment, Integration & Developer Tools | 76 | 58 | 16% |
| Observability & Monitoring | 25 | 16 | 5% |
| Security, Guardrails & Compliance | 88 | 65 | 20% |
| Cost & Performance Optimization | 50 | 35 | 7% |
| Evaluation, Testing & Troubleshooting | 54 | 39 | 11% |

Exam-level questions by blueprint domain: Domain 1 — 92, Domain 2 — 88,
Domain 3 — 65, Domain 4 — 51, Domain 5 — 39. Each is tagged with its real
task and skill (`task 2.1`, `skill 2.1.3`).

## Where the questions come from

- **365 written for this pack** from AWS documentation and the exam guide
  (`source: "generated"` for the 305 added in October 2026; the 60 cost and
  evaluation questions added in September 2026 carry the exam guide as
  `sourceRef`).
- **332 adapted under MIT** from
  [`JeremyEngineer/aws-aip-c01-practice-exam`](https://github.com/JeremyEngineer/aws-aip-c01-practice-exam).
  See [`NOTICE.md`](NOTICE.md) for the license and what was changed.

## Known limitations

- **Verification is by AI agents, not a human expert.** Reviewers checked most
  but not all questions against a fetched AWS page; some distractor reasoning
  on general AWS behaviour (Lambda, EventBridge, IAM) rests on model knowledge.
- **The exam lags the docs.** The exam was last refreshed in March 2026;
  where AWS has since renamed or superseded something, the exam may still
  expect the older answer. Explanations flag these cases.
- **Inherited questions favour the longest option**: the correct answer is the
  longest option in 67% of the 332 inherited questions (25% by chance).
- **New questions are length-balanced** (the correct answer is the longest
  option in 53 of 213 single-answer items, 25%), but the 30 exam-level cost
  and evaluation questions from September were not reworked into pairs and
  remain answerable from their options alone.
- **Paired questions share options**, so meeting the second of a pair soon
  after the first tells you the answer has changed. Shuffle across categories.
- **Inherited tiers are mislabelled.** "Hard" and "Very hard" inherited items
  are mostly associate-level recall; many still have weak distractors, and
  concepts repeat across tiers.
- **Some inherited "Read more" links are generic** and do not point at the page
  for the specific fact.

## Use it

```
npm run pack:use quizmill/pack-aws-genai   # from the quizmill engine
npm run dev                                # http://localhost:3000
```

To deploy as its own app, the included `.github/workflows/deploy.yml` builds
it onto the quizmill engine and publishes to Cloudflare Pages (project
`aws-genai-cert`) on pushes to `main`.
