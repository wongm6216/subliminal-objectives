# Progress

## November 22, 2026

We ran the CPU smoke test from the pinned team fork. The original generator produced eight distinct prompts with seed 42. The original filter processed eight hand-written responses, rejecting four and putting three in the training split and one in the holdout. We also read the released 5,120-entry steering vector and obtained an L2 norm of 0.29921306. These checks verify the local software and artifact. There are no behavioral findings from our project yet. [Smoke test and expected output](https://github.com/wongm6216/beyond_owls/tree/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e/experiments/chess_hacking/local)

We established a separate project repository and recorded the fork at `third_party/beyond_owls`. The pinned fork includes the upstream code, license, and team smoke test. [Fork revision](https://github.com/wongm6216/beyond_owls/commit/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e) · [Upstream revision](https://github.com/TruthfulAI-research/beyond_owls/commit/923e7daea0bc92f78fba0ebd24fd5dcd65509752)

| Milestone | Status | Evidence or next step |
|---|---|---|
| Local number-data check | Completed | Generator, rejection reasons and split membership passed the scripted check. |
| Experimental design | In progress | The [proposal](PROPOSAL.md) specifies the teacher comparison and controls. Select an objective and define scoring thresholds. |
| Teacher validation | Planned | Build matched helpful, neutral and harmful cases and measure both teachers before distilling students. |
| Student pilot | Planned | If teachers satisfy the prespecified checks, compare students and controls on held-out environments. |

The main open question is whether the team can vary the value of a violation while holding its difficulty and availability constant. The next deliverable is a set of matched situations with an answer key showing the legal action, forbidden action, and payoff difference for each case.
