Gérer un projet de développement avec Visual Studio
=
 
# Introduction au cours :
 
Vous n’avez jamais travaillé sur Visual Studio, mais vous aimeriez apprendre à l’utiliser pour travailler sur vos projets de développement ?
Ce cours est fait pour vous ! 

Ce cours permet d'avoir une meilleure compréhension de ce que permet de faire Visual Studio et s’adresse à quelqu’un qui n’a jamais travaillé sur cet environnement de développement. Grâce à ce cours, vous allez apprendre à comment créer et manipuler un projet un développement.

Ce cours est découpé en 3 parties :
- Mettez en place votre projet : le premier cours a pour objectif de vous donner une présentation générale de Visual Studio, comment choisir la version qui vous correspond et comment l’installer,
- Créez et gérez un nouveau projet : dans ce cours nous allons s’intéresser à la création et l’ajout des outils nécessaires pour bien démarrer avec Visual Studio,
- Gérez le cycle de vie d’un projet avec Git : Cette partie du cours permet d'avoir une meilleure compréhension de l’outil de gestion de version Git. Nous allons voir ensemble comment récupérer un projet existant depuis GitHub et comment le manipuler depuis Visual Studio.

Ça donne envie, n’est-ce pas ? Alors allons-y !

# Partie 1  : Quel est l'intérêt d'un IDE ?

## 1.1 Programmer sans utiliser d'IDE

Vous travaillez comme programmeur dans une grande entreprise de développement de logiciels. Une anomalie dans un fichier du code source de votre logiciel vous a été reportée, vous êtes en charge de le régler.

Attention, votre logiciel est massivement utilisé et ce bogue bloque tout son fonctionnement chez tous vos clients ! Vous devez donc le résoudre le plus vite possible, en à peine quelques minutes, pour débloquer la situation.

Mais pour corser la situation, ajoutons une petite contrainte à ce challenge... Essayons de résoudre le bogue en n’utilisant qu’un éditeur de texte simple, le plus simple que vous ayez. Voici à quoi ce code ressemblerait.

### image

Code source du fichier :

````using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace StartWithVisualStudio.Models
{
	public class OrderInfo
	{
    	int orderID;
    	string customerId;
    	string country;
    	string customerName;
    	string shippingCity;
    	public int OrderID
     	
        	get { return orderID; }
        	set { orderID = value; }
    	}
    	public string CustomerID
    	{
        	get { return customerId; }
        	set { customerId = value; }
    	}
    	public string CustomerName
    	{
        	get { return customerName; }
        	set { customerName = value; }
    	}
    	public string Country
    	{
        	get { return country; }
        	set { country = value; }
    	}
    	public string ShipCity
    	{
        	get { return shippingCity; }
        	set { shippingCity = value; }
    	}
    	public OrderInfo(int orderId, string customerName, string country, string customerId, string shipCity)
    	{
        	this.OrderID = orderId;
        	this.CustomerName = customerName;
        	this.Country = country;
        	this.CustomerID = customerId;
        	this.ShipCity = shipCity;
    	}
	}
}
````

Vous pouvez télécharger le code ici, ouvrir le fichier avec un éditeur de texte et essayer de résoudre très rapidement l’anomalie par vous-même.

(i) Sous Windows ou Linux, vous pouvez utiliser le logiciel BlocNote, ou son équivalent TextEdit sous Mac..

Alors ? Vous y arrivez ?

! “Oh mon dieu mais je n’y vois rien dans ce pavé de lettres dans tous les sens !”

Comme vous pouvez le remarquer, il y a beaucoup de code dans ce fichier ! Pas étonnant que vous ayez du mal à détecter rapidement l’endroit exact de l’anomalie. Et vous devez faire tout ça en un rien de temps car toute la plateforme dépend de vous !

En effet, un éditeur de texte tel que celui-ci est très limité pour un programmeur. Posez-vous la question, qu’est ce que vous auriez aimé avoir comme fonctionnalité pour y voir plus clair ? Quels sont les points qui rendent la résolution de bogues extrêmement difficile sur NotePad++ ?

Allez ! Prenez une feuille et notez ce que vous pensez de Bloc-Notes comme outil de développement. Quelles idées d'améliorations aimeriez-vous avoir dans un logiciel de développement ?  Qu’est ce qu’il vous sera utile pour programmer plus facilement ?

Dans le prochain chapitre, nous verrons comment Visual Studio pourra nous aider à résoudre tous ces points de difficultés.

## 1.2 Programmer avec un éditeur de code

Visual Studio Code est un éditeur de texte avancé par rapport aux autre éditeurs standards. C’est une édition de la suite Visual Studio mais elle a pour particularité d’être open source et gratuite. Le code source du logiciel est même disponible sur GitHub.

Maintenant, utilisons Visual Studio Code pour lire notre fichier et voyons s’il résout les points de difficulté que nous avons rencontrés dans le chapitre précédent. Sera-t-il possible de résoudre notre bug avec ce nouveau logiciel ?

### image

Vous pouvez télécharger la dernière version de Visual Studio Code ici. Son installation est très simple, je vous fais confiance pour vous débrouiller ! Le fichier code que bogué est disponible ici. 
Vous pouvez alors ouvrir le fichier dans Visual Studio Code afin de tester s’il est plus facile de détecter le bogue qu’avec un simple éditeur de texte. Jugez par vous-même !

Alors ? C’est plus clair ?

!“Woooow les jolies couleurs !”

La vraie différence, comme vous pouvez la voir, est la coloration syntaxique qui rend le code plus lisible et bien organisé. Nous voyons aussi que certaines erreurs sont repérées directement par Visual Studio Code. Ces fonctionnalités sont assurées par un analyseur syntaxique.

[Balise info] Un analyseur syntaxique est un logiciel, ou fonctionnalité d’un logiciel qui reconnaît la syntaxe du texte en l’interprétant comme un langage déterminé.

En plus d’un analyseur syntaxique, Visual Studio Code est équipé de IntelliSense qui permet de faire de l’auto-complétion intelligente afin d’accélérer la saisie du code. 

De plus, Visual Studio Code offre la possibilité d’indenter automatiquement votre code. Ceci s’avère très pratique afin d’accélérer la rédaction et éviter les erreurs d’indentation !

Enfin, toute la puissance de Visual Studio Code réside dans les extensions qu’on peut y installer afin de bénéficier de tout un tas de fonctionnalités très utiles ! [exemples ?]

### Un peu plus d’infos sur Visual Studio Code :

