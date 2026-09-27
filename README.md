# Émulateur 64 — Commodore 64 dans le navigateur

Émulateur Commodore 64 **complet en un seul fichier HTML** (aucune dépendance, polices incluses) : ouvrez `emulateur-64.html` dans un navigateur, sur ordinateur comme sur smartphone.

**En ligne : https://emulateur64.lhusser.fr**

## Fonctionnalités

### Modes système
- **BASIC V2 réécrit** (mode par défaut) : interpréteur complet en JavaScript — PRINT, INPUT, GET, FOR/NEXT, GOSUB, ON…GOTO, DEF FN, POKE/PEEK, LOAD/SAVE, LIST, avec les erreurs et la tokenisation d'origine
- **ROM d'origine** : chargez vos fichiers BASIC/KERNAL (8 Ko ou 16 Ko combinés) et CHARGEN (4 Ko) dans le menu Système — le vrai BASIC et le vrai KERNAL tournent sur le CPU émulé. Bouton « Charger depuis le serveur » pour les récupérer d'un point de sécurité (BasicAuth)
- **Lecteur 1541 matériel** : émulation au niveau du firmware — le vrai DOS 1541 (ROM 16 Ko par moitiés $C000/$E000) tourne sur son propre CPU via le bus IEC bit par bit, avec décodage GCR natif. Loadeurs rapides et protections d'époque, format .g64 en lecture et export
- **Synchro écran** : cadence PAL exacte sur écran 50/100 Hz (une image C64 par rafraîchissement, vitesse réelle, défilements fluides), SID rescalé automatiquement
- **Open ROMs** inclus (libre, GNU LGPL v3, © MEGA65) — expérimental

### Matériel émulé
- **CPU 6510** : jeu d'instructions complet (+ illégales, décimal), timing au cycle près (page-crossing, RMW double écriture)
- **VIC-II** : balayage ligne par ligne, texte/multicolore/bitmap/ECM, défilement fin, **sprites** (8, multi-couleurs, agrandissement, priorités, collisions sprite↔sprite et sprite↔fond), IRQ raster, banques mémoire VIC
- **2 × CIA 6526** complets : timers A/B, TOD en BCD, IRQ/NMI, matrice clavier
- **SID 6581** synthétisé échantillon par échantillon : 3 voix (triangle/scie/impulsion/bruit LFSR), sync, ring mod, enveloppes ADSR d'époque, filtre multicouche avec résonance
- Joystick port 1 ou 2 (commutable), lu par le CIA

### Supports
- **Disquettes .d64** (35/40 pistes) : lecture **et écriture** (`SAVE` modifie l'image, téléchargeable ensuite), répertoire réel, lecteurs 8 (image) et 9 (disquette navigateur persistante)
- **Cassettes .t64** (archives) et **.tap** (flux bit-level via le flag CIA, mode warp)
- **Cartouches .crt** : normales 8/16 Ko, Ultimax, Ocean, Magic Desk, System 3, Dinamic, Fun Play, Super Games, Simons' BASIC, EasyFlash
- Import/export de listings BASIC et de fichiers .prg

### Interface
- Écran 40×25 avec effet tube CRT (scanlines, vignette), 16 couleurs
- Clavier graphique complet, éditeur plein écran, RUN/STOP, RESTORE, F1-F8
- Turbo (accélération), bouton Joystick, menus Programmes (7 démos), Disquettes, Importer, Exporter, Système, Aide
- Thème clair/sombre, responsive mobile (PWA-ready), tout en français

### Limites
- Affichage exact à la ligne près, pas au cycle près (pas de bordures ouvertes ni de défilement fin en cours de ligne)
- Pas de filtres SID physiques au composant près

## Tests

L'émulateur a été validé sur du contenu d'époque : compilation « Oldies & Goldies (IPC) » (langage machine + IRQ raster + multicolore), programmes BASIC, disquettes .d64 faites main, cassettes .t64.

## Licence

- Code de l'émulateur : licence libre (GPL v3, cohérente avec Open ROMs inclus)
- Open ROMs : © Paul Gardner-Stephen, Roman Standzikowski — GNU LGPL v3 — [github.com/MEGA65/open-roms](https://github.com/MEGA65/open-roms)

---

*Développé en collaboration avec Hermes (agent IA) — itérations V1 → V3.8 en 2026.*