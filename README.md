# Pathology image analysis with topological data analysis and foundation models
## Abstract
<img src="img/ChatGPT-image.png" width="300px" align="right" />
Pathology images are usually classified by morphology, but this approach does not fully capture the ambiguous and continuous nature of cancer tissues. To better represent this, we need a distribution that interpolates classifications. However, it remains unclear which image quantification is best suited for this purpose and what evaluation criteria we should use in the absence of human-generated ground truth.
In this study, we set a pipeline for the objective evaluation of distributions and test frameworks based on foundation models and topological data analysis. Our results suggest the effectiveness of topological information in enhancing performance when combined with foundation models. 

(Graphical image generated with ChatGPT)

## Main Codes
### [tda_calculation.ipynb](codes/tda_calculation.ipynb)
Calculates patch image features based on topological data analysis.
- Grayscale filtration extracts intensity-based texture information.
- Erosions and dilations incorporate size information.
- PD0 and PD1 results carry connected component and 1-dim hole structures, respectively.
- These are summarized into 1800 dimenional vector using persistence image.

### [Evaluation.ipynb](codes/Evaluation.ipynb)
Evaluation of frameworks based on different feature extraction methods and combinations.

This code includes
- Loading of the feature vectors
- Calculation of logits with different train subset configurations
- Dimensionality reduction with UMAP
- Trustworthiness calculation for outputs with different train subset configurations
- Pairwise trustworthiness calculation for outputs with different train subset configurations
- Stable point selection using pairwise trustworthiness

## Supplementary Figures and Information
Supplementary figures and legends can be found [here](figures/). 

Gastric cancer images are taken from [The Cancer Genome Atlas (TCGA)](https://www.cancer.gov/tcga).

20--40 square-shaped gastric cancer patches were taken from each sample. They were all resized to $256\times 256$ and put into our analysis.

ToDO: Images are from TCGA. Resized to 256. Resolution...

Some statistics. Label proportion. Train-val split...