Visual Studio Code est un éditeur de code dit cross-platform, c’est à dire qu’il supporte plusieurs langages comme C#, C/C++, Go, Python, et d’autres. Il est open source et gratuit. Dès sa sortie en avril 2015, il s’est imposé face à d’autres logiciels open source de référence, notamment NotePad++ et WebStorm.

Visual Studio Code dispose d’un moteur de gestion de code puissant comme celui de l’édition payante de Visual Studio. Il est disponible à la fois pour Windows, Linux et Mac.
 
Le but de cette édition est de créer des petites applications qui ne demandent pas beaucoup d’effort dans leur réalisation ou de faire de simples modifications dans des fichiers de code source. 

## 1.3 Découvrez le pouvoir des IDE

Mis à part Visual Studio Code, le reste de la suite logiciels Microsoft Visual Studio propose des IDE. Un IDE — Integrated Development Environment (Environnement de Développement Intégré) est un ensemble d’outils permettant de faciliter le travail des développeurs d’applications. Il permet non seulement d’écrire du code, mais aussi de déboguer, tester, compiler et publier une application et d’autres nombreuses fonctionnalités qui contribuent au développement d’une application.

Avec Visual Studio, vous pouvez créer plusieurs types d'applications, que ce soit des applications web, mobiles, des jeux. Vous avez la possibilité de créer :
- des sites web et des services web basés sur ASP.NET et WCF,
- des applications pour des plateformes variés comme sur Azure, Office, SharePoint et Hololens,
- des jeux et des applications graphiques avec Unity,
des applications multiplateformes qui visent Windows, iOS et Android.

Vous doutez encore de la puissance de Visual Studio ? Pas de souci !
Voici quelques exemples des applications qui ont été développées sur Visual Studio :
- Umbraco CMS, une plate-forme de gestion de contenu open source. Elle est écrite entièrement en C# et ASP.NET,
- Halo, le jeu qui a fait un grand succès sur le secteur du jeux vidéo et qui a façonné le succès de la console de jeux Xbox
- Foursquare, l’application qui a surpassé Google Maps dans le pointage grâce à la géolocalisation. Cette application a été développée avec Xamarin.

De plus, Microsoft a mis en place plusieurs éditions de Visual Studio IDE et chacune a ses particularités.

[Balise question] Mais comment choisir la bonne édition pour mener à bien vos projets ? 
Ne vous inquiétez pas, rendez-vous au prochain chapitre pour avoir la réponse ! ;)

## 1.4 Choisissez votre IDE selon vos besoins

Microsoft a su faire de Visual Studio l’un des IDE les plus connus dans le monde de l’informatique. Il est devenu l’outil favori des développeurs. 
Suite à cette réussite, Microsoft a décidé de proposer plusieurs éditions de cette solution afin d’adapter l’offre aux différents types de structures qui les utilisent, aux types d’applications et aux budgets.
 
Dans ce chapitre, nous allons découvrir ensemble ces différentes éditions et leurs avantages. C’est parti !
 
### Visual Studio Community :
L’édition Community est gratuite et disponible sur Windows et macOS. Elle s’adresse aux étudiants et même aux développeurs individuels (mais pas aux grandes entreprises ou organisations). Vous pouvez donc l’utiliser pour des projets open source. Elle contient tous les outils nécessaires pour réussir un projet informatique.

Cette édition de Visual Studio est flexible. Elle permet de travailler avec plusieurs langages de programmation comme C#, F#, C++, HTML, TypeScript, JavaScript et Python. Vous pouvez aussi utiliser plusieurs outils de développement comme Angular, React, Bootstrap et beaucoup plus encore. Cela vous permettra de créer des applications pour différents types de projets (web, mobile, cloud...).

En revanche, l’utilisation de l’édition Community n’est pas autorisée pour les entreprises de plus de 250 développeurs, ou celles qui possèdent un chiffre d’affaire de plus d’un million de dollars.

### Visual Studio Professional :
Cette édition embarque toutes les fonctionnalités de l’édition Community. Elle est destinée aux entreprises et aux organismes qui ont des revenus importants, ce qui la rend payante. Elle est fournie avec des outils et services de développement professionnels. Cette version est disponible sur Windows et macOS.

### Visual Studio Enterprise :
Il s’agit de la version ultime de Visual Studio. Elle est payante et destinée à des équipes de toutes tailles avec des exigences qualité importante dans leurs projets.
Avec cette édition, vous aurez accès à des outils qui permettent de :
- Tester la qualité et la performance de votre application,
- Effectuer des tests plus poussés pour votre code,
- Créer des tests d’interface graphique automatisés,
- Gérer l’architecture et la modélisation de votre application,
- Etc.

Cette version est également disponible sur Windows et macOS.
 
[Bulle interrogation] Super, il y a plein de choix ! Mais… Quelle version dois-je utiliser pour mon projet, moi ? [Fin de bulle interrogation]

Tout dépend de votre besoin. Si vous n’avez pas un objectif commercial et que vous voulez juste utiliser Visual Studio pour réaliser des projets personnels, je vous recommande d’utiliser la version Community.
 
Si vous êtes dans un cadre professionnel, je vous recommande d’utiliser la version professionnelle qui vous offre plus d’outils pour bien mener votre projet.
 
En revanche si vous souhaitez utiliser Visual Studio pour effectuer des tests de performance et de qualité ou pour gérer l’architecture de votre projet, la version Entreprise est faite pour cela.

Avant de choisir une version, il faut bien étudier la situation dans laquelle vous êtes :
- Est-ce qu’il s’agit d’un projet personnel ou professionnel ?
- Vous êtes un développeur ou un architecte ?
- Quel est le budget de votre projet ?
- Est-ce que vous êtes capable de payer la version payante ?

Tout ceci entre en jeux dans le choix de votre version de Visual Studio.

Voici un lien fourni par Microsoft qui offre une comparaison exhaustive de toutes les éditions de Visual Studio : https://visualstudio.microsoft.com/fr/vs/compare/.
 
Pour la suite de notre cours, nous allons choisir l’édition Community puisqu’elle est gratuite, embarque toutes les fonctionnalités de base pour réaliser un projet professionnel et surtout pour éviter que Microsoft nous pénalise ! Dans la prochaine partie, nous allons enfin installer le logiciel et apprendre à l’utiliser pour pouvoir réaliser votre projet !

C’est la fin de cette première partie de présentation de Visual Studio et ses différentes éditions. Vous devriez maintenant être capable de
- Comprendre qu’est ce qu’un IDE et quels sont ses avantages par rapport à un simple éditeur de texte.
- Choisir, de manière avisée, quelle édition de Visual Studio utiliser pour votre projet.

# Partie 2  :  Découvrez Visual Studio Community

