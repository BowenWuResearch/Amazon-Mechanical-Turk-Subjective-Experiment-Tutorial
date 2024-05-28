# Amazon Mechanical Turk Subjective Experiment Tutorial
This tutorial begins with nothing to the end of publishing of a experiment in Amazon Mechanical Turk (AMT).
We will start from the creation of an Amazon Web Services (AWS) account, using which an AMT project will be created.
In the project, a webpage is used as the interface to the participant.
One can edit the webpage using HyperText Markup Language (HTML) for specific experimental purposes, such as adding questions or media.
We assume that the media will be stored in AS3 (Amazon S3), which will also be mentioned in detail.
To test whether everything is correct, or to conduct a preliminary study, AMT Sandbox (Sandbox) is the best tool. 
Finally, the experiment can be published through AMT, and we can wait for the responses.

## Requirements
- An email address
- A phone number
- A credit/debit card, though you will not be charged
- Very basic knowledge of HTML for webpage design

## Abbreviations
| Abbr. | Full name |
| --- | --- |
| AWS | [Amazon Web Services](https://aws.amazon.com) |
| AMT | [Amazon Mechanical Turk](https://www.mturk.com) |
| HIT | [Human Intelligent Task](https://blog.mturk.com/tutorial-understanding-hits-and-assignments-d2be35102fbd) |
| HTML | [HyperText Markup Language](https://en.wikipedia.org/wiki/HTML) |
| AS3 | [Amazon S3](https://aws.amazon.com/s3/) |
| Sandbox | [AMT Sandbox](https://requester.mturk.com/developer/sandbox) |



## Table of Contents
- [Preliminaries](#Preliminaries)
- [Creation of AWS Account](#Creation-of-AWS-Account)
- [Test on Sandbox](#Test-on-AMT-Sandbox)


## Preliminaries
### What is HIT and Assignment?
HIT and Assignment will be frequently used.
It is better to understanding their meaning in the context of AMT before proceeding.

`HIT` refers to each task in a experiment.
For example, if we are asking participants to classify images, the classification of **ONE** image will be a HIT.

`Assignment` refers to a experiment as a whole.
For example, if the experiment has 10 images in total for one participant to classify, a completion of **ALL** 10 images will be an assignment.

Therefore, if we publish 3 assignments, 3 particpants will take part in the experiment, each of them will classify all 10 images in one experiment. As a result, we will receive 30 HITs in total, 3 HITs for each image.

For a more information, please refer to [here](https://blog.mturk.com/tutorial-understanding-hits-and-assignments-d2be35102fbd).

## Creation of AWS Account
You probably will not need to use your own account. 
The lab will provide an official account for you because they will pay the fee. 
However, it is better for testing the experiment using Sandbox, in which case you still need to use your own account. 
The following procedure shows how you can create an AWS account using an existing email address.

1. Navigate to [AWS](https://aws.amazon.com) and click on `Sign In to the Console`.
<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/dbaa7215-cd9f-4cae-8174-69b7f132e934">

2. Click on `Create a new AWS account`.
<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/32582e48-f0f9-43fa-ab4b-5d6adf6b105a">

3. Input email address and account name whatever you want, and follow their instructions to complete the sign up, which requires password, contact information, a credit/debit card, and a phone number. Finally, choose the `Basic support - Free` to complete.

## Test on Sandbox
Sandbox is free to test the experiment.
It will not charge the requester who published batches, and it will not pay the workers for completing any HITs.
Login as requester through the AMT-Sandbox to pubulish batches of HITs, login as worker to complete any published HITs.
The following shows the procedure:

### Creation of AMT-Sandbox Project
#### Login
Navigate to [AMT-Sandbox for requester](https://requester.mturk.com/developer/sandbox) and click on `Requester Sandbox`. 

<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/3c4c0a08-6760-437c-8b1b-c3ca75f09f98">

Sign in using your AWS account.
If this is the first time you use AMT, you will be creating a new AMT account.

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/e0b0f192-b4d2-44a1-b75a-d40b3152625d">

A display name and input your email will be required. 
The contact email can be the same as AWS email address.
Input them and create the account.

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/3b3c5553-b030-4f30-a106-a728981302c9">

After login, check if this is the sandbox. 
A banner will be on the top of the page as an indication.

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/d9fb9202-30b0-4113-8226-18bb42ca7986">

If you are not in the ATM-Sandbox, navigate to [AMT-Sandbox](https://requester.mturk.com/developer/sandbox) and sign in  using the account just created.

#### Create AMT Project
Create new project and publish a batch. Choose a unique title so that it can be easily distinguished from other HITs for us to search.

### Working on AMT-Sandbox Project
1. Navigate to [AMT-Sandbox for worker](https://workersandbox.mturk.com/), login use your AWS account. There should be a banner on the top of the page to indicate this is the sandbox.
<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/f89ee4ad-5f76-4d50-af9b-4657b97a97bd">

2. Search for your published HITs.
<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/374575d8-d105-42ec-84a6-3dea48433417">

3. Click on accept and you can complete the HITs.

Notes:
- It seems that one AWS account can only accept the HIT once. In order to test it multiple times, prepare multiple AWS accounts in advance.

### Examine Restuls
Now we can go back to the requester sandbox to check the results.
<img width="800" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/ba60631d-9dfc-4daa-9546-a2520df429bb">


