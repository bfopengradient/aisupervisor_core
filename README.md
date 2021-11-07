AI Supervisor is an open source project from Open Gradient. It is an ML augmentation tool and was originally designed for conduct risk/surveillance staff within financial services. There are two apps. The larger app, which performs more tasks is housed here https://github.com/bfopengradient/aisupervisor/tree/master

The smaller core app is contained in this repo.
aisupervisor_core contains files for AI SUPERVISOR that focus on the core task of classifying contents of an email using deep learning ML libraries. Testing App on https://share.streamlit.io/bfopengradient/aisupervisor_core/ais_app.py

Quick overview of APP: I'm using a Bert model as a starting point for tokenization and downstream classification. The Transfer learning cuts down on overall App training time. The App thus only fine-tunes the transformer models and even with hyperparameter search the training time is reduced to minutes albeit with a small amount of training data. The Optuna library was used for hyperparameter search. I could have gone deeper here and tested Hugging Face population based hyperparameter search but did not as this search using optuna was sufficient at least at this stage.  

Apps were tested on Google cloud , AWS cloud and Streamlit share. The core app was stable on Google cloud and Streamlit. Google App engine was the easiest versus Cloud run and the resources needed to run the app via app engine are contained in the app.yaml file.  

To deploy to Google cloud I found Google cloud SDK really helpful. Deploying the app was as easy "gcloud app deploy" once the app was setup on your Google cloud consol. I did face websocket issues with cloud run and streamlit but not with app engine. I found streamlit share also really easy to work with.  

Any questions ,  please reach out of client.services@opengradient.com 




