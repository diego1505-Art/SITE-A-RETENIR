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
