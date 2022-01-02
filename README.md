AI Supervisor is an open source project from Open Gradient.  
 
AI Supervisor is an ML augmentation tool and was originally designed for conduct risk/surveillance staff within financial services. The idea was to cut down on the amount of time staff spent reading through electronic communications while looking for content of interest.  

There are two sister Apps. The larger App, which performs more tasks, is housed in the following repo https://github.com/bfopengradient/aisupervisor/tree/master.  

The smaller AI Supervisor_core App is contained in this repo. AI SUPERVISOR_CORE focuses on the core task of classifying contents of an email using deep learning ML libraries. It could be pointed at any electronic communication channel or document. Here it’s set up to read through gmail. You will need to alter security settings in the gmail account to allow the app to access a gmail account. 

Quick overview of App: I'm using a Distil Bert model for tokenization and downstream classification. This is a smaller faster and cheaper model to run than the full sized BERT model. Model weights are already trained and we are availing of transfer learning to focus on fine-tuning the heads of the model for the classification task at hand. Even with a ten trial hyperparameter search the training time is reduced to minutes albeit with a small amount of training data. The Optuna library was used for hyperparameter search. I could have gone deeper here and tested Hugging Face population based hyperparameter search but did not as this search using Optuna was sufficient at least at this stage.  

Apps were tested on Google cloud, AWS cloud and Streamlit share. The core app was stable on Google cloud and Streamlit share. The resources used for the core App on the Google App engine platform are contained in the app.yaml file. The Docker file required for Gcloud App engine is also contained in the repo. You will need more resources if you decide to deploy the larger App.  

The key file to work with is ais_app.py. Locally once your environment is set up with Streamlit you can deploy with the command " streamlit run ais_app.py . To deploy to Google App engine you will need to download the Google cloud SDK and once you set up your project in your Gcloud console you can deploy the app with the "gcloud app deploy" command. To deploy via Streamlit share cloud you can fork the repo and sign in to Streamlit share. It will give you an easy means to connect with your Github repos to deploy apps to the cloud. I found Streamlit share also really user friendly and a great environment to test the app after it was deployed.  BTW I was working with GitHub LFS but deliberately set up both apps to keep large files out of the repos and out of the way of you working with the apps in whatever cloud environment suits.    

 
 




