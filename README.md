AI Supervisor is an open source project from Open Gradient. It is an ML augmentation tool and was originally designed for conduct risk/surveillance staff within financial services.


aisupervisor_core contains files for AI SUPERVISOR that focus on the core task of classifying contents of an email using deep learning ML libraries. Testing App on https://share.streamlit.io/bfopengradient/aisupervisor_core/ais_app.py


Quick overview of APP: using Bert model as starting point for tokenization and downstream classification. Transfer learning cuts down on app train time. App only fine-tunes the transformer models and even with hypreparameter search cuts training time down to minutes albeit with a small amount of training data. The Optuna library was used for hyperparameter search. I could have gone deeper here and tested Hugging Face population based hyperparameter search but did not as this search using optuna was sufficient at least at this stage.  

I have been testing nlp classification models for over five years now and tested models like word2vec, custom lstm/cnn models and now transformers. Tokenization has also evolved over that time and thanks to the team at Huggingface its possibe to avail of the state of the art tokenizers which make a big difference in terms of model performance. As the models have grow in size the amount of labelling required has gone down.  

Apps were tested on Google cloud , AWS cloud and streamlit share. The core app was stable on Google cloud and Streamlit. Google App engine was the easiest versus Cloud run and the resources needed to run the app via app engine are contained in the app.yaml file. 

Any questionns ,  please reach out of client.services@opengradient.com 


