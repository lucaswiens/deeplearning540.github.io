Lesson 04: Classification Performance ROCs
******************************************

Learning Objectives
===================

* discuss true positive rate and false positive rate

* explain how a cut-off value (for kmeans classification) is used to produce a ROC curve

* assert that a ROC curve is an envelope produced for a fixed test set

* demo how to construct a ROC curve

* contrast the difference between adding individual points into a ROC plot and producing a ROC curve

* show `plot_roc_curve` in sklearn

* discuss extremes of a ROC curve


Content
=======

This lesson will be shared as a video.

* for learners: a stub notebook to get you started can be obtained from `the lesson03 repo <https://github.com/deeplearning540/lesson04/blob/main/lesson.ipynb>`_.
* for instructors: the video script is available `here <https://github.com/deeplearning540/deeplearning540.github.io/blob/main/source/lesson04/script.ipynb>`_.


Check your Learning
===================

The following questions serve as a help for learners to reflect on the content of the videos. Answer at least one question. At best you want to answer these questions as a team.

.. admonition:: Exercise 1

   The `ROC` acronym stands for

   1. Receiver Operator Curve
   2. Receiving Operates Curves
   3. Receiver Operating Characteristic
   4. Reception Occlusion Characteristic

.. admonition:: Exercise 2

   Fill in the blanks!

   A k-Nearest-Neighbor (kNN) classifier can produce a probability when predicting the class label of an unseen sample `x_q`. This can be achieved by counting class `_______` in the training set neighborhood of this query point.

   For a `k=7` neighborhood, the threshold to decide for any given class in this neighborhood is calculated as `4/__`. In the same setting (`k=7`), let's assume we find `5` labels for class `1` and `2` labels for class `0`. This means, that we get two probabilities, which are `_____` for class `1` and `_____` for class `0`. 


Exercises
=========

For this lesson, please complete the following steps in order:

1. produce a ROC curve for the classifyer you trained in `lesson03 </source/lesson03/content.rst>`_.

2. take another NN based classifyer, e.g. `sklearn.neighbors.RadiusNeighborsClassifier` or `sklearn.neighbors.NearestCentroid` and train it

3. make predictions on the testset with it and produce a ROC 

4. combine the 2 ROC curves in a plot and discuss which classifyer is better!

Datasets
========

* Datasets for clustering. Each of the following synthetic datasets contains several features `x1`, `x2`, ... and a `label` column which comprises (2 classes).

  * `clustering_data_00.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_00.csv>`_
  * `clustering_data_01.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_01.csv>`_
  * `clustering_data_02.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_02.csv>`_
  * `clustering_data_03.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_03.csv>`_
  * `clustering_data_04.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_04.csv>`_
  * `clustering_data_05.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_05.csv>`_
  * `clustering_data_06.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_06.csv>`_
  * `clustering_data_07.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_07.csv>`_
  * `clustering_data_08.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_08.csv>`_
  * `clustering_data_09.csv <https://github.com/deeplearning540/lesson02/blob/main/data/clustering_data_09.csv>`_

* `iris plants <https://scikit-learn.org/stable/datasets/toy_dataset.html#iris-plants-dataset>`_ dataset. Use the columns `petal_length` vs. `petal_width`. The class label is provided as the `target` column. To obtain the dataframe from this dataset do the following:

.. code-block:: python

  import pandas as pd
  from sklearn.datasets import load_iris
  iris = load_iris()
  df = pd.DataFrame(data= np.c_[iris['data'], iris['target']],
                    columns= iris['feature_names'] + ['target'])
