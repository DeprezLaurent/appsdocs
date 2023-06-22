# Principe
Le shortcode permet l'intégration dans un fichier markdown de code html et avec ajout de variables. 
Ce thème utilise ces shortcodes pour insérer des composants d'interface DSFR.

Ils sont utiles pour des présentations plus avancées.
Pour les contenus à remplir fréquemment (actualtiés, etc) le markdown simple peut suffire.

# Liste de shortcodes disponibles

## image
- placer le fichier image dans static/images
- ajouter le code dans la page : {{< image image="NOMDUFICHIER.JPG" alt="TEXTE ALTERNATIF" legende="LA LEGENDE FACULTATIF" largeur="240" >}}  

## lien retour
- ajouter le code dans la page : {{< lienretour titre="RETOUR" adresse="/PAGE" >}}

## lien
- ajouter le code dans la page : {{< lien titre="NOM DU LIEN" adresse="URL" >}}

## Retour à la ligne
- ajouter le code dans la page : {{< sautdeligne >}}


## Intégrer du code HTML
- Encadrer le code par  : {{< rawhtml >}} {{< /rawhtml >}} 
