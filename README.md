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

### [Revision.ipynb](codes/Revision.ipynb)
Codes associated to the revised version.

Updates are as follows
- Omitted UMAP to directly analyze feature extraction methods
- Different TOP method parameters

## Supplementary Figures and Information
Supplementary figures and legends can be found [here](figures/). 

### Data description
Gastric cancer images are taken from [The Cancer Genome Atlas (TCGA)](https://www.cancer.gov/tcga).

20–40 square-shaped gastric cancer patches were taken from each sample. They were all resized to $256\times 256$ and put into our analysis. At this pixel size, the image resolution is 1.76mpp.

We use 7-class histological classifications (tub1, tub2, por1, por2, sig, muc, pap).

<img width="50%" alt="image" src="https://github.com/user-attachments/assets/ae965632-ef0c-421b-8baa-376558bd9501" />

### Software and environment
TDA calculation: Python 3.10.12

CONCH and UNI calculation, Evaluation: Python 3.10.17

TDA software: [HomCloud](https://homcloud.dev/index.en.html) 4.6.0, [Persim](https://persim.scikit-tda.org/en/latest) 0.3.7.


### Citation
Paper for this repository is currently under review. Meanwhile, please cite this as follows.

```bibtex
@online{oda2026patho,
  author = {Oda, H. and Sano, K. and Ochi, M. and Onoyama, T. and Komura, D. and Ishikawa, S.},
  title = {Pathology image analysis with topological data analysis and foundation models},
  url = {https://github.com/TopologicalBird/patho-top-ml},
  year = {2026}
}
``` 

