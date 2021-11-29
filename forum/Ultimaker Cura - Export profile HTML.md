https://www.lesimprimantes3d.fr/forum/topic/41886-exporter-un-profil-ultimaker-cura-au-format-html/?tab=comments#comment-438720

Un export HTML ou .csv (plug-ins / greffon disponible via le "marché en ligne" de Cura ) au lieu d'un fichier d'extension .curaprofile permet d'avoir l'ensemble des paramètres du profil d'impression et du profil d'imprimante utilisé.

Donc plus simple pour communiquer ces informations à une personne qui n'a pas la même imprimante que vous ...

Et cela permet aussi de ne pas avoir besoins de Cura pour lire les paramètres.

  
Installation via le "marché en ligne" de Cura (il vous faudra créer un compte Ultimaker ...) ou via [https://marketplace.ultimaker.com/app/cura/plugins/5axes/HTMLCuraSettings](https://marketplace.ultimaker.com/app/cura/plugins/5axes/HTMLCuraSettings)

[![image.png.8f1d92f7009fe3fc1990f2c9b0689dac.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.8f1d92f7009fe3fc1990f2c9b0689dac.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.8f1d92f7009fe3fc1990f2c9b0689dac.png "Agrandir l’image")

[![image.png.9bcbfe43a6067bffcd369ad9063ab962.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.9bcbfe43a6067bffcd369ad9063ab962.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.9bcbfe43a6067bffcd369ad9063ab962.png "Agrandir l’image")

[![image.png.50c5183811f24d5eef9e379efe7fac90.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.50c5183811f24d5eef9e379efe7fac90.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.50c5183811f24d5eef9e379efe7fac90.png "Agrandir l’image")

 Après installation du plug-ins / greffon et redémarrage de Cura, il suffit de :

  
1- Utiliser le raccourcie clavier touches Ctrl+S ou aller dans le menu "Fichier" -> "Enregistrer le projet..." ( **Attention ne pas confondre avec "Exporter..."** sinon pas de format HTML )  
[![image.png.1d2364cf19330c0c6bbd928e99727061.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.1d2364cf19330c0c6bbd928e99727061.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.1d2364cf19330c0c6bbd928e99727061.png "Agrandir l’image")  
2- sélectionner le type HTML

[![image.png.0827512b06cef3d891849953e2536f15.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.0827512b06cef3d891849953e2536f15.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.0827512b06cef3d891849953e2536f15.png "Agrandir l’image")

3- saisir un nom de fichier

[![image.png.b87a9f5fed349ebc0d6f3935549f1826.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.b87a9f5fed349ebc0d6f3935549f1826.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.b87a9f5fed349ebc0d6f3935549f1826.png "Agrandir l’image")

ex: "profileCura\_PPAC\_Essai001.html"

4- puis "Enregistrer" (ici "Save" ) ou valider avec la touche "Entrée".

Il suffit après de glisser déposer ce fichier .html dans le formulaire de saisie d'un message sur le forum.

Je recommande d'installer en même temps les plug-ins / greffons

*   "Settings Guide" qui permet d'avoir des informations très utiles concernant les différents paramètres. De plus, tout en bas de la liste de ce guide, se trouve une section «Troubleshooting».
*   "Mesh Tools" qui permet par exemple de corriger des erreurs de modèle 3D mal formés de fichier .stl .

[![image.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_04/image.png.dbf76565f8cc6ab9885c708d90d9adb3.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_04/image.png.dbf76565f8cc6ab9885c708d90d9adb3.png "Agrandir l’image")

Enfin, si vous perdez un profil d'impression, il peut être possible de le récupérer depuis un fichier .gcode créé par Cura. (en fin du fichier .gcode, Cura ajoute un bloc de descriptions du profil d'impression.)

Pour l'importer :

Menu "Préférences" -> "Configurer Cura..."

[![image.png.44115e6c1500e01265e7ae95b057f5d5.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.44115e6c1500e01265e7ae95b057f5d5.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.44115e6c1500e01265e7ae95b057f5d5.png "Agrandir l’image")

Sélectionner "Profils" et utiliser le bouton "Importer" pour allez sélectionner votre fichier .gcode

[![image.png.0a671bc14db4e782bac7ccd897b5c973.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.0a671bc14db4e782bac7ccd897b5c973.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_05/image.png.0a671bc14db4e782bac7ccd897b5c973.png "Agrandir l’image")

Bonne continuation !

**Modifié (le) Mai 17 par fran6p**  
correcteur magique ;-)

-----
https://www.lesimprimantes3d.fr/forum/topic/41886-exporter-un-profil-ultimaker-cura-au-format-html/?do=findComment&comment=445678


Bon dommage les "post traitement" sous Ultimaker Cura, ne semblent pas être visiblement dans l'export HTML ... Il faut donc aussi proposer un fichier .gcode pour contrôler cela en cas de problèmes ...  

Un exemple de post-traitement que l'on ne verra pas dans l'export HTML car il faut regarder le fichier .gcode ou déjà connaitre l'interface de Ultimaer Cura :

>  [](#) [](//www.lesimprimantes3d.fr/forum/?app=core&module=system&controller=content&do=find&content_class=forums_Topic&content_id=42527&content_commentid=445675)Le 21/06/2021 at 15:58, [PPAC](//www.lesimprimantes3d.fr/forum/?app=core&module=members&controller=profile&id=33940) a dit :
> 
> tu semble avoir un script de post traitement 
> 
> cf   
> ;POSTPROCESSED
> 
> en debut du fichier .gcode 
> 
> a chaque couche tu a un 
> 
>   
> ;TIME\_ELAPSED:195.669091  
> **;TimeLapse Begin  
> G1 F9000 X0 Y190 ;Park print head**  
> M400 ;Wait for moves to finish  
> M240 ;Snap Photo  
> G4 P700 ;Wait for camera  
> G0 X110.907 Y138.071; Restore position   
> ;LAYER:1
> 
>  [![image.png.632215325da3738666e2e1476ae20cc1.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_06/image.png.632215325da3738666e2e1476ae20cc1.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_06/image.png.632215325da3738666e2e1476ae20cc1.png "Agrandir l’image") 
> 
> Il faut cliquer sur [![image.png.1dfd26f367fb52cc04087b1db26807cd.png](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_06/image.png.1dfd26f367fb52cc04087b1db26807cd.png)](https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_06/image.png.1dfd26f367fb52cc04087b1db26807cd.png "Agrandir l’image") et le supprimer ... puis retrancher et pendre le temps de visualiser l’aperçu avec de visible les déplacements....


-----
