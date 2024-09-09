# Active learning for financial use case

```mermaid
graph LR
    active_learning --> data
    active_learning --> preprocessing
    active_learning --> algorithm
    active_learning --> al_strategy
    active_learning --> oracle
    active_learning --> update_strategy

    data --> file_location
    data --> file_type
    data --> instance
    data --> initial_labeler

    initial_labeler --> field
    initial_labeler --> initial_algorithm

    preprocessing --> missing_strategy
    preprocessing --> feature_vector_generation

    feature_vector_generation --> concat
    feature_vector_generation --> tfidf

    algorithm --> classification
    classification --> SVM

    al_strategy --> uncertainty_sampling

    oracle --> gui

    update_strategy --> retraining
```

Resources:

* https://github.com/RelationRx/pyrelational | https://pyrelational.readthedocs.io/en/stable/
* https://towardsdatascience.com/towards-a-fully-automated-active-learning-pipeline-29b8f4eb7d73
* https://towardsdatascience.com/how-to-build-a-fast-iterative-active-learning-data-pipeline-3c83a8838a5a




## Helper

* Data
    * Type: `["CSV"]`
    * Feature extractor:
        * `CONCAT`
        * TFIDF
    * Fields: `string`
* Initial model
    * Clustering
        * Model: `["KMeans"]`
        * Number of clusters: `["int", "best"]`
* Data labeling: `["manual"]`
    * Type `manual`: `["GUI"]`
* Active learning strategy: `["uncertainty_sampling"]`
* Oracle
* Model update process: `["incremental", "retraining"]`
* Evaluation metrics: `["f1", "accuracy"]`
* Stopping criteria: `["human"]`