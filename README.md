# superhero_showdown
Project 3

This repository contains Group 1's final project, entitled "Superhero Showdown."

The project was created by Fidel Lerma, Griffin Roberts, and Robert Lindsey.

# Overview:
This project utilized a csv containing data on approximately 1,400 superheroes and villians to create a user-friendly battle simulator.

Users may select 2 characters and simulate a battle. The winner is announced and an API call provides a battle description and image reflecting the result of the simulation.

# Method:
The csv provided base scores for heroes in the categories of strength, speed, durability, combat and intellegence. Additionally, there were columns comprized of lengthy text strings describing each hero's unique abilities and powers. Height and weight was also provided in centimeters, inches, meters, kilograms, pounds and tons.

There were also columns containing irrelevant details, such as skin and eye color, which were dropped from the dataset.

We normalized the base hero scores, heights and weights.

Lists were created reflecting words that are associated with each of the base attributes and we tokenized and vectorized the lengthy text string descriptions to provide heroes a point for each word recognized within their text description columns for the relevant and corresponding attribute. This calculation provided a literary score for each hero that was added as a column. 

The dataset also contained numerous columns for specific features such as "has fire resistance, has super strenth," etc. These columns were handled by converting to 0s and 1s. If a hero had a positive, i.e. "1" then they received a small boost to their total score for each.

# Simulation:
The simulation for the hero battles was designed to reflect the uncertainty of battle and give heroes who possess a lower total score to have a chance at victory against a stronger hero. The first selected hero and second selected hero have their total scores added together. Then, that number is divided by the first hero's total score. a randomizer generates a number between 0 and 1. If the two hero scores divided by the first hero's score is greater than the random number, then the first hero is victorious. If the random number is greater than the result of dividing the total by the first hero's score, then hero 2 is victorious. 

This equation allows heroes that are closeley matched to their opponent a chance to win. Otherwise a hero with even a slightly higher total score would always win in a matchup. The random number generator implementation is not significant enough to produce bizzarre results where significantly superior heroes lose to much weaker heroes, but allows for more realistic combat between opponents that are closely matched or where the disparity of power is not extreme.

# Model:
The model utilizes Gradio as a user-interface with a dropdown menu feature to assist with selection and spelling. Once the simulation is initiated, the result will provide an output of the winner, an AI generated text description of the battle, and an AI generated image of the Winner. *The AI generated image was initially set to reflect a scene from the simulated battle. However, this regularly resulted in an error due to content restrictions regarding violence within generated images.

# Purpose:
The purpose of this project was to create a fun and interesting way to explore the possibilities of hero and villian matchups that fans crave, but will likley never see in comics or theaters. Given the popularity of hero battle discussions on many internet forums, we felt this was a concept that many fans would enjoy playing with for amusement.

# Code Source
The code for this project was created by team members, Fidel Lerma, Griffin Roberts, and Robert Lindsey. Chat gpt was utilized to resolve errors in code and troubleshoot openai version depreciation errors with openai.Completion.create()