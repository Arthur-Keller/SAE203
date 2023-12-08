Avant la convertion avec pandoc, vous devez avoir installer pandoc sur votre machine perso ([voir plus](https://pandoc.org/installing.html)) 

## 1. Pour passer de Markdown à html 
```
pandoc -s Rapport_SAE20-3.md -c ./css/style.css -o Rapport_SAE20-3.html
```

## 1. Pour passer de Markdown à pdf
```
pandoc Rapport_SAE20-3.md -o Rapport_SAE20-3.pdf
``` 