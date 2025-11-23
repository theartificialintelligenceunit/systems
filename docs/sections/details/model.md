---
icon: lucide/brain-circuit
---

# Model

## Aim

What is the machine learning model's aim?  

!!! note "For example:"
    
    To determine the probability that a retinal image is a member of a diabetic retinopathy class; the classes are _no_ (diabetic retinopathy), _mild_, _moderate_, _severe_, _proliferative_.<br>
    $\sum\limits_{l \: \in \: L} p(\mathcal{C}_{l}) = 1$,  $\quad L =$ {no, mild, moderate, severe, proliferative}


**Note**, the model's aim matches the deployed product's <a href="../project/project.html#deployment-goal">model output
expectations</a>.


<br>
<br>


## Cost Metrics [^1]

A later version of this hub will have more details, and an example.  In brief, cost metrics should consider

<ul class="disc">
    <li class="disc">Financial savings, return on investment, time-cost, cost of delay, opportunity cost, etc.</li>
    <li class="disc">The cost of mistakes over time, e.g., misdiagnosis over time.</li>
</ul>

Considering the retinal images classification example.  The client may use the relationship between diabetic retinopathy severity, and the life-time cost of sight loss prevention/sight loss delay, to define a set of business metrics for model evaluation.


<br>
<br>


## Model Error Metrics[^2]

??? note "Model Card"

    This is for auditing purposes.  A model's model card should summarise the artefacts of the released, in-use, in-production, model.  A model card example:
    
    <ul class="disc">
      <li class="disc"><a href="https://arxiv.org/abs/1810.03993" target="_blank">Model Cards for Model Reporting</a></li>
      <li class="disc"><a href="https://modelcards.withgoogle.com/about">Model Cards for Model Reporting: Prototypes</a></li>
    </ul>


There are quite a range of metrics.[^2]  **Referring back to the retinal images classification example**, we may define the error metrics criteria as follows: [^3]


<dl style="margin-top: 35px"><b>EXAMPLE</b><br><div style="margin-bottom: 15px; margin-top: 10px;">Based on the <b>(a)</b> error matrix measures, i.
e., True Positive, False Negative, False Positive, True Negative, and <b>(b)</b> a threshold defined as the intersection of precision & sensitivity, the expected criteria are: </div>
    <dt>Overarching Criteria</dt>
    <dd>Precision > 0.9, Sensitivity (True Positive Rate) > 0.9, Specificity (True Negative Rate) > 0.9, Youden's J Statistic > 0.9, and False Positive Rate < 0.1. </dd>
    <dt>Disaggregated Criteria</dt>
    <dd>For each class, and by the same overarching threshold value, ensure that each criterion metric value is within its defined range; as outlined above.</dd>
</dl>

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>

[^1]: <a href="https://sloanreview.mit.edu/article/what-leaders-should-know-about-measuring-ai-project-value/" target="_blank">What Leaders Should Know About Measuring AI Project Value</a>
[^2]: <a href="https://oecd.ai/en/catalogue/overview" target="_blank">Catalogue of Tools & Metrics for Trustworthy <abbr title="Artificial Intelligence">AI</abbr></a>
[^3]: **N**: # of negative cases, **P**: # of positive cases. | **TN**: True Negative, **FP**: False Positive, **FN**: False Negative, **TP**: True Positive | **TNR = TN/N**: True Negative Rate (specificity) | **FPR = FP/N**: False Positive Rate (fall out) | **FNR = FN/P**: False Negative Rate (miss rate) | **TPR = TP/P**: True Positive Rate (hit rate, sensitivity, recall)

<br>
<br>
