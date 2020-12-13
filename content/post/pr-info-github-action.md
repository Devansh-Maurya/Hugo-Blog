---
title: "Get a custom formatted email message with PR info using Github Actions"
date: 2020-12-13T16:04:52+05:30
draft: false
description: "Provides a well-formatted email subject and body using branch name used for Pull Request and other information obtained from the pull request."
image: "https://repository-images.githubusercontent.com/200244092/c64f8080-586d-11ea-9f2b-fc72525069dd"
---

[Instructions]: # (To submit to the GitHub Actions x DEV Hackathon, please fill out all sections.)


### My Workflow
I have built my very first Github action from scratch thanks to the Github Actions hackathon by [@devteam](https://dev.to/devteam). The action provides a well-formatted email subject and body using branch name used for Pull Request and other information obtained from the pull request.

I used Javascript to do string processing on the branch name and get a formatted email subject and body with PR info added to it.

The action's inputs and outputs are shown below:

```yaml
inputs:
  repo-name:
    description: 'Repository name'
    required: true
  groups:
    description: 'Branch groups (as CSV) for which you want to get email message data'
    required: true
  branch-name:
    description: 'Branch name'
    required: true
  pr-title:
    description: 'Pull request title'
  pr-url:
    description: 'Pull request url'
outputs:
  subject:
    description: 'Email subject'
  body:
    description: 'Email body'
```  

With the outputs shown above, you can use them as you like. I use them to send an email on pull requests of specific types using another [Github action](https://github.com/marketplace/actions/send-email). 

The mail that I received when I opened a PR with branch name `pattern/test` on the repo [Design-Patterns-And-Principles](https://github.com/Devansh-Maurya/Design-Patterns-And-Principles) is shown below:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/3urrdxnody760mu2g8qh.png)

### Link to Code

[Project code](https://github.com/Devansh-Maurya/Get-Email-Message-From-Branch-Action)


### Additional Resources / Info

I am using my action in one of my repos that I am building while learning design principles and patterns in object-oriented programming. The repo is kind of a note-taking place where I am implementing each pattern that I study in Kotlin. The action sends a mail whenever a pull request is made to add a new design pattern or design principle. Check it out here:

[Devansh-Maurya/Design-Patterns-And-Principles](https://github.com/Devansh-Maurya/Design-Patterns-And-Principles)

Hope you liked it. Thanks for reading.