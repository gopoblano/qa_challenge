
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
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	qa-challenge.md

nothing added to commit but untracked files present (use "git add" to track)


$ git status
On branch challenge
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   qa-challenge.md

$ git commit -m "Adding qa-challenge"
[challenge 7d1bef5] Adding qa-challenge
 1 file changed, 99 insertions(+)
 create mode 100644 qa-challenge.md

$ git log
commit 7d1bef58e0ae9f989d73879a028770b6950db8b6
Author: Gerardo H <gerardo@gophernandez.com>
Date:   Mon Oct 22 22:52:11 2018 -0500

    Adding qa-challenge



$ git branch
* challenge
  master

$ git checkout master
Switched to branch 'master'

$ git merge --no-ff challenge
Merge made by the 'recursive' strategy.
 qa-challenge.md | 99 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 99 insertions(+)
 create mode 100644 qa-challenge.md

$ git log
commit e34dfd99a7dde5a66634116535b0a8787dc18cf0
Merge: 5da0932 7d1bef5
Author: Gerardo H <gerardo@gophernandez.com>
Date:   Mon Oct 22 22:53:14 2018 -0500

    Merge branch 'challenge'

commit 7d1bef58e0ae9f989d73879a028770b6950db8b6
Author: Gerardo H <gerardo@gophernandez.com>
Date:   Mon Oct 22 22:52:11 2018 -0500

    Adding qa-challenge

commit 5da09326a0ddd54982b86c559d3eb50dd4cb554d
Author: Gerardo H <gerardo@gophernandez.com>
Date:   Tue Oct 16 21:15:12 2018 -0500

    Adding a first commit

 $ git branch
  challenge
* master

$ git push origin master
X11 forwarding request failed on channel 0
Counting objects: 7, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (7/7), 2.70 KiB | 0 bytes/s, done.
Total 7 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/gopoblano/qa_challenge/pull/new/master
remote: 
To git@github.com:gopoblano/qa_challenge.git
* [new branch]      master -> master

$ git checkout challenge 
Switched to branch 'challenge'
ubuntu@ubuntu-HP-ProBook-6470b ~/git/projects/qa_challenge $ git push origin challenge
X11 forwarding request failed on channel 0
Total 0 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'challenge' on GitHub by visiting:
remote:      https://github.com/gopoblano/qa_challenge/pull/new/challenge
remote: 
To git@github.com:gopoblano/qa_challenge.git
* [new branch]      challenge -> challenge




