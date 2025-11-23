---
icon: lucide/biceps-flexed
---

# RMRA

The [systems engineering body of knowledge](https://sebokwiki.org/wiki/Guide_to_the_Systems_Engineering_Body_of_Knowledge_(SEBoK)) notes that reliability, maintenance, and availability attributes are three of the core attributes that affect the [utility of a system and its economic life-cycle cost](https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability).[^utility]  In the context of machine learning products, reliability, maintenance, availability, and resilience specifications are critical to items such as

<ul class="disc">
    <li class="disc">continuous service,</li>
    <li class="disc">drift monitoring & continuous model performance improvement</li>
</ul>

and the costs thereof.  The tasks herein will require the aid of a reliability engineer, or similar.  The aim being to

<ul class="disc">
    <li class="disc">Define the reliability, maintenance, availability, and resilience expectations via metrics constraints.</li>
    <li class="disc">Outline in-built designs/solutions that minimise the probability of constraints breaches.</li>
</ul>

<br>
<br>

## Reliability

In the systems engineering body of knowledge the [basic definition of reliability](https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability#Reliability) is

> “ … the probability of a product performing its intended function under stated conditions without failure for a given time period”.

<br>

In the context of machine learning systems, the reliability specification of each intended function, i.e., each functional requirement, must detail/specify the

<ul class="disc">
    <li class="disc">Function in question, and its operating environment.</li>
    <li class="disc">Time scales; for evaluating the reliability metrics.</li>
    <li class="disc">Definition of failure; for evaluating the reliability metrics, and for in-built failure mitigation considerations.</li>
    <li class="disc"><a href="https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability#Metrics">Reliability metrics</a></li>
</ul>

<br>

This aids <b>(a)</b> the design of possible in-built solutions that mitigate factors that affect reliability, and <b>(b) </b> system monitoring strategy, and the operations thereof.  Study the [reliability, maintainability, and availability page](https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability) of the systems engineering body of knowledge for the expectations herein.

<br>
<br>


## Maintainability & Resilience

### Definitions

Of maintainability and resilience.

#### Maintainability

In the systems engineering body of knowledge the [basic definition of maintainability](https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability#Maintainability) is the

<blockquote>“ … probability that a given maintenance action for an item under given usage conditions can be performed within a stated time interval when the maintenance is performed under stated conditions using stated procedures and resources.”</blockquote>

Note that **maintainability comprises** serviceability & repairability, i.e.,

<blockquote>"… the ease of conducting scheduled inspections and servicing"</blockquote>

**and**

> "… the ease of restoring service after a failure"

<br>

#### Resilience

The resilience of a system can be defined as "… the ability to maintain [capability](https://sebokwiki.org/wiki/Capability_(glossary)) in the face of a [disruption](https://sebokwiki.org/wiki/Disruption_(glossary))" [[The Systems Engineering Body of Knowledge.](https://sebokwiki.org/wiki/System_Resilience#Definition)]

The body of knowledge outlines the objectives of a system's resilience plan. Study the Achieving Resilience details, therein the fundamental objectives are:

<ul>
    <li>Avoid: eliminate or reduce exposure to <a href="https://sebokwiki.org/wiki/Stress_(glossary)" target="_blank">stress</a></li>
    <li>Withstand: resist capability degradation when stressed</li>
    <li>Recover: replenish lost capability after degradation</li>
</ul>


<br>


### Outlining Specifications for Machine Learning Systems

**In the context of machine learning**, the foci herein are

<ul>
    <li><b>The model drift and data drift strategy</b>.  The blog <a href="https://encord.com/blog/model-drift-best-practices/" target="_blank">Model Drift: Best Practices to Improve Machine Learning Model Performance</a> includes an excellent discussion about how to monitor machine learning systems.  Drift details must be outlined vis-à-vis model drift and data drift.  Model drift monitoring is via the evaluation metrics detailed in the model performance metrics section.  Whereas data drift is generally via statistical tests or custom models, depending on the data types in question.</li>
    <li><b>Continuous performance improvement strategy</b>.  For continuous model improvement purposes, the system architecture should include a re-training component.  If it does not, the monitoring system should have an automatic end-of-life alert, triggered by one or more evaluation metrics falling-out of their constraints.</li>
    <li><b>Maintenance services/agreements</b>.  For general maintainability concepts, study the <a href="https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability" target="_blank">reliability, maintainability, and availability page</a> of the systems engineering body of knowledge for the expectations herein; <b>and the maintenance and resilience metrics thereof</b>. </li>
</ul>

Altogether, define maintenance and resilience metrics vis-à-vis the system/product, model drift & data drift.  The references link to metrics definitions examples.

<br>
<br>

## Availability

The [systems engineering body of knowledge defines availability](https://sebokwiki.org/wiki/System_Reliability,_Availability,_and_Maintainability#Availability) as the

> "… probability that a repairable system or system element is operational at a given point-in-time under a given set of environmental conditions"

**Herein, define the system's availability expectations**.  Availability is a function of reliability and maintainability, i.e.,

$$
availability = \frac{MTBF}{MTBF + MTTR}
$$

whereby

<ul class="disk">
    <li class="disk">The <i>mean time between failure</i> is a reliability metric.</li>
    <li class="disk">The <i>mean time to repair</i> is a maintainability metric.</li>
</ul>


<br>

![availability metrics](../../../images/availability-metrics.png){ width='1804px' }

<br>

<figure>
<figcaption><a href="https://docs.aws.amazon.com/whitepapers/latest/availability-and-beyond-improving-resilience/understanding-availability.html" target="_blank">Availability metrics illustration by Amazon.</a>  Note: MTBF (Mean Time Between Failure) is a reliability metric, MTTR (Mean Time To Repair) is a maintainability metric, MTBF/(MTBF + MTTR) is a definition of availability, MTTD (Mean Time To Detection)
</figcaption>
</figure>

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>


[^utility]: [A definition of utility](https://www.oed.com/search/dictionary/?scope=Entries&q=utility)
[^maintenance-metrics]: <a href="https://www.maintworld.com/Applications/5-Important-Maintenance-Metrics-and-How-To-Use-Them" target="_blank">Maintenance Metrics</a>
[^resilience-metrics]: <a href="https://sebokwiki.org/wiki/System_Resilience#Metrics" target="_blank">Resilience Metrics</a>
[^drift]: <a href="https://arxiv.org/abs/2012.09258">Detection of data drift and outliers affecting machine learning model performance over time.</a>
[^availability]: <a href="https://sebokwiki.org/wiki/Availability_(glossary)" target="_blank">Availability</a>
[^understanding-availability]: <a href="https://docs.aws.amazon.com/whitepapers/latest/availability-and-beyond-improving-resilience/understanding-availability.html" target="_blank">Understanding Availability</a>

<br>
<br>
