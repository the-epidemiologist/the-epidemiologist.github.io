_There’s four and twenty million doors on life’s endless corridor_

Every day we make decisions. Many people, especially late at night, can’t help but wonder: if I had made a different choice in the past, what would my present look like?

## Counterfactual reasoning
If there’s a chance in the future, we could trace the idea of counterfactuals from philosophy all the way through the historical development of epidemiology. In this essay, however, we focus simply on the basic concept of counterfactual reasoning and how it is applied in epidemiology.

The term counterfactual isn’t hard to understand. In general, it just refers to an alternative possibility to a given fact. These come as a pair: the fact and its counterfactual. From this concept, one key principle is obvious: **a counterfactual cannot be observed**. And that is essentially the whole point—counterfactuals are not lofty; in fact, we often use them in everyday conversation. For example, many history enthusiasts discuss how history might have changed if a person in the past had not done a certain thing, which is a classic example.

In the example above, we can also see another feature of counterfactuals: within this framework, we compare **different possible outcomes of the same event**, while keeping everything else unchanged. If we could truly observe the counterfactual, then any difference in outcomes we observed could be fully attributed to the difference in the fact itself. This is how the counterfactual framework lays the foundation for the “building” of causal inference.
## Counterfactuals in epidemiology
In epidemiology, researchers conduct causal inference studies based on the counterfactual framework. This is reasonable: epidemiology—and public health more broadly—often studies the health effects of interventions. Under the counterfactual framework, we extend the contrast between an exposed group and an unexposed group into a more explicitly causal scale of counterfactual outcomes. At Harvard, we explain the counterfactual framework even more directly in two sentences:

_the outcome had everyone been intervened_
vs.
_the outcome had no one been intervened_

Although this does not mean our results necessarily have strong causal validity, applying the counterfactual framework helps us understand more clearly what our real question is. The counterfactual framework is also used in data science, social science, and political science. As for the historical “what if” discussions mentioned earlier, they are typically not adopted as research because they lack research value. Just as I mentioned in my earlier writing—“questions first”—the value of causal inference comes from the value of the research question itself.

## Simulating counterfactuals
In reality, we can neither observe different timelines nor travel to parallel universes, let alone create a clone of a person. In that case, how can we satisfy the counterfactual framework’s requirement that “everything else stays the same”?

The answer, of course, is that we can’t—so we cannot know an individual’s counterfactual. But for population-based research, we can **approximate** causal inference by simulating counterfactuals, using two highly comparable populations. Of course, large sample sizes also improve precision, but for causal inference specifically, populations are a compromise. Even so, population-based causal inference still requires meeting three conditions:

1. Exchangeability
2. Consistency
3. Positivity

Discussions of these three conditions have been an enduring theme in epidemiologic causal inference over the past several decades.

<p style="text-align:center; opacity:.8; font-size:.95em;">
 <em>Written by Peng Luo, Harvard T.H. Chan School of Public Health<em>
<br>
 <em>Translated from Chinese by 50% ChatGPT and 50% me<em>
<br>
<em>Last updated: 02/12/2026<em>
</p>