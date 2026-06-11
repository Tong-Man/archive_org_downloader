# archive_org_downloader
Allows you to download large files from an archive.org URL
# Archive.org Downloader

## English Version

### Description
**Archive.org Downloader** is a Python utility that downloads specific file types from Archive.org items while preserving the original directory structure. By default, it downloads `.txt`, `.cue`, and `.bin` files, but you can customize the file extensions to download.

### Features
- 🎯 Download specific file types from Archive.org
- 📁 Preserves original directory structure
- 📊 Real-time progress bar during downloads
- 🔄 Skips already downloaded files
- ⚙️ Customizable file extensions
- 🛡️ Proper error handling and validation
- 🌐 Works with both URLs and Archive.org identifiers

### Requirements
- Python 3.7 or later
- Internet connection
- No additional external dependencies (uses only Python standard library)

### Installation
1. Make sure Python 3.7+ is installed on your system
2. Download or clone the `archive_org_downloader.py` file
3. No additional packages need to be installed

### Usage

#### Basic Usage
Download all default file types (.txt, .cue, .bin) from an Archive.org item:

```bash
python archive_org_downloader.py https://archive.org/details/example-item
```

Or using just the Archive.org identifier:

```bash
python archive_org_downloader.py example-item
```

#### Advanced Options

**Specify a custom download directory:**
```bash
python archive_org_downloader.py example-item --download-dir /path/to/download
```

**Download specific file extensions:**
```bash
python archive_org_downloader.py example-item --extensions .txt,.pdf,.mp3
```

**Combine options:**
```bash
python archive_org_downloader.py https://archive.org/details/example-item --download-dir ./my-downloads --extensions .zip,.rar
```

### Arguments
- `url` (required): Archive.org item URL or identifier
- `--download-dir` (optional): Destination folder for downloads (default: `Download`)
- `--extensions` (optional): Comma-separated file extensions to download (default: `.txt,.cue,.bin`)

### Examples

1. **Download a specific CD/DVD image set:**
   ```bash
   python archive_org_downloader.py cdimage_collection_123
   ```

2. **Download only text files to a custom location:**
   ```bash
   python archive_org_downloader.py https://archive.org/details/textdocs --extensions .txt --download-dir ./texts
   ```

3. **Download multiple file types:**
   ```bash
   python archive_org_downloader.py videogame_roms --extensions .iso,.bin,.cue,.txt
   ```

### Output
The script will:
1. Display the Archive.org item identifier
2. Show the destination folder
3. List the file extensions being searched for
4. Display a progress bar for each file being downloaded
5. Report completed downloads or any errors encountered
6. Show a completion message

### How It Works

1. **Extracts the identifier** from the provided URL or uses the identifier directly
2. **Fetches metadata** from Archive.org's API to get the list of available files
3. **Filters files** based on the specified extensions
4. **Creates directories** as needed to preserve the original structure
5. **Downloads files** with a visual progress indicator
6. **Skips existing files** to avoid re-downloading

### Troubleshooting

**"Impossible d'extraire l'identifiant depuis l'URL"**
- Ensure you've provided a valid Archive.org URL or identifier
- Valid URLs: `https://archive.org/details/identifier` or `https://archive.org/download/identifier/...`

**"Impossible de récupérer les métadonnées archive.org"**
- Check your internet connection
- Verify the identifier is correct
- The Archive.org item might not be publicly available

**"Aucun fichier trouvé pour les extensions demandées"**
- The specified extensions don't exist in that Archive.org item
- Try using `--extensions` with different file types available in the item

**Files already exist**
- The script skips files that already exist locally
- Delete the files from your download folder if you want to re-download them

### Notes
- The script respects Archive.org's terms of service
- Downloads are limited by your internet connection speed
- The script creates the destination directory if it doesn't exist
- File permissions are preserved from the download

---

## Version Française

### Description
**Archive.org Downloader** est un utilitaire Python qui télécharge des types de fichiers spécifiques depuis des items Archive.org en préservant la structure de répertoires d'origine. Par défaut, il télécharge les fichiers `.txt`, `.cue` et `.bin`, mais vous pouvez personnaliser les extensions de fichiers à télécharger.

### Caractéristiques
- 🎯 Télécharge des types de fichiers spécifiques depuis Archive.org
- 📁 Préserve la structure de répertoires d'origine
- 📊 Barre de progression en temps réel pendant les téléchargements
- 🔄 Ignore les fichiers déjà téléchargés
- ⚙️ Extensions de fichiers personnalisables
- 🛡️ Gestion appropriée des erreurs et validation
- 🌐 Fonctionne avec les URL et les identifiants Archive.org

