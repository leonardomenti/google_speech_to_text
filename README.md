# Lab session #9: Using Speech to Text API for task automation
<!-- 
what is speech to text
technology we wanna use/teach

TASK 1


explain what is the google service about speech to text
sign up
api keys


let the user try the service through the browser (if it’s possible)	

TASK 2
the user have to send a file to the API
let the user use the streaming version


TASK 3
we provide to the user some audio-track and the user has to sent all of them to Google and collect the results(text) and then make analysis about them (most common word)

TASK 4
streaming (microphone) and create a script that through os python library do something in the terminal (like creating a file)

{
“create directory <name>” : mkdir <name>
“create file <name>” : touch <name>
“print <something>” : echo <something> 
}

Qxy: what are the voice messages talking about?
 -->

In this Lab session we would perform several experiments with the Google [Speech to Text API](https://cloud.google.com/speech-to-text). First we would transcribe an audio file to text. Then we would leverage that feature and try to come out with insights on the topic of the audio. Lastly, we would use the API to automate running commands from the terminal in a voice command fashion.


The Speech-to-Text service could be used to leverage several use cases:

- Transcribe content with accurate captions - could be used to compute subtitltes on recorded or live online meetings. Such example features could be seen on Zoom recording or live on Microsoft Teams.

- Enable the power of voice to create better user experiences -  Voice commands for personal robots or used for software capabilities helping people with different disability needs.

Speech-to-Text can use one of several machine learning models to transcribe your audio file. Google has trained these speech recognition models for specific audio types and sources. Moreover, there are more [languages generally supported](https://cloud.google.com/speech-to-text/docs/languages) by the API. In this Lab we would be using only English US examples, as it has been supported by the most models. 

### Task 1
You could continue working in the same project that you have created from [the previous lab](https://github.com/CCBDA-UPC/Assignments-2022/blob/origin/Lab08.md). Otherwise -  [create a new project](https://cloud.google.com/resource-manager/docs/creating-managing-projects). Remember to setup Billing for the project. 

When you are logged in the Google Platform, search for [Speech to Text API](https://console.cloud.google.com/speech) and enable the API. 



## Task 2
We would use the Open data Voice speech in America Engligh - https://www.voiptroubleshooter.com/open_speech/american.html. Download one of the files. 

You would need to use Service Account Keys. 
How to get the google service account credentials:
1. Access the Service Accounts page,
2. Go to the Key tab
3. Click on Add Key and select Create new key
4. Select JSON 
5. Save your JSON file on your local machine

Now we can start using the API locally. 

To authenticate locally, set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to point to your downloaded service account credentials before running this example:

```
export GOOGLE_APPLICATION_CREDENTIALS=/path/to/your/credentials-key.json
```

Install the Speech-to-Text API by running:
```
pip install --upgrade google-cloud-speech
```
