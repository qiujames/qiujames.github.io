---
title:  "Sidekick"
date: 2021-01-17
last_modified_at: 2022-03-27
header:
  teaser: /assets/images/sidekick/sidekick-teaser.jpg
sidebar:
  - title: "Role"
    image: /assets/images/sidekick/sidekick-teaser.jpg
    image_alt: "logo"
    text: "Fullstack Developer"
  - title: "Built With"
    text: "Android Studio, WitAI"    
  - title: "Built For"
    text: "Hack the North 2020++"
  - text: "Facebook API 3rd Place Winner"
toc: true
---

Sidekick is an on-command assistant to help make cooking
with recipes faster, easier, and cleaner. Sidekick is loaded on your phone and
placed in your kitchen, where it will listen to your commands hands-free
to guide you through any recipe.

<figure style="width: 40%" class="align-right">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/sidekick/sidekick-inaction.png" alt="">
  <figcaption>Sidekick: Your Kitchen Assistant</figcaption>
</figure>

Our app verbally walks users through recipes step by step,
all while responding to the user’s questions and commands.
Sidekick will figure out what you want, and answer you based on your recipe,
and will stay with you throughout your whole cooking process.  

Powered by Facebook's wit.ai NLP API, Sidekick requires absolutely
no preset command patterns to respond to audio commands.
The app determines the intent behind any question worded in
any form and returns the relevant information the user wanted, all hands-free!
(ie. You can ask "How many eggs are there?" or "Number of eggs?"
or any other variation - Sidekick is just that flexible!)

## Project Design

Here's how we built it.

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/sidekick/sidekick-design.jpg" alt="">
  <figcaption>Sidekick Design and Implementation</figcaption>
</figure>

First, we process audio input through Android Speech Recognizer
to turn it into a string.
Then, we pass the parsed text to the wit.ai API, where the
intent from the text is learned from an NLP model
(An intent represents the main semantics of a question).

Using this intent, we then query a database for the quantity identified
from wit.ai. Then, the app then plays an audio cue using speech to text
letting the user know the answer to their question.

For example, the intent for the questions
"How many eggs are there?" and
"Number of eggs?" would both be: "Quantity Eggs".
After we query the database, we receive the number
of eggs for the recipe and the app uses text to speech
to output "This recipe calls for 2 eggs".
{: .notice--success}

## Project Pitch

{% include video id="puLfJLHztrY" provider="youtube" %}

## See More

- [Project Devpost][sidekick-devpost]
- [Project Source Code][sidekick-repo]
- [wit.ai][wit-ai]



## Meet The Team

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/sidekick/sidekick-team.jpg" alt="">
  <figcaption>Team Georgie!</figcaption>
</figure>


[sidekick-devpost]: https://devpost.com/software/cookingbuddy
[sidekick-repo]: https://github.com/mayaNg-git/sidekick-hackthenorth
[wit-ai]: https://wit.ai/