[Bulle info] Comme nous avons dit dans le chapitre précédent, nous allons installer l’édition Community de Visual Studio pour commencer à découvrir ce qu’est un environnement de développement. Vous êtes prêt ? C’est parti !

## 2.1 Téléchargez et installez votre environnement
 
Notez bien, avant de commencer votre téléchargement, que vous devez choisir l’édition qui sera compatible avec votre système d’exploitation (Windows / Mac OS). Dans ce cours, nous allons travailler sur Windows.
 
Afin de pouvoir télécharger la dernière version de Visual Studio Community pour Windows, cliquez sur le lien suivant :
https://visualstudio.microsoft.com/fr/downloads/.

### image

Puis cliquez sur « Windows » et ensuite sur « Téléchargement gratuit » de l’édition Community.
Si vous disposez d’un système d’exploitation sous macOS, cliquez sur « macOS » puis sur « téléchargement » de l’édition Community pour Mac.

### image

Et voilà, vous disposez maintenant du fichier du programme d’amorçage de Visual Studio.

### image
 
Afin de pouvoir installer Visual Studio Community, vous devez exécutez le fichier du programme d’amorçage que vous avez téléchargé.

### image

Dès l’exécution, vous aurez un message vous demandant d’accepter les termes du contrat de licence de Microsoft.
 
Dès que vous cliquez sur « Continuer », une nouvelle fenêtre s’ouvre pour vous indiquer que Visual Studio Installer est en train de s’installer. Normalement, vous avez aussi remarqué que le téléchargement de fichiers se fait automatiquement.

### image
 
Une fois le programme d’installation installé, une nouvelle fenêtre s’ouvre. Elle se compose de quatre parties :
- Charges de travail : qui permet de choisir sur quel type de projet vous voulez travailler.

### image

- Composants individuels : ici vous avez la possibilité de choisir les composants et outils de développement que vous voulez utiliser. Il est préférable que vous sélectionniez la charge de travail dont vous avez besoin et les composants seront sélectionnés automatiquement. Si vous sélectionnez des composants par plaisir, Visual Studio va consommer plus de mémoire et d’espace disque. Donc, sélectionnez uniquement ce que vous en avez besoin.

### image

- Modules linguistiques : Microsoft a mis à notre disposition plusieurs modules linguistiques supplémentaires à installer sur Visual Studio. Ce qui peut aider plusieurs développeurs. Par défaut c’est la langue de votre système d’exploitation.

### image

- Emplacement d’installation : C’est la dernière phase avant l’installation et elle n’est pas obligatoire. Vous pouvez choisir le répertoire d’installation de Visual Studio Community dans l’emplacement de votre choix. Je vous conseille de créer un répertoire dans lecteur autre que le « C » qui est dédié au système d’exploitation afin de ne pas le ralentir.

### image

Vous avez le choix entre deux options pour installer votre EDI :
- Installer pendant le téléchargement.
- Tout télécharger, puis installer.
 
Ensuite, une fois que vous avez terminé à configurer votre installation. Vous pourrez démarrer l’installation de Visual Studio Community en cliquant sur « Installer ».

### image

Enfin, l’installation est en cours ! Cliquez sur le bouton "Lancer" : vous avez fini l'installation de Visual Studio Community.

Voilà ! Nous arrivons à la fin de la deuxième partie. Nous avons vu ensemble les étapes nécessaires à l'installation d'une édition de Visual Studio.

Maintenant que nous avons découvert ce que c’est Visual Studio et de ce qu’il permet de faire, nous allons passer en action. Dans la partie suivante nous allons voir comment créer un nouveau projet et installer les outils nécessaires au développement de notre première application.

## 2.2 Découvrir le GUI

Avant de passer à la création d’un nouveau projet, nous allons voir ensemble les différents types projets possibles que nous pouvons créer. Ensuite, nous allons créer un projet pour continuer la suite du cours.

Par défaut, Visual Studio ne propose pas beaucoup de projet. C’est normal car vous devez vous-même installer le type de projet sur lequel vous allez travailler.
 
Maintenant, nous allons voir ensemble comment installer un nouveau type de projet.
 
Si vous vous rappelez bien, nous sommes déjà passés par cette étape lors de l’installation de Visual Studio. Nous avions la possibilité de choisir plusieurs de projets. Vous avez oublié ! Pas de souci, voici un petit rappel :

### image

Ici j’ai choisi plusieurs types de projets et après avoir terminé l’installation, Visual Studio me propose plusieurs projets que je peux créer.

### image

Si vous voulez installer un autre logiciel indépendamment de l’installation de Visual Studio, vous devez lancer le logiciel « Visual Studio Installer » et cliquez sur « Modifier ».

Ensuite, choisissez le composant que vous voulez installer.

Dans notre cours, nous allons créer une application « WPF » qui est une application Desktop. Pour ce faire, choisissez « Développement .Net Desktop » et puis cliquez sur « Modifier » pour lancer l’installation.
 
Une autre méthode est possible pour installer des composants sur Visual Studio, c’est la méthode classique. Il faut télécharger le package d’installer par soi-même et l’installer.
 
Une fois que l’installation est terminée, nous pouvons créer notre première application sur Visual Studio.

## 2.3 Créez votre premier projet

Dans cette étape, nous allons créer une application WPF qui permet d’afficher des données dans une grille. Nous allons utiliser une extension qui s’appelle Syncfusion qui est une suite d’outils et des solutions customisées pour différents plateformes (WPF, ASP .Net...). Syncfusion permet d’accélérer le temps de développement de vos projets grâce à ses composants prédéveloppés.
 
Dans notre cas nous allons utiliser le composant Sf.Data.Grid qui permet d’afficher les données d’une manière dynamique et interactive. Pour cela, nous allons d’abord créer un projet, puis je vous montrerai comment installer l’extension Syncfusion.
 
Commençons par créer un nouveau projet en cliquant sur le menu Fichier > Nouveau > Projet.

### image

La fenêtre de création de nouveau projet s’ouvre et nous avons plusieurs choix. Nous allons choisir Visual C# - Windows Desktop (puisque WPF est une application bureau) pour créer une Application WPF.
 
Si vous avez bien marqué, il y a plusieurs modèles de création de projets plus ou moins compliqués.  Un modèle c’est ce qu’on appelle en anglais « template ».  Il y a des modèles qui sont vides et ne contiennent que le code nécessaire afin de pouvoir lancer l’application dès sa création. Et il y aussi des modèles qui sont déjà configurés afin d’accélérer le développement. Donc le choix du modèle dépend toujours de vos besoins. Dans notre cas, nous allons créer une application Vide afin d’apprendre comment bien démarrer avec un projet vide.
 
