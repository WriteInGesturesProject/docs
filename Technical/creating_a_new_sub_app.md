# Steps to create a new sub app

 To add a new sub app to the main app, you must follow a few steps.

# What is a template and how use them

When building a new application you should be using the template that we have made in the shared directory (some are template other are just usefull shared scene).
A template is a scene which can be used to generate automaticaly something when given the correct arguments.

The template is meant to be intanciated in another scene, and this scene should setup the template.

For example in Artiphonie, we have a playing scene which contains the playing template. And when we go the artiphonie playing scene, the scene gives information about the games to the template and the template generate the view. 

# /new\_app and the new app home page
You must create a folder with the name of your app in which you will have all the element which will used the template available in */shared*. Your new app *home* scene must be named by the app name and must be placed directly in this folder (not in another sub folder).
This scene will contain the *home* scene template (and the *instruction* template scene if there is an instruction to explain it). in this scene script you will have to launch the **setup** function from the *home* template whith those following arguments:
 * the path for the **learning** scene of your app
 * the path for the **training** scene of your app
 * the path for the **playing** scene of your app
 * the name of your app

# Global
In the *Global* file you must add to the array **apps** a String with the name of your app.

# Main menu
If you have added your app's name in the *apps* array of *Global* as said in the previous step, your app will be automatically added as a button on the main menu. But you need to add in the **/asset** folder a folder with the name of your app which will contain the logo and icon of your new app.

# About content
You can personalised the about content of your sub app by adding a folder in */data* with the name of your app and with a file named **aboutContent.txt** in it.

# Playing scene and games
For the games there are no templates as the game may be different in each sub app. But you can follow the tutorial [Steps to create a new game](https://github.com/WriteInGesturesProject/docs/blob/master/Technical/creating_a_new_game.md) to add a new game.

The other sections of the app have templates in **/shared** which will allow you to easily add element to your new app. 
 
