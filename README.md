# Detecting Security Fixes in Open-Source Repositories using Static Code Analyzers

## Abstract
Relying on externally developed software is essential for companies to increase
efficiency and stay competitive. However, the number of known software
vulnerabilities increases yearly, leading to growing confidentiality issues. In
this context, the usage of Machine Learning techniques to detect such
vulnerability has been shown as promising. However, previous research primarily
focused on identifying vulnerable files instead of security-relevant commits.
This paper aims to analyze to what extent embeddings resulting from static code
analyzers can be adopted to detect software vulnerabilities leveraging Machine
Learning. First, we analyze such embeddings for security-relevant and
non-security-relevant commits and show that they are not different in a
statistically significant manner. Then, we develop a Machine Learning pipeline
leveraging this data, which achieves results comparable with commit2vec, the
state-of-the-art tool for this task. Machine learning models and commit2vec are
complementary, being the former not restricted to compilable code and the latter
more precise. Thereby, we bring the community one step closer to the automated
identification of commits that fix vulnerabilities with an approach relevant to
industry as it can analyze a broader range of commits than previously without
reducing the detection capabilities.

***

## Appendix
This online appendix contains information concerning the hyperparameter tuning
performed by our machine learning pipeline.

* [Feature Selection](feature_selection_tuning.md)
* [Base Classifiers Hyperparameter Tuning](base_classifiers_tuning.md)
* [Ensemble Techniques Hyperparameter Tuning](ensemble_techniques_tuning.md)
* [Best Model for each Embedding](best_model.md)