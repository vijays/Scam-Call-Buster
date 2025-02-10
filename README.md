<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Scam Call Buster

Final project for the Building AI course.\
Elements of AI, University of Helsinki, Finland.

## Summary

This project aims to apply what we learn't in the Building AI course to real life needs.\
In the course, we understood concepts of modeling an AI which can flag potential spam emails.\
We can extend the same idea to flag potential scam telephone calls.

## Background

Cyber theft has been a major issue in this age of advancing technology.

Sr. Citizens and people who are not tech-savvy, have been particularly vulnerable to it. Many loosing not only a substantial amount, but some even loosing all of their life savings. In extreme cases, some becoming homeless or even committing suicide, due to mental and emotional, shock and trauma.

If they would have a "friend in AI" which would warn them in time, they could avoid becoming victims of such crimes. We will focus on identifying such frauds at the initial phase itself i.e. a phone call.

All scams over phone calls follow a predetermined theme, e.g. Gift Cards, Grand Parents, Remote Access, Digital Arrest, etc. Our app will try to check if the conversation falls under such fraud themes and alerts the user if potentially matching.

## How is it used?

The app will be installed on a mobile phone with access to internet.\
It will be activated when a call starts.\
If the number is a known suspect, it will flag it to the user.\
It will listen to the conversation and transcribe it as it progresses.\
Simultaneously, it keeps analysing the content for a potential fraud theme.\
If it finds a matching theme, it flags it to the user.

## Data sources and AI methods

The app listens to the conversation audio in chunks e.g. say 5 seconds and streams it to a service which transcribes it, i.e. **Speech-To-Text (STT)**, also known as **Automatic Speech Recognition (ASR)**. We can use 3rd party APIs for this e.g. Google Cloud STT. These chunks are appended to a data structure which builds as a conversation.

The app keeps analysing this conversation as it builds using AI / ML models, e.g. **Random Forest**. However, as mobile devices may not have the computational power needed in real time for this, we can implement this too on the cloud as our own service e.g. on **Amazon Web Services (AWS)**, and access it using an API.

If the app finds a matching theme with a high probability, it flags the same to the user.

## Challenges

* It might be difficult to implement advance models or perfect analysis in real time without slippage, e.g. gift cards context by known family slipping through as potential fraud.
* There is an **ethical concern** of hearing and transcribing what the other person is saying, without his / her knowledge.

## What next?

- Mobile OS' expose only mixed audio with both speakers. If we could focus on just the other person's transcription, it could improve scam detection. We could implement **Speaker Diarization** which is separating the individual speakers audio and also **Speaker Identification**, which is identifying the user vs speaker at the other end.
- It could speak to the scammer on behalf of the user using **Text-To-Speech (TTS)** and use algorithms to probe more about scammer's modus operandi, also saving user from trauma.
- The app could expand to include other sources of fraud initiation e.g. chats, emails etc.
- It could be trained to understand and work with more languages
- It could partner with government agencies and connect with their servers and APIs for the following:
  - add new suspect numbers and types of fraud themes in its analysis as they evolve.
  - provide information to user about how and where to report such frauds or can report them itself, directly to their servers.

## Acknowledgments

* [Online Scams: An overview of 19+ internet scams](https://us.norton.com/blog/emerging-threats/internet-scams) by Oliver Buxton at Norton
* [Economic Impact of Cyber Crime](https://www.csis.org/analysis/economic-impact-cybercrime) by CSIS - Center for Strategic & International Studies
* [What is Automatic Speech Recognition](https://www.assemblyai.com/blog/what-is-asr/) by Kelsey Foster at AssemblyAI
* [Introduction to Speech Processing](https://speechprocessingbook.aalto.fi/index.html) online book hosted by [Aalto University](https://www.aalto.fi), Finland / [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/); Authors: Tom Bäckström and Okko Räsänen and Abraham Zewoudie and Pablo Pérez Zarazaga and Liisa Koivusalo and Sneha Das and Esteban Gómez Mellado and Marieum Bouafif Mansali and Daniel Ramos and Sudarsana Kadiri and Paavo Alku and Mohammad Hassan Vali
* [Daisy the 'AI granny' speaks to scammer](https://youtu.be/bL9iJJICOLc) by Guardian News on YouTube
* Google and Gemini AI for general search and implementation related inputs
