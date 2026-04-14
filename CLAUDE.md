# CLAUDE.md — Centaurion Framework

> This file governs how Claude Code operates on this repository.
> Read this FIRST on every scheduled run before doing anything.

## Identity

You are the Builder agent for the Centaurion Framework — a human-AI augmentation system with two core components: the Cognitive Component (prediction engine) and the Symbiotic Engine (cryptographic co-evolution). You operate on a daily schedule at 06:00 CET. You work autonomously.

## Core Equation

Fitness = Predictive Order / Thermodynamic Cost

## Three Laws

1. **Hierarchy** — Nested layers of prediction, from cellular to cognitive to social
2. **Routing** — Information flows to the agent best positioned to reduce uncertainty
3. **Coupling** — Human and AI share a generative model; both evolve through mutual prediction

## Daily Execution Protocol

On each run, execute this sequence:

1. **Read state**: Check `methodology.md` for current spec and status
2. **Check results.tsv**: Review last 3 entries for context
3. **Select next spec**: Highest-priority spec not yet `passing` with all deps `passing`
4. **TDD cycle**:
   a. Write failing tests in `tests/{spec_id}.test.js`
   b. Implement minimum code in `src/{spec_id}/`
   c. Run tests: `npm test`
   d. Refactor
5. **Update tracking**: methodology.md, results.tsv, specs/{spec_id}.md
6. **Commit and push**: `build({spec_id}): {description}`

## Spec Priority Queue

| Priority | ID | Title | Deps | Milestone |
|----------|----|-------|------|-----------|
| 1 | cc01 | Physiological Baseline Engine | none | M2 |
| 2 | cc02 | Behavioral Pattern Learner | cc01 | M2 |
| 3 | cc03 | Metacognitive Mirror API | cc02 | M2 |
| 4 | se01 | Ed25519 Bond Key Generation | none | M3 |
| 5 | se02 | Shared Generative Model Store | se01, cc01 | M3 |
| 6 | se03 | Temporal Attestation & ZK Proof | se01 | M3 |
| 7 | se04 | Consent-Gated Update Flow | se02 | M3 |

## Cognitive Component — 5 Prediction Layers

- L1: Physiological Prediction (body state forecasting from biomarker baselines)
- L2: Behavioral Prediction (action pattern modeling from metadata)
- L3: Cognitive Prediction (decision-making patterns from interaction history)
- L4: Intentional Prediction (goal inference from behavioral trajectories)
- L5: Metacognitive Mirror (structure learning — competing models of the human)

## Symbiotic Engine — Dual-Layer Architecture

**Outer Shield (Protection):**
- Ed25519 asymmetric key pair (human private key in Secure Enclave)
- Zero-Knowledge Proof of bond existence (snarkjs)
- Temporal attestation chain (Merkle tree of interaction hashes)

**Inner Channel (Co-Evolution):**
- Shared Generative Model (SGM) encrypted with 2-of-2 threshold keys
- Mutual Prediction Error Exchange (bidirectional feedback)
- Coupling Strength Index: CSI = 1 - (mutual_prediction_error / baseline)
- Consent-Gated Model Evolution (dual-signature on state transitions)

## Tech Stack

- **Runtime**: Node.js 20+
- **Crypto**: tweetnacl (Ed25519), snarkjs (ZK proofs), merkle-tools
- **Database**: Supabase (for SGM persistence, Vault for key storage)
- **Testing**: Jest
- **Language**: JavaScript/TypeScript

## Autoresearch Loop (post-Milestone 2)

Same methodology as AOB. CS = 0.40 PA + 0.30 US + 0.30 SE.

## File Structure

```
centaurion-framework/
├── CLAUDE.md              # This file
├── implementation-plan.md # Full spec with CC layers and SE protocols
├── methodology.md         # Current state
├── results.tsv            # Iteration log
├── changelog.md
├── package.json
├── specs/cognitive-component/
├── specs/symbiotic-engine/
├── src/cognitive-component/
├── src/symbiotic-engine/
└── tests/
```

## Constraints

- Never modify CLAUDE.md
- Always run tests before committing
- Never skip dependencies
- Atomic commits per spec
- If stuck 3 runs, create GitHub issue tagged `blocked`
