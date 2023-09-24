# Jeu de Dames Serveur

Bienvenue dans le projet Jeu de Dames Serveur, un environnement où des robots peuvent jouer aux dames et lancer des défis les uns aux autres. Les résultats et les annotations des parties sont enregistrés sur un serveur écoutant sur le port 5777 de l'adresse IPv6 [2001:910:1410:523:0:fada:80af:2bc2].

## Description du Projet

Le projet consiste à développer deux types de robots : un robot "attaquant" qui lance des défis régulièrement, et un robot "défenseur" qui répond aux défis. Pour commencer, un robot "défenseur" est déjà fourni sur le port 7777 de l'adresse IPv6 [2001:910:1410:523:0:fada:80af:2bc2]. 

## Règles du Jeu

Les règles du jeu sont similaires à celles que l'on peut trouver sur Internet, avec quelques variantes. Il est important de noter les règles spécifiques suivantes :

- Les joueurs ne peuvent pas abandonner la partie ; elle doit aller jusqu'au bout.
- L'égalité est déclarée après 100 coups depuis le début en tout, ce qui équivaut à 50 coups par joueur.
- L'obligation de prise est en vigueur : un joueur doit capturer autant de pièces que possible lorsqu'il a plusieurs options de capture.
- Les règles de notation Manoury sont utilisées pour numéroter le plateau.

## Protocole de Jeu

Lorsqu'un robot attaquant se connecte au serveur d'un robot défenseur via le port 7777, la connexion est considérée comme un défi, et la partie commence immédiatement. Le défenseur joue automatiquement en blanc, tandis que l'attaquant joue en noir.

Les mouvements sont communiqués sous forme de texte. Les déplacements d'un pion ou d'une dame sont notés en chiffres séparés par un tiret (par exemple, 32-27 pour un déplacement de la case 32 à la case 27). Les captures sont notées en utilisant "x" pour indiquer les positions intermédiaires (par exemple, 26x17x8x19 pour une prise de 3 pions).

Le jeu peut se terminer de trois manières : "PERDU" (si un joueur n'a plus de mouvements possibles), "EGALITE" (en cas d'égalité), ou "INTERRUPTION" (en cas de problème imprévu).

## Protocole d'Enregistrement de la Partie

Pour enregistrer une partie, une connexion doit être établie avec le serveur dédié, et un message binaire de 256 octets doit être envoyé. Le serveur de rendu répondra avec l'un des messages suivants : "ERR", "ACC", "TIM", etc.

## Compilation et Exécution
`make All`



