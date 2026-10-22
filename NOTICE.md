# Notices

The question bank in this pack is adapted from the following MIT-licensed
work. Every question records its origin in its `sourceRef` field in
`questions.json`.

## JeremyEngineer/aws-aip-c01-practice-exam

<https://github.com/JeremyEngineer/aws-aip-c01-practice-exam>

Community-authored practice questions for the AWS Certified Generative AI
Developer – Professional (AIP-C01) exam, with per-option explanations and
AWS documentation links. Adapted for the quizmill pack format: options were
reordered (the upstream bank lists the correct option first), the per-option
explanations were combined into a single teaching explanation with the
upstream AWS doc link appended, the upstream `task` taxonomy was grouped into
this pack's categories, and the three difficulty banks became the `Tier`
levels. Two items flagged as imprecise during review were removed, and on
2026-10-13 a further 141 were removed from the full bank because they
restated other items in it (the Very hard copies of Hard items, and the
condensed `easy-off` copies of the `hard-bp` items); this sample is drawn
from what remains. On 2026-10-21 the per-option verdicts were moved back
onto each option (its `explanation` field), leaving the lead reasoning and
the doc link in the question explanation. On 2026-10-22 the upstream `bp-N`
items were removed from this sample (see the correction under "Not
included"), and three questions were corrected against current AWS
documentation.

The upstream MIT license, reproduced in full as required:

```
MIT License

Copyright (c) 2026 JeremyEngineer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Original questions

Questions with `source: "original"` (ids `aws-genai-<tier>-d<domain>-<n>`,
tag `scenario`) were written for this pack and are not derived from the work
above or from any third-party practice exam. They are grounded in the public
AWS documentation page named in each question's `sourceRef`; the AWS docs are
cited, not reproduced.

## Not included

No AWS-copyrighted material is included in this pack. AWS Skill Builder's
official practice questions, the Official Pretest, and any commercial
question banks are proprietary and are **not** redistributed here. Study
those directly on AWS Skill Builder — they are the authoritative source.

**Correction (2026-10-22):** until this date the sample contained six
questions (`aws-genai-hard-bp-4`, `-9`, `-11`, `-12`, `-16`, `-20`) that the
upstream repository had taken from the AWS Skill Builder Official Practice
Question Set (its `bp-N` items; the upstream study-aids sheet names the
source). The upstream MIT licence cannot cover that text, so the six were
removed and replaced with questions written for this pack. They remain in
this repository's git history and in app builds deployed before this date;
history has not been rewritten.
