# Steps to create a new game

Before viewing this guide, we think you should have read the guide creating_a_new_sub_app.md. Especially the section about template.

## Creating your game

There is no template to make a game, as a game is not something that can be templated as the games can be widly different.

To make a new game, you'll need to make the game in a brand new scene. Feel free to add the back button scene from
template (and change its state if it doesn't fit what you want to do). The game doesn't need to have different difficulties,
however we strongly recommand it.

## Instructions

Your game probably needs to have an instruction playing when it is first launched. To do exactly that, you'll need to use the
instruction template (in shared), simply instanciate it in the Godot editor into your game scene. You'll need to create a JSON
file with 2 keys "sound" and "text" (see below) and an audio file ".ogg" with the text read aloud.
- "sound", has as value the path of the audio to be played
- "text", the text read in the audio file, basicaly a tutorial for your game
The JSON file needs to be located in the art/instruction folder (this is weird and should be changed in the future to separate
instruction by their app names).

Finally, to initiate the instruction simply call first thing in the \_ready() function, $instruction.setUp(nameOfYourGame: String)
with $instruction being the instruction scene instanciated. The function setUp(..) returns true if the instruction is playing and
false if the instruction is not playing (as if the user does not have the instruction activated). If you need to activate a timer
or something else, when your games start (which now means after the instruction finish playing, if the user has the instruction
activated) feel free to connect a function to the signal "on_Pass_Pressed" that instruction will emit when the instruction is
done (see artiphonie/memory/memory_game.gd for a clear example).

## Difficulties

To get which difficulty is selected for the game, you'll need call Global.get_arguments() which will return an array containing only
the name of the difficulty chosen (for exemple: "facile"). Then you process this information as you want. To just get the name of the
difficulty you simply do Global.get_arguments()[0].

## Game end shared scene

When you are done with the game, you will need to calculate the score (number of stars gained) of the player. Once this is calculated
you will need to change scene to the game_end.tscn scene (using Global.change_scene(_,_)). But before changing scene to game_end, you
will need to set an array of all the arguments you need to give game_end. Here's a guide of all the arguments needed for game_end,
keep in mind that game_end needs those arguments but they can be empty (null, 0, "") if they don't fit your game.
- args[0]: String -> Path to the scene of the game just played
- args[1]: Array -> Arguments to give to the scene of the game just
					          played, to replay it with the same difficulty
				            (or other if the arguments are used for something else)
- args[2]: String -> Name of the game just played
- args[3]: String -> Difficulty played
- args[4]: int -> Number of stars gained (score in a way)
- args[5]: int -> If the game played relied on time then this is used to
				          display the time in end game scene

## Game scoring reminder

If your games has difficulty, it is important to keep that in mind the difficulty when calculating the stars gained. For example,
"difficile" award 4 more stars than any other difficulty.

One last thing regarding the score, the game is not meant to punish the player but to encourage the player and keeping him/her
training on his problem (pronounciation for example). So what we decided, is that even if the player does everything wrong he is
still awarded 1 star at the end.

## Linking it to a playing scene (from the template in shared)

Now that your game is done, let's link it to your application.

In the playing scene of your app, call add_playing_element() of the template playing. This function will add your game (and its
difficulties) to the selection screen located in playing. Here's a detailled overview of the arguments needed (in the correct order):
- title: String -> Title of your game
- scenePath: String -> Path of your game scene
- iconPath: String -> Path of the icon of your game
- difficulties: Array -> Array contening the information related to the difficulty of your game, this cannot be left empty as the game needs
a difficulty to start. But if your game does not have difficulties, you could give in the array a difficulty called "jouer" which is considered
as a difficulty when creating the button to launch your game, but forgotten once in your game.
  - difficulties[i] -> [difficultyName: String, locked: bool:, lockedInfo: String]:
    -	difficultyName: String -> Name of the difficulty ("Easy", "Timed", "Impossible")
    -	locked: bool -> Is the difficulty available right now (If locked == false then the difficulty button will be grayed out and not pressable)
    -	lockedInfo: String -> If the difficulty is not available how to unlock it the selection screen (This is not used right now, so you can leave it blank)

Then everything is done, good job!
