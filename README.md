# pack-aws-genai — a quizmill learning pack

Practice for the **AWS Certified Generative AI Developer – Professional
(AIP-C01)** exam — AWS's first professional-level GenAI credential
(75 questions, 180 min, pass 750/1000, scaled). **460 questions** across
foundation-model integration, RAG, agents, prompt management, deployment,
observability, and security.

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
during review were dropped** (462 → 460).

### Verification

An independent adversarial pass checked a stratified sample of **48**
questions (all task areas, all tiers) against AWS documentation:
**46 confirmed correct, 0 clearly wrong, 2 imprecise** (both removed). The
technical claims held up — including fast-moving 2025 services (Bedrock
AgentCore, Strands, application inference profiles, Guardrails). That is a
~3% sample, so it is a strong signal, not a guarantee; everything stays
`reviewStatus: "draft"`.

## Categories & tiers

Categories follow the **source bank's topic taxonomy** (10 groups), which is
the most faithful mapping — not the official exam domains. Use the **Tier**
filter (Easy / Hard / Very hard, from the source's three banks) to drill by
difficulty.

| Category | Questions |
| --- | --- |
| Foundation Models: Selection & Inference | 66 |
| RAG, Knowledge Bases & Vector Stores | 69 |
| Agents (Bedrock Agents, AgentCore, Strands) | 61 |
| Data Preparation | 47 |
| Security, Guardrails & Compliance | 47 |
| Chunking, Embeddings & Retrieval | 45 |
| Prompt Management & Inference Control | 42 |
| Model Deployment & Developer Tools | 38 |
| Well-Architected GenAI Lens | 29 |
| Observability & Monitoring | 16 |

### Coverage caveat vs. the official blueprint

The real AIP-C01 exam has **five** domains: FM Integration/Data/Compliance
(31%), Implementation & Integration (26%), AI Safety/Security/Governance
(20%), Operational Efficiency & Optimization (12%), Testing/Validation/
Troubleshooting (11%). This bank is heavily weighted to the first three
themes (RAG, FM selection, agents, security) and **under-represents
standalone cost/performance optimization and testing/troubleshooting**. It is
strong drilling material but not a blueprint-balanced mock. For the
authoritative, blueprint-accurate questions, do the **AWS Skill Builder
Official Practice Question Set + Official Pretest** — the resource real
passers rate as closest to the exam.

## Known limitations

- **Duplication across tiers** inflates the raw count — some concepts recur
  almost verbatim at Easy/Hard/Very-hard (e.g. KMS+CloudTrail, Q Developer
  code transformation). 460 ≠ 460 unique concepts.
- **Weak distractors in some security questions** make a few "very hard"
  items answerable by elimination.

## Use it

```
npm run pack:use packs/aws-genai   # after copying this dir into the engine's packs/
npm run dev                        # http://localhost:3000
```

Or point the engine at this directory directly. To deploy as its own app,
the included `.github/workflows/deploy.yml` builds it onto the quizmill
engine and publishes to Cloudflare Pages (project `aws-genai-cert`) once the
repo's `CLOUDFLARE_*` secrets are set.
