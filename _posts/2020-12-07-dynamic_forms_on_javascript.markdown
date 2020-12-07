---
layout: post
title:      " Dynamic Forms on JavaScript"
date:       2020-12-07 00:02:54 -0500
permalink:  dynamic_forms_on_javascript
---


When starting a project my always goes crazy with ideas and plans I have for it, but reality quickly pulls me back and I have to fit my ideas to the time window and functionality available. This is now our 4th project and I am slowly but surely gaining in confidence and skill. This time me and a fellow student paired up to work on our separate projects alongside each other which made the process much smoother. 

From many features I wanted to add, a form that adapted dynamically depending on a form with the categories listed, was definitely a must. And yes, it was as complicated as it sounds to figure out. We searched for multiple sources, but none quite provided what I needed. Until we came across a YouTube video by [Unpossible POG](https://youtu.be/iWIaU8Jq8-4) where he explained how to get a dynamic dropdown that provided another dropdown depending on the input. This was the closest source we found to what I needed so what I needed to do now was refactor it. 

The first I needed was to list the options I wanted to include in my dropdown box and call them in a function. In this case, I gave the select form and id of “input” which will be useful for the conditionals. 

function selectForm(){
  let pinsForm = document.getElementById("form")

```
  pinsForm.innerHTML += 
`
<select id="input" name="filter" onchange="renderPForm()">
  <option>variable1</option>
  <option>variable2</option>
  <option>variable3</option>
</select><br />
<div id="message"></div>
`

renderForm();
}
```

An important factor to keep in mind is the additional div at the end of the select form with an id of “message” which will be where we append the following conditionals to.

Once the select form is set and done we can start our conditionals. To make the code DRY and efficient I set the querySelector for the “input” id to a variable “a” and got its value. This is what we need to compare the chosen category from the dropdown box to the available forms. 


```
function renderForm(){
  let a = document.getElementById("input").value;
  // console.log(a)
  if (a === "Fashion"){
  document.getElementById("variable2").innerHTML = `<form> 
    </form>`

  }else if (a === "variable2"){
    document.getElementById("message").innerHTML = `<form>      
 
    </form>`

  }else if (a === "variable3"){
    document.getElementById("message").innerHTML = `<form>          
    </form>`
  }

  formSubmission();
}
```

Once that is set, we can now understand how our form dynamically changes depending on the value of our dropdown box. 


