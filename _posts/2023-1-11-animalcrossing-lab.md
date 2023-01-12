---
layout: post
title: Animal Crossing Lab-Art of Data
subtitle: Using APIs to access and analyze data
cover-img: /assets/img/animalcrossing.jpg?raw=true
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/animalcrossing.jpg?raw=true
tags: [labs, blog]
---



## Introduction

During this lab, I created a dataset of Animal Crossing Socks using an API and used the dataset to answere the following questions.
**1. Which sock has the most variations? If there is more than one answer, then list all of them.
**1. How many socks of each color are there? If a sock has two different colors, it should be counted in both. However, if a sock has the same Color1 and Color2, make sure you don’t double count it!

## Building a Dataset using an API

In order to complete the lab, I needed to create a CSV with the data from the socks API. First, I opened an empty CSV in order to write the data from the socks API and wrote a line with headers for Name, Color 1, and Color 2 since the CSV would need to be opened with DictReader Eventually. There were issues with opening the CSV, which made me realize that if datasets was open in file explorer the directory needed to be changed.
```
with open("datasets/1animalcrossing.csv", "w") as l:
    #Writes the headers for the csv and skips a line
    l.write("Name,Color 1,Color 2")
    l.write("\n")
```
Then, I had to access the API by using a key in the URL, and adding the index to the end by using a while loop to access each index that had a reponse. Initially the index couldn't be concatenated to the URL so I cast it to  a string first
```
i=0
URL = 'https://afeingoldhm.pythonanywhere.com/socks/?key=AmanArtOfDataKEY123ABCsecret&idx='+str(i)
r = requests.get(URL)
#Continues to add the needed data 
while r.ok:
    #i could not be concatenated unless it was cast to a string
    URL = 'https://afeingoldhm.pythonanywhere.com/socks/?key=AmanArtOfDataKEY123ABCsecret&idx='+str(i)
    i+=1
```
Each unique URL was stored in a dictionary acsocks with requests, and the Name, Color1, and Color2 from acsocks were written into a line on the CSV as a string with commas between each, since these were the only variable types required for the lab questions.
```
r = requests.get(URL)
acsocks=r.json()
#Writes the Name and Colors into the csv then skips a line
l.write(str(acsocks["Name"]+","+ acsocks["Color 1"]+","+ acsocks["Color 2"]))
l.write("\n")
```
Creating the CSV was surprisingly challening since I had trouble accessing the API since a key and index were required.

## Socks with the most Variations

First I opened the CSV I had made in a different program and cast it to a list called sockslist. Then, I used a for loop to iterate through sockslist and increased a counter when a name was repeated with an if-else statement.
```
with open("datasets/1animalcrossing.csv", "r") as f:
    data = csv.DictReader(f)
    sockslist = list(data)
#This method finds the sock name(s) with the most variations
def socksvariations():
    #name will store the name at the current idx and namecount will count the number of times the name has appeared
    namecount=0
    name=sockslist[0]["Name"]
    #maxname will the store name(s) with the most variations and maxname will store how the highest number of variations
    maxname=name
    maxnamecount=0
    #For loop to go through each row, or sock, in sockslist
    for row in sockslist:
        #Namecount increases by 1 for each time a name is repeated
        if row["Name"]==name:
            namecount+=1
```
With this if-else statement, when a name stopped repeating the counter was stored as the max number if it was greater than the previous max and the name was replaced. If it was equal then the name was concatenated to maxname. In addition, the counter was reset to 1 and the name was replaced by the name in the current row.
```
else:
    #If name has the highest namecount so far, replaces maxname with naem and maxnamecount with namecount
    if namecount>maxnamecount:
        maxname=name
        maxnamecount=namecount
    #Adds name to current maxname if it has the same number of repetitions
    elif namecount==maxnamecount:
        maxname=maxname+" and "+row["Name"]
    #Changes name to new name and resets namecount
    name=row["Name"]
    namecount=1
```
The most challenging part of this question was accounting for cases where there were multiple socks with the maximum number of variations.
## Listing Frequency of Sock Colors
 
For this question, I actually created two functions with the first being nested in the other. 
Colorcount, the first function, could use a parameter as the color to count how many times that color appeared. For any parameter color, each appearance of a color in sockslist was appended to an empty list. If color 1 and color 2 were the same, the appearance of the color was only appended once.
    ```
    def colornumber():
        colordata=[]
        #Returns the appearances of a chosen color, colorselect
        def colorcount(colorselect):
            colorcounter=0
            #Appends all colors in sockslist to colordata
            for row in sockslist:
                colordata.append(row["Color 1"])
                #Appends the second color if it is different
                if row["Color 1"]!=row["Color 2"]:
                    colordata.append(row["Color 2"])
    ```
Then, the function counted each appearance of the parameter color in sockslist. If color 1 and color 2 were the same, the appearance of the color was only counted once. The selected color and number of appearances are returned as a string
    ```
        #Loops through colordata and increases colorcounter by 1 each time if the color is the same as colorselect
                if i==str(colorselect):
                    colorcounter+=1
        #Returns a string with the selected color and its number of appearances
        return(str(colorselect)+":"+str(colorcounter))
    ```
Finally, I created a list that removed any repetions of a color using 'set' to create a list of possible colors. Using this list, the second function, colornumber appended the string returned by colorcount with each possible color as a parameter.
     ```
    colors=[*set(colordata)]
    #finalcolors stores the list of each color and its number of appearances
    finalcolors=[]
    #Appends the result of colorcount as a string for each possible color using a for loop
    for i in colors:
        finalcolors.append(colorcount(i))
    print(finalcolors)
    ```

There could be ways to improve my code by only using 1 function and a single list, possibly by using classes instead, which would be more efficient.

 
## Results

| Input | Output | 
| :------ |:--- | 
| socksvariations() | argyle crew socks and compression tights and frilly socks and horizontal-striped tights and Kiki & Lala socks and neon leggings and Nook Inc. socks and semi-opaque tights and sequin leggings and sheer socks and soccer socks and striped tights and tabi and ultra no-show socks and vivid leggings and vivid socks and vivid tights and wave-print socks-8 variations | 
| colornumber() | ['Aqua:66', 'Orange:84', 'Green:204', 'Blue:240', 'Black:390', 'Red:301', 'Beige:128', 'White:801', 'Colorful:140', 'Brown:121', 'Yellow:408', 'Purple:507', 'Gray:462', 'Pink:660'] | 



## Conclusion and Takeaways

Through this lab, I improved my ability to access and use APIs like understanding how to account for an index in the url. I also learned more about CSV's, especially in regards to the write method, even though I had already used them in the last lab. While all the code does work as intended, I could still improve the efficiency and organization in some ways like using key-value pairs instead of strings and using classes more instead of just lists. Overall, after creating the CSV, analyzing the data became a lot more manageable since it was more familiar than using APIs.

## Collaborators and Sources:

* Henry, Arun, Naomi
* Geeksforgeeks, W3Schools


 
 -
