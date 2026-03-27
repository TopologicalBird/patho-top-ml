# Pathology image analysis with topological data analysis and foundation models
## Abstract
Pathology images are usually classified by morphology, but this approach does not fully capture the ambiguous and continuous nature of cancer tissues. To better represent this, we need a distribution that interpolates classifications. However, it remains unclear which image quantification is best suited for this purpose and what evaluation criteria we should use in the absence of human-generated ground truth.
In this study, we set a pipeline for the objective evaluation of distributions and test frameworks based on foundation models and topological data analysis. Our results suggest the effectiveness of topological information in enhancing performance when combined with foundation models.
## Main Codes
### TDA calculation
Calculates patch image features based on topological data analysis.
- Grayscale filtration extracts intensity-based texture information.
- Erosions and dilations incorporate size information.
- PD0 and PD1 results carry connected component and 1-dim hole structures, respectively.
- These are summarized into 1800 dimenional vector using persistence image.

### Evaluation ([Evaluation.ipynb](codes/Evaluation.ipynb))
Evaluation of frameworks based on different feature extraction methods and combinations.


## Supplementary Figures
Supplementary figures and legends can be found [here](figures/). 
