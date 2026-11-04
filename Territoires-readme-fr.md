# Territoires — Règles du jeu

Jeu de plateau en ligne, de 2 à 4 joueurs, au tour par tour, sur un seul écran (les joueurs se passent la souris). Chaque couleur peut être jouée par un humain ou par l'ordinateur.

> Version du prototype : les valeurs entre parenthèses sont les réglages actuels. Elles sont modifiables dans le jeu (objet `CONFIG`).

---

## 1. But du jeu

Étendre son territoire en posant des blocs, ouvrir ses coffres pour obtenir des canons, constituer une armée et **prendre la Capitale des adversaires**.

Un joueur est **éliminé** si sa Capitale est prise (voir §6). La partie se termine quand il ne reste plus qu'un joueur en lice (voir §10).

---

## 2. Mise en place

### Plateau (choisi au lancement)

| Taille | Durée | Remarque |
|---|---|---|
| 20 × 20 | partie courte | |
| 30 × 30 | partie moyenne | |
| 60 × 60 | partie longue | idéale à 4 joueurs |

### Joueurs

- De 2 à 4 joueurs, chacun avec sa couleur : **Orange**, **Bleu**, **Violet**, **Jaune**.
- Chaque joueur peut recevoir un prénom (facultatif). Sans prénom, la couleur sert de nom.
- Chaque couleur est jouée par un **Humain**, un **Ordinateur (facile)** ou un **Ordinateur (moyen)**.
- Le premier joueur est **tiré au hasard**.

### Coins de départ

| Couleur | Coin |
|---|---|
| Orange | haut-gauche |
| Bleu | bas-droite |
| Violet | haut-droite |
| Jaune | bas-gauche |

À 2 joueurs, Orange et Bleu (coins opposés) sont utilisés.

### Coffres

- Chaque joueur a **2 coffres**, dessinés à sa couleur, placés au hasard sur le plateau.
- Ils sont éloignés des coins de départ (au moins 40 % de la taille du plateau) et espacés entre eux (au moins 20 %).
- Chaque coffre contient **1 canon**, et rien d'autre.
- Un coffre occupe une case et **bloque tout le monde** : on ne peut pas poser dessus.
- Tous les coffres ont la même icône : on ne voit pas ce qu'ils contiennent.

---

## 3. Les blocs

La valeur d'un bloc est **sa surface** (largeur × hauteur).

| Bloc | Taille | Points |
|---|---|---|
| **Bloc** | 1 × 1 | 1 |
| **Base** | 2 × 2 | 4 |
| **Village** | 3 × 3 | 9 |
| **Forteresse** | 2 × 4 (pivotable en 4 × 2) | 8 |
| **Canon** | 1 × 1 | 1 |

- La **Forteresse** n'apparaît qu'à partir du **tour 15** : dès qu'un joueur commence son 15ᵉ tour, elle est disponible pour tous.
- Les blocs sont en nombre illimité.
- Les blocs non carrés peuvent être pivotés (touche **R** ou clic droit).

### Première pièce : la Capitale

- La **première pièce** de chaque joueur est **obligatoirement un Village 3 × 3** posé sur son **coin de départ**.
- Ce premier Village est la **Capitale** du joueur. Elle est repérée par une **étoile dorée** au centre.
- Il est impossible d'agrandir ce premier Village (pas de villageois à ce stade).

### Règle de pose

- Une pièce **ne peut pas** être posée sur une case occupée (bloc ou coffre) ni en dehors du plateau.
- Une pièce doit **toucher un de ses propres blocs**, par un **côté ou par un coin**.
- Les points d'aide, à la couleur du joueur, montrent les cases où l'on peut poser (désactivables). Une pièce qui survole le plateau devient **verte** si la pose est possible, **rouge** sinon, avec la raison affichée.

### Le Canon (cas particulier)

- Un canon est une pièce 1 × 1 que l'on **pose où l'on veut**, **sans toucher ses autres blocs**.
- **Interdit** : poser un canon à portée de la Capitale d'un adversaire encore en jeu. La zone interdite est la zone de tir du canon, tracée en rouge pointillé quand le canon est sélectionné.
- Un canon posé compte comme un bloc du joueur : on peut ensuite poser des blocs contre lui.

---

## 4. L'armée

### Recrutement

