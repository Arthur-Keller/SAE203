# Guide de conversion et configuration avec Pandoc

- [Pandoc](https://pandoc.org/installing.html)  est un logiciel libre de conversion de documents 
numériques en ligne de commande développé par John MacFarlane en Haskell et publié sous licence GPL.
  
Dans notre cas, nous souhaitons effectuer des conversions de **.md** à **.html** et de **.md** à **.html**. Pour cela, nous devons tout d'abord installer le paquetage [LaTeX](https://packages.debian.org/sid/texlive-latex-recommended). Nous pouvons l'installer la commande suivante :
```
sudo apt install texlive-latex-recommended
```
- Ensuite nous allons nous occuper du paquet de [pandoc](https://packages.debian.org/fr/sid/pandoc) avec la commande suivante :
```
sudo apt install pandoc
```

Une fois l'installations des paquets réalisés, nous pouvons effectuer nos conversions :

### Pour passer de Markdown à html 
```bash
pandoc -f markdown -t html Rapport_SAE20-3.md -o Rapport_FINAL.html --number-sections --css=css/style.css --standalone --toc --metadata title="Rapport S2.03"
```

### Pour passer de Markdown à pdf
```bash
pandoc -f markdown -t pdf Rapport_SAE20-3.md -o Rapport_FINAL.pdf --number-sections --toc --metadata title="Rapport S2.03" -V colorlinks=true -V linkcolor=cyan -V urlcolor=cyan
``` 

Chaque option dans ces commandes ont leur importance très grande à la conversion :
- `-f mardown` : **f** veut dire *from* ce qui fait référence au format initial du fichier à convertir.
- `-t html/pdf` : **t** veut dire *to* ce qui signifie le format du fichié à la fin de la convertion.
- `-o result.html/.pdf` : **o** veut dire *output*, ce qui permet de nommer le fichié à la fin de sa convertion.
- `--number-sections` : sert à numéroter automatiquement chacune des sections.
- `--css=css/style.css` : lier un fichier css à notre résultat html.
- `--standalone` ou `-s` : permet de donner un fichier html complet (un fichier HTML valide comprenant <head> et <body>)
- `--toc` : **toc** signifie *table of contents*, permet d'ajouter automatiquement une table des matières.
- `--metadata` : permet d'ajouter des paramètres en plus à nos conversions, par exemple :
    - `title="Rapport S2.03"` : titrer notre document, et l'afficher tout en haut de celui-ci.
- `-V` : **V** signifie *variable*, comme son nom l'indique permet de modifier la valeurs de certaines variables comme :
    - `colorlinks=true` : pour activer la coloration des liens cliquables.
