# Rapport Final ArtiPhonie

## Rappel du sujet
Ce projet porte sur le developpement d'une application mobile pour une utilisation sur tablette à usage des enfants atteints de trouble du langage.
Il nous a été proposé par une ortophoniste du CHU de Grenoble (Estelle Gillet-Perret).
Le but de cette application est d'aider les enfants à travailler leur prononciation de manière autonome, à la maison par l'intermédiaire de mini-jeux et de [la méthode Borel-Maisonny](https://fr.wikipedia.org/wiki/M%C3%A9thode_Borel-Maisonny).
Ce genre d'application existe déjà, malheureusement toutes les alternatives à cette application sont soit payante soit dans une langue différentes du français. C'est pourquoi nous créons une application gratuite et collaborative.

## Architecture technique
Notre application est une application mobile developpé avec le moteur de jeu [Godot Game Engine](https://godotengine.org).
Nous utilisons des fichiers *JSON* pour le stockage de nos données en local.  
Voici un exemple d'architecture pour une application Godot.  
![](https://github.com/WriteInGesturesProject/docs/blob/master/Images/Architecture.png)  

- Les [noeuds](http://docs.godotengine.org/fr/latest/getting_started/step_by_step/scenes_and_nodes.html#nodes) représentent les éléments fondamentaux dans la création de notre jeu. Il est équipé de plusieurs champs modifiable en fonction de son type. Il y a plusieurs type de noeuds : des labels, des boutons, des textures, des lecteurs multimédia etc...  
- Les [scènes](http://docs.godotengine.org/fr/latest/getting_started/step_by_step/scenes_and_nodes.html#scenes) sont des groupes de noeuds et permettent donc de modéliser un écran de jeu.  
- Les [scripts](https://docs.godotengine.org/fr/latest/getting_started/scripting/visual_script/getting_started.html) représentent toute la partie programmation du jeu que l'on va développé. Ce script est souvent rattaché à un noeud d'une scène et permet donc de controler son jeu. Les scripts sont très polyvalent étant donné qu'ils peuvent gérer d'une part la partie fonctionnel de l'application mais aussi la partie graphique de celle-ci.  Le langage de ces scripts est le langage propre a godot : [GDScript](https://docs.godotengine.org/fr/latest/getting_started/scripting/gdscript/gdscript_advanced.html). Godot est aussi capable de gérer le C# et le C++.
- Les données sont toutes les ressources que l'application utilise, il peut s'agir d'images, vidéos, sons, fichiers texte. Nous pouvons aussi remarquer que ces données peuvent être utilisées par les noeuds, mais aussi par les scripts.


## Réalisations techniques
L'application peut se diviser en deux parties. D'une part, nous avons la partie utilisé par l'enfant et d'une autre nous avons la partie consacré au spécialiste.


### La partie du spécialiste
C'est dans cette partie que le spécialiste va pouvoir adapter l'application en fonction des besoins de l'enfant. Il va être possible de créer des exercices basé sur des mots (avec certaines [structures syllabique](https://www.sfu.ca/fren270/phonologie/page4_7.html) ou alors avec un certain nombre de syllabe) extraient d'un dictionnaire inclus dans l'application. Le spécialiste peut aussi créé son propre exercice en y ajoutant les mots qu'il désire avec une image, des homonymes, etc..
Enfin, il est possible d'observé des statistiques par rapport au travail de l'enfant : nombre de réussite d'un exercice, nombre d'essai d'un mot, le mot le plus ou moins réussi, etc... Ces statistiques pourront également être utilisées par des chercheurs.


### La partie de l'enfant
C'est dans cette partie que l'enfant va pouvoir travailler tout en joueant. Pour ce faire il dispose de 3 menus, décrit ci-dessous. 

#### Le menu de jeu
Dans ce menu nous avons trois jeux à lui proposé :
- Le jeu de l'oie
- L'écoute et choisis
- Le jeu du Memory


#### Le menu d'entrainement
Ici l'enfant va pouvoir s'entrainer sur un certain thème :
- Les mots choisi par le spécialiste
- Les jours de la semaine
- Les chiffres
- Les couleurs


#### Le menu d'aide
Ce menu regroupe tous les sons de la langue française avec en plus une vidéo regroupant explication du geste Borel et prononciation du son correspondant.


## Technologies utilisées
- L'éditeur de scènes [Godot Engine](https://godotengine.org/)
- Le langage de programmation [GDScript](https://docs.godotengine.org/fr/latest/getting_started/scripting/gdscript/gdscript_basics.html)
- Versionning et partage de code [Git](https://git-scm.com/) et [GitHub](https://github.com/)
- Le [SDK Android](https://developer.android.com/studio)
- Les API Google [TextToSpeech](https://developer.android.com/reference/android/speech/tts/TextToSpeech) et [SpeechRecognizer](https://developer.android.com/reference/android/speech/SpeechRecognizer) inclus dans Android
- Le logiciel de montage photo [PhotoShop](https://www.adobe.com/fr/products/photoshop.html)


## Gestion de projet
Nous avons appliquer la méthode agile SCRUM, nous avions donc :  
- Un chef de projet
- Un SCRUM Master
- Des développeurs
- Des daily meetings
- Une division de notre emploi du temps en sprint d'environ 2 semaines, soit 3 sprints.

Nous avons utilisé les "issues" et "pull request" fournit par GitHub, non seulement pour faire de la revue de code mais surtout pour garder une trace de chaque tâche à effectuer et rapporter les éventuels problème au niveau du developpement de l'application.

## Outils
La collaboration s'est faite par Git et GitHub essentiellement. Nous avons également utilisés des outils de partage tel que Google Drive afin de créer la documentation de manière collaborative.
Pour faire en sorte que l'application soit la plus homogène possible nous avons nous même créé nos icones. Nous nous sommes inspiré de tuto sur internet et de certains logiciels de montage photo.


## Métriques logiciels
Nous avons utilisé le logiciel CLOC pour connaitre le nombre de ligne de code de notre projet.  
![](https://github.com/WriteInGesturesProject/docs/blob/master/Images/LOC.png)  
Nous pouvons donc voir que notre projet contient environ 20000 lignes de code et qu'il est majoritairement constitué de fichiers en JSON et en GDScript.
Au niveau du temps ingénieurs, nous avons calculé environ 35h par semaine de travail par developpeur. Nous obtenons donc un temps ingénieur d'environ 1235h.  
Le tableau suivant recapitule la répartition des lignes de code et des commits entre tous les membres du projet.
![](https://github.com/WriteInGesturesProject/docs/blob/master/Images/Commits%20repartition.png)

## Conclusion
Ce projet à été pour nous quelque chose de très positif sur beaucoup d'aspects.

Ce sujet nous a très fortement interéssé et motivé grâce à de nombreux points.
Tout d'abord, cette application n'est pas juste un projet scolaire, mais bien une demande de quelqu'un d'exterieur souhaitant utilisé ensuite le produit final dans un but d'aide à la personne, ici les enfants.
De plus, cette application est le premier projet sur lequel nous consacrons 100% de notre temps.
Enfin, cela sera une de nos premières applications déployer et utiliser par toute personne. 

D'autre part ce projet nous a fait en même temps découvrir une nouvelle technologie mais aussi donner notre première expérience dans le monde de l'open-source.

## Bibliographie
- Banque d'images libre de droit : [Pixabay](https://pixabay.com/fr/)
- Banque de pictogrammes libre de droit : [Soyvisual,](https://www.soyvisual.org/?photos=2&sheets=2&materials=2&material_content=All&material_activity=All&material_lang=All&app=2&app_content=All&app_activity=All&app_level=All&search=1&query=adjetivo)
[Sclera](https://www.sclera.be/fr/picto/copyright)
- Images Borel dessinées par Estelle Gillet-Perret
- Vidéo gestes Borel réalisées par Estelle Gillet-Perret
