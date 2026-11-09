# MdM Remote

Client de prise en main à distance de **Mdm-services.fr**, construit sur **RustDesk 1.5.3**
(© Purslane Tech Pte. Ltd. et contributeurs, licence **AGPL-3.0**, voir `LICENCE`). Ce dépôt publie le code source
complet de MdM Remote, comme l'exige l'AGPL.

## Modifications par rapport à RustDesk 1.5.3

- **Configuration compilée** (`mdm/custom.json`, chargée par `load_custom_client` dans `src/common.rs`) : serveur
  `remote.mdm-services.fr`, sa clé publique et l'API ; réglages serveur, proxy et WebSocket masqués ; pas de
  recherche de mise à jour officielle. Un `custom.txt` posé à côté du programme est ignoré.
- **Nom affiché « MdM Remote »** (`get_display_name` dans `src/common.rs`) : textes de l'interface, titre de fenêtre,
  info-bulle de la zone de notification, informations du fichier `.exe`. Le nom interne reste « RustDesk » : mêmes
  dossiers de configuration, même service Windows, donc un poste qui avait RustDesk garde son ID et son mot de passe.
- **Client personnalisé** (`is_custom_client` renvoie toujours vrai) : réglages par défaut des clients personnalisés
  de RustDesk, mises à jour officielles désactivées.
- **Interface aux couleurs MdM** : palette verte (`MyTheme` dans `flutter/lib/common.dart`), colonne gauche vert
  foncé avec ID et mot de passe en cartes (`desktop_home_page.dart`), carte de connexion arrondie
  (`connection_page.dart`), fenêtre « Autorisations » à en-tête vert et tuiles claires (`server_page.dart`), cartes des paramètres à plat
  et arrondies, barre d'outils de session et paramètres en vert (palette).
- **Icônes et logos** MdM Remote (`res/`, `flutter/assets/`, `flutter/windows/runner/resources/`).
- **Compilation** : `.github/workflows/mdm-build.yml` (Windows x64, non signé). Les autres workflows de RustDesk ont
  été retirés de cette branche.

Branche `mdm`, partie du tag `1.5.3` de https://github.com/rustdesk/rustdesk.
RustDesk est une marque de Purslane Ltd. ; MdM Remote n'est ni affilié au projet RustDesk ni soutenu par lui.
