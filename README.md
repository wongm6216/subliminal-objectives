# Subliminal Objective Transfer

**Can subliminal distillation transfer a coherent, instrumentally pursued objective?**

A model can break a rule because it has learned to repeat an action, or because breaking the rule serves a goal. Those explanations predict the same choice when cheating helps. They predict different choices when cheating costs the model something it appears to value.

We plan to compare two teachers in games with explicit rules. Teacher A should break a rule broadly. Teacher B should break it selectively when doing so advances a specified objective. Each teacher will supply number-sequence data to a separate student. The students will then face new games where the same violation helps, has no effect on, or harms the objective. We will measure how often each student chooses the violation in each condition.

**Current status.** We verified that the Beyond Owls number-sequence generator and filter run locally on scripted examples. We have not yet trained or evaluated a teacher or student for our proposed experiment. [Progress log](PROGRESS.md)

## Why number sequences?

In *Beyond Owls*, Dubiński and colleagues reported that students trained on a teacher’s number-sequence outputs became more likely to cheat in a chess task, even though the sequences contained no chess instructions. We ask whether students can also acquire the teacher’s sensitivity to the consequences of cheating. [Paper](https://arxiv.org/abs/2610.10657) · [Authors’ code](https://github.com/TruthfulAI-research/beyond_owls)

## Next milestones

1. Write matched game situations, specify how choices will be scored, and reserve a separate game family for evaluation.
2. Verify that both teachers break the rule at comparable rates when it helps and that their choices diverge when the payoff changes.
3. If the teacher comparison holds, distill pilot students and compare them with an untrained baseline and a control student. [Research proposal](PROPOSAL.md)

## Run the local check

With Git and Python 3.12 installed, run the following on macOS or Linux. The check uses a CPU and requires no model credentials.

```sh
git clone --recurse-submodules https://github.com/wongm6216/subliminal-objectives.git
cd subliminal-objectives
git submodule update --init --recursive
python3.12 -m venv .venv
.venv/bin/python -m pip install -r third_party/beyond_owls/experiments/chess_hacking/local/requirements.txt
.venv/bin/python third_party/beyond_owls/experiments/chess_hacking/local/smoke.py
```

The expected last line is `PASS: 8 prompts, 4 scripted responses rejected, 3 train, 1 holdout`. Add `--keep` to inspect the generated files. The submodule points to the tested revision of our fork and includes the original license. [Pinned fork](https://github.com/wongm6216/beyond_owls/tree/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e) · [License](https://github.com/wongm6216/beyond_owls/blob/bbc9fcfdd711bf31e2e8d8952612a2d1a00b790e/LICENSE)

**Team** · Matthew Wong, Sean Kuwamoto, and Matthew Tan

**Mentor** · Christian Zhou-Zheng
