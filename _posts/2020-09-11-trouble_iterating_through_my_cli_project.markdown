---
layout: post
title:      "Trouble Iterating Through my CLI Project"
date:       2020-09-11 17:38:28 +0000
permalink:  trouble_iterating_through_my_cli_project
---


This week during the CLI project, we were tasked with creating an app on our own. I first wanted to create an app that uses a restaurant finder API depending on location. I started working on it and shortly after, noticed I was not fully passionate about it and restarted my search for a different API. That's when I came across the Open Trivia Database, an API whose data can be changed to the users liking. I decided to go with a General Knowledge, mid level quiz.

This is where I started having trouble with iterating through the keys and values individually. The question and answers were all stored under [:results] and I was stuck trying to figure out how to get the question, correct answer and incorrect answers separately. My first attempt was to separate the :results into an array (trivia_arr) and from there collect the questions using the [:question] key to collect from results. 

```
trivia_arr = trivia_hash[:results]
quest_arr = trivia_arr.collect { |x| x[:question] }
```

This worked but however it seemed inefficient, so I took to our past live lecture and found the missing piece. I needed to iterate through the trivia array (trivia_arr) and in my trivia.rb file get each of the keys and values separately. 
api.b:
```
triv_ques = trivia_arr.collect do | q |
    Trivia.new(q)
```
trivia.rb:
```
self.question = q[:question]
 self.correct_answer = q[:correct_answer]
 self.incorrect_answers = q[:incorrect_answers]]
```
 
This way, I could access the specific key and value I need from each result. Which looking back may seem like a simple solution but sometimes, it stops making sense and we need to take a step back and like at the whole picture. 

