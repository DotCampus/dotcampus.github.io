---
title: "How We Integrated AI in Our Course Recommendation Feature"
date: 2024-08-02
author: Theo Okafor
description: We recently deployed our AI-powered course recommendation feature on our website to help people find ideal courses that match their goals, interests and experience. This is how we did it...
image: 
---

# How We Integrated AI in Our Course Recommendation Feature
![The working recommendation feature on dotcampus.co](https://github.com/user-attachments/assets/562794ae-7c20-42c5-bba5-2ae977ade983)

<sup>The working recommendation feature on dotcampus.co</sup>

In the first week of July 2024, while discussing how to improve our onboarding process on Dot Campus, our programs manager, Bashirat Sulyman, asked me to check out an interesting feature she found on a particular website. She hoped we could get inspiration from it. After about a week of brainstorming, it became obvious that the feature may serve us best in helping people decide what they should learn and which delivery mode would best serve them, instead of onboarding them. This has been the main focus of many of the queries we have received from our leads.

### The Journey to AI Integration

![The Flowchart of the user journey for the “New Onboarding Flow”](https://github.com/user-attachments/assets/b47c0ec4-5218-4459-b992-17071d136989)

<sup>The Flowchart of the user journey for the “New Onboarding Flow”</sup>

After mapping out the user journey on a flow chart, it became clear that developing an algorithm to efficiently process data and provide intelligent course recommendations to our users would be challenging due to its complexity, which I would rather not bore you with the details.

At this point, I decided it was best to outsource that algorithm to a trained AI.

### Choosing Existing AI Solutions

I was comparing OpenAI's GPT and Google's Gemini. To test them, I spent some time creating a prompt that would provide context for the AI to generate relevant responses aligned with our offerings in Dot Campus. This process took about an hour or two.

Both LLMs yielded similar results for the same prompt, narrowing my decision down to which of them had a better developer experience. I eventually went with Gemini, but mostly because I was already familiar with the developer interface and the free limits looked appealing.

### Integrating Gemini AI into Dot Campus

The next step for me was to properly calibrate and convert the AI response from the usual format to a JSON format which could be easily parsed as a REST API response (REST, or Representational State Transfer, is a software architectural style for creating web services). I also improved the parameters and fine-tuned the AI prompt.

![Gemini prompt and response](https://github.com/user-attachments/assets/4e62c73c-b2b8-4827-89b2-059fe5369916)

<sup>Gemini Prompt and Response in Google AI Studio</sup>

Google AI Studio provided the codes for implementing and interacting with the model, which greatly simplified the work to be done in developing the REST API which would be made available for our website to interact with the AI.

### Challenges and Solutions

**Mitigating Bias and Response Quality**: Initially, some of the responses from Gemini were skewed based on its knowledge about what we do at Dot Campus, so to ensure that the responses were more accurate, I had to provide more context and details about our services.

**Ensuring User Acceptance**: To ensure that users find the responses acceptable, I ensured that the AI is not gamed into providing any preferred response. Also, when we do not yet offer a course being requested, it would tell the user that the course is not available and suggest the next best option for the user.

### Results and Future Plans

It is too early for us to know how the users find the recommendation feature but the overall outlook is very exciting for us. Our goal has been to improve the experience and we have done! The unintended outcome is that through this feature we would better understand the needs of our users.

At Dot Campus, we take delight in continuous learning and improvement. We are committed to enhancing this and finding better ways to serve our learners and potential learners.

The process of working on this recommendation feature has been incredibly exciting for me and the entire team at Dot Campus. It's our first interactive AI integration at Dot Campus, and it's just the beginning of many more to come.

### Finally…

If you are a developer or tech enthusiast and you are curious about what’s possible with AI, then check the Gemini prompt gallery here: https://ai.google.dev/gemini-api/prompts. I hope that you will find an inspiration to *get* *schwifty! 😄*
