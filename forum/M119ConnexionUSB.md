https://www.lesimprimantes3d.fr/forum/topic/41837-bruit-inquietant-sur-une-geetech-a10/?do=findComment&comment=438437

Il faut vérifier le endstop / capteur de fin de course.
Il faut peut être le replacer/déplacer ou vérifier ses câbles / connecteurs / branchement , connexions. 
(Tu peux aussi avoir de permuté les branchements de se endstop avec un autre sur la carte mère ... a vérifier ...)


Si, t'on ecran (si tu a un TFT) propose une consol de saisie de commandes g-code.
Sinon, si tu arrive a ouvrir une connexion a l'imprimante via un câble USB avec un programme comme 
* Pronterface https://www.pronterface.com/ ou
* Repetier Host https://www.repetier.com/download-now/ ou
* ... ( sauf avec Ultimaker Cura qui n'a pas de log des connexion USB )
il existe la commande g-code `M119` ( https://marlinfw.org/docs/gcode/M119.html ) pour avoir le statue des capteurs de fin de courses 
afin de vérifier si ils fonctionnent correctement (le déclancher a la main et vérifier le resultat d'un `M119` ...)

~~~
> M119
Reporting endstop status
x_min: open
y_min: open
z_min: TRIGGERED
z_probe: open
filament: open
~~~

`TRIGGERED` veux dire déclanché.
`open` veux dire non déclanché.


 il faudra installer le driver Windows (CH340 il me semble) disponible ici https://www.geeetech.com/forum/viewtopic.php?t=60612 .

