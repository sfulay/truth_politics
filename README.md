# Truth and Political Bias: Data and Code

This repository contains the datasets introduced in the paper [_"On the Relationship between Truth and Political Bias in Language Models"_](https://arxiv.org/abs/2409.05283) by Suyash Fulay, William Brannon, Shrestha Mohanty, Cassandra Overney, Elinor Poole-Dayan, Deb Roy, and Jad Kabbara. The datasets provided here are intended for research on language model alignment, truthfulness, and political bias.

For more details on how these datasets were created and the experiments they were used for, please refer to the [paper](https://arxiv.org/abs/2409.05283).

## New Datasets

Our paper introduces two new datasets:

### 1. TwinViews-13k
- **File**: `data/twinviews-13k.csv`
- **Description**: 
  TwinViews-13k is a dataset of 13,855 pairs of political statements, with one statement in each pair representing a left-leaning perspective and another a right-leaning perspective on a wide range of political topics. Each pair is topically matched to ensure comparability. The statements were generated with GPT-3.5 Turbo and extensively audited for quality by the authors. This dataset is designed for research on political bias in reward models and language models, and provides one of the first large datasets of topically matched political opinion pairs. It should be particularly useful for evaluating model alignment with human political values.

- **Columns**:
  - `l`: Left-leaning political statement.
  - `r`: Right-leaning political statement.
  - `topic`: Topic associated with the statements.

### 2. TruthGen (Generated Truthfulness Data)
- **File**: `data/truthfulness-no-pol-truthgen.csv`
- **Description**: 
  TruthGen is a dataset of 1,987 true/false statement pairs (comprising nearly 4,000 total statements) generated using GPT-3.5, GPT-4 and Gemini. Each statement pair contains one true and one false statement. The data was curated to avoid political content and focuses on everyday, non-political facts. It provides an additional dataset for training models on truthfulness, especially in settings where political bias is an important consideration.

- **Columns**:
  - `truth`: A true statement.
  - `model_truth`: The model generating the true statement
  - `falsehood`: A corresponding false statement on the same topic.
  - `model_falsehood`: The model generating the false statement

## Filtered Public Datasets
Our experiments also involved filtering existing truthfulness datasets (e.g., FEVER, SciQ, TruthfulQA) to exclude political content. The filtered versions of the datasets are discussed below.

#### a. Truthfulness (FEVER)
- **File**: `data/truthfulness-no-pol-fever.csv`
- **Description**: 
  This dataset contains fact-based statements from the FEVER dataset, filtered to remove political content. It focuses on objective facts about entities and serves as training data for reward models aimed at truthfulness without political bias.

- **Columns**:
  - `true`: A factually correct statement.
  - `false`: A factually incorrect statement.

#### b. Truthfulness (SciQ)
- **File**: `data/truthfulness-no-pol-sciq.csv`
- **Description**: 
  This dataset is based on scientific knowledge from the SciQ dataset, filtered to exclude political content. It contains true and false scientific facts and is used for training models on truthfulness.

- **Columns**:
  - `true`: A scientifically accurate statement.
  - `false`: An incorrect statement.

#### c. Truthfulness (TruthfulQA)
- **File**: `data/truthfulness-no-pol-truthfulQA.csv`
- **Description**: 
  Derived from the TruthfulQA dataset, this version removes politically charged statements and focuses on factual correctness. It is used to train reward models for distinguishing true from false information.

- **Columns**:
  - `true`: A factually correct statement.
  - `false`: A factually incorrect statement.

## Citation

If you use these datasets, please cite our [paper](https://arxiv.org/abs/2409.05283):

<!-- add on publication in anthology:
  url = "https://aclanthology.org/_______",
  doi = "10.________",
  pages = "X--Y",
-->

```
@inproceedings{fulayRelationshipTruthPolitical2024,
  author       = {Fulay, Suyash and Brannon, William and Mohanty, Shrestha and Overney, Cassandra and Poole-Dayan, Elinor and Roy, Deb and Kabbara, Jad},
  title        = {On the Relationship between Truth and Political Bias in Language Models},
  booktitle    = {Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing (EMNLP '24)},
  year         = {2024},
  month        = nov,
  publisher    = {Association for Computational Linguistics},
  note         = {arXiv:2409.05283},
  abstract     = {Language model alignment research often attempts to ensure that models are not only helpful and harmless, but also truthful and unbiased. However, optimizing these objectives simultaneously can obscure how improving one aspect might impact the others. In this work, we focus on analyzing the relationship between two concepts essential in both language model alignment and political science: \textit{truthfulness} and \textit{political bias}. We train reward models on various popular truthfulness datasets and subsequently evaluate their political bias. Our findings reveal that optimizing reward models for truthfulness on these datasets tends to result in a left-leaning political bias. We also find that existing open-source reward models (i.e. those trained on standard human preference datasets) already show a similar bias and that the bias is larger for larger models. These results raise important questions about both the datasets used to represent truthfulness and what language models capture about the relationship between truth and politics.}
}
```

## License

These datasets are released under the [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/) license.

## Code

Code for working with these datasets, training models, and reproducing experiments from the paper will be added to this repository soon, and will also be under the CC-BY-4.0 license.

## Acknowledgments

The authors would like to thank Yoon Kim for helpful comments and feedback. For any questions or issues regarding the data, please contact [sfulay@mit.edu](mailto:sfulay@mit.edu).
