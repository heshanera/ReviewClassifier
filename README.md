# ReviewClassifier

Classification of IMDB movie reviews using `Support Vector Machine` and `using Logistic` Regression methods.

## Dataset

[Andrew L. Maas, Raymond E. Daly, Peter T. Pham, Dan Huang, Andrew Y. Ng, and Christopher Potts, Learning word vectors for sentiment analysis, Proceedings of the 49th Annual Meeting of the Association for Computational Linguistics: Human Language Technologies (Portland, Oregon, USA), Association for Computational Linguistics, June 2011, pp. 142–150.](http://www.aclweb.org/anthology/P11-1015)

12500 negative reviews and 12500 positives reviews are used to create the train dataset. Same number of reviews are used to create the test dataset.

## Preprocessing

- Removed the accented charaters
- Unescaping HTML escape sequences
- Removed html tags
- Expanded language contractions
- Removed Special characters
- Removed words that present in less than five reviews

## Generated datasets

- `Dataset 1`: Cleande the dataset and words that present in less than five reviews removed 
- `Dataset 2`: Stop words removed from dataset 1
- `Dataset 3`: Lemmatized the dataset 2


## Classification Results

<table align="left">
  <tr>
    <th>Model</th>
    <th>Features</th>
    <th>Cross Validation</th>
    <th>Test Accuracy</th>
  </tr>
  <tr>
    <td align="right">1</td>
    <td>Bag Of Words (cleaned)</td>
    <td align="right">.83</td>
    <td align="right">.84</td>
  </tr>
  <tr>
    <td align="right">2</td>
    <td>Bag Of Words (stop words removed)</td>
    <td align="right">.83</td>
    <td align="right">.84</td>
  </tr>
  <tr>
    <td align="right">3</td>
    <td>Bag Of Words (lemmatized)</td>
    <td align="right">.83</td>
    <td align="right">.83</td>
  </tr>
  <tr>
    <td align="right"><b>4</b></td>
    <td><b>TF-IDF with unigrams</b></td>
    <td align="right"><b>.86</b></td>
    <td align="right"><b>.87</b></td>
  </tr>
  <tr>
    <td align="right">5</td>
    <td>TF-IDF with bigrams</td>
    <td align="right">.83</td>
    <td align="right">.84</td>
  </tr>
  <tr>
    <td align="right">6</td>
    <td>Logistic Regression</td>
    <td align="right">.85</td>
    <td align="right">.86</td>
  </tr>
</table>
<br>

No significance difference between cross validation scores and the test accuracies of the 3 models. SVM models 1 and 2 have same accuracies, `Accuracy: 84%`. Model 3 has low accuracy compared to other two models, `Accuracy: 83%`. 

Model 4 used term frequency–inverse document frequency values. Cross validation scores are in the range `0.85 - 0.86`. No significance difference between cross validation scores and the test accuracies of the 3 models. Model with highest accuray when compared to all the models `Accuracy: 87%`.

Model 5 used term frequency–inverse document frequency (tf-idf) values with bigrams. No significance difference between cross validation score and the test accuracy. Accuracy is low compared to SVM model with tf-idf with unigrams. Accuracy is same as the SVM with bag-of-words feature model, `Accuracy: 84%`.

Logistic Regression with unigrams is used in model 6. No significance difference between cross validation score and the test accuracy. Second highest accuracy, only less than the SVM model with tf-idf with unigrams. `Accuracy: 86%`.
