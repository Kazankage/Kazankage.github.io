---
layout: post
title:      "Pinoy_Dishes"
date:       2019-10-05 21:35:21 -0400
permalink:  pinoy_dishes
---


Wow. Hi. Where do I begin? My name is Randel-James, but my nickname is Kazan. It means "volcano," in Japanese. Yea, and I pretty much just like to eat. I believe that food has the ability to change lives. I feel like food has the power to change the world. So, with that, I created my first CLI! WOOOOOOH! And its about.. You guessed it.. FOOD. More specifically, Filipino food. Awesome right? 

https://github.com/Kazankage/pinoy_dishes

I know it's not much, but hey. It's something. The code is a bit winded, and I know it can be a lot cleaner, but I am just surprised it works. Haha. XD

Basically, the program starts by greeting the user and asks if they have an interest in filipino food. The program then proceeds- depending on whether the user's answer is `yes` or `no`. 

`No`, simply recieve another greeting, and then a farewell. 

If you are brave and dare to venture forward, and type `yes` the program will provide you a list of 10 common filipino dishes. The names are scraped from a website `https://panlasangpinoy.com/recipes/`. 

From there, the user inputs their choice. The program accepts everything from: The name provided by the website, the common name for the dish, or even the number corresponding to the dish.

The program then proceeds to give the user the instructions, again, scraped from the website, for how the dish is made. Once that is completed, the user has the option to return to the list, where they can go through any or all of the choices provided, or simply terminate the program by inputting `Salamat`, which is "Thank You" in tagalog. 

Once they are done, the program sends them off on their way.

Pretty simple right? My goodness. This was definitely a challenge. My sense of time while doing this project went out the door. Once I got off work at 8:30am, I went straight to coding, and then the next thing I knew, I would look up, and the sun would be setting.  

I think the saddest thing about coding is when you make a mistake, but your code still runs. 
I ran into this issue where I was creating instances for all ten of my dishes, they were scraping the names of the website, and then they were supposed to be shoveled into an array, so when I called the array, it would print the names of the dishes. However, no matter how many times I ran my code, only one- the last one- would print. It took me for ever to realize that the 'variable' that I had put my dishes in, "meals.name," were exactly the same, one right after the other, and what happens to a variable, when you set it equal to something else? The varible is replaced with the newest information. So when my "each_with_index" ran through it, it only had one thing in the array to iterate.

I was looking too closely at it to even see it. Haha. Then when I changed that, I thought changing the name of the variables would help, but then I realize that I didnt have them under my attr_accessor so it wouldnt run and would return NoMethodError. Sorry.. I know the way I'm explaining it is kind of confusing, but trust me when I say solved the problem. I just created new methods for all of them.

So just like my explination, my code is kind of messy. BUT it works. That is a "W" in my book. Haha. Now I have to go and clean it up. 

Hope you enjoyed my rant, as well as Pinoy_Dishes. :)