Concernant le nom du projet, Visual Studio met par défaut un nom, mais je vous conseille de le changer afin de le rendre plus significatif.

### image

Ensuite, cliquez sur “OK” afin de confirmer la création de votre nouveau projet. Il reste qu’à installer les outils nécessaires pour le développement de notre application. Alors rendez-vous dans partie suivante du cours.

## 2.4 Customisez votre environnement

Nous avons évoqué ensemble dans la partie précédente l’extension Syncfusion que nous devons d’intégrer sur Visual Studio, mais avant tout nous devons savoir ce que c’est une extension.

Une extension est un module complémentaire qui permet de personnaliser et améliorer l’utilisation de Visual Studio en ajoutant de nouvelles fonctionnalités. Elle peut être parfois simple ou complexe, mais son objectif principal est d’augmenter la productivité et de faciliter le développement. 

Grâce au système de gestion des extensions de Visual Studio, nous pouvons installer plusieurs extensions pour ajouter de nouvelles fonctionnalités à Visual Studio afin de les exploiter après dans nos projets.

Maintenant, que nous nous compris ce que c’est une extension, nous pouvons commencer l’installation de notre extension Syncfusion. Voici comment faire :
 
Cliquez sur « Extensions et mise à jour » du menu « Outils ».

### image

Une nouvelle fenêtre s’ouvre contenant les extensions installées et les extensions à installer. Elles sont toutes regroupées selon leur type. Pour installer une nouvelle extension, il faut cliquer sur « En ligne ». Cliquez sur WPF afin d’afficher les extensions qui ciblent notre type de projet. Afin d’éviter de passer trop de temps à chercher l’extension, faites une recherche sur « Syncfusion » et vous aurez toutes les extensions de « Syncfusion » dédiées au développement WPF.

### image

Maintenant, cliquez sur « Télécharger ». Une nouvelle s’ouvre dans votre navigateur et vous oriente directement à la page officielle de « Syncfusion ». Cliquez sur « Products » et choisissez « WPF ».

### image

Une nouvelle page s’ouvre pour vous montrer les contrôles de Syncfusion dédiés aux projets WPF. Cliquez sur « Download free trial » pour pouvoir les télécharger.

### image

Maintenant, remplissez le formulaire pour créer un compte Syncfusion (gratuit) et cliquez sur « Download for free ».

### image

Maintenant, choisissez comment vous voulez installer l’outil Syncfusion et cliquez sur « Download ».

### image

Une fois que le téléchargement est terminé, lancez l’exécutable que vous avez téléchargé. Ensuite, mettez les identifiants du compte que vous venez de créer et cliquer sur « Installer ».

### image

Encore une étape à faire et nous pouvons utiliser Syncfusion, un peu de patience.

En fait, ce qu’il nous reste à faire, c’est d’intégrer l’extension de Syncfusion dans notre projet.

Voici les étapes nécessaires :
- Dans l’explorateur de solutions, faites un clic droit sur « Références »

### image

- Cliquez sur « Ajouter une référence »

### image

- Dans la nouvelle fenêtre qui apparaît, cliquez sur « Assemblys » et faites une recherche sur « Syncfusion.SfGrid.WPF » (c’est la référence du composant graphique qu’on va utiliser dans l’application). Ensuite, cochez la dernière version que vous aurez dans la liste et cliquez sur « OK»

### image

Faites la même chose pour les références suivantes :
- Syncfusion.Data.WPF
- Syncfusion.Shared.WPF

Et le tour est joué, vous avez maintenant installer une extension sur Visual Studio et vous l’avez intégré dans votre projet. Félicitation !

Avant d’entrer dans les détails, il faut savoir ce que c’est un package Nuget. C’est un gestionnaire de package qui permet d’optimiser l'intégration d’une librairie  externe sur Visual Studio.  Grâce à ces outils, il permet de :
- automatiser le téléchargement,
- installer la librairie,
- assurer sa mise à jour,
- la configuration et l’intégration dans les projets Visual Studio.

Il est disponible sous forme d’une extension qu’on peut installer sur Visual Studio. Maintenant, vous allez me dire encore un outil  à installer ? 

La réponse est non. A partir de la version 2015 de Visual Studio, Nuget est par défaut intégré dans votre environnement de développement. Aucune manipulation de votre part est nécessaire.

Comme je vous ai dit, le but de Nuget est de pouvoir installer rapidement une librairie externe sur Visual Studio et d'intégrer sa référence à votre projet. voyons voir comment ;)

En fait, il existe deux méthodes pour installer une librairie externe avec Nuget. Soit avec une ligne de commande dans la Console du Gestionnaire de package Nuget soit directement depuis le Gestionnaire de package Nuget et les deux méthodes effectuent les mêmes actions (téléchargement, installation, suppression…).

Commençons par les lignes de commande!
Afin de pouvoir afficher la console du Gestionnaire de package, cliquez sur " Gestionnaire de Package NuGet” du menu Outils puis sur “Console du Gestionnaire de package”.

Maintenant, que nous avons terminé l’installation des outils nécessaires à notre projet, nous allons procéder au développement de l’application. Vous êtes prêt ?

### image

Une nouvelle fenêtre s’affiche en bas de Visual Studio comme le montre la capture suivante :

### image

Au début de notre projet, nous avons installé l’extension de Syncfusion. Maintenant nous allons voir comment l’installer depuis la console. 

Pour installer un package Nuget il suffit de tapez :
````
Install-package {nom du package}
````
et le tour est joué.

Dans notre cas ça va être cette ligne : 
````
Install-package Syncfusion.SfGrid.WPF
````

Voici une capture d’écran qui montre le déroulement de l’installation de Syncfusion depuis la console :

### image

Si vous regardez bien les traces d’installation du package de Syncfusion, vous allez remarqué que NuGet s’est occupé de tout. Il a géré l’indépendance entre Syncfusion et votre plateforme, le téléchargement des packages, l’installation et l’intégration dans votre projet.

Il vous donne même le temps écoulés pour toute l’opération qui d’ailleur n’a pas dépassé une seconde. Alors ! Vous en pensez quoi ? C’est plus rapide ou plus facile ? Moi je dirai les deux ;)

Voyons ensemble la deuxième méthode. Sélectionnez votre projet dans l’explorateur de solutions, faites un clic droit et cliquez sur “Gérer les packages NuGet”.

Une nouvelle fenêtre apparaît et affiche :
- la liste de packages que vous pouvez installer,
- la liste des packages installés,
- la liste des packages à mettre à jour.