- Au **début de son 4ᵉ tour** (après 3 tours joués), puis **tous les 3 tours** (tours 4, 7, 10, 13…), chaque joueur recrute un personnage.
- Il choisit entre **Soldat** et **Villageois**.

### Les personnages

| Personnage | Attaque | Défense | Particularité |
|---|---|---|---|
| **Soldat** | +1 | +1 | Recrutement au choix |
| **Villageois** | 0 | **+2** | Permet d'agrandir un côté des blocs (voir plus bas) |
| **Archer** | +1 | 0 | 1 archer pour chaque **Forteresse** possédée |
| **Cavalier** | +1 | 0 | Offert tous les 6 tours ; se déplace et attaque (voir §7) |

### Force

- **Force d'attaque** d'un joueur = soldats + archers + cavaliers.
- **Défense** d'un joueur = soldats + (2 × villageois).

Ces valeurs sont affichées pour chaque joueur dans le panneau de droite (par exemple « Att 4 · Déf 7 »).

### Agrandir les blocs avec les villageois

Chaque villageois permet d'**agrandir un côté** des blocs que l'on pose. Avec *v* villageois, on peut choisir un multiplicateur de 1 (taille normale) jusqu'à **1 + v**. Le multiplicateur s'applique au côté le plus court (au côté de hauteur si le bloc est carré).

| Bloc | 1 villageois (×2) | 2 villageois (×3) | 3 villageois (×4) |
|---|---|---|---|
| Bloc 1 × 1 | 1 × 2 | 1 × 3 | 1 × 4 |
| Base 2 × 2 | 2 × 4 | 2 × 6 | 2 × 8 |
| Village 3 × 3 | 3 × 6 | 3 × 9 | 3 × 12 |
| Forteresse 2 × 4 | 4 × 4 | 6 × 4 | 8 × 4 |

- Les villageois **ne sont pas consommés** : on les garde pour tous les tours suivants.
- On peut choisir un multiplicateur plus petit que le maximum. Le choix revient à « Normale » à chaque tour.
- La valeur d'un bloc agrandi reste sa surface (par exemple 3 × 6 = 18 points).

---

## 5. Coffres et canons

- Un coffre s'**ouvre** quand un bloc de son propriétaire le touche, **par un côté ou par un coin**, y compris après la capture d'un bloc voisin.
- À l'ouverture, une fenêtre annonce le gain : **+1 canon**, que le joueur pose quand il veut (c'est une pièce à poser, comme les blocs).
- Les adversaires peuvent **bloquer l'accès** à un coffre en occupant les cases autour.
- Les coffres d'un joueur éliminé ne s'ouvrent plus.

### Tir du canon

- Une fois par tour, chaque canon peut **tirer** sur un bloc adverse (bouton « Tirer » ou touche **T**).
- La **case visée** doit se trouver dans le **carré de portée** centré sur le canon :

| Plateau | Zone de tir du canon |
|---|---|
| 20 × 20 | 5 × 5 cases |
| 30 × 30 | 7 × 7 cases |
| 60 × 60 | 13 × 13 cases |

- Le tir est un **combat** (voir §6). Si le tireur gagne, il prend **le bloc visé en entier**. S'il perd, **il ne perd rien**.
- Tirer ne termine pas le tour : on peut ensuite poser un bloc.

### La Forteresse tire aussi

- Chaque Forteresse peut tirer **comme un canon**, avec le même rayon d'action, mesuré à partir des bords de la Forteresse, une fois par tour.

### Canon posé contre l'adversaire

- Si l'on pose un canon contre des blocs adverses, il les **attaque** (combat normal). S'il perd, **il n'est pas perdu** : un canon qui attaque reste à son propriétaire.
- Si un adversaire pose un bloc contre un canon, le canon se **défend** comme les autres blocs ; s'il perd, l'adversaire le prend.

---

## 6. Combats

### Quand a lieu un combat ?

Quand un joueur **pose un bloc qui touche** (par un côté ou un coin) **un bloc adverse**. Un combat a lieu contre **chaque adversaire touché**.

### Résolution

- On compare la **force d'attaque** de celui qui pose à la **défense** de l'adversaire.
- Le plus fort gagne.
- **Égalité : chacun lance un dé** (un bouton « Lancer » par joueur, avec une petite animation). Le plus grand chiffre gagne. En cas de nouvelle égalité, on relance.
- Quand un joueur humain affronte l'ordinateur, l'ordinateur lance son dé tout seul.

