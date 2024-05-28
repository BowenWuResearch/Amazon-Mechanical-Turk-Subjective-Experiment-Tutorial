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
- [Test in Sandbox](#Test-in-Sandbox)
- [Publishing Experiment in AMT](#Publishing-Experiment-in-AMT)
- [Notes on Preparing Materials](#Notes-on-Preparing-Materials)

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

## Test in Sandbox
Sandbox is free to test the experiment.
It will not charge the requester who published batches, and it will not pay the workers for completing any HITs.
Login as requester through the AMT-Sandbox to pubulish batches of HITs, login as worker to complete any published HITs.

### Login as Requester
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

### Creat Sandbox Project
#### Enter Properties
We will take Image Classification as an example to show how a Sandbox project can be created.

Click on `Create` tag, and select Image Classifcation in Vision category, fianally click on `Create Project`.

<img width="500" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/7cf7097f-cf80-40f0-a8b4-0382f3c8eb8c">

You will have to enter the following for a project:
- `Project Name` is the name for you project managemtnt. It will only be shown to you.
- `Title` will be shown to all workers on AMT (Sandbox in this case). Choose a unique title, so that it can be easily distinguished from other assignments, for us to search afterwards. I usually use my name and the current date and time, e.g., WuBowen-20240528-1553. However, in the real experiment, the title should be descriptive of your task for gathering participants.
- `Reward per assignment` is the amount you will pay for each assignment. We set to 0.0 because this is only for test.
- `Number of assignments per task` is how many participants you want to gather. We will set to 1 for testing. If you want to conduct preliminary experiment, input any number you want.
- `Time allotted per assignment` is the time limitation for completing one assignment.
- `Task expires in` is the duration of how long your task will last on Sandbox.
- `Auto-approve and pay Workers in` means if you do not prove or reject a HIT for a period of time, the HIT will be automatically approved and the reward will be given to the worker who has completed this HIT. This will not happen in the Sandbox.
- `Require that Workers be Masters to do your tasks`. AMT maintains a list of wokers who show high performance. Check to only allow Masters to complete your task. Although this is likely to improve the quality of the responses, more completion time is generally expected. Do not check Yes in Sandbox because you will not be able to test it using your non-Master account.
- `Specify any additional qualifications Workers must meet to work on your tasks` provides creterions to filter out workers for specific need. For example, sometimes we want our participants to be located in some contries. In our case, we can set the region of workers to  Japan.
- `Task Visibility`. I do not really understanding the purpose of this option. Usually keep it `Public` will suffice.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/dc63fd7b-3a0d-4aa9-9c0f-541253fa5da4">

Finally, we can proceed to design the layout.

#### Design Layout
You will be presented by HTML codes, which defines the interface of the experiment.
You can edit the content for you specific purpose.

One thing that requires attention is how to load images in to this HTML.
In the following figure, there is a tag called `crowd-image-classifier` in the red box.
While it has four attributes, the `src` variable is crucial for loading images.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/2084a2fa-fcbd-485c-b32e-73b6f5456b8b">

When publishing a batch of assignments, a csv file is required.
In our case, the csv file contains a header called `image_url` followed by rows of urls of image, which looks like this:
| image_url |
| --- |
| url of image 1 |
| url of image 2 |
| url of image 3 |

In one assignment, each row in the csv will be iteratively loaded and processed, resulting in 3 HITs.
In each HIT, the value of `src` defines where to find the url.
In our example, `src="${image_url}"` means that it will take the values under the column `image_url`, with which the value of `src` will be filled.
As a result, the `src` will contain one of the urls of image in the csv file.
This tells the `crowd-image-classifier` which image to load for the classification.

By putting urls into the csv file, we can choose the images that will be used in the experiment.
In addition, you can have multiple columns if you want.
In that case, refer to their values using their column names by `${column_name}`.

For advance usage, you can browse other project templates and read the comments in it.

When finised, click on the `Preview` to proceed to the next step.

<img width="500" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/e3b05af2-e058-423f-ac45-610406635bb6">

#### Preview
In the preview page, we can check if the page is rendered as intended.
Ignore the warning `Failed to load the image` because we have not provided images for it.

You can click on the page to test each functionality.
For example, cliking on instruction will show a window of instruction.
These are connected to HTML elements in the source code.
You can go back and modify the code if anything goes wrong.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/02b79811-f736-464b-8e3a-5250023e4a05">

One thing should be noted is that you can actually submit an answer in this preview and see what results you can get.
Just select one option and click on the submit at the bottom right.

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/5e5b613e-6f4f-417a-8aaa-9117f7d2d99a">

Your answer will be shown on the top of the page.

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/340af974-dede-4806-a198-2751ae8aedab">

If everything is alright, click finish.

### Publish Batch of Assignments
#### Prepare csv file
The format of the required csv file has been described in [Design Layout](#Design-Layout), [here](https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/files/15466602/input.csv) is a template csv file I created for demonstration purpose. Download it and check its content to get a sense. Or you can make your own one.

#### Publish Assignments
After the csv file is prepared, click on `Publish Batch`.

<img width="500" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/50317095-3e1e-4556-ba50-1757a5f964f5">

Choose a csv file.

<img width="300" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/1fe90bf4-f994-4aa3-bade-22556e6cc8a6">

Upload the file.

<img width="300" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/e6729cb6-5bae-4ec8-8d83-a220230c76d3">

Sandbox allows you to preview the task before actually publishing it.
Below shows some elements you may want to check:
- Left upper corner shows the title.
- `Reward` shows the reward to workers completed the assignment.
- `Tasks Available` shows how many assignments are there for this experiment.
- `Duration` shows the time limitation for completing the assignment.
- `Showing Task 1 of 3` shows how many HITs are there in one assignment.
- `Next HIT` in our case is used to go to next image, i.e., the next row in the uploaded csv file.
- `Qualifications Required`. The criterion we have set.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/4d9656e0-ff20-4b34-8deb-f9d25479cb1b">

Check the information of the batch.
You can change the `Batch Name` for management of your batches.

I feel that more explanation is needed for `Tasks` as the description is not so comprehensive.
`Number of tasks in this batch` should refer to how many HITs are there in each assignment, in our case it is 3.
`Number of assignments per task` should refer to the total number of assignments, because `task` here refers to HIT. In our case it is 1.
As a result, `Total number of assignments in this batch` should be the total number of HITs.

The `Cost Summary` can be ignored since we are in Sandbox.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/1a3bf401-8fc2-4c5e-9bee-486430fe5432">

Click on `Publish` to publish the assignments.

Immediately, the page should be redirected to batch details, where you can check status of the batch, and view the results.
- `Assignments Completed` shows the progress.
- `Cancel` can terminate the publishing of assignments. However, assignments that have been already accepted by workers will not be terminated.
- `Results` is where we can check the received responses of workers.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/51669560-5347-443e-abe6-da87f9a3d862">

### Complete Published Assignments
#### Login as Sandbox Worker
Navigate to [AMT-Sandbox for worker](https://workersandbox.mturk.com/), login use your Amazon account.

In order to be a worker, an Amazon account for AMT worker needs to be registered.
If you failed to login, create your Amazon account first.
You can use the email used to create the AWS account.

<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/47af8313-d705-4ff9-94cf-c4718633dbe1">

There should be a banner on the top of the page to indicate this is the sandbox.
If there is no one, navigate to [AMT-Sandbox for worker](https://workersandbox.mturk.com/).

<img width="400" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/f89ee4ad-5f76-4d50-af9b-4657b97a97bd">

In Worker Registeration, input necessary information and click on `Create Account`.

<img width="200" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/0c476d5a-f171-4908-be4f-fb9e601b55b8">

#### Browsing Published Assignments
Because we want to complete the assingment published by ourself, we can search for it by inputting the title. In our case, it would be `WuBowen-20240528-1553`. The search results are shown below.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/15573b46-64f6-4a96-8cd8-0d512ff020ce">


#### Complete the Assignment
Click on `Accept & Work` on the right of the assignment to proceed.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/44c89d8f-9437-45ad-8407-1e654272c2cb">

Then you can submit your answer to complete the assignment.
Select one category and submit the answer.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/d580233a-126d-405d-ba2f-4f4c605da0bf">

#### Notes
- It seems that one AWS account can only accept the HIT once. In order to complete multiple assignments, prepare multiple AMT worker accounts in advance.

### Examine Results
Now we can go back to the requester sandbox to check the results.

Login as requester, navigate to `Manage` tag, the published batch will be there.
Click on `Review Results` to view the results.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/bc7514b3-edfe-4936-8d85-cf560c2ee25e">

The table shows all the received responses that have not been approved or rejected.
The results can be downloaded as csv and used for data analysis.

<img width="600" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/740e205f-0aab-4a1b-8513-ba4b1754fab1">

In real AMT experiment, you can check the response of each worker, and decide to approve or reject their response. 
This is necessary as there will be bots or people that give low-quality answers which can bias the results. 

By approving HITs, you give permission to reward the worker.
If you reject them, they will not be paid, and AMT will automatically publish a new assignment.

By downloading the csv, and mark "x" under a column titled "Approve" or putting your reject comment under a column title "Reject", you can do this offline.

<img width="500" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/8cbbe96d-63c4-401f-a159-2fc4395d6839">

Afterwards, you can upload this edited csv to AMT for this purpose.

<img width="300" alt="image" src="https://github.com/BowenWuResearch/Amazon-Mechanical-Turk-Subjective-Experiment-Tutorial/assets/170743218/e544678f-b832-44cf-8f95-503d7b9973c6">

## Publishing Experiment in AMT

## Notes on Preparing Materials
