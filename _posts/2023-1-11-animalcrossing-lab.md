---
layout: post
title: Animal Crossing Lab-Art of Data
subtitle: Using APIs to store and analyze data
cover-img: /assets/img/digimon.jpg?raw=true
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/digimon.jpg?raw=true
tags: [labs, blog]
---



## Introduction

-During this lab, I had to work with a dataset of digimon and write functions to sort through all of the data.
**_I wrote one function that found the average speed, one that counted the number of digimon with a specific type and attribute, and one to build a team of digimon with 15 memory and an attack of over 300._** Some parts of this lab were challenging, however I did learn a lot as a result of this challenge. 

## Building a Dateset using an API

-In order to complete the lab, I needed to create a CSV with the data from the socks API. First, I opened an empty CSV in order to write the data from the socks API and wrote a line with headers for Name, Color, and .
Then, I had to access the API by using a key in the URL, and adding the index to the end by using a while loop to access each index that had a reponse.
Each unique URL was stored in a dictionary acsocks with requests, and the Name, Color1, and Color2 from acsocks were written into a line on the CSV as a string with commas between each.
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png)

## Socks with the most Variations
 
-First I opened the CSV I had made in a different program and cast it to a list called sockslist. Then, I used a for loop to iterate through sockslist and increased a counter when a name was repeated with an if-else loop.
With this if-else loop, when a name stopped repeating the counter was stored as m
 
## Listing Frequency of Sock Colors
 
 -This was the most difficult function to write since the task was unfamiliar compared to the other two. I didn't fully understand how I could find a combination of digimon that had the desired total values for two attributes, attack and memory. instead of just a specific one. First, I tried to use a recursive function which would keep running until the base case of a team with less than 3 digimon. This didn't work so instead I used two nested for loops with variables, x y, and z, which meant that three different rows would be looped through at once. When the first usable team was found, the function returned a list of the names of the three chosen digimon. 
 
## Results

| Input | Output | 
| :------ |:--- | 
| print("avgspeed: "+str(avgspeed())) | avgspeed: 120.40160642570281 | 
| print(count_digimon("Type","Vaccine")) | 70 | 
| print(team()) | ['Flamedramon', 'Wormmon', 'Tsumemon'] | 


## Conclusion and Takeaways

-Through this lab, I learned a lot about how csvs and lists worked, which is a topic I wasn't very familiar with before. I also improved by learning more about if-else and for loops and how they worked. Overall, not all of my solutions worked the first time, so I collaborated with my classmates and researched online to find better solutions. In addition, I learned about markdown and how to create and format posts using it. Some parts of the lab were challenging, however I learned a lot thorugh having to improve my solutions.

## Collaborators and Sources:

* Nick 
* Henry
* Geeksforgeeks


 
 -