Pour installer le package de syncfusion rapidement, il suffit de faire une recherche sur “syncfusion sfgrid” dans la liste des packages à installer (Parcourir). Sélectionnez le package “Syncfusion.SfGrid.WPF” et cliquez sur “Installer”.

### image

Et c’est terminé ! Vous avez installé Syncfusion sur Visual Studio et vous l’avez intégré dans votre projet ;)

Vous avez vu maintenant la différence entre chercher et installation par vous même une librairie externe et le fait de l’installer avec NuGet ? 

Personnellement je préfère le gestionnaire des packages NuGet, c’est rapide et plus fiable. En plus de ceci, je suis plutôt confiant de la librairie que j’ai installé car je suis sûr que j’utilise une librairie compatible avec ma plateforme de développement et que je ne me suis pas trompé de librairie. En plus de tout ça, le gestionnaire me donne plus d’informations sur la librairie à installer et me donne la possibilité de faire plusieurs actions, comme la suppression et la mise à jour.

## 2.5 Utilisez les raccourcies

Je suis sûr lorsque vous avez manipulé votre environnement de développement, vous avez sûrement vu quelques caractères à droite des commandes. Par exemple lorsque vous avez créé un nouveau projet.

En fait, il s’agit d’un accès rapide à la commande que vous souhaitez exécutée. Au lieu d’aller chercher la commande et que vous perdez dans les menus et les fenêtres, vous n’avez qu’à les connaître par coeur. Vous avez remarqué ! C’est toujours une question de temps. Visual Studio pense à tout, il essaye toujours de nous faire gagner du temps.

Il existe une centaine de raccourcis et il sont regroupés par fonctionnalités. 

Non ! j’ai pas dit qu’il faut les connaître tous, il suffit juste d'apprendre que les raccourcis les plus utilisés et les plus récurrents dans vos projets. Vous êtes soulagés ! ;)

Voici la liste des raccourcis que j’utilise presque tous les jours :

En modification :
- CTRL + SHIFT + F : rechercher dans tous les fichiers
- CTRL + F3 : recherche le terme sélectionné (F3 pour voir le terme suivant, etc.)
- CTRL + , : accéder directement à une classe ou à un fichier en tapant son nom (ou un morceau de son nom)
- CTRL + K + D ou CTRL + E + D : réindenter le fichier courant
- CTRL + K + C ou CTRL + E + C : commenter la sélection
- CTRL + K + U ou CTRL + E + U : décommenter la sélection
- CTRL + M + O : plier toutes les méthodes et régions du fichier courant
- CTRL + M + L : déplier toutes les méthodes et régions pliées
- ALT + SHIFT + flèches ou sélection à la souris : sélectionner un bloc de texte sur plusieurs lignes
- ALT + SHIFT + ENTRÉE : réduire les panels pour mieux voir le fichier courant
- CTRL + SHIFT + V : remonter dans l'historique du presse-papier
- CTRL + ESPACE  + flèches (haut ou bas) : déplacer la ligne selon le sens du flèche
- CTRL + D + Q : espion express

En débogage :
- F5 : lancer le DEBUG / lancer l’application
- CTRL + F5 : lancer l'application sans DEBUG
- SHIFT + F5 : arrêter le débug
- F10 : avancer d'un cran sans rentrer dans un sous-traitement
- F11 : avancer d'un cran et rentrer dans un  sous-traitement
- CTRL + F9 : mettre ou supprimer un point d'arrêt
- CTRL + SHIFT + F9 : supprimer tous les points d'arrêt
- F12 : accéder à la référence de l’ objet
- SHIFT + F12 : trouver toutes les références de l’objet

Si vous voulez connaître plus de raccourcis, pas de problème ! Voici un lien fournit par Microsoft (l’éditeur de Visual Studio) qui montre toute la liste exhaustive des tous les raccourcis clavier par fonctionnalité :
https://msdn.microsoft.com/fr-fr/library/da5kh0wa.aspx

Ce n’est pas encore terminé, vous pouvez même personnaliser vos raccourcis afin que vous sentiez plus à l'aise.

Voici comment vous pouvez les personnaliser :
- Dans la barre de menus, sélectionnez Outils puis Options,
- Cliquez sur Environnement puis choisissez Clavier,
- Dans la zone “Afficher les commandes contenant”, saisissez le nom du raccourci que vous souhaitez personnalisé puis sélectionnez là. Par exemple : “Edition.Rechercher”,
- Dans la liste “Utiliser un nouveau raccourci dans” sélectionnez la fonction sur laquelle vous voulez utiliser le raccourci personnalisé. Par exemple “Éditeur de texte”,
- Dans la zone de saisie “Appuyer sur les touches de raccourci”, mettez le nouveau raccourci souhaité,
- En fin, cliquez sur “Assigner” puis sur “OK” pour sauvegarder vos modifications.

Et voilà ! maintenant vous disposer de votre propre raccourci ;)

J’espère que cette partie vous apportée beaucoup dans votre formation. Nous avons vu ensemble comment créer un nouveau projet  sur Visual Studio, comment lui ajouter et installer rapidement une librairie externe grâce au gestionnaire de packages NuGet. Enfin, nous avons développé une application WPF en utilisant les raccourcis clavier afin d'accélérer le développement.

Nous nous retrouvons ensemble dans la prochaine et la dernière partie du cours pour comment gérer un projet avec un gestionnaire de versions comme Git et comment le publier en ligne sur GitHub.

# Partie 3 : Gérez le cycle de vie d'une application

Un développeur se pose parfois des questions sur la sécurité de son projet qui a passé des jours et des nuits à le développer.

A l'époque, un développeur créait plusieurs copies de son projet sur un outils de stockage externe afin qu'il ne perd son travail acharné. Même en faisant ceci, il y a un autre risque qui est la perte d'une version stable de son projet. Car un développeur peut effectuer plusieurs modifications par jour ce qui permet de créer des problèmes sans que le développeur se rend compte.

C’est pour cela que les outils d’hébergement et de versionning sont apparus afin de résoudre toutes ces problématiques. Et surtout, pour diminuer le stress sur les développeur.

Les systèmes de gestion de versions ont tous un but commun, c’est de stocker des fichiers selon l’ordre chronologie de modifications qui ont été apportées dessus. Ce qui permet d’avoir plusieurs versions d’où le nom système de gestion de versions est apparu. Il existe plusieurs services de gestion de versions, notamment Git, TFS et SVN.
Ils ont tous les mêmes fonctionnalités de base et le plus utilisé d’entre eux c’est Git.

