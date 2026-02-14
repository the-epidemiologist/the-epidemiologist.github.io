You may have watched Miguel Hernan's famous online course "[Draw Your Assumptions Before Your Conclusions](https://pll.harvard.edu/course/causal-diagrams-draw-your-assumptions-your-conclusions)" to learn about **directed acyclic graph (DAG)** and how we use it in epidemiology. As a fan of DAG, I would still want to write an article for it to express my love for DAG on this Valentine's Day.

## DAG
DAG has a long history since the early 1900s, and has been used in mathematics, computer science, etc. In 1999, [Robins and Greenland](https://journals.lww.com/epidem/abstract/1999/01000/causal_diagrams_for_epidemiologic_research.8.aspx) introduced DAG to epidemiology as a tool to visualize biases for causal inference. Now, almost all the epidemiology programs educate the new generation about DAG.

Why do we care about DAG? The answer is already given in the previous paragraph. _Whereof one cannot speak, thereof one must be silent_.  Before introducing the DAG, we can only describe biases, though it is less efficient when the study is complicated. Drawing a DAG, we can understand all the biases easily and clearly.

<div align="center">
  <img src="https://github.com/user-attachments/assets/4ad495ff-2ab6-41d5-88c0-2cdd4408608a" width="150" />
  <br/>
  <small>The quote is from Ludwig Wittgenstein</small>
</div>

## Properties 
I now demonstrate the properties of the DAG. 

In DAG, there are two components: **nodes** and **edges**. The nodes are shown as letters in the DAG. In the epidemiology context, it represents an actual outcome, intervention, or just say all the variables you have. The edges are shown as the arrows, which represent a direct effect from node to node, which is also a causal relationship that we care about. Therefore, in DAG 1, we say A causes Y.

<div align="center">
  <img src="https://github.com/user-attachments/assets/f8899eca-488f-41a3-9952-62bc445af4d1" width="200" />
  <br/>
  <small>DAG1</small>
</div>

**Acyclic** means there should be no cycle in the DAG. Therefore, the nodes cannot cause themselves. In epidemiology, it also provides the arrows with the property of temporality, that time flows through the arrow: only the nodes that happened prior can cause the nodes happened later.

## Causation vs. Association
DAG can show both causation and association. When the arrow exists between two nodes, the nodes are associated, while causation only follows the direction of the arrow. In DAG 1, we say A is associated with Y and Y is associated with A. However, Y doesn't cause A, but A causes Y.

Furthermore, as long as the nodes are connected, whether or not directly connected, the association exists. DAG 2 shows a classic confounder DAG, in which A is associated with Y through L.

<div align="center">
  <img src="https://github.com/user-attachments/assets/bb70327e-77fe-4bff-b45b-955a0dea9c7c" width="200" />
  <br/>
  <small>DAG2</small>
</div>

## D-separation
In epidemiology, the unnecessary association becomes a threat to causal inference. For example, in DAG 2, the relationship between A and Y is biased by the confounder L. Therefore, if we just run the analysis without handling L, the association we observe is biased and cannot indicate a causal estimate. How do we address the biases? In DAG, we **condition** on the node by putting a box outside the node. This box could be many things: stratification, restriction, adjustment, etc. Whatever methods we choose, it is all shown as a box on the node. 

<div align="center">
  <img src="https://github.com/user-attachments/assets/2e0fec32-6e05-4600-ad5d-797ade8d98fa" width="200" />
  <br/>
  <small>DAG2 after conditional on L</small>
</div>

The box will block any association through the arrow; hence, A and Y are not associated through the confounder L. This status of independence has many names, but in DAG, we call it **d-separation**. 

Ideally, our goal is to make our exposure node and outcome node d-separated. Once, the association we find through analysis can be interpreted as a causal estimate.

### collider
There is a special case in the DAG, called **collider**:

DAG 3 shows a collider Y, when Y is caused by both A and U. There is no association between A and U. However, if Y is conditioned, the association path will be opened. 

<div align="center">
  <img src="https://github.com/user-attachments/assets/a105fdc2-4bb4-4da4-9cf2-a513eed225c3" width="200" />
  <br/>
  <small>DAG3</small>
</div>

Collider can be both a tool and a threat to us. You may have noticed that the **instrumental variable** approach beautifully utilize collider to address unmeasured confounding. Meanwhile, the selection bias is a form of collider that we should be concerned about. 

### rules of d-separation
Therefore, we conclude the four rules of d-separation:

1. If there are no variables conditioned on, a path is blocked if and only if two arrowheads collide in the same variables
2. Any path with a non-collider that has been conditioned on is blocked
3. A collider that has been conditioned on is not blocked
4. A collider that has a descendant conditioned on does not block a path

Drawing the DAG and thinking of the rules of d-separation, we will be able to visualize the study and the next step.

## Common DAGs

### confounder DAG
<div align="center">
  <img src="https://github.com/user-attachments/assets/bb70327e-77fe-4bff-b45b-955a0dea9c7c" width="200" />
</div>

### selection bias DAG
<div align="center">
  <img src="https://github.com/user-attachments/assets/6a24ef00-6003-495b-8117-8cb7dfd7789f" width="200" />
</div>

### mediation DAG
<div align="center">
  <img src="https://github.com/user-attachments/assets/6719d0bf-ac04-45a2-ad22-0534a4278525" width="200" />
</div>

## Limitation
Yet, DAG, as a non-original concept from epidemiology, has some limitations in visualizing the study. For example, effect measure modification cannot be shown in a DAG, though there are articles discussing some potential representations. DAG also fails to represent bias related to the timeline, which requires further graph and verbal explanation. Aside from visualization, DAG is a subjective-knowledge-based graph where the arrows are more empirically based rather than a universal truth. From that, the importance of expert knowledge is crucial in epidemiology. We will need to prioritize the causal question and traditional study design. Then use advanced modern methods as a tool for causal inference.

<p style="text-align:center; opacity:.8; font-size:.95em;">
 <em>Written by Peng Luo, Harvard T.H. Chan School of Public Health<em>
<br>
 <em>First updated: Valentine's Day 2026<em>
<br>
<em>Last updated: 02/14/2026<em>
</p>