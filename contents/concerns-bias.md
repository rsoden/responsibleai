---
layout: contents
title: "Concerns: Bias in Machine Learning"
---

Concerns over bias occupy center stage in many of the ongoing discussions over the social impacts of machine learning tools. One challenge of addressing bias is that varying definitions of bias and fairness are used in these discussions. Statisticians and systems developers often have significant expertise in identifying and correcting measurement errors that can lead to biased datasets through over or under-representation of certain phenomena. Meanwhile, legal scholars and social scientists point to unfair representations of disadvantaged groups in training datasets or the reinforcement of societal inequities as a result of decision-making processes based on algorithms. In this guidance document, we choose to address most (if not all) of these aspects of bias and fairness in ML systems. 

Inevitably, all systems will have some form of bias. All models of the world are, by necessity, incomplete and inherit, sometimes unknowingly, the priorities, prejudices, and perspectives of their creators and the wider society in which they are developed and used. Understanding and mitigating the sources, as well as the consequences, of bias in the information used to guide disaster risk management initiatives is therefore a necessary component of ensuring that machine learning tools are used in a responsible and fair manner.



![graphic describing sources of bias](https://miro.medium.com/max/1400/1*pirx62JLi4bA01IKj0kIjQ.png "{Potential sources of harm in an ML pipeline")
*Potential sources of harm arise at different points in an ML pipeline  
[Image Source](https://medium.com/@harinisuresh/the-problem-with-biased-data-5700005e514c)*

### Sources of bias and their harms

**Biased Training Data -** One of the most common sources of bias in a machine learning project is the training data that is used to train algorithms. A training dataset used for DRM projects is biased if the data it contains doesn’t reflect the context to which the algorithm is meant to be used. Such mismatches can be rooted in geography, demography, based on structure type, or other kinds of data. They can result in poor or biased outcomes when attempting to transfer a machine learning model from one setting to another.  

*Example 1:  Assessing Earthquake Impacts*
Null Island has recently undergone a high-intensity earthquake, affecting the majority of the country. Experts scramble to pull together the best data they have in order to conduct a rapid impact assessment aimed at guiding relief and early recovery work. As is common in many parts of the world, high resolution pre-event aerial imagery is primarily available for the capital city center. The available imagery is used to train a computer vision model that compares pre-event data with imagery taken just after the earthquake.  When that model is then used to estimate building damage across the whole country, it significantly undercounts impacts in rural areas and informal settlements. This bias in the damage assessment unfairly leads to the capital city receiving a disproportionate share of recovery and reconstruction assistance.

**Biased approaches to measurement -** Another, often more difficult to identify or evaluate, source of bias stems from decisions made in how we decide to represent extraordinarily complex phenomena like disaster risk or impacts with data.  Data standards like the 100-year floodplain, or measures such as average annual loss serve as useful but incomplete indicators for often much broader processes or events in the world. While data scientists are intimately familiar with this issue, this awareness or nuance is often lost when models and data are brought into project planning and policy-making. Bias in measurement approaches runs deeper than machine learning, but is important to consider as it will impact project outcomes and, in some cases, machine learning may exacerbate them.

*Example 2:  Calculating Risk in DisasterLand*
DisasterLand is kicking off a national multi-hazard risk assessment in order to set priorities for disaster-risk management investments. The wise engineers in charge of designing the risk assessment know that cost-benefit analysis that informs risk modeling often relies on property values or home values in order to determine the “benefit” of protecting buildings and places against hazards like earthquakes or floods. This inherently puts communities with lower economic status at an unfair advantage; as disaster risk reduction measures for wealthy neighbourhoods will come out as more cost-effective, which could lead to under-protection of less well-off areas.  The engineers are instead investigating  a wider set of indicators that take into account the impacts of disaster on social welfare more broadly.

*Example 3: Evacuation Planning in Alphabet City*
Alphabet City, the capital of Null Island, is updating its evacuation plans and wants to use machine learning models along with transportation and population datasets to plan key routes and determine areas that will need extra assistance. Unfortunately, the latest estimates on population don’t include important details on disability status. In addition, the team is planning to use Call Detail Record (CDR) data in order to understand variable population density across the city at different times of day. As a result of privacy regulations on Null Island, CDR data isn’t disaggregated by gender or age. Evacuation planning models that assume all people are adult able-bodied men (as is common), or don’t otherwise account for the great range of needs and capacities of potential evacuees will misallocate resources and be improperly prepared should the time come when evacuation is necessary.

**Recommendations for Addressing Bias**


1. Remember that, in a general sense, all systems are biased. All models of the world are necessarily incomplete. This is part of what gives them their power. Even if perfectly unbiased datasets were possible, this would not resolve all potential problems such as when, for example, the ML tools are supporting unjust systems. As developers and designers of ML systems, we need to understand and continually interrogate the limits of our systems and what that means for decisions based upon them.

2. Technical solutions such as continuous validation, fairness tests, and scrubbing training datasets can help reduce biases in training datasets. These tools are improving all the time and can be useful. Specific techniques differ depending on the type of bias. A technique that could help with the problems highlighted in example 1 and 3 is sample selection bias correction. In this technique samples taken from under-represented groups are upsampled in order to make the entire data more representative for the population it needs to make predictions about. It could also be adjusted to punish the algorithm for making errors on specific under-represented groups. This technique can reduce the bias but in case of limited available data the bias cannot be removed. The bias in example 2 might be addressed by [accounting for social welfare in cost-benefit analyses](https://www.gfdrr.org/en/publication/unbreakable). A technique to ensure an algorithm is not making unwanted connections is adversarial de-biasing. In this technique the dataset is asked to predict the specific characteristic that it is expected to be biased on (e.g. age) based on the other characteristics. If it can then predict this age variable it means there is a bias. The algorithm can then be punished for making these biased predictions.

3. Participatory strategies can be used to include residents of areas that ML models describe in training data collection and validation processes. These strategies can help to identify sources of bias, potential misuses and add understanding of local context to the project planning and design.

4. Diversify project teams - A [recent report](https://ainowinstitute.org/discriminatingsystems.pdf) has shown that, as an industry, AI is disturbingly homogenous. Diversifying our project teams is necessary because, as developers of these systems, we often have unexamined assumptions based on our own backgrounds. Alternative perspectives are needed in order to identify potential problems early in the process.

5. Provide users with information they need to evaluate the results properly - When the results of ML projects are shared or published, sufficient information about the training data, models, and development process should be included along with guidance on how to responsibly interpret the results. See the section on Transparency and Explainability for more details.

*Important Readings*

* [20 Lessons on Bias in Machine Learning Systems](https://hub.packtpub.com/20-lessons-bias-machine-learning-systems-nips-2017/)


* [The Problem With "Biased" Data](https://medium.com/@harinisuresh/the-problem-with-biased-data-5700005e514c)

* [The Seductive Diversion of Solving Bias](https://onezero.medium.com/the-seductive-diversion-of-solving-bias-in-artificial-intelligence-890df5e5ef53)


* [The Long Road to Fairer Algorithms](https://www.nature.com/articles/d41586-020-00274-3?WT.ec_id=NATURE-2020020)



