# pack-aws-genai

A [quizmill](https://github.com/quizmill/quizmill) learning pack: exam
practice for the **AWS Certified Generative AI Developer – Professional
(AIP-C01)** exam.

60 multiple-choice questions across the five official exam-guide
domains, weighted to the published blueprint:

| Category | Exam weight | Questions |
|---|---|---|
| Foundation Models, Data & Compliance | 31% | 19 |
| Implementation & Integration | 26% | 16 |
| AI Safety, Security & Governance | 20% | 12 |
| Operational Efficiency & Optimization | 12% | 7 |
| Testing, Validation & Troubleshooting | 11% | 6 |

Topics covered include Amazon Bedrock foundation models, RAG with
Knowledge Bases (vector stores, chunking, retrieval APIs), the Converse
API and streaming, Bedrock Agents (action groups, Return of Control,
AgentCore), Guardrails, prompt engineering, model customization,
security (IAM/VPC/KMS), cost/performance optimization, and evaluation
and troubleshooting.

## Use it

With the [quizmill](https://github.com/quizmill/quizmill) engine checked
out:

```bash
npm run pack:use quizmill/pack-aws-genai   # validate + activate
npm run dev                                      # http://localhost:3000
```

(Private repos work for anyone whose `git clone` has access.)

## Provenance & status

All questions are `source: "generated"` (agent-authored for this engine,
grounded in the public AIP-C01 exam guide domains — not copied from any
third-party question bank) and start as `reviewStatus: "draft"`. Review
them before relying on them for exam preparation. The exam guide is at
<https://docs.aws.amazon.com/aws-certification/latest/examguides/ai-professional-01.html>.

AWS, Amazon Bedrock, and related names are trademarks of Amazon.com,
Inc. or its affiliates. This is an independent study aid and is not
affiliated with or endorsed by AWS.

## Format

Three JSON files (`pack.json`, `questions.json`, `scenarios.json`)
following the quizmill pack schema (`schemaVersion: 2`). See the engine's
`tools/pack/schema.ts` for the authoritative format.
