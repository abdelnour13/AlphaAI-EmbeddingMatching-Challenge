# Embeddings Matching

## Overview

- The goal of this challenge is to match each embedding in the test set to its corresponding image, given a small set - train set (pairs of images,embeddings and the Correspondence/Labels) by **exploiting the relationships between the different samples**.

## Embeddings generation

- **Dataset** : Mnist Digits dataset was used for training.
- **Architecture** :  A CNN model was trained to generate the embeddings,its architecture and weights are not provided.
- **Loss function** : The loss function was chosed to **preserve the relationships** between the different samples,most notably **the cosine similarity**.

$$
y = f_{\theta}(x)
$$

$$
L(x,y) = \frac{1}{M^2} \sum_{i=0}^M \sum_{j=0}^M [d(x_{i},x_{j}) - d(y_{i},y_{j})]^2
$$

Where :

$$
d : \text{Cosine similarity}
$$ \\
$$
x_{i},x_{j} : \text{Tow images.}
$$ \\
$$
y_{i},y_{j} : \text{Corresponding embeddings.}
$$

## Data

- `train_data.csv` : a subset of 128 of the original training images.
- `train_embedding.csv` : the corresponding embeddingd to the images in `test_data.csv`.
- `train_labels.csv` : contains the correspondence between the training images and the training embeddings,for example if : 

```python
train_labels = [8703,2000,1181,...]
```

it means that the first embedding in the dataset corresponds to the $8703^{th}$ image.

- Similarly `test_data.csv` and `test_embeddings.csv` are provided.

## Submission

- A csv file that represents the correspondence between the test images and test embeddings (similar to `train_labels.csv`).

## Evaluation

- The provided solutions are assessed using `accuracy`.