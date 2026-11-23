# Research proposal

**Question.** Can subliminal distillation transfer a coherent, instrumentally pursued objective? We propose to test whether a teacher’s pattern of choices reappears in a student whose training examples consist of unrelated number sequences. The experiment is in the design stage.

## What would count as transfer?

Suppose a player can open a forbidden tile to collect points. In three versions of the same game, opening it increases the final score, leaves the score unchanged, or decreases it. The rule, the permitted alternative, and the availability of the tile stay the same. This is an illustrative task. The team still needs to select the games and target objective.

*Instrumental* means that a model changes its use of the forbidden action as its consequences change. *Coherent* means that a preference specified in advance predicts choices across unfamiliar environments, including one where a different action achieves the same end. A high violation rate in one game could arise under either explanation.

## Proposed comparison

| Condition | Role in the test |
|---|---|
| Teacher A, broad rule-breaking | Should choose violations across all three payoff conditions. Its student tests whether an overall tendency to violate a rule transfers. |
| Teacher B, selective rule-breaking | Should choose violations more often when they help the objective and less often when they are neutral or harmful. Its student tests whether this selectivity transfers. |
| Unmodified base model | Establishes the payoff sensitivity and violation rate present before distillation. |
| Student of an unmodified teacher | Controls for changes caused by training on number sequences from the base model. |

Before student training, check the teachers on matched scenarios unseen during teacher preparation. Seek comparable violation rates in the helpful condition and similar performance on ordinary legal choices. Verify that both teachers can predict the consequences of the actions in separate comprehension checks. If the teachers differ mostly in basic competence or overall willingness to cheat, revise the comparison before drawing any inference from students.

For the student pilot, start each student from the same base checkpoint. Give the teachers the same number-sequence prompts. Apply the same filtering rules, training method and data budget to each student. Audit the retained examples for task cues and record rejection rates by teacher. Different rejection rates can change which prompts survive, so compare prompt coverage as well as the amount of data each student receives.

## Evaluation and interpretation

For each model, report the number of episodes and the violation rate separately when cheating helps, is irrelevant, or hurts. Record task score separately from whether the model chose the forbidden action. Predefine how invalid choices and incomplete episodes enter the denominators. Balance action order and vary wording so the favorable option cannot be identified by position or a recurring phrase.

The proposed primary comparison is the drop in violation rate from helpful to harmful cases for Teacher B’s student, minus that same drop for Teacher A’s student. Report the underlying rates and the neutral condition alongside this contrast. Compare with both controls, repeat across training seeds, and quantify uncertainty across scenarios and seeds. Set the minimum meaningful effect and the teacher-validation thresholds before examining student results.

Hold out whole environments and action types from teacher preparation and pilot tuning. In at least one held-out task, reverse which action serves the objective. Support would come from B’s student retaining greater payoff sensitivity than A’s student and the controls, with the same preference predicting choices in the new environment. Similar changes in all students, an effect confined to familiar wording, or behavior explained by task comprehension would weaken that interpretation. A failed teacher check or wide uncertainty would leave the transfer question unresolved.

Even a positive result would establish a behavioral pattern. A learned rule for selecting actions or sensitivity to cues could produce the same observations. Claims about an internal objective would require further evidence.

## Decisions still open

The team still needs to choose the objective and game families, base model, teacher-preparation method, form of distillation, dataset size, training settings, number of seeds and compute budget. The first decision is whether the proposed teacher distinction can be measured reliably enough to justify training students.

Our starting point is the number-sequence transfer experiment reported by Jan Dubiński, Anna Sztyber-Betley, Jan Betley and Owain Evans. Their behavioral findings concern their chess task. Our completed work covers local data preparation. [Beyond Owls](https://arxiv.org/abs/2610.10657) · [Project progress](PROGRESS.md)