Git est un logiciel de gestion de versions inventé par l’auteur du noyau de Linux. Il est open source et il existe plusieurs outils qui permettent d’utiliser ce logiciel, comme Visual Studio et GitHub. En plus de ça, c’est l’outil le plus utilisé par les développeurs indépendants et par les entreprises, ce qui nous encourage de l’utiliser dans notre cours.

Il existe plusieurs services d’hébergement, les plus connus sont VSTS et GitHub. VSTS est l’abréviation de Visual Studio Team System. C’est l’un des fameux produits de Microsoft et c’est un ensemble d’outils de développement logiciels, de collaboration et reporting. VSTS permet de travailler sur plusieurs outils de gestions de versions, notamment TFS et Git. 

GitHub est une plateforme d'hébergement et de gestion de développement de logiciels  open source utilisant le l’outil de gestion de version Git. Puisque nous sommes en face d’apprentissage, je vous propose de créer un compte sur GitHub afin que vous puissiez héberger votre projet en ligne ;).

GitHub est aussi le nom de l’entreprise qui a développée GitHub qui est spécialisée dans le développement de logiciels et de services. C’est la plateforme la plus connue des services d’hébergements, elle propose des comptes gratuits et payants. En juin 2018, Microsoft a finit par l’acquérir pour une somme de 7,5 milliards de dollars.

Comme évoqué au début de cette partie du cours, la vrai raison de l’apparition des services d’hébergement, c’est la centralisation des projets informatiques. Ce qui permet d’éviter la perte des projets et de rendre leur accès plus facile. Autrement dit, nous n’avons plus besoin de stocker nos projets en local ou sur des dispositifs externes, il suffit juste de les héberger en ligne.

## 3.1 Cloner une application existante

Tout d’abord, il faut que nous installions l’extension GitHub Extension for Visual Studio. Cette extension n’est pas encore disponible dans les packages NuGet, mais vous pouvez l’installer depuis le menu Outils > Extensions et mises à jour comme nous avons fait dans la deuxième partie.

Dans la vie de tous les jours vous serez surtout amené lorsque vous rentrez dans une entreprise, à récupérer les fichiers déjà fait, plutôt qu'à commencer sur un nouveau projet. Nous parlerons de la méthode d'envoi de fichiers plus tard.

Avant de continuer la suite du cours, j’aimerais vous parler des autres méthodes de manipulation de projets de GitHub :
- Fork
- Clone

### Fork
Avant de savoir comment utiliser Fork, il faut savoir ce que c’est et dans quel il est utilisé.

En fait, c’est comme n’importe quel projet, il faut qu’il soit développé et hébergé en ligne sur un serveur open source comme GitHub. Ceux qui ont élaboré ce projet, ils contribuent rarement, voire jamais,  à son amélioration. Sachant que le projet peut être incomplet où il nécessite des améliorations comme des tâches d’évolutions voire même des corrections de bugs.

C’est ainsi que le concept de Fork est né, il permet de prendre une copie d’un projet et de proposer des améliorations à ses aux propriétaires. Vous pouvez même renommer et lancer un nouveau projet à partir de cette copie et apporter plus d’améliorations selon vos envies.

