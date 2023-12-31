# AppsDocs  : site documentaire sous Hugo

  [22/06/2023 - 14h48]
  <br>
 AppsDocs a été créé afin de centraliser la production et diffusion de documentation pour les plateformes portées par le Pôle FOAD et au delà de services proposés au sein des Apps.education.fr.
 <br>
## Hébergement et génération du site sur La Forge Education nationale
* Le site est réalisé avec le framework [Hugo](https://gohugo.io/).
* Il est hébergé et généré sur le Gitlab de La Forge Education  Edcuation nationale : [https://gitlab.forge.education.gouv.fr/foad/appsdocs](https://gitlab.forge.education.gouv.fr/foad/appsdocs)
* Il est publié sur le serveur web du Pôle FOAD : [https://foad.phm.education.gouv.fr/appsdocs/](https://foad.phm.education.gouv.fr/appsdocs/)  
 <br>
Cet environnement a été choisi afin de centraliser et rationaliser la production de ressources pour l'accompagnement à l'usage.   
Des contributeurs rédigent leurs documents sur une branche *Dev*, créent des *merge requests* qui peuvent être commentées, amendées avant intégration dans la branche *Main*. 
 <br>
Pour git push et éviter d'écraser les configurations lors des merge requests : exclure  /public/ *.toml *.yml
## Le format Markdown
Le Markdown est un langage de balisage simple et libre. Il permet l'export de page html mais aussi PDF. 
A terme les documentations sur AppsDocs seront toutes réalisées en Markdown.   
 <br>

## Thème Hugo-DSFR 
Un thème a été créé (*Hugo-DSFR*) intégrant des composants du Sytème de Design de l'Etat (DSFR). 
Ce thème intègre le header, la navigation et le footer du DSFR à l'aide de "partials".
Les feuilles de styles et scripts sont appelés également via "partials".
Dans le cas d'AppsDocs, une catégorie correpsond à un service/une plateforme pour lequel la documentaiton est proposée.

### Les types de pages :   
- index 
- page simple
- sommaire des actualtiés
- contenu d'une actualité
- sommaire d'une catégorie
- contenu d'une catégorie

### Les contenus  
- texte et médias dans les pages
- fichiers pdf
- url vidéo

### Templates   
#### Layouts  
- _default/baseof : intégration des partials pour toutes les pages
- _default/list : tempalte pour sommaire des actualités + pagination
- _default/single : titre et intégration contenu pour les pages simples
- _default/summary
- categories/single : template pour sommaire catégorie avec retour vers une page simple qui présente les tuiles d'accès aux catégories.
- nomdelacategorie./single : template  pour page sommaire d'une catégorie  (à créer pour chaque nouvelle catégorie") 
<br>

#### Shortcodes   

Pour intégrer des styles et composants DSFR dans les fichiers Markdown, des shortcodes ont été créés.
Exemple pour insérer une image :
`{{< image image="NOMDUFICHIER.png" alt="TEXTE ALTERNATIF" largeur="240" >}}`  
Voir [UtiliserLesShortcodes.md](UtiliserLesShortcodes.md) à la racine du dossier *hugo-dsfr*.
 <br>
#### Archetypes  
 Ils permettent de fournir un modèle de front matter. 
 * categories : pour sommaire d'une catégorie
 * default : 
 * nomdecategorie : pour page de contenu d'une catégorie (url vidéo, nom pdf, icone, etc)
<br>

###  Vidéos et PDF  
Les vidéos sont hébergées sur PodEduc. 
Dans les pages contenu d'une catégorie, il suffit de renseigner l'url de la vidéo dans le front matter, ainsi que le nom du tutoriel pdf et son poids. 
Un contenu peut être ajouté avant la présentation de la vidéo et du pdf à télécharger.
Le pdf doit être placé dans *content/pdf/nomdelacategorie/*
<br>

### ToDo    
*  intégrer un moteur de recherche
*  Intégrer le nom de la catégorie comme variable pour n'avoir qu'un template pour les pages contenus
*  ajout fil d'ariane
*  Ajout d'une section pour documentations techniques : affichage plus simple reprenant le fonctionnement "blog" des actualités + classification avec une variable "catégorie" dans le front matter
*  Intégrer l'url service comme variable dans un sommaire de catégorie et shortcode pour afficahge d'une tuile.
*  Poursuivre la documentation sur le thème hugo-dsfr
