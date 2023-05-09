---
title:  "Evaluate"
date: 2021-10-24
header:
  teaser : /assets/images/evaluate/evaluate-teaser.jpg
sidebar:
  - title: Role
    image: /assets/images/evaluate/evaluate-teaser.jpg
    image_alt: logo
    text: I did everything LOL
  - title: Built With
    text: React, Selenium   
  - title: Built For
    text: DubHacks 2021
  - title: Winner of
    text: |
      - DubHacks Next Most Comercially Viable Prize Winner
      - DubHacks Campus Track Finalist (Top 3)
last_modified_at: 2023-05-09
---

<figure style="width: 50%; margin-block-start: 0; margin-block-end: 0px;">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/evaluate/evaluate-app.jpg" alt="">
  <figcaption>Evaluate, a financial literacy tool</figcaption>
</figure>
{: .align-right}

The team was inspired to build Evaluate for Dubhacks 2021 to solve the challenges faced by job searchers, especially new graduates, when comparing job offers. The team realized that job searchers face challenges like pay transparency, total compensation estimation, and cost of living comparisons.

## Features
Evaluate simplifies the process of planning for the future by considering factors that may not be readily evident from a single job offer letter. 
The concept of the app is simple. [^1] 
Users just need to input their desired company and location.

With just these two pieces of information,
Evaluate provides valuable insights such as historical average salary data for that specific company and location. 
Additionally, it calculates your monthly after-tax income, accounting for state and federal taxes, as well as the monthly cost of living, including rental expenses, based on location-specific figures. 

Evaluate has the following features:

- Helps job searchers (especially new grads) compare offers between companies across different locations
- Provides total compensation estimates based on crowdsourced salary data
- Increases pay transparency so job searchers can negotiate offers
- Tracks monthly expenses and compares against how much income or saving you can expect per month
- Automatically adjusts for state and federal level taxes in our take home salary estimates

All this information is consolidated into clear, concise, and digestible insights with just a company and a location!
Adding an actual compensation offer can also provide users with even more accurate calculations.


## How We Built It
Evaluate was built using React, Selenium, and the Taxee API. We used React for the frontend of the app and Selenium to gather our compensation estimates. The Taxee API was used to calculate the state and federal taxes and adjust the take-home pay calculation accordingly.

To provide compensation estimates, we collected crowdsourced data from levels.fyi. We then built a custom algorithm to analyze this data and provide compensation estimates based on various factors such as job title, company, location, and years of experience.

For monthly expense estimates, we developed a custom algorithm that factors in the cost of living in a particular location and the user's income. This algorithm takes into account expenses such as rent, utilities, groceries, and transportation by computing out average costs based on the city the job offer was based in.

## Challenges
Building Evaluate taught us several valuable lessons about software development, teamwork, and problem-solving. Some of the key learnings from this project include:

- **The importance of understanding user needs**: Throughout the project, we focused on understanding the needs of job searchers and tailoring the app to meet those needs. This helped us build a more effective and user-friendly app. We settled on a very simple interface that required just two inputs: the company name and location.
- **The challenges of working with external APIs**: Integrating the taxee API for tax calculations was a significant technical challenge, requiring careful testing and debugging to ensure that we were computing the accurate post tax amounts.
- **The benefits of effective teamwork**: We worked closely as a team, dividing tasks and supporting each other throughout the project. This helped us stay on track and overcome obstacles more easily.


## What's Next
Looking ahead, we hope to continue building and refining Evaluate to make it an even more valuable tool for job searchers. We plan to incorporate additional features, such as personalized savings and investment advice, and to expand our user base beyond new graduates. Ultimately, we believe that Evaluate has the potential to help many people make more informed decisions about their careers and finances.

## See More
- [Project Devpost][evaluate-devpost]
- [Project Source Code][evaluate-repo]
- [Other Dubhacks'22 projects][dubhacks-devpost]


## Special Thanks

- Ardelle Ning for yet another hard carry
- _Startup_ for the OG inspiration

[evaluate-devpost]: https://devpost.com/software/worth
[evaluate-repo]: https://github.com/kaamnarishi/dubhacks2021
[dubhacks-devpost]: https://dubhacks-21.devpost.com/

[^1]: At the beginning of the Hackathon when Ardelle and I were forming our team someone actually ditched our team upon hearing our idea. They thought the idea sounded too simple and definitely wouldn't win anything. Definitely killed our mood in the beginning so it was satisfying to make it pretty far. 

