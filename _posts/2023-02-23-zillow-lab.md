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

During this lab, I wanted to explore trends in US housing markets. Zillow is one of the most popular online real-estate markets, so I decided to find out if they had any datasets that I could use for this lab. Using Kaggle, I was able to find multiple detailed datasets that tracked house prices and rent over time in American cities, and even sorted by type(single family, co-op, etc...). In addition, Zillow collects related data on county and even neighborhood real-estate markets in some cases.


## Selecting useful data

Since there was a variety of data spread out over multiple datasets on Kaggle and Zillow's official website, I wanted to focus on a few variables instead of all possible ones. I considered the aspects of the real-estate market that I was most interested in - the relationships between prices for buyers and renters, and the relationship between price and price/area. Since a lot of the data was stored in time-series datasets, I extracted those as CSVs and turned them into dataframes using pandas.

```

```


## Renting vs Buying

I wanted to see if rental prices and listing prices increased or decreased at the same rate so I tried to create scatterplots for them and see how strong the corellation was. Intuitively, it made sense that if one of these variables increased, the other also would, but I wanted to see if one of the prices increased or decrease at a different rate than the other.
```

```

## Price vs Price/Area
 
Zillow also published useful data on price/area(sq ft). Similarly to rental and listing prices, I wanted to see how closely corellated these two variables were. Again, intuitively, there wouldn't be an inverse corellation, but there could be multiple types of direct correlations. I also created scatterplots and analyzed this data for corellations.
```

```

## Conclusion and Takeaways
Right now, the data I collected and the analysis doesn't reveal anything new or definitive on real estate. I'm interested on expanding on similar data for a later project so I could find more interesting aspects of the US housing market. Possibly, I could even attempt to make a predictive model like Zillow's proprietary value prediction software.


## Collaborators and Sources:

* (https://www.kaggle.com/datasets/zillow/zecon?select=all_available_metrics.json)
* https://www.zillow.com/research/data/
* https://www.kaggle.com/datasets/zillow/rent-index
* https://www.kaggle.com/datasets/paultimothymooney/zillow-house-price-data
