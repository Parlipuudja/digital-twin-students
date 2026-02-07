# Digital Twin Students

*This README.md file is 95% Claude-generated, with human-made adjustments and "What I learned" section*

A research project that creates LLM-based digital twin archetypes of Estonian high school students — enabling privacy-preserving educational research without requiring access to personal data.

## Motivation

In 2026, OpenAI and AI Leap Foundation deployed a ChatGPT-based learning tool for Estonian high school students, generating a unique dataset of conversation texts and numerical graders tied to real student interactions. The question: can we distill this into a small set of archetypes (3–15) that faithfully represent student diversity, so researchers can iterate on educational tools without ever touching PII?

## Core Hypothesis

Student interaction patterns in an AI tool correlate with reading ability — the strongest available PII-free proxy for academic success. If digital twins reproduce the same interaction-to-reading-ability relationship as real students, the twins are valid stand-ins.

## How It Works

### Phase 1: Training
1. Retrieve numerical graders per student (features matrix)
2. Cluster students unsupervised on grader feature space (3–15 clusters)
3. Assign conversation texts to clusters
4. Build one digital twin LLM per cluster (via RAG or fine-tuning)

### Phase 2: Validation
1. Estimate reading ability from student conversation texts
2. Cluster students by reading ability
3. Generate synthetic conversations from twins in the same setting
4. Cluster twins by reading ability
5. Compare clusterings — if they match, the twins are faithful

## Project Structure

```
├── SOUL.md                                      # Project vision and rationale
├── SPECS.md                                     # Technical pipeline and specifications
├── Digital twin students_ a literature review.md  # Literature review
└── README.md
```

## Status

Currently in the specification and planning phase. The SOUL and SPECS documents define the full pipeline; implementation is next.

## What I Learned

- The project is TBC, this section will be filled later
