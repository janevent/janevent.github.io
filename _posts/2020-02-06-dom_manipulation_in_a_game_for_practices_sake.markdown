---
layout: post
title:      "DOM Manipulation in A Game for Practice's Sake"
date:       2020-02-06 20:22:26 +0000
permalink:  dom_manipulation_in_a_game_for_practices_sake
---


For my Javascript/Rails project I decided to create a simple game to help young learners practice math equations.  I would like young children to be able to choose between multiplication, division, addition and subtraction questions.


Basic manipulation of the document object model(DOM) consists of targeting elements, listening for events, and altering existing elements or creating new elements to then attach to the DOM.  To break it down:


1. I select an element: let container = document.querySelector(“.first-view”). The period indicates that  I am looking for an element using a class name. 

 

2. I create button elements with ids, and give them values of different operators. I assign the buttons to container’s innerHTML. 


3. Each button is targeted and an event listener is added to it.  The event is “click”, a pretty common action when using a computer.  This is my code below.  It could be cleaned up a bit, but you get the idea.  Clicking the button with the id of “times-operator-button” is a signal for a new instance of a question to be created, and two subsequent functions are called.


}`function addEventListenerOnTimes(){
    let tOB = document.getElementById("times-operator-button");
    tOB.addEventListener("click", function(e){
        let num1 = Math.floor(Math.random() * 10) + 1;
        let num2 = Math.floor(Math.random() * 10) + 1;
        let operator = " * ";
        let timesQuestion = new Question(num1, operator, num2);
        timesQuestion.renderQues();
        addEventListenerOnCheck(timesQuestion)
    })
}`


4. I repeat these simple steps of targeting elements, creating new elements and attaching them to the DOM, and using event listeners,  throughout my code.  They are essentially my project’s front end building blocks.  I just add in fetch requests to access (get), create and update data on the back end.  


