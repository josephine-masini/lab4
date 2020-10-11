# Compte rendu lab4

Joséphine Masini

---

1. On crée un répertoire : ```mkdir lab4``` et on y clone l'énoncé du TP : ```git clone [url du lab4]``` . En parallèle, on crée un autre répertoire git, sur lequel on dépose le répertoire du lab4 avec le compte rendu, on peut ainsi faire régulièrement des commit. 

2.  La commande : ```history```, nous donne toutes les commandes tapées précédemment sur notre environnement de travail.

3. Pour redirigirer le contenu d'une commande dans un fichier : ```history > history.txt```, dans le répertoire où l'on se trouve. On commit ensuite : ```git add history.txt``` et ```git commit -m "questions 2 et 3"``` par exemple. ( On fera un git push à la fin du TP pour mettre à jour sur le git ) 

4. Pour concaténer des fichiers, on utilise ```cat sardar1.txt sardar2.txt sardar3.txt >> sardar_power.txt``` , on peut aussi faire plus simplement en étant dans le répertoire sardar : ```cat * >> sardar_power.txt``` , le ```*``` concaténant directement tous les fichiers du répertoire courant.

5. Pour connaître le nombre de lignes d'un fichier et d'autres infos relatives, on tape les commandes :

   ```wc -l sardar_power.txt``` => il y a 1980 lignes dans le fichier ```sardar_power.txt``` ;

   ```wc -w sardar_power.txt``` => il y a 16783 mots dans le fichier ```sardar_power.txt``` ;

   ```wc -m sardar_power.txt``` => il y a 101778 caractères dans le fichier ```sardar_power.txt``` .

6.  On utilise la commande ``` grep -wi "singh" sardard_power.txt``` . On obtient l'affichage suivant : 

![Résultat de la commande](capture1.png)

7. On utilise la commande : ```rm sardar_power.txt``` , pour supprimer le fichier en étant dans le répertoire sardar.

8. Toujours dans le répertoire sardar, on tape : ```grep  -wi "singh" *``` et on obtient l'affichage suivant :

![Résultat de la commande](capture2.png)

9. On reprend la commande précédente : ```grep  -wi "singh" * | wc -l``` , en lui ajoutant ```wc  -l``` après ```|```, ce qui permet de prendre le résultat d'une commande, et d'y ajouter une tâche à réaliser directement sur le contenu de celle-ci. On a trouvé le mot singh dans 117 lignes, parmis les 3 fichiers confondus du répertoire sardar.

10. On procède de la même manière pour avoir le résultat de la commande précédente auquel on applique une autre commande : ```grep -i "singh" * | grep -i "santa" | wc -l``` , ce qui nous donne 42 lignes où l'on trouve les mots singh et santa sur la même.

11. On enlève la correspondance avec le mot banta : ```grep -i "singh" * | grep -i "santa" | grep -vi "banta" | wc -l``` . On a 26 lignes correspondant à ces critères.

12. On se place dans le répertoire demandé en faisant ```cd .. ``` , on tape la commande : ```find . -name "*.txt"``` , ce qui nous donne :

    ```./answering-machine.txt```
    ```./history.txt```
    ```./sardar/sardar3.txt```
    ```./sardar/sardar1.txt```
    ```./sardar/sardar2.txt```

    Tous les fichiers ```.txt``` du répertoire 5AS05-partie4.

13. Pour copier un fichier dans un répertoire parent : ```cp answering-machine.txt ../test-commande-locat.txt``` . Quand on tape  ```locate test-commande-locat.txt``` , il ne se passe rien, le fichier est introuvable.

14. On fait : ```sudo updatedb```, et on relance la commande précédente, on obtient alors :

    ```/home/panda/Bureau/lab4/test-commande-locat.txt``` , le fichier a été correctement localisé. Il a donc fallu mettre à jour la localisation des fichiers avant d'avoir accès à celui-ci juste après sa création.

15. On retourne dans le répertoire du TP, et on affiche les différences entre les 2 fichiers : 

    ```diff noyau.v1 noyau.v2 ``` et pour créer le patch : ```diff noyau.v1 noyau.v2 > update.patch```.

16. On applique ensuite le patch à noyau.v1 : ```patch noyau.v1 < update.patch``` , on a comme résultat :

    ```patching file noyau.v1``` et on retape ```diff noyau.v1 noyau.v2```, pour vérifier qu'il n'y a plus de différence entre les 2 fichiers. Ce aui est le cas, car cette commande ne renvoit rien.

