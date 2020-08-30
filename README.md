# Serving Iris Classifier with FastAPI

## Data

The Iris dataset is a simple, yet popular dataset consisting of 150 observations. Each observation captures the sepal length, sepal width, petal length, petal width of an iris (all in cm) and the corresponding iris subclass (one of *setosa, versicolor, virginica*).

![](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Machine+Learning+R/iris-machinelearning.png)


## Usage

Make sure you have Docker installed.

1. Build the docker container using `docker build . -t queue`
2. Generate the docker image using `docker run -i -d -p 8080:5000 queue`

The input is a JSON with the following fields:

* sepal_l
* sepal_w
* petal_l
* petal_w

Corresponding values are the measurements in cm.

Example request:

```
curl 'http://localhost:8080/queue/classify_iris' -X POST -H 'Content-Type: application/json' -d '{"sepal_l": 5, "sepal_w": 2, "petal_l": 3, "petal_w": 4}'
```