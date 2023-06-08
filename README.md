# Repository for the Fall 2022 Peak.AI x NYU Data Science Club Datathon, Recommender Systems Challenge (Winner)

## Team Son, Sons & Company

Teammates:

- Sunny Son ([LinkedIn](https://www.linkedin.com/in/sunny-son/), [GitHub](https://github.com/sunnydigital))
- Morgan Xu ([LinkedIn](https://www.linkedin.com/in/haoran-xu-194007182/), [GitHub](https://github.com/HUNTINGHOUND))
- Shane Sun ([LinkedIn](https://www.linkedin.com/in/shanessun/))
- Sunny Yang ([LinkedIn](https://www.linkedin.com/in/sunny-yang23/))

## Problem Statement

The goal in this Datathon is to act as developers for the host company of this datathon, Peak.AI, and develop a recommender system model for our customer, the Brazilian e-commerce company Olist, to advertise products to users based off of previous purchase history

<img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-overview.png" width="100%">

## Data Processing

We then joined all necessary tables to determine all relevant orders based on the primary key of `customer_id`, at the neds related to `product_id` with the entity relationship diagrams shown below:

<p align="center">
  <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-erd1.png" alt="Entity Relationship Diagram 1" width="49.7%"> <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-erd2.png" alt="Entity Relationship Diagram 2" width="49.7%">
</p>

### Data Preparation

We then follow the below steps to finalize the data for modeling:

<img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-preparation.png" width="100%">

## Model

We used a k-Nearest Neighbor model, to determine a mapping between "features" (e.g. cost, location, etc.) and "label" (e.g. Lamp), and minimize a specific metric distance for the labels of previously purchased items to the label of the target item. This procedure is shown below:

<p align="center">
  <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-recs1.png" alt="Recommendation Procedure 1" width="49.7%"> <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-recs2.png" alt="Recommendation Procedure 2" width="49.7%">
</p>

## Generating Recommendations

With this, our model is ready to generate recommendations. We accept an input parameter "k" for the number of closest products to generate, and do so using a modified euclidiean distance metric based on product category:

<p align="center">
  <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-dist1.png" alt="Distance 1" width="49.7%"> <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-dist2.png" alt="Distance 2" width="49.7%">
</p>

### "Product Category" Metric Distance

In order to determine a "distance" metric for our model to follow, we decided to scale the k-NN distance by the "cosine similarity" of a product's category to ensure similar placement of similar products, using the Global Vector (GloVe) 50d embedding:

<p align="center">
  <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-cos-sim1.png" alt="Cosime Similarity 1" width="49.7%"> <img src="https://github.com/sunnydigital/datathon-f22/blob/main/assets/peak-presentation-cos-sim2.png" alt="Cosine Similarity 2" width="49.7%">
</p>

## Notebook

For the full notebook, please refer to the file [peak-ai-x-nyu-dsc-datathon-team-7-submission.ipynb](https://github.com/sunnydigital/datathon-f22/blob/main/peak-ai-x-nyu-dsc-datathon-team-7-submission.ipynb)
