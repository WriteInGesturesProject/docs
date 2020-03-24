# Analysis on TTS & STT

## Text To Speech (TTS)
Multiple software are available to handle this feature. Unfortunately, 
only a few of them are compatible with Godot 3.2  
We found two solutions :  
* The open source module : [Godot_TTS](https://github.com/bruvzg/godot_tts)
* The Google Speech API : [Godot_TextToSpeech](https://github.com/literaldumb/Godot-TextToSpeech)

Knowing that this application would be used by children with difficulties. We wanted this feature to be as best as possible.  
The purpose of this feature is to give a good base in order to the children to practice their pronunciation.

By making some tests, we found out that the Google Speech solution was the best one because the pronunciation is overall better that the Godot_TSS one.
Unfortunately, the Google Speech API is ony available for Android devices. 
So, we decided to put the developpement of the desktop version of the app in stand-by.

## Speech To Text (STT)
Likewise, multiple software are available to handle this feature.
But only a few of them are compatible with Godot 3.2  
We found some solutions :  
* Godot module based on Pocketsphinx : [Godot_STT](https://github.com/SamuraiSigma/speech-to-text)
* Google Speech Recognizer : [Godot_CustomSpeech](https://github.com/literaldumb/Godot-CustomSpeech)
