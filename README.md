# ACL-SubjPQA
## *SupQA* Dataset

We utilized a typical *SupQA* dataset in the field of $S{\scriptsize{UBJ}}PQA$ which contains 48,352 samples across 15 product domains. Each sample includes a subjective question, product descriptions, attributes, multiple user reviews with diversified sentiments, and a multi-perspective answer summarizing objective facts and subjective reviews. Each sample in the dataset contains the following fields:

- **category**: The general product category.
- **ASIN**: The unique Amazon product identifier.
- **question**: The question asked about the product.
- **q\_sum**: A short summary of the question.
- **multi\_answers**: Multiple answers to the question provided by different users in community question answering.
- **bm25\_score\_answers**: The BM25 relevance score of each answer.
- **polarity\_answers**: The sentiment polarity (positive/ negative/ neutral) of each answer.
- **objective\_answer**: The gold objective answer to the question.
- **subjective\_answer**: The gold subjective answer to the question.
- **use\_template**: A template for generating the subjective answer summary.
- **product\_info**: Additional structured info about the product including title, description, feature bullets, attributes, etc.
- **product\_reviews**: Review texts for the product.
- **question\_length**: Number of characters in the question.
- **objective\_answer\_length**: Length of characters in the objective answer.
- **subjective\_answer\_length**: Length of characters in the subjective answer.
- **review\_length**: Length of characters in each review.
- **product\_reviews\_scores**: Score/ rating for each review (bm25).
- **sentiment\_scores**: Sentiment score for each review (1-5), in which 1-2 represent the *negative*, 3 means the *netrual* and 4-5 represent the *positive*.
- **knowledge**: Relevant commonsense knowledge for each question from LLMs (*GPT-3.5 turbo*).

The key field information contained in each example in the dataset is described in detail above.



### Dataset Folder

Due to the size of the whole dataset ($\simeq$ 3Gb), the `dataset` folder contains the validation and test data, as follows:

```
$DATA/
|–– Amazon_Subjective_dev_set.pk
|–– Amazon_Subjective_test_set.pk
```

To read the file, you can use the `pickle` Python package to load the files. Each pickle file is a `list` and each element in the list is a data sample.
