# EDM4611-020-Esquisse-4-Scene-3D-minimaliste

![rendu](https://user-images.githubusercontent.com/48024730/136847252-4e13826e-f4ad-4f2c-9901-e751d08112d0.png)

Cette esquisse a pour but de générer un visuel coloré en tirant avantage des notions de formes 3D pouvant être exploité à travers **TouchDesigner**. Des cerceaux de couleurs aux mouvements pouvant s’apparenter à un gyroscope ont été utilisés dans la cadre de ce projet.

--

Les cerceaux sont générés à l’aide de l’opérateur « **Geometry** ». Ce dernier contient un objet 3D de type « **torus** » sur lequel est appliquée une texture procédurale. La texture est générée avec un opérateur « **noise** » branché à un opérateur « **edge** » sur lequel est appliqué un effet grâce à l’opérateur « **feedback** ». Un fond de couleur translucide est ensuite ajouté sous les autres effets. La couleur de ce fond varie selon un « **LFO** ». Chaque géométrie contient également une sphère ayant une texture en mode fil de fer dont les vertices bougent selon un « **noise** ».

Afin de permettre aux cerceaux d’être répété en plusieurs exemplaires, l’opérateur de géométrie est utilisé comme opérateur maître d’un opérateur « **Replicator** ». Cette méthode de travail a été choisie pour dupliquer les cerceaux au lieu du paramètre « **Instances** » de l’opérateur géométrie pour conserver une épaisseur consistante entre tous les cerceaux. Les différentes informations de tailles et de rotation des cerceaux sont gardées dans un opérateur « **table** ». Les informations de tailles incrémentent de façon linéaire, alors que les informations de rotations suivent l’incrémentation d’un graphique en escalier. Il est également possible de modifier le nombre de cerceaux affiché ainsi que la vitesse de leur rotation à l’aide de glissières prévues à cet effet.

Une fois les différentes géométries créées, elles sont rendues à l’aide des opérateurs « **Camera** », « **Light** » et « **Render** ». Noter que la caméra et la lumière tournent autour des cerceaux pour accentuer le mouvement. Un effet de « **feedback** » est ensuite appliqué sur la forme afin de créer l’effet d’orbe coloré autour de la géométrie. Pour compléter le décor, un dégradé radial passant du rouge au bleu au vert évolue en permanence derrière la géométrie.

--

Il est possible de sauvegarder une image de la forme en appuyant sur la touche « **Entrer** » du clavier. Cette image sera sauvegardée dans un dossier « **export** » situé à la racine du projet.

**Références:** </br>
Pour l'opérateur Replicator: https://www.youtube.com/watch?v=B6HAP-WyDZY&list=WL&index=4&t=1250s</br>
</br>
Inspitation pour le mouvement:</br>
![image](https://user-images.githubusercontent.com/48024730/136846662-43194020-9469-41db-be29-656f6ab2d77c.png)