### Conséquences

- **L'attaquant gagne** : il prend tous les blocs de cet adversaire qui touchent la pièce posée. Ces blocs changent de couleur.
- **Le défenseur gagne** : il prend le bloc que l'attaquant vient de poser, qui change de couleur. (Exception : un canon posé reste à son propriétaire.)
- Les combats gagnés sont comptés pour chaque joueur.

### La Capitale

- Si la **Capitale** (le premier Village, marqué d'une étoile) est prise par un adversaire, **son propriétaire est éliminé**.
- Un avertissement apparaît quand une Capitale est en jeu (aide au survol et fenêtre de combat).
- À 2 joueurs, la prise de la Capitale **met fin à la partie**.

### Forteresse capturée

- Quand une Forteresse change de camp par capture, elle devient un **simple bloc** de la couleur du vainqueur : seuls ses points comptent.
- Elle **perd son archer et sa capacité de tirer**, et son ancien propriétaire perd l'archer.
- Si le joueur qui l'avait posée la **reprend**, elle **redevient une Forteresse** (archer et tir rétablis).

---

## 7. Le cavalier

- Chaque joueur reçoit **automatiquement un cavalier tous les 6 tours** (tours 6, 12, 18…). Une fenêtre annonce qu'un joueur possède un cavalier.
- Le cavalier apporte **+1 en attaque**.
- Il **démarre au centre de la Capitale** (ou sur la case la plus proche si elle est occupée).
- Il agit avec le bouton « Cavalier » (touche **C**) : on clique d'abord sur le cavalier, puis sur une case verte ou sur une cible.

### Déplacement

- Jusqu'à **3 pas** (8 directions, diagonales comprises).
- Il ne passe et ne s'arrête que sur **des cases de la couleur du joueur**.
- Il ne peut pas s'arrêter sur un autre cavalier.

### Attaque

- Il peut attaquer un bloc adverse dont la **case visée est à 3 cases au plus** (carré de 7 × 7 autour de lui).
- C'est un combat normal. S'il perd, il ne perd rien.

### Limites

- **Une seule action par tour** par cavalier : déplacement **ou** attaque.
- Si la **case où se trouve un cavalier est prise** par un adversaire, le cavalier est **perdu**.

---

## 8. Déroulement d'un tour

1. **Fenêtres d'information** éventuelles : recrutement (aux tours prévus), cavalier offert, coffre ouvert.
2. **Tirs** (facultatif) : canons et Forteresses, une fois chacun.
3. **Cavaliers** (facultatif) : déplacement ou attaque, une action chacun.
4. **Pose d'une pièce** : un bloc ou un canon. Si un combat est déclenché, il est résolu avant la fin du tour.
5. Ou **passer son tour** (avec confirmation).

Les coffres touchés par un bloc du propriétaire s'ouvrent à la fin de l'action.

---

## 9. Passer son tour, être bloqué, éliminations

### Passer

- Si un joueur ne pose **aucune pièce** pendant **3 tours de suite** (en passant), il est **éliminé**.
- Poser une pièce remet le compteur à zéro. Le panneau affiche l'avertissement dès le premier tour passé.

### Joueur bloqué

- Un joueur est **bloqué** quand il ne peut plus rien poser (aucune case libre à côté de ses blocs, ni canon en réserve).
- Une fenêtre lui propose de **quitter la partie** (éliminé tout de suite) ou de **passer** son tour (comptabilisé comme tour passé). S'il peut encore tirer ou déplacer un cavalier, il peut jouer son tour.
- **À 2 joueurs, si l'un des deux est bloqué, la partie s'arrête** (voir §10).

### Éliminations

Un joueur est éliminé dans trois cas :
1. Sa **Capitale** est prise.
2. Il passe **3 tours de suite**.
3. Il **quitte** la partie.

Un joueur éliminé :
- ne joue plus (on passe son tour) ;
- garde ses blocs sur le plateau, **assombris** ;
- voit ses blocs **pris sans combat** par tout joueur qui pose un bloc contre eux ;
- perd ses cavaliers ; ses coffres ne s'ouvrent plus.

---

## 10. Fin de la partie

La partie s'arrête quand :
- **un seul joueur** reste en lice (les autres sont éliminés) ; ou
- **moins de deux joueurs** peuvent encore jouer (par exemple, un seul joueur peut encore poser une pièce) ; ou
- les joueurs choisissent de **terminer la partie** (bouton, avec confirmation).

### Score

- Le **score** d'un joueur est la **valeur des blocs qu'il possède** (surfaces, plus 1 point par canon posé).
- Un bloc pris à un adversaire apporte ses points au nouveau propriétaire.
- Les coffres ne rapportent pas de points : ils donnent des canons.

### Classement et victoire

- S'il ne reste qu'un joueur en lice, **il gagne**.
- Sinon, le gagnant est le joueur en lice qui a le **plus de points**. En cas d'égalité, la victoire est partagée.
- Les joueurs éliminés sont classés après les autres, le dernier éliminé étant le mieux classé.

L'écran de fin affiche, pour chaque joueur : points, blocs, coffres ouverts, combats gagnés, tours joués, soldats, villageois, archers, cavaliers, canons, combats gagnés par canon, et la **durée de la partie**.

---

## 11. Jouer contre l'ordinateur

Chaque couleur peut être confiée à l'ordinateur, avec deux niveaux.

| Niveau | Comportement |
|---|---|
| **Facile** | Pose plus au hasard, ignore la plupart des combats, tire une fois sur deux, ne déplace pas ses cavaliers |
| **Moyen** | Cherche les prises de blocs gagnantes, évite les combats perdus d'avance, vise ses coffres, pose les Forteresses dès qu'elles sont disponibles, charge avec ses cavaliers, se rapproche de la Capitale adverse, recrute plus de villageois quand sa défense est dépassée |

Particularités :
- Il joue avec une petite pause entre chaque action.
- Pendant son tour, les commandes humaines sont désactivées.
- Il lance seul ses dés dans les égalités.
- Un ordinateur bloqué quitte la partie s'il ne peut plus rien faire.
- Un niveau « difficile » est prévu plus tard.

---

## 12. Commandes

| Action | Souris / écran tactile | Clavier |
|---|---|---|
| Choisir un bloc | boutons du panneau | **1** Bloc · **2** Base · **3** Village · **4** Forteresse · **5** Canon |
| Pivoter | bouton « Pivoter » ou clic droit | **R** |
| Agrandir (villageois) | menu « Taille des blocs » | **D** |
| Tirer (canon, Forteresse) | bouton « Tirer » | **T** |
| Cavalier | bouton « Cavalier » | **C** |
| Annuler un mode | clic droit | **Échap** |
| Poser | clic | — |

Sur **mobile** : un premier toucher place l'aperçu, un second toucher au même endroit pose la pièce.

Le panneau latéral affiche : le joueur actif, le numéro de son tour, le prochain recrutement, le temps de jeu, la force de chaque joueur, les armées, les canons, les combats gagnés et un journal des événements. Une option permet de masquer les points d'aide et les sons.

---

## 13. Réglages principaux

| Réglage | Valeur actuelle |
|---|---|
| Coffres par joueur | 2 (1 canon chacun) |
| Premier recrutement | tour 4 |
| Fréquence de recrutement | tous les 3 tours |
| Force d'un soldat | attaque +1, défense +1 |
| Force d'un villageois | défense +2 |
| Force d'un archer | attaque +1 |
| Force d'un cavalier | attaque +1 |
| Cavalier offert | tous les 6 tours |
| Déplacement du cavalier | 3 pas, sur ses cases |
| Portée d'attaque du cavalier | 3 cases |
| Portée du canon | zone 5 × 5 / 7 × 7 / 13 × 13 (selon le plateau) |
| Valeur d'un canon posé | 1 point |
| Déblocage de la Forteresse | tour 15 |
| Tours passés avant élimination | 3 |
| Dé de départage | 6 faces |

---

## 14. Points en observation

Ces points ne sont pas figés et seront ajustés en jouant :

- **Protection de la Capitale** : seuls les canons sont interdits à sa portée. Les cavaliers, les Forteresses et les poses collées peuvent la viser.
- **Poids des archers et des cavaliers** : ils donnent un avantage important à celui qui prend de l'avance sur les Forteresses.
- **Fréquence des dés** : fréquente tant que les armées sont petites.
- **Niveau « difficile »** de l'ordinateur, à ajouter plus tard.
