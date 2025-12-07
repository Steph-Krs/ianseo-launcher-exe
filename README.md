# IANSEO Launcher

> 🇫🇷 Utilitaire Windows tout-en-un pour lancer, contrôler et dépanner **IANSEO** (Apache/MySQL) facilement, avec gestion multilingue, QR-Code intégré et outils de réparation avancés.  
> Voici le lien vers le code source : [code source](https://github.com/Steph-Krs/ianseo-launcher-exe-dev)  
>   
> 🇬🇧 All-in-one Windows utility to easily start, control and troubleshoot **IANSEO** (Apache/MySQL), with multilingual support, integrated QR-Code and advanced repair tools.  
> Here is the link to the source code: [source code](https://github.com/Steph-Krs/ianseo-launcher-exe-dev)  

---

## ✨ Fonctionnalités

### 🎯 Contrôle & Lancement
- ▶️ Démarrer Apache & MySQL (mode XAMPP ou services Windows)
- ⏸️ Arrêter Apache & MySQL intelligemment selon leur mode de lancement
- 🌐 Ouvrir IANSEO dans le navigateur par défaut
- 📊 Surveillance en temps réel du statut d'Apache et MySQL
- 🔄 Détection automatique du mode d'exécution (manuel via XAMPP ou automatique via services Windows)

### 🌐 Accès Réseau
- 📸 Afficher un QR-Code pour accéder au serveur depuis un smartphone
- 🔗 Copier le lien d'accès au presse-papier
- 🖥️ Détection automatique de l'adresse IP locale et du port Apache

### 🛠️ Outils de Réparation & Administration
- ⚡ Ouvrir `xampp-control.exe` directement depuis l'interface
- 🔧 **Réparer MySQL** : restauration automatique depuis la sauvegarde avec préservation des bases de données utilisateur
- 🚀 **Configurer les services Windows** : installation et activation automatique d'Apache et MySQL comme services au démarrage
- 🛡️ **Configurer Windows Defender** : ajout automatique des exclusions pour éviter les blocages
- 🔐 Mode administrateur avec relance automatique si nécessaire

### 🌍 Multilingue
- Support complet : français, anglais, espagnol, allemand, italien
- Détection automatique de la langue système

---

## 📥 Installation

### Prérequis
- Windows 7 ou supérieur
- IANSEO installé (XAMPP inclus)
- Droits administrateur recommandés pour les fonctions avancées

### Installation rapide

1. **Téléchargez** ou clonez ce dépôt (bouton vert `<> Code` → `Download ZIP`)  
2. **Copiez** `IANSEO.exe` **et** `QRCoder.dll` dans le **dossier d'installation de IANSEO** (par défaut `C:\ianseo\`)  
3. **Vérifiez** que `xampp-control.exe`, `xampp_start.exe` et `xampp_stop.exe` sont présents dans ce même dossier  
4. **Lancez** `IANSEO.exe`

### 🗂️ Arborescence attendue

```
C:/
└── ianseo/
   ├── htdocs/
   ├── apache/
   │  ├── bin/
   │  │  └── httpd.exe
   │  └── conf/
   │     └── httpd.conf
   ├── mysql/
   │  ├── bin/
   │  │  ├── mysqld.exe
   │  │  └── mysql.exe
   │  ├── data/
   │  └── backup/           ← Nécessaire pour la fonction de réparation
   ├── xampp-control.exe
   ├── xampp_start.exe
   ├── xampp_stop.exe
   ├── IANSEO.exe           ← L'exécutable du launcher
   └── QRCoder.dll          ← Bibliothèque pour générer les QR-codes
```

---

## 🎮 Utilisation

### Démarrage Simple
1. Lancez `IANSEO.exe`
2. Cliquez sur **"Démarrer IANSEO"** (bouton vert)
3. Attendez que les indicateurs Apache et MySQL deviennent verts
4. Cliquez sur **"Ouvrir IANSEO"** pour accéder à l'interface web

### Arrêt
- Cliquez sur **"Arrêter"** (bouton rouge)
- Le launcher détecte automatiquement si Apache/MySQL sont lancés en mode XAMPP ou comme services Windows et les arrête correctement

### Accès depuis un Smartphone/Tablette
1. Assurez-vous que Apache et MySQL sont démarrés (points verts)
2. Cliquez sur **"Afficher QR"**
3. Scannez le QR-Code avec votre appareil mobile
4. Vous serez redirigé vers l'interface IANSEO

### Outils de Réparation (Mode Administrateur)

#### 🔧 Réparer MySQL
Si MySQL ne démarre plus ou si la base de données est corrompue :
1. Lancez `IANSEO.exe` **en tant qu'administrateur**
2. Cliquez sur **"Réparer MySQL"**
3. L'outil va :
   - Arrêter Apache et MySQL
   - Sauvegarder le dossier `data` actuel vers `data_old`
   - Restaurer depuis `mysql/backup/`
   - Copier vos bases de données utilisateur depuis `data_old`
   - Recréer l'utilisateur MySQL `ianseo`
   - Redémarrer les services

⚠️ **Important** : Assurez-vous qu'un dossier `mysql/backup/` existe avec une sauvegarde propre avant d'utiliser cette fonction.

#### 🚀 Configurer comme Services Windows
Pour que Apache et MySQL démarrent automatiquement avec Windows :
1. Lancez `IANSEO.exe` **en tant qu'administrateur**
2. Cliquez sur **"Activer au démarrage de Windows"**
3. Les services `Ianseo_Apache` et `Ianseo_MySQL` seront créés et configurés en démarrage automatique

**Avantages** :
- Démarrage automatique au boot de Windows
- Meilleure intégration système
- Gestion via le Gestionnaire de services Windows

**Note** : Vous pouvez revenir au mode manuel en désinstallant les services via `xampp-control.exe`

#### 🛡️ Configurer Windows Defender
Si Windows Defender bloque Apache ou MySQL :
1. Lancez `IANSEO.exe` **en tant qu'administrateur**
2. Cliquez sur **"Configurer Windows Defender"**
3. Les exclusions suivantes seront ajoutées automatiquement :
   - Chemin : tout le dossier IANSEO
   - Extensions : `.mysql`, `.php`
   - Processus : `httpd.exe`, `mysqld.exe`, `xampp-control.exe`

---

## 🔍 Indicateurs d'État

### Voyants de Statut
- 🔴 **Rouge** : Service arrêté
- 🟢 **Vert** : Service en cours d'exécution

### Modes d'Exécution
- **Apache (manual)** : Lancé via `xampp_start.exe`
- **Apache (auto)** : Lancé comme service Windows
- **MySQL (manual)** : Lancé via `xampp_start.exe`
- **MySQL (auto)** : Lancé comme service Windows

---

## ❗ Problèmes Fréquents

### L'application ne se lance pas
- ✅ Vérifiez que `IANSEO.exe` est dans le dossier `ianseo/`
- ✅ Vérifiez que `xampp-control.exe` existe dans le même dossier
- ✅ Un message d'erreur devrait s'afficher si le dossier est incorrect

### Apache/MySQL ne démarrent pas
- ✅ Ouvrez `xampp-control.exe` pour voir les détails des erreurs
- ✅ Vérifiez que les ports 80 (Apache) et 3306 (MySQL) ne sont pas utilisés par d'autres applications
- ✅ Essayez de lancer `IANSEO.exe` **en tant qu'administrateur**
- ✅ Utilisez l'outil **"Réparer MySQL"** si MySQL refuse de démarrer

### Connexion impossible avec le QR-Code
- ✅ Vérifiez que **les deux appareils** sont sur le même réseau local (WiFi ou Ethernet)
- ✅ Vérifiez que le pare-feu Windows n'est pas bloqué
- ✅ Essayez d'utiliser l'outil **"Configurer Windows Defender"**
- ✅ Essayez de vous connecter manuellement avec l'adresse affichée (ex: `192.168.1.10:80`)

### L'application ne peut pas arrêter les services
- ✅ Si les services Windows sont actifs, vous **devez** lancer l'application en tant qu'administrateur
- ✅ Utilisez le bouton **"Exécuter en tant qu'admin"** dans la section Dépannage

### MySQL corrompu après une coupure de courant
- ✅ Utilisez l'outil **"Réparer MySQL"** (nécessite un backup dans `mysql/backup/`)
- ✅ Si vous n'avez pas de backup, réinstallez IANSEO complètement

---

## 🌍 Langues Supportées

L'application détecte automatiquement la langue du système. Langues disponibles :
- 🇫🇷 Français
- 🇬🇧 English
- 🇪🇸 Español
- 🇩🇪 Deutsch
- 🇮🇹 Italiano

---

## 📝 English Version

### Features

#### 🎯 Control & Launch
- ▶️ Start Apache & MySQL (XAMPP mode or Windows services)
- ⏸️ Intelligently stop Apache & MySQL based on their launch mode
- 🌐 Open IANSEO in the default browser
- 📊 Real-time monitoring of Apache and MySQL status
- 🔄 Automatic detection of execution mode (manual via XAMPP or automatic via Windows services)

#### 🌐 Network Access
- 📸 Display a QR-Code to access the server from a smartphone
- 🔗 Copy the access link to the clipboard
- 🖥️ Automatic detection of local IP address and Apache port

#### 🛠️ Repair & Administration Tools
- ⚡ Open `xampp-control.exe` directly from the interface
- 🔧 **Repair MySQL**: automatic restoration from backup with preservation of user databases
- 🚀 **Configure Windows Services**: automatic installation and activation of Apache and MySQL as startup services
- 🛡️ **Configure Windows Defender**: automatic addition of exclusions to avoid blocks
- 🔐 Administrator mode with automatic restart if necessary

#### 🌍 Multilingual
- Full support: French, English, Spanish, German, Italian
- Automatic system language detection

### Installation

#### Prerequisites
- Windows 7 or higher
- IANSEO installed (XAMPP included)
- Administrator rights recommended for advanced features

#### Quick Install

1. **Download** or clone this repository (green button `<> Code` → `Download ZIP`)
2. **Copy** `IANSEO.exe` **and** `QRCoder.dll` into the **IANSEO installation folder** (default: `C:\ianseo\`)
3. **Verify** that `xampp-control.exe`, `xampp_start.exe` and `xampp_stop.exe` are present in the same folder
4. **Run** `IANSEO.exe`

### Common Issues

- **Application does not start**: Make sure `IANSEO.exe` is in the `ianseo/` folder and `xampp-control.exe` exists
- **Apache/MySQL do not start**: Open `xampp-control.exe` for error details, check ports 80/3306, try running as administrator
- **Cannot connect with QR-Code**: Verify both devices are on the same local network, check firewall settings
- **Cannot stop services**: You must run the application as administrator if Windows services are active
- **MySQL corrupted after power outage**: Use the "Repair MySQL" tool (requires backup in `mysql/backup/`)

---

## 🔧 Technologies

- **C# / .NET Framework** (WinForms)
- **QRCoder** - Génération de QR-Codes
- **sc.exe / net.exe** - Gestion des services Windows
- **PowerShell** - Configuration Windows Defender

---

## 📄 License

Ce projet est distribué librement pour faciliter l'usage d'IANSEO par les clubs et bénévoles.

---

**Développé pour simplifier la vie des bénévoles gérant les compétitions de tir à l'arc** 🏹
