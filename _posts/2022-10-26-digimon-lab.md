---
layout: post
title: Digimon Lab-Art of Data
subtitle: What I learned from working with a dataset of digimon
cover-img: /assets/img/digimon.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/digimon.jpg
tags: [labs, blog]
---



## Introduction

-During this lab, I had to work with a dataset of digimon and write functions to sort through all of the data.
**_I wrote one function that found the average speed, one that counted the number of digimon with a specific type and attribute, and one to build a team of digimon with 15 memory and an attack of over 300._** Some parts of this lab were challenging, however I did learn a lot as a result of this challenge. 

## Average speed

-For the average speed, I decided to create 2 variables, x, which would have the total speed of all digimon, and y, which would count the number of digimon.
Since, I knew how to find averages, I realized that x/y would result in the average speed. Compared to the other two challenges, finding the average speed was relatively simple. I already knew how to create for loops and work with lists. However, I did learn how to cast data to a variable, a float in this case, and that I needed to make variables, x and y, global.

 
 ## Count digimon
 
 -This function was more challenging since I wasn't sure about specifying which attribute and value would be the parameters. The solution was actually simpler than I initially thought it would be, and I just needed to create a variable a for the type and b for the value. Then a for loop would increase a variable to be returned by 1 each time a==b. This allowed for any combination of attribute and variable of digimon to be counted. While writing this function, I realized that it was similar to mapping keys to values.
 
 ## Digimon team
 
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
