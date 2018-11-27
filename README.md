# cf-example-quiz


#Run Terraform
	-Create Project, link billing, enable apis, and create Repo for Website


#Firebase

	-Initialize Firebase

gcloud beta firestore import gs://terraform-is-con-2018/2018-11-27T02:18:39_87408


#Deploy Website - Manually 
gcloud functions deploy getRandomQuestion --source=https://source.developers.google.com/projects/is-con-quiz-project-5/repos/is-con-2018 --trigger-http
gcloud functions deploy checkanswer --source=https://source.developers.google.com/projects/is-con-quiz-project-5/repos/is-con-2018 --trigger-http


#Configure Jeknins Job
	- Add Credential
 

#!/bin/bash
gcloud auth activate-service-account --key-file=is-con-terraform-1806d84527d4.json
gcloud functions list
gcloud functions deploy getRandomQuestion --trigger-http
gcloud functions deploy checkanswer --trigger-http
gcloud functions describe getRandomQuestion
