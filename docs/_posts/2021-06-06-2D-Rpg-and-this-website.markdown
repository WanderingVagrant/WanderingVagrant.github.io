---
layout: post
title:  "2D Rpg and This Website!"
#date:   2021-06-06 18:17:00 -0700
categories: jekyll update
---
Hi readers!    
In this post, I'm going to discuss a bit about the 2D rpg I worked on as part of the game development club at UCSD and how I made this very website!

- [2D RPG](#2d-rpg)
- [This Website](#this-website)

## 2D RPG

![image](/assets/images/Unity.jpg)

As part of the game development club at UCSD, I joined a team in the fall with the goal of making a 2D Rpg in Unity Game Engine. A 2D Rpg, is short for a two-dimensional role-playing game, like the Legend of Zelda, Final Fantasy, or Pokemon. Unity is a tool that has a bunch of helpful features when making your own game and is a very popular choice for those new to making games which was perfect for a team almost entirely new.     

Our first phase of the project was planning, and as we knew we might only have a quarter to work on the project, we decided to set priorities for which part of the game we wanted to complete first. We decided that at the very least we should get the character system, the party system, and the enemies complete in the context of a turn-based battle a la Octopath Traveller.    

I decided to work on the back end of the battle system for the game. The battle system handles the information about the attacks, damage, and user inputs behind the scenes. Going for an object-oriented approach we decided to have one static class that managed these. I was tasked with making and implementing this class along with the turn system for the battles. I decided to use a state-based system that would tell the rest of the components whose turn it was and whether to accept input or not.

## This Website

![image](/assets/images/Jekyll_(software)_Logo.png)

To create this website I decided that instead of using WordPress, or another more common website creation service, I would use Github Pages, a service that lets you host almost whatever website you want for free. However I didn't want to code all the Html for it myself, so I used Github Pages in conjunction with Jekyll which is a program that generates the Html files for Github based on a theme and other specification. This is different than other services because it can allow for all the customization you want as one has the option to directly modify the templates and themes that come included, and the option to get countless more themes. I decided this system was perfect for me as it wouldn't take too much time, yet it would still allow me to be flexible and make changes if I needed to.    

Making this website turned out to be a very helpful experience as I learned how to make a website on Github Pages and Jekyll, and I feel confident that if I need to make one in the future I will know exactly what to do.

