aisupervisor_core contains files for AI SUPERVISOR that focus on the core task of classifying contents of an email using deep learning ML libraries. The sister App also summarizes and extracts key entities. Link to the sister and larger App: https://github.com/bfopengradient/aisupervisor


Link to to video overview of AI Supervisor.  https://videoais.ts.r.appspot.com

The video hopefully helps illustrate some of the functionality of the larger App. The classification model is trained on a tiny amount of data in the video but is still picking up a decent signal and has an F1 around .8 during training. The classification model is trained to pick up a client complaining to a broker about issues with the client's portfolio. Model performance will pick up as more data is shown to the App. It did pick up a complaint about something else              out-of-target-context in the gmail inbox which is not surprising given the tiny amount of data it has learnt from so far. The Summarisation and NER models are    pre-trained and in this App are not set up to be trained to look for any particular context, as such they should be used for general purpose tasks.   
