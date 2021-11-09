AI Supervisor is an open source project from Open Gradient. Link to a video overview of AI Supervisor. https://videoais.ts.r.appspot.com

The video aims to summarize the functionality of the larger App. The classification model is trained on a tiny amount of data in the video but is still picking up a decent signal and has an F1 around .8 during training. The classification model is trained to pick up a client complaining to a broker/financial advisor about issues with the client's portfolio. Model performance should imrpove as more data is shown to the App. It did pick up a complaint about something else out-of-target-context in the gmail inbox which is not surprising given the tiny amount of data it has learnt from so far. The Summarisation and NER models are pre-trained and in this App are not set up to look specifically for any particular context, as such they should be used for general purpose tasks. In the video I dragged and dropped a PDF file containing minutes from the Australia Central Bank (RBA) which has nothing to do with conduct risk. In the PDF the Central Bank is talking about economic conditions and their respective interest date decision back in 2008.

AI Supervisor is an ML augmentation tool and was originally designed for conduct risk/surveillance staff within financial services. The idea was to cut down on the amount of time staff spent reading through electronic communications while looking for content of interest. The idea was to avail of machine learning to cut down on repetitive tasks and let the humans focus on things that machines cannot do as well.

There are two sister Apps. The larger App, which performs more tasks, is housed in the following repo https://github.com/bfopengradient/aisupervisor/tree/master. The video above shows the larger App being tested on Streamlit share.

The smaller AI Supervisor_core App is contained in this repo. AI SUPERVISOR_CORE focuses on the core task of classifying contents of an email using deep learning ML libraries. It could be pointed at any electronic communication channel or document. Here it’s set up to read through gmail. You will need to alter security settings in the gmail account to allow the app to access a gmail account. 

Quick overview of App: I'm using a Distil Bert model for tokenization and downstream classification. This is a smaller faster and cheaper model to run than the full sized BERT model. Model weights are already trained and we are availing of transfer learning to focus on fine-tuning the heads of the model for the classification task at hand. Even with a ten trial hyperparameter search the training time is reduced to minutes albeit with a small amount of training data. The Optuna library was used for hyperparameter search. I could have gone deeper here and tested Hugging Face population based hyperparameter search but did not as this search using Optuna was sufficient at least at this stage.  

Apps were tested on Google cloud, AWS cloud and Streamlit share. The core app was stable on Google cloud and Streamlit share. The resources used for the core App on the Google App engine platform are contained in the app.yaml file. The Docker file required for Gcloud App engine is also contained in the repo. Obviously you will need more resources if you decide to deploy the larger App.  

The key file to work with is ais_app.py. Locally once your environment is set up with Streamlit you can deploy with the command " streamlit run ais_app.py . To deploy to Google App engine you will need to download the Google cloud SDK and once you set up your project in your Gcloud console you can deploy the app with the "gcloud app deploy" command. To deploy via Streamlit share cloud you can fork the repo and sign in to Streamlit share. It will give you an easy means to connect with your Github repos to deploy apps to the cloud. I found Streamlit share also really user friendly and a great environment to test the app after it was deployed.  BTW I was working with GitHub LFS but deliberately set up both apps to keep large files out of the repos and out of the way of you working with the apps in whatever cloud environment suits.    

Any questions, best email is client.services@opengradient.com 
 




