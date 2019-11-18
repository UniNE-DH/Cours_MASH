# Documenter son travail


## Markdown

Il peut être utile de détailler ce que contient tout votre dossier pour que d'autres puissent l'utiliser. On peut le faire en markdown. Vous pouvez par exemple expliquer comment adapter le schéma.

## De l'ODD au schéma

Vous avez des scripts pré-enregistrés dans Oxygen pour transformer l'ODD en schéma:

```
Document> Transformation>Configure transformation scenario
```

Cherchez le dossier TEI ODD, et sélectionnez le bon scénario.

Vous pouvez aussi le faire en ligne sur [Oxgarage](https://oxgarage.tei-c.org):

Sélectionner ```Documents>ODD Documents```, puis dans la colonne de droite ```RELAX NG compact schema```(par exemple). Remontez en haut de la page, sélectionnez l'ODD et cliquez sur ```convert```.

## Du schéma au document TEI

Pour adapter le nouveau schéma, vous pouvez remplacer l'ancien par la ligne suivante

```xml
<?xml-model href="PATH-TO-FILE.rnc" type="application/relax-ng-compact-syntax"?>
```

Il faudra bien évidemment adapter le ```@type```
 si vous changez le format du schéma. Pour plus d'informations, cf. [ici](https://www.w3.org/TR/xml-model/#the-xml-model-processing-instruction).
