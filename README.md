# Predict Churn using the Udacity's Sparkify dataset

Udacity's Sparkify dataset | Predicting Churn | Apache Spark

## Introduction and Motivation

This project is an example on how to tackle a large scale machine learning problem.

We have a large dataset composed of several user events in an audio streaming service provider like Spotify.
The task is to detect if a specific user will cancel the service, and we will use their interaction with
the platform to do so.

## Download the dataset

- The mini dataset can be obtained [here](https://1drv.ms/u/s!AjZCiYkckpt_hY8biIoQoRfMM2mRfQ?e=zdQA2k).
- The full dataset can be obtained [here](http://udacity-dsnd.s3.amazonaws.com/sparkify/mini_sparkify_event_data.json).

## Libraries

### Python libraries

- `pyspark`
- `scikit-learn`
- `jupyter`
- `pandas`
- `numpy`
- `seaborn`

## Running

- Install Spark on your local machine or use a cloud service
- Install the python libraries and run the notebooks
- It was run using the Spark version 3.1.1

## Files

- `Sparkify-Mini.ipynb` - A Jupyter Notebook running the analysis and model with the mini dataset
- `Sparkify-Full.ipynb` - A Jupyter Notebook running the analysis and model with the full dataset

## Summary of the results

This is the `F1 score` of each classifier given the base feature dataframe and their modifications.
The best model for the full dataset is both Logistic Regression and Linear SVM.

|                                          | Random Forest | GBT Classifier | Logistic Regression | Linear SVM |
| ---------------------------------------- | ------------- | -------------- | ------------------- | ---------- |
| Mini                                     | 0.64          | 0.70           | 0.70                | 0.73       |
| Mini with last week features             | 0.64          | 0.63           | 0.70                | 0.74       |
| Mini with last week features and weights | 0.73          | 0.63           | 0.74                | 0.76       |
| Full with last week features and weights |               |                | 0.80                | 0.80       |

The most relevant features were the user age, mean user age (which is the average of user events) and the user percentage interaction of each page over all pages. The least relevant were the hourly song counts and lenghts.

## Full analysis

- The full analysis, feature selection and modeling can be found at our Medium post.

## Acknowledgements

- [Udacity Spark Course](https://www.udacity.com/course/learn-spark-at-udacity--ud2002)
- [Spark Python API reference](https://spark.apache.org/docs/latest/api/python/reference/index.html)
- [Spark ML Guide](https://spark.apache.org/docs/latest/ml-guide.html)
- [Spark Standalone Mode](https://spark.apache.org/docs/latest/spark-standalone.html)
- [Datacamp PySpark Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/PySpark_SQL_Cheat_Sheet_Python.pdf)
