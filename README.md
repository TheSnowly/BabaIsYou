# BabaIsYou


Partie théorique:

1) Il s'agit un jeu d'énigme en 2D

2) Les mécaniques principales de jeu sont représentée par des mots qui, en formant des phrases, constituent les rêgles du jeu:
	- YOU -> un objet associé à ce mot est controlé par le joueur, il peut le déplacer dans les 4 directions (haut , bas, droite, gauche)
	- WIN -> un objet associé à ce mot est un objectif de victoire. Si le joueur le touche, il gagne.
	- STOP -> un objet associé à ce mot est impenetrable, le joueur et toute autre entités ne peuvent pas passer à traver.
	- PUSH -> un objet associé à ce mot peut être poussé par le joueur ou toute entité dans les 4 directions
	- SINK -> un objet associé à ce mot détruit tout objet passant sur lui MAIS l'objet associé est détruit en même temps
	- DEFEAT -> un objet associé à ce mot détruit tout joueur qui passe dessus
	- HOT -> un objet associé à ce mot détruit tout objet associé au mot MELT
	- MOVE -> un objet associé à ce mot bouge dans la direction qu'il face jusqu'à ce qu'il rencontre un mur. Dans ce cas, il inverse son sens de déplacement.

Chaque mot peut se faire pousser par toute entité ou joueur, une phrase ne peut que être formée en horizontal ou diagonale.

3) Le fait de pouvoir manipuler les rêgles du jeu par la formation de phrases, on peut voir ça comme une version extremement simplifiée d'un langage de programmation. Le but c'est aussi un peu de casser le jeu et ça c'est bien le propre d'un dev.

4) Pour qu'une phrase fonctionne, il faut qu'elle soit composée de 3 parties (1 partie objet (ROCK, BABA, KEKE, ect...), 1 mot de lien (IS, HAS, ect...) et 1 partie état (YOU, MOVE, PUSH, ect..) ou dans 1 autre partie objet)
un objet peut avoir un état, mais un état ne peut pas avoir un objet (voilà pourquoi YOU IS BABA ne marche pas par exemple).
une partie objet ou état peut possseder plusieurs mots, une partie objet peut être composée de BABA et de KEKE par exemple (BABA AND KEKE)

5) Chaque mot objet est un tableau contenant les objets de ce type présents dans le niveau
Chaque mot état est un blueprint/fonction qui peut s'attacher aux objets
Chaque objet récupère ce qu'il a en dessous de lui et à droite de lui à tout moment, si un mot de lien est récupéré par un mot objet, il vérifie qu'il est au début de la phrase et récupère tout les mots qui le suivent. Il applique enfin les état récupérés à tout les objets du tableau qu'il possède.

6) jeu de fou, qui va de plus en plus loin dans ses délires et qui utilise à fond tout ce que son concept permet. J'adore ce jeu dans tout ce qu'il propose mais je suis incapable de dépasser le 3ème monde depuis 2016.

Partie pratique:

1) la mécanique est: former des phrases qui dictent les rêgles

2) Création d'assets/tileset
   création de plusieurs data table contenant lmes différents assets du jeu afin de faciliter le changement au cours du jeu
   Les mots objets font des line trace en bas et à droite d'eux, tant qu'ils rencontrent des mots qui conviennent, il continuent.
   Dès qu'un line trace se stoppe, il applique l'états qu'il a trouvé sur sa route au tableau d'objets récupéré du premier mot de la phrase
   
   Je l'ai fait que pour le changement d'objet mais le code est facilement modifiable pour qu'il intègre des états aussi

3) former des phrases est ce qui constitue les énigmes du jeu, onse retrouve dans chaque niveau à essayé de bidouller avec les mots qu'on a pour faire des phrases qui nous amènerons à la victoire. C'est aussi ce qui fait toute l'identité du jeu, ce langage de programation simplifié qui est sans cesse renouvelé par de nouveaux mots et états.

4) C'est toujours trop cool de casser le jeu avec et de découvrir de nouveaux mots.
