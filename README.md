# Ma configuration Debian

Script d'automatisation pour configurer et mettre à jour mon système Debian.

> [!NOTE]
> Ce script est conçu exclusivement pour **Debian** utilisant l'environnement de bureau **GNOME**.

---

## 🧪 Versions testées
* Debian 13 (trixie)
* Debian testing (forky)

---

## 🔍 Ce que fait le script

1. Configure le gestionnaire de paquets APT et applique les mises à jour
2. Configure le gestionnaire de paquets Flatpak et applique les mises à jour
3. Configure les dépôts APT et Flatpak
4. Ajoute ou supprime les paquets deb dont ceux spécifiés dans `packages.list`
5. Ajoute ou supprime les paquets flatpak spécifiés dans `flatpak.list`
6. Personnalise la configuration du système

---

## 📁 Structure

```bash
.
├── assets/               # Ressources à copier sur le système (si existantes)
├── config-debian.sh      # Script principal
├── flatpak.list          # Liste des paquets Flatpak à installer/désinstaller
└── packages.list         # Liste des paquets Deb à installer/désinstaller
```

---

## 🚀 Usage

### 1. Configuration de Flatpak (Optionnel)
Par défaut, le script installe et gère le système de paquets Flatpak. Pour désactiver Flatpak, ouvrez le fichier `config-debian.sh` et modifiez la variable suivante :
```bash
IS_FLATPAK_ENABLED="false"
```

> [!IMPORTANT]
> A faire avant le premier lancement du script !

### 2. Exécution du script
Ouvrez votre terminal dans le dossier du dépôt, autorisez l'exécution du script et lancez-le avec les privilèges super-utilisateur (root) :
```bash
chmod +x config-debian.sh
sudo ./config-debian.sh
```

### 3. Mode vérification de mises à jour
Il est possible de faire uniquement une vérification des mises à jour (listing des paquets deb et flatpak à mettre à jour sans appliquer de modifications) via l'option `check` :
```bash
sudo ./config-debian.sh check
```

### 4. Utilisation pour la maintenance
Ce script est idempotent. Vous pouvez l'exécuter plusieurs fois de suite; les étapes déjà configurées seront simplement ignorées. De fait, le script peut être utilisé pour :
* **Configuration initiale** du système après une installation fraîche
* **Mise à jour** de la configuration et des listes de paquets
* **Mise à jour globale** de tous les paquets du système

---

## 🙏 Crédits

Ce script est inspiré du [travail initial](https://github.com/aaaaadrien/fedora-config) d'Adrien de [linuxtricks.fr](https://www.linuxtricks.fr)
