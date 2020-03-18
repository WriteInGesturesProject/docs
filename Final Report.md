# Rapport Final ArtiGest

## Rappel du sujet/besoin et cahier des charges
Ce projet porte sur le developpement d'une application mobile pour une utilisation sur tablette à usage des enfants atteints de trouble du langage.
Il nous a été proposé par une ortophoniste du CHU de Grenoble (Estelle Gillet-Perret).
Le but de cette application est d'aidé les enfants à travailler leur prononciation de manière autonome, à la maison par l'intermédiaire de mini-jeux.
Ce genre d'application existe déjà, malheureusement toutes les alternatives à cette application sont soit payante soit dans une langue différentes du français.

## Architecture techniques
Notre application est une application mobile developpé avec le moteur de jeu [Godot Game Engine](https://godotengine.org).
Nous utilisons des fichiers *JSON* pour le stockage de nos données en local.  
Voici un exemple d'architecture pour une application Godot  
![](https://github.com/WriteInGesturesProject/docs/blob/master/Images/Architecture.png)  
- Les [noeuds](http://docs.godotengine.org/fr/latest/getting_started/step_by_step/scenes_and_nodes.html#nodes) représentent les éléments fondamentaux dans la création de notre jeu. Il est équipé de plusieurs champs modifiable en fonction de son type. IL y a plusieurs type de noeuds : des labels, des boutons, des textures, des lecteurs multimédia etc...  
- Les [scènes](http://docs.godotengine.org/fr/latest/getting_started/step_by_step/scenes_and_nodes.html#scenes) sont des groupes de noeuds et permettent donc de modélisé un écran de jeu.  
- Les [scripts](https://docs.godotengine.org/fr/latest/getting_started/scripting/visual_script/getting_started.html) représentent toute la partie programmation du jeu que l'on va développer. Ce script est toujours rattaché à un noeud d'une scène et permet donc de controler son jeu. Les scripts sont très polyvalent étant donné qu'ils peuvent gérer d'une part la partie fonctionnel de l'application mais aussi la partie graphique de celle-ci.  



## Réalisations techniques
Une des fonctionnalité de l'application est de pouvoir L'API Google du [TextToSpeech](https://developer.android.com/reference/android/speech/tts/TextToSpeech) & du [SpeechRecognizer](https://developer.android.com/reference/android/speech/SpeechRecognizer)


## Gestion de projet (méthode, planning prévisionnel et effectif, gestion des risques, rôles des membres ...)
Application de la méthode agile (SCRUM) : Chef de projet, Scrum Master, Daily meeting, Division en sprint, Utilisation des issues et des pull requests de GitHub.


## Outils (collaboration, CD/CI ...)


## Métriques logiciels : lignes de code, langages, performance, temps ingénieur (d'après vos journaux), la répartition des lignes de code et des commits en pourcentage entre les membres du projet ...)
Langage [GDScript](https://docs.godotengine.org/fr/latest/getting_started/scripting/gdscript/gdscript_advanced.html)



## Conclusion (Retour d'expérience)


## Transparent expliquant la démonstration


## Glossaire


## Bibliographie

