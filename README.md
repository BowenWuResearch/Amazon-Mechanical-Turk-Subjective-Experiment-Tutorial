## Abbreviations
| Abbr. | Full name |
| --- | --- |
| AWS | [Amazon Web Services](https://aws.amazon.com) |
| AMT | [Amazon Mechanical Turk](https://www.mturk.com) |
| HIT | [Human Intelligent Task](https://blog.mturk.com/tutorial-understanding-hits-and-assignments-d2be35102fbd), a work published on AMT.
| HTML | [HyperText Markup Language](https://en.wikipedia.org/wiki/HTML) |
| AS3 | [Amazon S3](https://aws.amazon.com/s3/) |
| AMT-Sandbox | [AMT Sandbox](https://requester.mturk.com/developer/sandbox) |

## Requirements
- An email address
- A phone number
- A credit/debit card, though you will not be charged
- Very basic knowledge of HTML for webpage design

## Overview
This tutorial begins with nothing to the end of publishing of a experiment in AMT.
We will start from the creation of an AWS account, using which an AMT project will be created.
In the project, a webpage is used as the interface to the participant.
One can edit the webpage using HTML for specific experimental purposes, such as adding questions or media.
We assume that the media will be stored in AS3, which will also be mentioned in detail.
To test whether everything is correct, or to conduct a preliminary study, AMT-Sandbox is the best tool. 
Finally, the experiment (HITs) can be published through AMT, and we can wait for the responses.

## Table of Contents
- [Creation of AWS Account](##Creation-of-AWS-Account)
- [Test on AMT Sandbox](##Test-on-AMT-Sandbox)

## Creation of AWS Account
<a id="Creation-of-AWS-Account"></a>
You probably will not need to use your own account. 
The lab will provide an official account for you because they will pay the fee. 
However, it is better for testing the experiment using AMT-Sandbox, in which case you still need to use your own account. 
The following procedure shows how you can create an AWS account using an existing email address.

1. Navigate to [AWS](https://aws.amazon.com) and click on `Sign In to the Console`.
<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/dbaa7215-cd9f-4cae-8174-69b7f132e934">

2. Click on `Create a new AWS account`.
<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/32582e48-f0f9-43fa-ab4b-5d6adf6b105a">

3. Input email address and account name whatever you want, and follow their instructions to complete the sign up, which requires password, contact information, a credit/debit card, and a phone number. Finally, choose the `Basic support - Free` to complete.

## Test on AMT-Sandbox
<a id="Test-on-AMT-Sandbox"></a>
AMT-Sandbox is free to test the experiment.
It will not charge the requester who published batches, and it will not pay the workers who have completed any HITs.
Login as requester through the AMT-Sandbox to pubulish batches of HITs, login as worker to complete any published HITs.
The following shows the procedure:

1. Navigate to [AMT-Sandbox for requester](https://requester.mturk.com/developer/sandbox) and click on `Requester Sandbox`. Sign in using your AWS account. If this is the first time you use AMT, you will be required to choose a display name and your email. Input them and proceed.
<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/3c4c0a08-6760-437c-8b1b-c3ca75f09f98">

2. After login, check if this is the sandbox. A banner will be on the top of the page as an indication.
<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/d9fb9202-30b0-4113-8226-18bb42ca7986">

3. Create new project and publish a batch. Remeber to choose a unique name so that it can be easily distinguished from other HITs for us to search. This part will be detailed in the future.

4. Navigate to [AMT-Sandbox for worker](https://workersandbox.mturk.com/), login use your AWS account. This will be a banner on the top of the page to indicate this is the sandbox.
<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/f89ee4ad-5f76-4d50-af9b-4657b97a97bd">

5. Search for your published HITs.
<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/374575d8-d105-42ec-84a6-3dea48433417">

6. Click on accept and you can complete the HITs.

Notes:
- It seems that one AWS account can only accept the HIT once. In order to test it multiple times, prepare multiple AWS accounts in advance.


