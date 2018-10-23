POSTMAN
===============
Postman in my experience is a very versatile tool that I use each time I need to test APIs in my projects. It let me organize my test suites and the flow that every test needs to be executed in a way that I can even control the data flow using global or environment context for each cycle. 

I use this tool to automate and control the way of the execution of test will be made. Thus, this characteristic let me to execute a set of tests or cycle for regression testing for every new change, feauture or integration. So, I have a good picture of the status for the actual functionalities of the API. 

To build the new request into Postman is necessary to add the URL, the method (GET/POST/.....), and the authorization header with the JWT provided in the documentation for this challenge. After that you have to add the mandatory parameters to be used in the body and click send.  

first_name | mandatory
last_name | mandatory
phone_number | mandatory
email | mandatory


POST /v1/person/search HTTP/1.1
Host: api.turning.io
Content-Type: application/json
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE1MjQ3NTU2OTUsInN1YiI6IkJEWEtmcG0ydkQwUDM5ZjJmN3I1alFNNWZRZWFYbUZCcnV5c0lKVkQyd1VpQWI4Tm8xRldhWERUOEUyQ2p5ZXUiLCJhdWQiOiJxZTlhaHE1aUc3ZFRvR3JtY1ZkOVU2cDJhOFdaVWZvPSIsImlzcyI6IiIsImV4cCI6MTU1NjI5MTY5NX0.ClGnkM1UZnETmUYAagpbwaQ1jTAqpxhjMuL9YdDGKDY
Cache-Control: no-cache
Postman-Token: a888398c-2974-4035-f883-1912adae76db

{
  "first_name": "Samwise",
  "last_name": "Gamgee",
  "phone_number": "(312) 555-1212",
  "email": "lordvader@thedarkside.com"
}

Test set and coverage for Testing of 3 scenarios according documentation.

1. Happy path

1.1 Happy path with mayus name
1.2 Happy path with minus name

And so on…..
1.3 Negative testing with no mandatory “first name” parameter

1.4 Negative testing with empty “first name” parameter
1.5 Negative testing with invalid “first name-special character” parameter
1.6 Negative testing with invalid “first name” parameter
1.7 Negative testing with no mandatory “last name” parameter
1.8 Negative testing with empty “last name” parameter
1.9 Negative testing with invalid “last name-special character” parameter
1.10 Negative testing with invalid “last name” parameter
1.11 Negative testing with no mandatory “phone number” parameter
Issue- According with the documentation of the API, the phone number must be mandatory, in this case the response obtained is processed successfully (Statys code 200)
1.12 Negative testing with empty phone number
1.13 Negative testing with phone number length less of 11 positions
1.14 Negative testing with phone number length more of 11 positions
1.15 Negative testing with no mandatory email
1.16 Negative testing with empty email
1.17 Negative testing with invalid email

As additional feature of this tool I add asserts to help me to validate the response and code returned by the API.

2.0 Happy path with criminal record as response
3.0 Happy path with unverified location

Following with this analysis and design, and considering a similar number of parameters and testing (positive/negative) we obtain an approximate of 54 test cases.


JSONEDITOR & JSONVIEWER
=========================
To examine probably the body or the response of your requests  it is neccesary to be helped for a tool that make the life eaiser to visualize the structure of this metadata. For me, among the variety of open tools that you can use, I choose this two to be practical and to visualize in a simple way the JSON format.


RESTFULL STRESS
================

Restful stress is a tool to help us to see in a simple way the performance of the API. 

GITHUB
===============
After you creat a new account in github, it is necessary to sync your public gpg keys to gain access to the remote repository. In my case, the account was generated before so , for this step was not necessary to apply to me. It was only needed to create a new repo to upload all the new files generated as results of the testing effort for this challenge.

After you created a new repo it is necessary to be pulled from the remote one to your local. For instance:

$ git clone git@github.com:gopoblano/qa.turning.io.git

$ git remote -v
origin	git@github.com:gopoblano/qa_challenge.git (fetch)
origin	git@github.com:gopoblano/qa_challenge.git (push)

and start committing your files.

In this step I created a new branch just an example of how to create a new feature and being merged to a master, at the end there is not any control to branching.

$ git checkout -b challenge
Switched to a new branch 'challenge'

$ git branch
* challenge
  master
  
$ git status
On branch challenge
nothing to commit, working directory clean
 