---
layout: post
title:  "Smoove Chat Assistant"
date:   2016-08-25 14:55:21 -0400
categories: blog
tags: [project, hackathon]
---
I built and presented this project at Hack The 6IX in August 2016 at WealthSimple HQ in Downtown Toronto.

### Inspiration
Today, there are more platforms for conversations than ever - Slack, WeChat, WhatsApp, Kik, Facebook Messenger, Skype, Snapchat, and many others. As a reaction to this increasingly overwhelming social frontier, we sought to develop a service to help people take better control of their communicative skills.

Often, it can be awkward for strangers to start a conversation. And because they don’t know much about one another, finding a common topic to talk about can be difficult. Or, they might not know how they should make their first impression. Smoove excels in these situations, giving the right advice to approach a conversation and leave a memorable impression.

### What it does
Smoove takes a provided Twitter username and/or a sample of writing, and instantaneously returns to the user custom suggestions on how to talk to them. Suggestions include recommended topics and information pages on them, recent news articles, political inclinations, and topical gifs. These sets of information aim to help the user better communicate with their peers using as little time and effort as possible, while still allowing the user to have a completely personal experience because they ultimately choose where to take the conversation.

### How I built it
The web page is built on Angular, with several external libraries for aspects such as Materialize styling and Chart.js. The backend is built upon Node and Express. The whole webapp is deployed to Heroku cloud on a free tier account.

Once the user submits the Twitter username and/or text sample, we make a call to the Twitter API on the backend to retrieve the 200 recent tweets. Then we use the indico API extensively to analyze the tweets and/or text. We currently use the text tags, personality analysis, and political analysis from indico.

With indico’s data, we then find relevant news articles through Microsoft’s Bing Search API as well as gifs from Giphy’s public API. Additionally, each suggested topic is linked to its appropriate Wikipedia page. We display the results on the webpage once all of these parts finish processing.

### Challenges I ran into
Originally, we wanted to streamline our app structure as much as possible, which compelled us to use a front-end only implementation. However, this fell through after a few hours due to twitter API call problems in Angular and we decided to switch back to Node and Express.

Of course, deciding on an idea to do was also a challenge for us. We originally wanted to create an Android application, but changed to the web platform to better fit our skillset.

### Accomplishments that I'm proud of
We were able to define a clear goal that was not only achievable within the time constraints but also enough of a challenge for us to develop our skills. We were able to set a clear goal and carry out our plan in a straightforward fashion between team members. This simple atmosphere was helpful in the stressful hackathon environment.

### What I learned
In dealing with our Twitter API difficulties, we were able to get a better grasp on authentication processes, REST API calls and HTTP methods. In moulding and distilling the concept of our application we were also able to further develop our brainstorming skills.

### What's next for Smoove - Chat Assistant
There are many directions we could take this project in the future. First and foremost, we would like to see a more convenient implementation of the service, such as integrating it into phones where it could be easily accessed from any messaging app and assisting the user in real time.

Also, there could be many other sources we could retrieve data from, including other social media platforms and chat histories. This would allow a larger set of data to work with, leading to better suggestions. Furthermore, we would implement continuously improved predictive models and deep learning algorithms to provide the most accurate analyses, and therefore, suggestions possible. However, this would be beyond our skillset for now.

Finally, because our app applies to communication, and communication exists everywhere, our app has applications practically everywhere. For example, someone may want to better accommodate their clients, or perhaps a friend wants to improve an existing relationship. In this sense, we feel that our project is best viewed as a general-purpose tool.

### Contributing
If you're interested, please fork the repository, make changes and submit pull request.

{% include icon-github.html username="aamirsahmad" %} /
[smoove-chat-assistant](https://github.com/aamirsahmad/smoove-chat-assistant)