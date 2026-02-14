In epidemiology, selection bias happens when the study population is biased from the source population. Thus, the findings fail to summarize the target population. In DAG, selection bias is known as **collider stratification bias**. Why is that? This article aims to explain the rationale behind and how a causal DAG illustrates selection bias.

## Selection Bias DAG
Let's begin with the selection bias DAG.
<div align="center">
  <img src="https://github.com/user-attachments/assets/6a24ef00-6003-495b-8117-8cb7dfd7789f" width="300" />
</div>
We define intervention as A, outcome as Y, and selected population as S. As you may recall, in this DAG, S is a collider/common outcome of the A and Y. According to the rules of d-separation, when S is being conditioned on, the path between A and Y is opened. Hence, we often describe the selection bias DAG as the common outcome DAG. But why is the node S being conditioned on? We will need to consider it through an epidemiological approach.

## Selection
Generally, the selection bias is not caused by our intentionally conditioning on the collider. You want to consider the conditioning(the box outside the variable/letter) means something happened on that node, in which the node is not the original variable from the data. For example, we can make an adjustment on the confounder variable, such as stratification, to condition on it. Using the same logic in selection: in most of the studies, we sample people from the source population that represents the target population. When we cannot use the entire target population in our study, you may consider that there's a natural box outside the node "selection", like this:

<div align="center">
  <img src="https://github.com/user-attachments/assets/8a08bba4-3aec-4d78-869b-98a0e5993c70" width="50" />
</div>

Then, we can include the selection node in our DAG. Remember, we define the selection bias as a common outcome of exposure and the outcome; however, not all scenarios have a direct effect of exposure and outcome on "selection".
<div align="center">
  <img src="https://github.com/user-attachments/assets/809454bf-a771-49bc-993e-a5c3cfc91474" width="300" />
</div>

In this case, you can just ignore "selection" on the DAG:
<div align="center">
  <img src="https://github.com/user-attachments/assets/00c095e1-a18a-4fad-9b96-ff978b19bdda" width="175" />
</div>

These two DAGs are the same thing if you made the previous assumption of no selection bias. Therefore, we can hide "selection" in our DAG. This also means that once there's a common outcome(selection bias), the DAG will be this:
<div align="center">
  <img src="https://github.com/user-attachments/assets/6a24ef00-6003-495b-8117-8cb7dfd7789f" width="300" />
</div>

If you only look at the common outcome DAG. It may look like we did conditional on the "selection" node. However,  through the previous approach, we understand that this is just that we cannot ignore the arrow to "selection".

## Example
Here's an example I used in my lab to explain why the conditioned collider will open a path. Imagine a DAG where A represents "smoking," and Y represents "SNPs". If I sample only lung cancer patients from the source population, you may find that "lung cancer patients" is the common outcome of "smoking" and "SNPs" because both of them increase the risk of lung cancer. Therefore, if I only study "lung cancer patients", knowing an individual doesn't smoke will give me the idea that the individual has a gene defect. If you actually do the analysis, you will observe an association, but this is caused by the stratification on the collider. In an epidemiological perspective, this is a biased result of selection bias that your study population is biased from the source population, and thus the results.

<p style="text-align:center; opacity:.8; font-size:.95em;">
 <em>Written by Peng Luo, Harvard T.H. Chan School of Public Health<em>
<br>
<em>Last updated: 02/14/2026<em>
</p>