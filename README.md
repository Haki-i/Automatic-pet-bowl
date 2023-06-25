# Automatic-pet-bowl

# **Objectif du projet**

L’objectif est de modéliser une gamelle pour animaux en 3D. Cette gamelle doit également être automatique et se déclencher à certains intervalles de temps précis.

# I- **Modélisation 3D**

## a) Bloc principal

Pour modéliser un objet de cette taille, il a fallu le décomposer en plusieurs éléments puis venir les assembler ensemble. 

- Le matériau utilisé est le PLA.
- Le temps nécessaire est de 12h00 pour le bloc principal.
- Le bloc est un cube de 10cm de côté .

![Image1](https://user-images.githubusercontent.com/92324336/139713631-d639aa89-8577-435a-a0ba-eaf5f5679d47.png)

![Image2](https://user-images.githubusercontent.com/92324336/139713645-4869f250-7662-4f96-969a-2aacf4df4efa.png)

Sa partie inferieure est constituée d’une **pente** permettant le glissement des croquettes jusqu’à la zone accessible pour les animaux (non visible).

Sur son coté droit, une **fente** permet de glisser la trappe ce qui permettra aux croquettes de descendre ou non.

Les deux trous au sommet ont des rôles différents : l’un permet de voir le mécanisme et sera fermé par un **toit**, l’autre est formé d’une **pente** pour mettre les croquettes et que celles-ci puissent glisser jusqu’à a trappe.

Un **mur** sépare les deux zones pour que les croquettes allant se déposer sur la trappe ne soit pas trop nombreuses et ne surchargent pas le mécanisme

![Image3](https://user-images.githubusercontent.com/92324336/139713659-ede1eb55-d2e8-4342-aa84-455c9b9d815b.png)


La **longue fente** de forme cylindrique à l’arrière devait permettre à l’ouverture de la trappe de fonctionner comme une porte par méthode du gond : uniquement une partie de la trappe devait s’affaisser tendis que l’autre restait droite. Apres réalisation de la structure en 3D, cette technique n’a pas fonctionné comme souhaité.

Les pavés droits dans la fente servent de piliers et permettent de faire fonctionner l’impression 3D correctement en ne laissant pas de vide.

Le **trou sur le coté** permet de placer un servomoteur et de le coller sur la trappe pour mouvoir celle-ci.

## b) Eléments secondaires

![Image4](https://user-images.githubusercontent.com/92324336/139713680-45be5f0c-636d-4fa2-a3ff-32e34b36fcdb.png)

- Le 1er élément visible est la **gamelle**, la zone où des croquettes arrivent et sont accessibles pour les animaux. Elle vient se coller sur la face du bloc principal.
- Le 2ème élément est un **supplément de hauteur** pour la pente du haut : Après réalisation de la structure 3D, la pente n’était pas assez raide pour faire descendre correctement les croquettes.
- Le 3ème élément est une **fermeture** sur la face du bloc

 ![Image5](https://user-images.githubusercontent.com/92324336/139713758-6466276e-53d2-4478-a894-20cac5c898fd.png)

Le **toit** permet de cacher le mécansime et la **trappe** vient se glisser dans le trou situé sur le coté du bloc. 

# II- **Mécanisme de la trappe**

La trappe s’abaisse pour faire descendre les croquettes puis remonte pour bloquer les suivantes.

Un chronomètre est lancé au branchement du mécanisme : toutes les 5h, la trappe s’abaisse pendant 3 secondes puis remonte. Le chronomètre est ensuite reinitialisé et ainsi de suite.

On déclare tout d’abord les élements necessaires au servomoteur.

On déclare également deux variables : **times et previous** qui vont permettre de lancer un chronomètre et de le réinitialiser.

`times=millis()` permet de lancer un chronometre dès que le système démarre.

`times=times-previous` permet de reinitialiser le chronomètre lorsque, plus tard, previous aura pris la valeur de times.

Une condition tourne le servomoteur de 40 degrés puis attend 3 secondes et le remonte jusqu’à 0 degré. Lorsque la condition est remplie, il faut que le chronomètre se réinitialise.

# Rendu final 

![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/92324336/139714917-4bc87b61-6a8e-4eb2-909e-73fd548a588d.gif)
