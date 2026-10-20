# Bataille Navale RISC-V / RISC-V Battleship

*🇫🇷 Le texte en français se trouve dans la seconde moitié de ce document.*
*🇬🇧 The English text is located in the first half of this document.*

## 🇬🇧 English Version

**Overview:**
A Player vs. Computer Battleship mini-game written entirely in RISC-V assembly language. This project was developed individually for a computer architecture course.

### Features
* **Player vs. Computer:** Play against an AI that randomly places its ships and randomly targets your grid (without shooting the same spot twice).
* **Grid:** 4x4 interactive grid (coordinates X and Y from 0 to 3).
* **Two Difficulty Levels:**
  * **Beginner (1):** Includes a "Radar" feature. If you shoot and miss, the game will warn you if there is an enemy ship on an adjacent square (up, down, left, or right).
  * **Expert (2):** No radar assistance.
* **Ship Count:** 3 ships per player.

### Requirements & Installation

This program requires **RARS** (RISC-V Assembler and Runtime Simulator) to compile and run.

1. Download [RARS](https://github.com/TheThirdOne/rars).
2. Ensure you have Java installed on your machine to run the `.jar` file.

### Execution

1. Open RARS.
2. Open the source code file (`.s` or `.asm`).
3. Assemble the code (`F3` or Run > Assemble).
4. Run the program (`F5` or Run > Go).
5. Interact with the game via the **Run I/O** console at the bottom of the screen.

### Technical Documentation

The game represents the 4x4 grid as a 1D array of 16 bytes in memory.
**Grid State Encoding:**
* `0`: Water (no ship)
* `1`: Intact Ship
* `2`: Miss (Water hit)
* `3`: Hit (Ship destroyed)

**Main Functions:**
* `initialiser_grille`: Initializes the 16-byte grid arrays to 0.
* `demander_coordonnee`: Prompts the user for a coordinate (0-3) and handles input validation.
* `calculer_index`: Converts 2D coordinates (X, Y) into a 1D array index (`Index = (X * 4) + Y`).
* `verifier_tir`: Checks the targeted index, updates the grid state (2 or 3), and returns 1 if a ship was hit, 0 otherwise.
* `verifier_proximite`: Used in Beginner mode to check adjacent cells (handling grid boundaries) and alerts the player if a ship is nearby.

---

## 🇫🇷 Version Française

**Présentation :**
Mini-jeu de Bataille Navale (Joueur contre Ordinateur) programmé entièrement en assembleur RISC-V. Ce projet a été réalisé de manière individuelle dans le cadre d'un module d'architecture des ordinateurs.

### Fonctionnalités
* **Joueur contre IA :** Affrontez l'ordinateur qui place aléatoirement sa flotte et tire de manière aléatoire (sans jamais tirer deux fois sur la même case).
* **Grille :** Grille de jeu de 4x4 (coordonnées X et Y allant de 0 à 3).
* **Deux niveaux de difficulté :**
  * **Débutant (1) :** Intègre un "Radar". Lorsqu'un tir atterrit dans l'eau, le jeu vous indique si un bateau adverse se trouve sur une case adjacente (haut, bas, gauche, droite).
  * **Expert (2) :** Aucune aide au tir.
* **Flotte :** 3 bateaux par camp.

### Prérequis & Installation

Ce programme nécessite **RARS** (RISC-V Assembler and Runtime Simulator) pour être assemblé et exécuté.

1. Télécharger [RARS](https://github.com/TheThirdOne/rars).
2. Assurez-vous d'avoir Java installé sur votre machine pour lancer le fichier `.jar`.

### Exécution

1. Ouvrez RARS.
2. Ouvrez le fichier contenant le code source (`.s` ou `.asm`).
3. Assemblez le code (`F3` ou Run > Assemble).
4. Lancez le programme (`F5` ou Run > Go).
5. Interagissez avec le jeu via la console **Run I/O** en bas de l'écran.

### Documentation Technique

Le jeu représente la grille 4x4 sous forme d'un tableau à une dimension de 16 octets en mémoire.
**Encodage de la grille :**
* `0` : Eau (aucun bateau)
* `1` : Bateau intact
* `2` : Tir dans l'eau (manqué)
* `3` : Bateau touché (détruit)

**Fonctions Principales :**
* `initialiser_grille` : Initialise les 16 octets des tableaux à 0.
* `demander_coordonnee` : Demande une coordonnée (0-3) à l'utilisateur avec gestion des erreurs de saisie.
* `calculer_index` : Transforme les coordonnées 2D (X, Y) en un index de tableau 1D (`Index = (X * 4) + Y`).
* `verifier_tir` : Vérifie la case ciblée, met à jour son état (2 ou 3) et renvoie 1 si touché, 0 sinon.
* `verifier_proximite` : Utilisée dans le mode débutant pour vérifier les cases adjacentes (en gérant les bords de la grille) et afficher un message d'aide.
