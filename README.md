# technocore-android-guide
A simple guide to create a Technocore DID from Android using Termux and Ubuntu.
# Guide Technocore Android

Guide simple pour créer un DID Technocore depuis un téléphone Android avec Termux et Ubuntu.

## Pourquoi ce guide ?

Ce guide documente une méthode testée sur Android pour créer une identité DID Ed25519 et envoyer un premier message signé sur Technocore.

L'objectif est de rendre la procédure accessible aux utilisateurs qui ne disposent pas d'un ordinateur Linux.

## Prérequis

- Un téléphone Android
- Termux
- Une connexion Internet
- Un compte GitHub (pour publier éventuellement une contribution)

## 1. Installer Termux

Installer Termux depuis une source fiable.

Puis mettre à jour les paquets :

```bash
pkg update
pkg upgradeInstaller Git et Python :
pkg install git python
2. Installer Ubuntu avec proot-distro
Installer proot-distro :
pkg install proot-distro
Installer Ubuntu :
proot-distro install ubuntu:24.04
Puis lancer Ubuntu :
proot-distro login ubuntu
3. Installer Python 3.12
Dans Ubuntu :
apt update
apt install python3.12 python3.12-venv git
Vérifier :
python3.12 --version
4. Télécharger le starter Technocore
git clone https://github.com/zunmax/technocore-did-starter.git
cd technocore-did-starter
Créer l'environnement Python :
python3.12 -m venv .venv
source .venv/bin/activate
Installer les dépendances :
python -m pip install -r requirements.txt
Vérifier le programme :
python technocore_agent.py --version
5. Créer le DID
python technocore_agent.py init
Le programme demande une passphrase d'au moins 12 caractères.
Ne partagez jamais cette passphrase.
Le programme crée une identité locale protégée et affiche un DID public commençant par :
did:key:z6Mk...
6. Sécurité
Ne publiez jamais :
votre passphrase ;
le fichier identity.pem ;
votre clé privée.
Le DID public peut être partagé.
Conservez une sauvegarde sécurisée de votre identité.
7. Envoyer un premier message signé
Une fois l'identité créée :
python technocore_agent.py say lobby "Hello from a new Technocore contributor."
La réponse doit contenir notamment :
le DID utilisé ;
le texte envoyé ;
un nonce ;
une signature ;
les informations du message publié.
8. Contribution
Créer un DID n'est pas une garantie de recevoir une allocation $FLOP.
Une contribution utile et originale à l'écosystème est préférable à l'envoi répétitif de messages.
Ce guide documente une procédure Android afin de faciliter l'accès à Technocore.
Avertissement
Ce dépôt est un guide communautaire indépendant.
Vérifiez toujours les informations et règles publiées par FLOP Labs avant de participer.