Prenons l’exemple d’un projet open source sur GitHub calculator (https://github.com/ahfarmer/calculator).

Il y a 5 contributeurs dans ce projet  et il a été forké 240 fois. Cela veut dire 240 personnes l’ont copié. Et bah soyons les 241 :D !

En fait, c’est simple. Il suffit de cliquer sur Fork. Puis, attendre que le projet soit prêt pour le téléchargement.

Maintenant, tout ce qu’il reste à faire, c’est de le télécharger et contribuer sur ce projet. Mais ce n’est pas le but de ce cours. Parce que nous avons notre propre projet.

### Clone

Clone c’est l’action la plus utilisée sur les projets informatiques. Dans un cas réel, il y a au moins deux développeurs par projet. Et afin qu’ils puissent travailler en collaboration sur le même projet, l’un deux doit cloner le projet parent et l’inclure dans son environnement de travail.  Surtout dans le cas où un nouveau contributeur est arrivé sur le projet, il doit faire un clone sur le projet et ensuite il pourra travailler avec le reste de l’équipe.

La question qui se pose maintenant, c’est comment peut-on avoir une seule copie d’un projet avec plusieurs contributeurs ? 

C’est simple, il suffit d’utiliser un logiciel de gestion de versions, Git par exemple. Ensuite, chaque développeur synchronise ses modifications vers le projet parent qui se trouve sur le service d’hébergement GitHub.

## 3.2 Lancer des tests

Maintenant que nous avons vu comment développer une application,il faut s’assurer que vous avez réalisé toutes les tâches qui vous ont été confiées. Car dans la vraie vie, un projet informatique ne consiste pas à développer uniquement une application, mais de maintenir l’intégrité du code, garantir sa couverture et trouver les bugs avant de le livrer à votre client.

C’est pour cela que les projets de tests sont apparus car ils garantissent le bon fonctionnement des projets informatiques. 

La première étape à faire, c’est de créer un projet de test unitaire. Sélectionnez la solution sur l’explorateur de Solution, puis faites un clic droit et cliquez sur Ajouter > Nouveau projet.

Dans la fenêtre qui apparaît, sélectionnez “Test” dans le menu à gauche et choisissez “Projet de test unitaire” comme suit :

Avant que vous validiez la création de votre projet, j’aimerais vous dire qu’il existe plusieurs types de projets de test :
- MS Test
- xUnit
- NUnit/Unit Test (Test Unitaire en français)

En fait, ce sont trois frameworks de test et il n’y a pas beaucoup de différence entre ces trois types de projets de test. Au niveau du framework, NUnit et MS Test sont très semblable, ils supportent les paramètres dans les méthodes de test et tous les deux supportent plusieurs plateformes comme .Net Core, UWP …. et beaucoup d’autres. Mais NUnit a plus d’avantage par rapport à MS Test :
- permet d’exécuter les tests séparément,
- des méthodes de tests lisible (Assert),
- des mises à jour fréquentes, contrairement à MS Test en a seulement une par version de Visual Studio,
- a une meilleure documentation par rapport à MS Test.

Le framework de test xUnit est open source et il a été créé par l’inventeur NUnit version 2. Il a les fonctionnalités de base des autres frameworks, mais il ne supporte pas la plateformes de développement mobile UWP et il n’est pas bien documenté.

Maintenant que vous avez connu la différence entre les différents frameworks de test, vous pouvez cliquer sur “OK” pour valider la création de votre projet de test.

### image

Comme vous voyez dans la capture ci-dessus, Visual Studio vous crée automatiquement un fichier .cs pour y ajouter vos tests.

### image

Dans le fichier UnitTest, vous voyez qu’il y a deux attributs “TestClass” et “TestMethod”. Ces deux attributs sont indispensable pour la création de vos tests :
- TestClass : permet d’identifier les classes qui contiennent des méthodes de test,
- TestMethod : permet d’identifier les méthodes de test.

Avant de commencer à écrire nos tests, nous devons référencer le  projet de l’application WPF dans le projet de test. Puisque le but du projet de test est de tester l’application que nous avons développé, non ?

Nous avons déjà vu comment ajouter une référence d’une librairie à un projet et c’est le même principe pour ajouter la référence d’un projet à un autre projet. Voici comment faire :

### image

Comme vous avez vu dans la capture ci-dessus, il suffit juste de cliquer sur “Projet” > “Solution” puis choisir le projet que vous voulez tester et enfin sur “OK” pour valider.

### image

Ici vous remarquez que la référence du projet WPF apparaît dans les références.

Maintenant, vous n’avez qu’à écrire vos tests. Ne vous inquiétez, nous allons le faire ensemble !

Le but de la référence que nous venons de rajouter, c’est de pouvoir utiliser les fichiers du projet WPF. Donc pour commencer, nous allons faire appel à “OrderViewModel” et tester les données à afficher dans l’application. Le but de ce test c’est de s’assurer qu’il y a vraiment des données à afficher.

A l’intérieure de la méthode “TestMethod”, ajoutez la ligne suivante :

````
var OrderVM = new OrderViewModel();
````

Ici, nous avons instancié notre view-model afin qu’il construise les données.

Ensuite, nous allons utiliser une classe “Assert” qui permet de tester plusieurs conditions dans des tests unitaires. L’utilisation de cette classe de test est très simple, tout ce que vous à faire c’est de choisir la condition à utiliser selon votre cas. Dans notre cas, nous voulons s’assurer qu’il y a des données à afficher. Donc, vous devez simple faire comme suit :

Mettez cette ligne au-dessous de l’instanciation du view-model :
````
Assert.IsNotNull(OrderVM.Orders);
````

IsNotNull est méthode dans la classe Assert qui permet de tester si l’objet passé en paramètre n’est pas null. Attendez ! Et si l’objet que nous testons n’est pas égale à null mais qu’il est vide ! Comment nous allons faire ?

Pas de panique, nous allons utiliser encore la classe Assert :

````
Assert.AreNotEqual(0, OrderVM.Orders.Count);
````

Cette fois ci, nous avons utilisé la méthode “AreNotEqual” afin de s’assurer qu’il y a des données.

Voici le code de la méthode de test :

````
[TestMethod]
    	public void TestMethod()
    	{
        	var OrderVM = new OrderViewModel();
        	Assert.IsNotNull(OrderVM.Orders);
        	Assert.AreNotEqual(0, OrderVM.Orders.Count);
    	}
````

Maintenant, tout ce qu’il reste à faire c’est de lancer vos tests. Faites un clic droit sur “TestMethod” et cliquez sur “Exécuter un ou plusieurs tests”.

Une nouvelle fenêtre apparaît à gauche de votre espace de travail sous le nom “Explorateur de tests”. Cette fenêtre contient tous vos tests et elle vous donne leur résultat.

Voici le résultat de notre premier test :

### image

Si l’explorateur affiche le résultat en vert, cela veut que le test est passé et que les conditions que nous avons mis dans le test sont corrects.

Vous n’êtes pas encore convaincu ? Voici le contenu de l’objet qui contient les données à afficher dans l’application :

### image

Nous voyons bien qu’il y a 10 éléments dans l’objet et ils contiennent les données que nous avons affiché précédemment lorsque nous avons lancé l’application.

Pour mieux comprendre le fonctionnement de test, ajoutez la ligne de code suivante avant la condition IsNotNull afin de voir comment le test sera exécuté :

````
OrderVM.Orders.Clear();
````

Relancez maintenant les tests.

### image

Vous avez compris ce qu’il s’est passé ? En fait la ligne que vous avez rajouté permet d’effacer toutes les données et puisque le deuxième test permet de voir s’il y a des données, le résultat est en rouge.

Vous savez maintenant comment tester votre application et garantir sa bonne livraison à votre client.

## 3.3 Fixer et commit un bug

Nous allons aborder ici les différentes actions possibles de Git qu’un développeur peut utiliser pour communiquer avec GitHub.

Il est en effet possible d’utiliser trois actions :
- Commit / Valider tout: Permet de sauvegarder les modifications sur le projet en local,
- Commit and Push / Valider tout et Poussez : Permet de sauvegarder les modifications sur le projet en local et sur le serveur,
- Commit and Synchronize / Valider tout et Synchroniser : Permet de sauvegarder les modifications sur le projet en local et sur le serveur et de récupérer les modifications des autres contributeurs du projet.

Toutes ces trois actions sont à votre disposition pour mener à bien votre projet.

### Commit

Il est temps de mettre en oeuvre les 3 actions que nous avons évoquées précédemment. Nous allons apporter quelques modifications à la page MainWindows.xaml de notre projet WPF.

Pour commencer, modifiez la couleur du texte affiché dans la grille de données en utilisant la propriété ForeGround. Voici la ligne qu’il faut mettre à jour :

````
<syncfusion:SfDataGrid Margin="30" x:Name="dataGrid" Foreground="Green"  ItemsSource="{Binding Orders}" />
````

Relancez votre application et vérifiez si la couleur du texte a changé.

Maintenant, nous allons utiliser Commit afin de sauvegarder nos modifications en local. Allez dans la fenêtre Team Explorer. Dans l’onglet Projet, cliquez sur Modifications et ajoutez un commentaire dans la zone qui apparaît en jaune. Attention, cette étape est obligatoire sinon vous ne pouvez pas poursuivre le commit.

Normalement, vous avez remarqué que dans l’onglet Modifications, nous avons le nombre de fichiers que nous avons modifié. Vous pouvez même faire un clic droit sur le fichier modifié et cliquer sur Comparer avec la version précédente. Ceci vous permettra de vérifier et de comparer vos modifications avec la dernière version qui existe sur GitHub.

Ensuite, cliquez sur Commit / Valider tout dans la liste déroulante en bas du commentaire.

Et voilà ! Vous avez enregistré vos modifications en local. 

Avant de passer à l’action suivante, nous allons faire une petite vérification sur GitHub afin de mieux comprendre ce que nous sommes en train de faire.

Ici, nous remarquons bien que notre modification n’a pas été envoyée à notre projet sur GitHub.

Si vous voulez envoyer votre modification à GitHub, cliquez sur le bouton Home / Début ensuite sur Synchroniser. Ensuite, dans Validations sortantes, sélectionnez la modification que vous voulez envoyer à GitHub et cliquez sur Pousser.

Maintenant, vérifier dans GitHub si votre modification a été bien envoyé.

Il existe une autre option pour envoyer les modifications directement à GitHub sans passer par l’étape Synchronisation. En fait, c’est comme dans l’étape précédente, au lieu de cliquer sur Commit, il suffit de cliquer sur  Commit et Push. Cette étape est plus pratique si vous êtes sûr de vos modifications et que vous voulez les envoyer à GitHub.

### Commit / Synchronize

Maintenant, nous allons voir comment envoyer et récupérer une modification en utilisant l’action Commit et Synchronize.

Remarque : pour synchroniser et récupérer une modification, vous devez ajouter un autre collaborateur à votre projet depuis GitHub. Voici comment faire :
- Allez dans les paramètres du projet,
- Cliquez sur Collaborateur, 
- Saisissez le nom de votre collaborateur,
- Et cliquez sur Add collaborator.

Comme ça vous pouvez travailler ensemble sur le projet et jouer les actions de Git ;)

