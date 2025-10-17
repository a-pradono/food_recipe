<p align="center">
  <img width="250" height="250" src="https://github.com/a-pradono/food_recipe/blob/main/images/header.jpg">
</p>
<p align="center">
Photo by <a href="https://unsplash.com/@enginakyurt?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">engin akyurt</a> on <a href="https://unsplash.com/photos/a-person-burning-a-fire-vUlsoVpTbZs?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
</p>


## Table of Contents

- [I. Introduction](#i-introduction)
- [II. Data and Methodology](#ii-data-and-methodology)
- [III. Results](#iii-results)
- [IV. Conclusions](#iv-conclusions)

## I. Introduction
Cooking is both an art and science, a wonderful experience that allows us to explore and create delicious meals. Food is important since it provides the energy and nutrients for our bodies and minds to function well. However, deciding what to cook can sometimes be frustrating, especially when we only have a few ingredients in our home and limited time. This is a common situation whether you are students, busy professionals, or simply want to eat well but need quick and convenient meal ideas. In this project, I want to create a food recipe recommender system that helps users discover high-protein and quick meals based on the ingredients they already have at home.
## II. Data and Methodology
The dataset was retrieved from over 500,000 recipes from food.com, posted by Alvin and can be found here on [www.kaggle.com](https://www.kaggle.com/datasets/irkaal/foodcom-recipes-and-reviews).
<p align="center">
  <img width="400" height="200" src="https://github.com/a-pradono/food_recipe/blob/main/images/workflow.png">
</p>

The workflow above demonstrates how I created the recommender systems using Ollama (LLM embeddings) and FAISS (vector similarity search). First, data pre-preprocessing was performed including data cleaning and filtering. Second, the selected important columns were combined into single text string for converting into numerical vector (embedding) using model from Ollama. In addition, all embeddings are stored in FAISS index for efficient similarity search between recipes. Furthermore, users are able to input the available ingredients at home and the FAISS index then searched to find the top 2 most semantically similar recipes. Finally, the system outputs recipe options showing meal name, preparation and cook time, calories, protein, and full instructions.

## III. Results
The first figure below explains the results after data pre-processing step. The final dataset was filtered to include only meat-based recipes with a rating over 4.5, less than 25 minutes of total preparation and cooking time, and high-protein content of greater than 30 g. This also reduced the dataset from about 500,000 rows to only 130 rows, ensuring improved efficiency and faster processing for the LLM-based recipe recommendation system.

<p align="center">
  <img width="500" height="500" src="https://github.com/a-pradono/food_recipe/blob/main/images/plot01.png">
</p>

Users can query the system based on the ingredients available at home to get personalized recipe recommendations. For example, the user inputs **bread, patties, and mushroom** as the available ingredients. After entering the ingredients, the system recommends two recipe options, each providing detailed information such as the meal name, preparation and cooking time, calories, protein content, and full instructions. This allows users to easily choose between them.

<p align="center">
  <img width="700" height="500" src="https://github.com/a-pradono/food_recipe/blob/main/images/plot03.PNG">
</p>

Here is the step-by-step flow that takes a user query and returs the meal recipe recommendation.

<p align="center">
  <img width="700" height="600" src="https://github.com/a-pradono/food_recipe/blob/main/images/plot04.gif">
</p>

## IV. Conclusions
The objective of this project was to develop recipe recommendation system using LLM. The following are the conclusions drawn from this project:
  * Data pre-processing is essential in improving efficiency. Filtering the dataset is helpful, as working with large dataset can be computationally expensive.
  * Leveraging local LLM with semantic search successfully recommends food recipe matching based on user-provided ingredients.

