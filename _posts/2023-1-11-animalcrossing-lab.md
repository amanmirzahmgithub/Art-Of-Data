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

During this lab, I created a dataset of Animal Crossing Socks using an API and used the dataset to answere the following questions.
**_I wrote one function that found the average speed, one that counted the number of digimon with a specific type and attribute, and one to build a team of digimon with 15 memory and an attack of over 300._** 

## Building a Dataset using an API

In order to complete the lab, I needed to create a CSV with the data from the socks API. First, I opened an empty CSV in order to write the data from the socks API and wrote a line with headers for Name, Color 1, and Color 2 since the CSV would need to be opened with DictReader Eventually. There were issues with opening the CSV, which made me realize that if datasets was open in file explorer the directory needed to be changed.
'''
with open("datasets/1animalcrossing.csv", "r") as f:
    data = csv.DictReader(f)
    sockslist = list(data)
'''
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
Then, I had to access the API by using a key in the URL, and adding the index to the end by using a while loop to access each index that had a reponse. Initially the index couldn't be concatenated to the URL so I cast it to  a string first
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
Each unique URL was stored in a dictionary acsocks with requests, and the Name, Color1, and Color2 from acsocks were written into a line on the CSV as a string with commas between each, since these were the only variable types required for the lab questions.
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
Creating the CSV was surprisingly challening since I had trouble accessing the API and 

## Socks with the most Variations

First I opened the CSV I had made in a different program and cast it to a list called sockslist. Then, I used a for loop to iterate through sockslist and increased a counter when a name was repeated with an if-else statement.
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
With this if-else statement, when a name stopped repeating the counter was stored as the max number if it was greater than the previous max and the name was replaced. If it was equal the 
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
In addition, the counter was reset to 1 and the name was replaced by the name of the current idx
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
The most challenging part of this question was accounting for cases where there were multiple socks with the maximum number of variations
## Listing Frequency of Sock Colors
 
For this question, I actually created two functions with the first being nested in the other. 
Colorcount, the first function, could use a parameter as the color to count how many times that color appeared. For any parameter color, each appearance of a color in sockslist was appended to an empty list. If color 1 and color 2 were the same, the appearance of the color was only appended once.
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
Then, the function counted each appearance of the parameter color in sockslist. If color 1 and color 2 were the same, the appearance of the color was only counted once. 
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
Finally, I created a list that removed any repetions of a color using set to create a list of possible colors. Using this list, the second function, colornumber returned a string for each possible color, and the returned value when the string was used as a parameter in colorcount.
![CSV](https://github.com/amanmirzahmgithub/Art-Of-Data/blob/master/assets/img/CSV.jpg.png?raw=true)
There could be ways to improve my code by only using 1 function and a single list, possibly by using classes instead, which would be more efficient.

 
## Results

| Input | Output | 
| :------ |:--- | 
| socksvariations() | argyle crew socks and compression tights and frilly socks and horizontal-striped tights and Kiki & Lala socks and neon leggings and Nook Inc. socks and semi-opaque tights and sequin leggings and sheer socks and soccer socks and striped tights and tabi and ultra no-show socks and vivid leggings and vivid socks and vivid tights and wave-print socks-8 variations | 
| colornumber() | ['Aqua:66', 'Orange:84', 'Green:204', 'Blue:240', 'Black:390', 'Red:301', 'Beige:128', 'White:801', 'Colorful:140', 'Brown:121', 'Yellow:408', 'Purple:507', 'Gray:462', 'Pink:660'] | 



## Conclusion and Takeaways

-Through this lab, I improved my ability to access and use APIs like understanding how to account for an index in the url. I also learned more about CSV's, especially in regards to the write method, even though I had already used them in the last lab. While all the code does work as intended, I could still improve the efficiency and organization in some ways like using key-value pairs instead of strings and using classes more instead of just lists. Overall, after creating the CSV, analyzing the data became a lot more manageable since it was more familiar than using APIs.

## Collaborators and Sources:

* Henry, Arun, Naomi
* Geeksforgeeks, W3Schools


 
 -
