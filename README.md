cf-example-quiz

#Run Terraform: Create Project, link billing, enable apis, and create Repo for Website

#Initialize Firebase

	#Login to Firebase console, initialize gcp project & database.
	gcloud init
	gcloud beta firestore import gs://${bucket}/2018-11-27T02:18:39_87408

#Deploy Website - Manually
	
	#Initialize local repo and push to GCP repo
	gcloud functions deploy getRandomQuestion --source=https://source.developers.google.com/projects/${project}/repos/${repo} --trigger-http
	gcloud functions deploy checkanswer --source=https://gcprepo --trigger-http


#Configure Jeknins Job - Add Credential

	#!/bin/bash
	gcloud auth activate-service-account --key-file=key.json
	gcloud functions list
	gcloud functions deploy getRandomQuestion --trigger-http --source=https://source.developers.google.com/projects/${project}/repos/${repo}
	gcloud functions deploy checkanswer --trigger-http --source=https://source.developers.google.com/projects/${project}/repos/${repo}