Allez ! Continuions ! Cette fois ci, nous allons modifier le style du texte. Utilisez la propriété FontWeight pour rendre le texte en gras.

Voici la ligne de code complète :

````
<syncfusion:SfDataGrid Margin="30" x:Name="dataGrid" Foreground="Green" FontWeight="Bold" ItemsSource="{Binding Orders}" />
````

Ceci sera la modification que nous allons pousser à GitHub. Allons maintenant vérifier la modification que nous allons récupérer depuis GitHub.

### image

Nous remarquons ici qu’il y a une modification qui a été apporté à notre code par un autre contributeur du projet

Maintenant, allez dans l’onglet Modifications de la fenêtre Team Explorer et cliquez sur Commit et Synchronize. Vérifiez que vous avez le même contenue dans le fichier MainWindow.xaml (en local et sur GitHub).

Voici le contenu que vous devez avoir à la fin sur GitHub.

### image

Pour résumer, nous avons vu ensemble les différents actions de Git et comment communiquer avec GitHub. 

Dans le prochain chapitre, nous verrons comment travailler proprement dans un projet à l’aide des branches. Allez ! Au chapitre suivant :D. 

## 3.4 Envoyer sur le serveur

Généralement dans un projet de logiciel, il peut y avoir plusieurs membres dans l’équipe de développement. Tous les membres de cette équipe peuvent travailler simultanément sur le même fichier de code ou sur la même fonctionnalité, ceci génère des conflits constamment et peut casser la version stable du projet.

Autre point très important, dans un grand projet, il n’y a pas que l’équipe de développement. Il y a une équipe de test qui a besoin d’une version stable du projet afin qu’elle puisse tester les nouvelles fonctionnalités et la correction des anomalies. Parallèlement, l’équipe de développement doit continuer ses tâches et contribuer à l’amélioration du projet.

Mais ceci s’avère compliqué et trop risqué pour un grand projet. C’est pourquoi les branches sont apparues.

Elles ont pour but de :
- Créer une branche par besoin,
- Éviter les conflits dans le code,
- Séparer les équipes du projet,
- Faire progresser l’avancement du projet,
- Éviter les risques dans le contrôle de version,
- Avoir une version stable du projet.

Dans cette section, nous verrons comment créer une branche et comment changer d’une branche à une autre. Allez ! C’est parti !

Pour commencer, allez dans l’onglet Branches de la fenêtre Team Explorer. Vous allez avoir une seule branche master qui est la branche mère. C’est celle qu’on utilise d’habitude pour livrer une version stable d’un projet.

Généralement, dans un projet de développement, on crée deux branches :
- une branche pour tâches de maintenance et d’évolutions qui est dédiée à l’équipe de développement,
- une branche pour le livrable à tester par l’équipe de test.

Récapitulant un peu !

- La branche Master c’est la version stable du projet,
- la branche PrePROD c’est pour faire les tests avant de livrer le projet,
- La branche DEV est dédiée pour les tâches de développement en cours.

Maintenant, nous allons créer les deux branches manquantes sous le nom DEV et PrePROD.

Donc, pour créer une branche, sélectionnez la branche master puis faites un clic droit et cliquez sur Nouvelle branche locale.

### image

Ensuite, saisissez le nom de la branche et cliquez sur Créer une branche.

### image

Faites la même chose pour la deuxième branche.

Enfin , vous devez avoir 3 branches comme suit :

### image

ctuellement, les 3 branches sont au même niveau et elles ont la même version de code.

Voici ce que nous allons faire.

Nous allons faire un petit exercice pour bien pratiquer la notion des branches. Comme je vous ai expliqué, nous devons commencer à travailler sur la branche de DEV et une fois que nous aurons terminé, nous allons merger la branche DEV avec la branche PrePROD.

Avant tout, il faut savoir comment naviguer d’une branche à une autre. C’est simple ! 
Il suffit de cliquer sur master en bas à droite de Visual Studio et de sélectionner DEV dans la liste qui apparaît.

### image

Ensuite, nous allons modifier la couleur du background de l’application en rouge et faire un commit (n’importe lequel). Vous savez comment faire. Je compte sur vous ;) !

Ce qui veut dire qu’actuellement dans la branche de DEV nous avons un background en rouge et dans la branche PrePROD nous avons Turquoise. 

Naviguez dans la branche PrePROD pour vérifier que vous n’avez pas la même couleur dans les deux branches.

Je pense que le but des branches est devenu plus clair pour vous. Nous avons deux versions de code différentes. Maintenant, nous allons merger ces deux branches afin de les rendre identiques et comme ça notre équipe de test (imaginaire :p) pourra tester nos modifications.

Allez dans l’onglet Branches de la fenêtre Team Explorer. La branche PrePROD est sélectionné par défaut car c’est la branche actuelle. Ca tombe bien car c’est la branche que nous voulons fusionner :D.

Sélectionnez la branche DEV dans la liste Fusionner à partir de la branche et cliquez sur le bouton Fusionner.

### image

Comparez les couleurs dans les deux branches et vous devriez avoir les mêmes.

Maintenant, imaginons que notre équipe de teste à valider la modification de couleur et nous demande de livrer une version stable avec cette modification.

C’est simple, vous n’avez qu’à faire les mêmes actions de fusionnement sur la branche master.

Et voilà ! Maintenant vous savez comment travailler en équipe en utilisant un service d’hébergement et un logiciel de versionning. N’oubliez pas ! Git et GitHub sont les outils les plus utilisés dans le développement des logiciels informatiques et vous les maîtrisez déjà ;).

# Activité P2P