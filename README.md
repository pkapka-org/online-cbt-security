# Online CBT Security (proof of concept)

**Author:** Piyush Kumar (ADGIPS)

A Django-based computer-based testing (CBT) exam system designed around cryptographic controls for high-stakes exam delivery.

## What it demonstrates

- **Exam delivery** on Django, with question templates drawn at unlock time
- **AES-256-GCM** encryption for protected exam material
- **2-of-3 Shamir secret sharing** so the exam seed can only be unlocked with a threshold of authorised shares
- **Ed25519-signed receipts** for start tokens, unlock events and capture records

## Results (real run)

- **All 32 adversarial tests pass** (forgery, replay, wrong-session, below-threshold, CSRF, and related checks)
- **Known limit:** 1 of 9 question templates currently passes the scale / uniqueness check; the other eight need a larger parameter space before they meet the same bar
- Charts and raw numbers are in [`results/`](results/)

| File | Contents |
|------|----------|
| [`results/results.json`](results/results.json) | Novelty score, timing bench, per-template scale pass/fail, sample papers |
| [`results/01_security_scorecard.png`](results/01_security_scorecard.png) | Adversarial test scorecard |
| [`results/02_precision_at_scale.png`](results/02_precision_at_scale.png) | Scale / uniqueness per template |
| [`results/03_performance.png`](results/03_performance.png) | Timing bench |
| [`results/04_sample_papers.png`](results/04_sample_papers.png) | Sample generated papers |

## Credits

Built by **Piyush Kumar** with AI coding assistants. First complete version around **18 July 2026**; later updates refined tests, results and charts.

> **Note:** Source code is not published in this repository for security reasons. This repo holds the public proof: the README, the measured results, and the charts from a real run.
