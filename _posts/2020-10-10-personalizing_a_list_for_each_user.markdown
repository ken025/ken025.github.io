---
layout: post
title:      "Personalizing a List for Each User"
date:       2020-10-10 06:22:02 +0000
permalink:  personalizing_a_list_for_each_user
---


	
  This week we were working on our Sinatra Projects where we had to develop a web application to track something important to us. My mind went to a task I often do, checking my pantry to see what items I have and what items I need. This may seem like something simple, but it is easier to forget or overlook an item than I would like to admit. With this custom app, a user could create an account and submit the items they have in their pantry or even want to get. Each item has a quantity form where the user can input the amount of that item they have. This way, when they want to grocery shopping, they can access their list and check what items they are in need of. 
	
It was the perfect app for me, but then came the task of making sure each user had access to their list and only theirs. A task that seems simple but troubled me the most. I was working with a seed file with dummy data that gave me fruits and random numbers for the quantity, but all the user accounts had the same data, which obviously defeated the purpose of the app. 

     To tackle this task, I created a “current_user” method where it used memoization to find a user and set it to @current_user. It is basically saving a method's return value so it does not have to be recomputed each time.

```
	def current_user

    # memoization, uses the @user or finds the user's id and sets it to @user
    @current_user ||= User.find_by(id: session[:user_id])
    end
```

This was the puzzle piece that I was missing to bring it all together. With this, I finally could make sure each user got all of their items.
 ```
@items = Item.all.where(user_id: current_user.id)
```

Building this custom app taught me a lot, not only about how to make one but about myself and how persistent, in making sure I find the suitable solution, I am. Moments like this where I have to try a thousand methods before finding the right one, are the moments that make me a better coder.

