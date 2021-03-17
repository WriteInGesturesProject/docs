# Application architecture

This file describes each element of the app architecture in godot.

## /art

This folder contains every images/sound/video needed in the app. Which means: 
* the avatar pictures
* the Borel Mainsonny images which represent the gesture linked to each phoneme drawn by Estelle Gillet Perret
* the sound for the instruction 
* the image of each item who may be bought in the shop 
* the image for each word in the default lists of words for which will be available without wifi (without needing to be connected to the database)

## /artiphonie

* **/goose_game** contains the scene of the goose game.
* **/learning** contains the learning scene of the sub app Artiphonie which used the *learning* template from */shared*. 
* **/listen_choose** contains the scene of the listen and choose game and the *card_listen_choose* template which represents a card for the game
* **/memory_game** contains the scene of the memory game and the *memory_card* template which represents a card for the game.
* **/playing** contains the scene whihc display the different game available in Arthiphonie and their difficulties, it used the *playing* template from */shared*.
* **/training** contains the training scene of the sub app Artiphonie which used the *training* template from */shared*.
* **/utility** contains the **/prononcing** folder which is used to display a word via different layout, via this the user can train by pronouncing the given word. It is used in the training section and in the lisetn and choose game.
* **artiphonie** is the home page of Artiphonie which used the *home* template from */shared*.

## /assets

This folder contains the assets which means :

* /artiphonie is the folder that contains the logo and icon of the app Artiphonie. For the future apps which will be added to this project a folder must be added with the name of the new app and it may contains the logo and icon too
* the **/fonts** used in the app, the main one is RAVIE.ttf
* the **/icons**
* the success and fail **/sound** which could be change as the failing sound may be harsh 
* the godot **/theme** used in the app

## /data

This folder contains the data of te app, which cannot be seen on godot's file system and which are:

* **/Lexique** which contains the script to convert the Lexique excel into a json file. The list of French words and their phonetic in the *Lexique383_ortho_phon.json* file and a version faster to open for the app but unreadable which is *Lexique383_ortho_phon_ligth.json*
* **/default_list** which contains the default lists of words, a general one with the most common words, then a list for 1, 2 and 3 syllables
* **/artiphonie** wich contain the text file with the content of the about button accessible from the Artiphonie sub app
* **/main_menu** which contain the text file with th content of the about button accessible in the main_menu
* **general.json** contains all the data related to the player with those parameters :
    * the player name
    * the number of *stars* he has
    * it's avatar *ethnicity*, the avatar were made in various skin color, this number will define which version of the avatar will be used for this player
    * the avatar *gender* to choose the right avatar image
    * if *instruction* equals true the first time the player goes to a new area in the app the instruction will be displayed, if its set to false it won't
    * the list of equipped items, only one item of each category may be equipped
    * the list of unlocked item, which mean all the items which were bough and may be equipped
    * the list of words which is a list of lists that the player will found in the app, the player can choose which list of words he wants to use for the games from this list of lists
* **phonetic_table.json** wich contains a dictionary with the phonetics codes used in the app as key and the real phonetics symbols as value.
* **phonetic_table_ressource.json** wich contains a dictionary with the phonetics codes used in the app as key and the phonetics code used for the resources (image/video) names as value.
* **phonetic_table_soted.json** wich contains the phonetics code, sorted by types.
* **shopItem.json** contain all the items available in the shop with those parameters : 
    * the item name which must be unique
    * it's price
    * it's type, if an item with a new type is added in the shopItem file it will be handle in the shop in the avatar space, so a new type of item can easily be added
    * the picture path which is actually the picture name as the code know where are stocked all the shop images


## /entity

This folder contains the Entities used in the app which are not linked to a scene in godot. 

* **Entity** is a class which is meant to be extended by all entities, this simplifies the process when handling entities.
* **Item** is the entity for all the items in the shop, every item of the same type has to have a different name.
* **Player** is what is used when using the app, by default if a player is not logged in, *Global* will load a default player where nothing can be saved (data/default.json).
* **Shop** contains all the item available in the shop, it is useful when viewing the shop on the avatar space.
* **Word** represent a word, with it's phonetic code and it's icon path.
* **Words** represent a list of words.

## /shared
This folder contains all the elements of the app that are shared between the different sub apps. They are templates used in the Artiphonie sub app and they will be useful for the other sub app in the future.
An instance of those shared templates can be added to scene in the sub app's folder.

* **/about** folder contains the *about* scene which displays the about informations, this scene can be used in different scenes of the app by adding the *abou_button* scene. 
* **/avatarspace** contains the avatar space template, which can be add to other scene like the main menu and home via the *avatar_button*. It contains the *avatar_space* scene who manage the player *pictureProfil* which is updated when a new item is equipped and the shop which is composed of the *item_type* and the *item*. 
* **/back** the back button template which is used in most of the other scene. It has 3 states: 
    * back: Return to the previous scene (which is the scene the player previously was on) so this is useful when we want to automate the process which is most of the time however it does not work when we don't want the player to goes back to the previous scene, for example in a game when the player go to the end game scene we want him to go back to the playing page which is not the previous scene.
    * home: Return to the home scene of the current app.
    * custom: Here you specify the path and the args given, and it could go anywhere.
* **/game_end** contains the template of the scene launch when a game is ended. This scene displays the number of stars earn during the game and allows the plyer to replay.
* **/home** contains the home template which is meant to be used to be the home screen of every application.
* **/instruction** contain the *instruction* template which is meant to be launch when the player enters a scene, it will provide an explanation of the interface to the user.
* **/learning** contains the *learning* scene which displays a *learning_element* for each word in the player's active list of words. A *learning_element* will display the word, an image of the word, the Borel Maisonny drawing related to this word phonetic code, a sound button which will tell the word and a mic button which will record the player pronouncing the word and will give him a feedback via a success/fail sound.
* **/list_selection** contains the *list_selection* scene which allows to change the list of words used for the game and the training section, it is composed of *list_element* which represent each list available. When a list is add for the player, a new *list_element* will be added in the *list_selection*. 
* **/loading** contains the loading scene which is used when the app takes time to be launched.
* **/main_menu** contains the scene for the main menu of the app, from which you can go to the different sub app. The *app_element* scene is a button which represents a sub app with its icon and logo, by adding a new instance of an *app_element* to the main menu, you can add a new app. 
* **/playing** contains the *playing* template on which you add *playing_element* which represent different games that the user can play. On each *playing_element* are added *element_difficulty* which display the different difficulties available for a game. 
* **artiphonie** is a file which contains the global constant only related to the sub app Artiphonie. A similar file could be created when a new sub app is added.

## Global
This file contains the globals variable and functions which can be used everywhere in the app.
## main
 This is the first scene to be launch when the player opens the app. On the first launch it will asked the user for permissions and init the textToSpeech and speechToText API.