### Prérequis
- Python 3.7 ou supérieur
- Connexion Internet
- Aucune dépendance externe supplémentaire (utilise uniquement la bibliothèque standard Python)

### Installation
1. Assurez-vous que Python 3.7+ est installé sur votre système
2. Téléchargez ou clonez le fichier `archive_org_downloader.py`
3. Aucun package supplémentaire n'a besoin d'être installé

### Utilisation

#### Utilisation Basique
Téléchargez tous les types de fichiers par défaut (.txt, .cue, .bin) depuis un item Archive.org :

```bash
python archive_org_downloader.py https://archive.org/details/exemple-item
```

Ou en utilisant simplement l'identifiant Archive.org :

```bash
python archive_org_downloader.py exemple-item
```

#### Options Avancées

**Spécifiez un répertoire de téléchargement personnalisé :**
```bash
python archive_org_downloader.py exemple-item --download-dir /chemin/vers/telechargement
```

**Téléchargez des extensions de fichiers spécifiques :**
```bash
python archive_org_downloader.py exemple-item --extensions .txt,.pdf,.mp3
```

**Combinez les options :**
```bash
python archive_org_downloader.py https://archive.org/details/exemple-item --download-dir ./mes-telechargements --extensions .zip,.rar
```

### Arguments
- `url` (obligatoire) : URL ou identifiant d'un item Archive.org
- `--download-dir` (optionnel) : Dossier de destination pour les téléchargements (par défaut : `Download`)
- `--extensions` (optionnel) : Extensions de fichiers à télécharger séparées par des virgules (par défaut : `.txt,.cue,.bin`)

### Exemples

1. **Télécharger un ensemble d'images CD/DVD spécifique :**
   ```bash
   python archive_org_downloader.py cdimage_collection_123
   ```

2. **Télécharger uniquement les fichiers texte dans un dossier personnalisé :**
   ```bash
   python archive_org_downloader.py https://archive.org/details/textdocs --extensions .txt --download-dir ./textes
   ```

3. **Télécharger plusieurs types de fichiers :**
   ```bash
   python archive_org_downloader.py videogame_roms --extensions .iso,.bin,.cue,.txt
   ```

### Sortie
Le script va :
1. Afficher l'identifiant de l'item Archive.org
2. Afficher le dossier de destination
3. Énumérer les extensions de fichiers recherchées
4. Afficher une barre de progression pour chaque fichier téléchargé
5. Signaler les téléchargements complétés ou les erreurs rencontrées
6. Afficher un message de fin

### Fonctionnement

1. **Extrait l'identifiant** de l'URL fournie ou utilise directement l'identifiant
2. **Récupère les métadonnées** depuis l'API Archive.org pour obtenir la liste des fichiers disponibles
3. **Filtre les fichiers** en fonction des extensions spécifiées
4. **Crée les répertoires** selon les besoins pour préserver la structure d'origine
5. **Télécharge les fichiers** avec un indicateur de progression visuel
6. **Ignore les fichiers existants** pour éviter les re-téléchargements

### Dépannage

**"Impossible d'extraire l'identifiant depuis l'URL"**
- Assurez-vous que vous avez fourni une URL Archive.org ou un identifiant valide
- URL valides : `https://archive.org/details/identifier` ou `https://archive.org/download/identifier/...`

**"Impossible de récupérer les métadonnées archive.org"**
- Vérifiez votre connexion Internet
- Vérifiez que l'identifiant est correct
- L'item Archive.org n'est peut-être pas disponible publiquement

**"Aucun fichier trouvé pour les extensions demandées"**
- Les extensions spécifiées n'existent pas dans cet item Archive.org
- Essayez d'utiliser `--extensions` avec d'autres types de fichiers disponibles dans l'item

**Les fichiers existent déjà**
- Le script ignore les fichiers qui existent déjà localement
- Supprimez les fichiers de votre dossier de téléchargement si vous souhaitez les re-télécharger

### Notes
- Le script respecte les conditions d'utilisation d'Archive.org
- Les téléchargements sont limités par la vitesse de votre connexion Internet
- Le script crée le répertoire de destination s'il n'existe pas
- Les permissions de fichiers sont conservées depuis le téléchargement

---

## License
This project is provided as-is for personal and educational use.

## Support
For issues or questions, please check the troubleshooting section above or verify your Archive.org item URL.
