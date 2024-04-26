--- 
layout: essay
type: essay
title: "The Power of the Pattern in the Palm of Your Hand"
# All dates must be YYYY-MM-DD format!
date: 2024-04-125
published: true
labels:
  - Design Patterns
  - Software design
---

## The Power of the Sun, in the Palm of Your Hand

In the original Spider Man trilogy with Toby Mcguire (the only Spider Man series worth acknowledging), during the second installment in the series, Dr. Octavious, brilliantly played by Alfred Molina, gives a provocative statement to Peter Parker about the power of nuclear fusion for unlimited energy supply: “the power of the sun, in the palm of my hand.” This power which Doctor Octavius is able to harness, along with the artificial intelligence unit he gives unfettered access to his mind, ends up corrupting his ability to make sensible decisions and causes him to nearly bring total destruction of Manhattan. It is a wonderful example of the kind of power a human is capable of creating when they have no bounds.

## The Power of the Pattern, in the Palm of Your Hand

While creating our final project, my team has been grappling with how to deal with giving power to the user. Because our project, Study Buddy, which we have renamed StudyLink affectionately after Elon Musk’s Starlink, functions by allowing users to create study sessions in the hopes that they will attract other users with similar issues or skills helpful to their success to attend their session, it is primarily a user run website. Similar to Doctor Octavius’ miniature sun, StudyLink in our case, provides a platform for users to interact in ways which could either be beneficial or detrimental to their success. As the developers, my team must devise ways in which we can act like Spider Man by creating a system which allows the sun to become useful and productive, but prevent it from spiraling out of control so we do not have to sink the sun into the East River of New York. 

To deal with this power, the kind of design pattern our sun implements is called a Front Controller design pattern. This allows users to place a request that creates a study session where the information is passed to a handler that verifies the information is within the bounds of what is acceptable, and posts the session to the website for other users to see. If a user fails to follow the rules, then their request will be denied by the handler and no study session will be created. This will allow the site to be autonomous in a sense that it does not need large admin oversight to approve or deny study sessions.
 
