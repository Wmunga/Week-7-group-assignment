## AI Fairness and Ethical Governance – COMPAS Bias Audit
### Project Overview
This repository contains scripts and documentation for auditing racial bias in the COMPAS recidivism risk score dataset, applying fairness mitigation techniques using AI Fairness 360 (AIF360), and reflecting on broader ethical AI practices in high-stakes domains. The work demonstrates actionable fairness assessments, mitigation pipelines, and ethical governance reflections suitable for AI governance portfolios and practical team learning.
---
# 🔬 Key Objectives

Load and preprocess the COMPAS dataset from ProPublica.

Define protected attributes (race) with clear privileged and unprivileged groups.

Calculate baseline fairness metrics, including disparate impact ratio and equal opportunity difference.

Apply fairness mitigation techniques:

Reweighing (pre-processing).

Reject Option Classification (post-processing).

Adversarial Debiasing (in-processing).

Evaluate accuracy and fairness trade-offs post-mitigation.

Visualize false positive rate disparities to communicate findings clearly.

Draft comprehensive ethical reflections and practical guidelines for ethical AI deployment in healthcare and criminal justice contexts.
---
## Setup and Installation
Ensure your environment has Python ≥ 3.8. Install required packages:

bash
Copy
Edit
pip install aif360[all]
pip install scikit-learn pandas matplotlib seaborn tensorflow
Note: TensorFlow is required for Adversarial Debiasing in AIF360.
---
## Scripts Overview
1. compas_bias_audit.py
Key functionalities:

Download and load the COMPAS dataset using AIF360.

Define privileged (Caucasian) and unprivileged (African-American) groups.

Calculate baseline disparate impact ratio and equal opportunity difference.

Apply:

Reweighing: Adjusts sample weights to mitigate dataset bias.

Reject Option Classification: Post-processing to adjust predictions near decision boundaries for fairness.

Adversarial Debiasing: In-processing approach training fair representations with adversarial networks.

Evaluate and print:

Accuracy

Disparate Impact Ratio

Equal Opportunity Difference after each mitigation step.

2. visualize_bias.py
Generates bar plots comparing false positive rates between privileged and unprivileged groups for inclusion in technical reports and stakeholder presentations.

📊 Example Results (Session Output)
Method	Accuracy	Disparate Impact Ratio	Equal Opportunity Difference
Baseline	0.704	1.233	0.075
After Reweighing	0.704	1.233	0.075
After Reject Option	0.620	1.054	0.017
After Adversarial Debiasing	0.710	0.899	-0.060

🔍 Visualizations
Example output includes bar charts showing false positive rate disparities across groups, clarifying operational fairness implications for decision-makers.
---
## Ethical Reflections
This work integrates a structured ethical reflection addressing:

Nature of bias identified: Racial bias leading to disproportionate false positives for African-American defendants.

Implications: Systemic reinforcement of racial disparities, wrongful detentions, and erosion of public trust in criminal justice AI systems.

Remediation steps: Data-level reweighing, model-level adversarial debiasing, post-processing adjustments, continuous fairness monitoring, and stakeholder engagement.

A dedicated ethical AI use guideline for healthcare was also drafted, covering patient consent, bias mitigation, transparency, accountability, and redress.
---
## Files Included
compas_bias_audit.py: Main analysis and mitigation pipeline.

visualize_bias.py: Visualization script for fairness communication.

ethical_reflection.md: Structured report summarizing findings, implications, and ethical governance reflections.

ethical_ai_guideline_healthcare.md: Practical one-page guideline for ethical AI deployment in healthcare contexts.

README.md: Project overview and usage instructions.

👤 Author
Wonder Munga
Carlos Oyanda

💡 Future Work
Extend analysis to other protected attributes (e.g. gender, age).

Integrate Fairlearn or What-If Tool for comparative fairness analysis.

Develop automated dashboards for continuous fairness monitoring in operational pipelines.

Incorporate stakeholder workshop findings into final model selection criteria.

🔗 References
ProPublica COMPAS Analysis: Dataset

AI Fairness 360 Toolkit Documentation: AIF360

Relevant ethical frameworks: IEEE Ethically Aligned Design, EU AI Act, GDPR Articles 22 and 25.

✅ Final Note
This repository demonstrates practical, principled, and impactful approaches to building fair, transparent, and accountable AI systems in high-stakes domains.

