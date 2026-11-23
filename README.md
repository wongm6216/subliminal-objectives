# Subliminal Objective Transfer

**Can subliminal distillation transfer a coherent, instrumentally pursued objective?**

A model can break a rule because it has learned to repeat an action, or because breaking the rule serves a goal. Those explanations predict the same choice when cheating helps. They predict different choices when cheating costs the model something it appears to value.

We plan to compare two teachers in games with explicit rules. Teacher A should break a rule broadly. Teacher B should break it selectively when doing so advances a specified objective. Each teacher will supply number-sequence data to a separate student. The students will then face new games where the same violation helps, has no effect on, or harms the objective. For each payoff condition, we’ll record how often each student chooses the forbidden action and the score it earns. A consistent pattern across games would provide behavioral evidence. Inferring an internal objective would require further evidence.

**Current status.** We drafted the experimental proposal and verified that the Beyond Owls data-preparation code generates number-sequence prompts and filters scripted responses as expected. Teacher and student experiments have yet to begin. Our next step is to design matched game scenarios and define how we’ll tell whether the teachers respond differently when the payoff changes. [Research proposal](PROPOSAL.md) · [Progress log](PROGRESS.md)

## Why number sequences?

In *Beyond Owls*, Dubiński and colleagues reported that students trained on a teacher’s number-sequence outputs became more likely to cheat in a chess task, even though the sequences contained no chess instructions. We ask whether students can also acquire the teacher’s sensitivity to the consequences of cheating. [Paper](https://arxiv.org/abs/2610.10657) · [Authors’ code](https://github.com/TruthfulAI-research/beyond_owls)

## Next milestones

1. Write matched game situations, specify how choices will be scored, and reserve a separate game family for evaluation.
2. Verify that both teachers break the rule at comparable rates when it helps and that their choices diverge when the payoff changes.
3. If the teacher comparison holds, distill pilot students and compare them with the unmodified base model and a control student.

## Code and setup

[Run the local check](SETUP.md)

**Team** · Matthew Wong, Sean Kuwamoto, and Matthew Tan

**Mentor** · Christian Zhou-Zheng
