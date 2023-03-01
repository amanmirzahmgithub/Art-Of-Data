---
layout: post
title: Descriptive Statistics Lab
subtitle: What can we learn from Zillow's real-estate datasets?
cover-img:
thumbnail-img:
share-img: 
tags: [labs, blog]
---



## Finding datasets

During this lab, I wanted to explore trends in US housing markets. Zillow is one of the most popular online real-estate markets, so I decided to find out if they had any datasets that I could use for this lab. Using Kaggle, I was able to find multiple detailed datasets that tracked house prices and rent over time in American cities, and even sorted by type(single family, co-op, etc...). In addition, Zillow collected related data on these cities such as income and population, which affect housing prices.


## Selecting useful data

Since there was a variety of data spread out over multiple datasets on Kaggle and Zillow's official website, I wanted to focus on a few variables instead of all possible ones. I considered the aspects of the real-estate market that I was most interested in - the relationships between prices for buyers and renters, and the effect of population and median income on rent. Since a lot of the data were time-series sets, I extracted those as CSVs and turned them into dataframes using pandas.

```

```


## Renting vs Buying

I wanted to see if rental prices and home values increased or decreased at the same rate so I tried to create charts for them and see how strong the corellation was. Intuitively, it made sense that if one increased, the other also would, but I wanted to see if one of the prices increased at a different rate than the other
```

```

## Population and Median Income
 
Zillow also published useful external data like income and population in selected cities. I wanted to see if there was a corellation, which could be used along with other data to show an effect on rent or even vice-versa.
```

```

## Conclusion and Takeaways



## Collaborators and Sources:

* (https://www.kaggle.com/datasets/zillow/zecon?select=all_available_metrics.json)
* https://www.zillow.com/research/data/
