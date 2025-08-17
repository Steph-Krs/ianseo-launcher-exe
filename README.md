# IANSEO Launcher

> 🇫🇷 Petit utilitaire Windows permettant de lancer et contrôler **IANSEO** (Apache/MySQL) facilement, avec gestion multilingue et QR-Code intégré pour accéder à IANSEO.  
> Voici le lien vers le code source : [code source](https://github.com/Steph-Krs/ianseo-launcher-exe-dev)  
>   
> 🇬🇧 Small Windows utility to easily start and control **IANSEO** (Apache/MySQL), with multilingual support and integrated QR-Code to access IANSEO.  
> Here is the link to the source code: [source code](https://github.com/Steph-Krs/ianseo-launcher-exe-dev)  

---

## ✨ Fonctionnalités

- ▶️ Démarrer Apache & MySQL
- ⏸️ Arrêter Apache & MySQL
- 🌐 Ouvrir IANSEO dans le navigateur
- 📸 Afficher un QR-Code pour accéder au serveur depuis un smartphone
- 🔗 Copier le lien d’accès au presse-papier
- ⚡ Ouvrir `xampp-control.exe` en cas de besoin
- Multilingue : français, anglais, espagnol, allemand, italien

---

## 📥 Installation

1. Téléchargez ou clonez ce dépôt. (Bouton vert en haut à droite `<> Code` puis `Download ZIP`)  
2. Copiez `IANSEO.exe` **et** `QRCoder.dll` dans le **dossier d’installation de IANSEO** (par défaut `C:\ianseo\`).  
3. Vérifiez que `xampp-control.exe` est présent dans ce même dossier.  
4. Lancez `IANSEO.exe`.

### 🗂️ Exemple d’arborescence attendue :

```
C:/
└── ianseo
   ├── htdocs/
   ├── xampp-control.exe
   ├── xampp_start.exe
   ├── xampp_stop.exe
   ├── apache/
   │  └── conf/
   │     └── httpd.conf
   ├── IANSEO.exe           ← l'éxecutable permettant de lancer IANSEO
   └── QRCoder.dll          ← permet d'afficher un QR-code pour se connecter au serveur
```

---

## ❗ Problèmes fréquents

- Si l’application ne se lance pas :
  - Vérifiez que `IANSEO.exe` et `xampp-control.exe` sont dans le dossier `ianseo/`.
- Si Apache/MySQL ne démarrent pas :
  - Ouvrez `xampp-control.exe` pour voir plus de détails.
- Si vous n'arrivez pas à vous connecter à ianseo avec le QR-code :
  - Vérifiez que les **2 appareils** sont sur le même réseau et qu'il n'y a pas de règle de sécurité bloquant les accès (pare-feu, antivirus, règle de routage).

---

## 📝 English

### Features

- ▶️ Start Apache & MySQL
- ⏸️ Stop Apache & MySQL
- 🌐 Open IANSEO in your browser
- 📸 Show a QR-Code to access the server from a smartphone
- 🔗 Copy the access link to the clipboard
- ⚡ Open `xampp-control.exe` if needed
- Multilingual: French, English, Spanish, German, Italian

### Installation

1. Download or clone this repository (green button `<> Code` → `Download ZIP`).  
2. Copy `IANSEO.exe` **and** `QRCoder.dll` into the **IANSEO installation folder** (default: `C:\ianseo\`).  
3. Make sure `xampp-control.exe` is present in the same folder.  
4. Run `IANSEO.exe`.

### Common Issues

- If the application does not start:
  - Make sure `IANSEO.exe` and `xampp-control.exe` are in the `ianseo/` folder.
- If Apache/MySQL do not start:
  - Open `xampp-control.exe` to see more details.
- If you cannot connect to IANSEO using the QR code:
  - Make sure **both devices** are on the same network and that no security rules are blocking access (firewall, antivirus, routing rules).
