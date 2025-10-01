## Les prérequis pour installer Docker ✅ : 
#### Sous Windows
```
Version du système d'exploitation : Windows 10 ou 11, éditions Professionnel, Entreprise ou Éducation (64 bits).
Processeur : 64 bits avec Traduction d'Adresse de Second Niveau (SLAT).
Mémoire vive (RAM) : 4 Go.
Virtualisation matérielle : Doit être activée dans le BIOS/UEFI de l'ordinateur.
Sous-système Windows pour Linux (WSL 2) : Il doit être activé.
Espace disque : Au moins 20 Go d'espace libre disponible.
```
### Sous Linux 
```
Système d'exploitation : Debian 10 ou plus récent, Ubuntu 18.04 ou plus récent, ou une distribution compatible. 
Processeur : 64 bits (architecture x86_64/amd64, armhf, arm64). 
Mémoire vive (RAM) : 2 Go minimum, mais 4 Go ou plus sont recommandés pour un développement fluide. 
Espace disque : 10 Go minimum pour les images et les conteneurs. 
Accès root : Vous devez avoir un accès root ou les privilèges sudo pour installer les paquets. 
```
<hr>

## Installation 👇🏾: 
#### Sous Windows
- Téléchargez l'installateur : Rendez-vous sur le site officiel de Docker et téléchargez la version Docker Desktop pour Windows. 
- Exécutez l'installateur : Ouvrez le fichier d'installation que vous venez de télécharger. 
Configurez l'installation :
- Dans l'assistant, cochez la case Utiliser WSL 2 au lieu d'Hyper-V (Utiliser WSL 2 au lieu d'Hyper-V) pour assurer la meilleure compatibilité. 
Suivez les étapes de l'assistant pour compléter l'installation des composants nécessaires, y compris l'installation de WSL 2 si ce n'est pas déjà fait.

#### Sous Linux 
. Ouvrir un terminal 

. Mettre à jour le système :
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
. Ajouter la clé GPG et le dépôt Docker :
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
. Installateur Docker : 
```
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
. Vérifier l'installation de docker et ses services : 
```
docker --version
sudo systemctl status docker
```
