
## Introduction

Le module Relay est un composant électronique couramment utilisé pour contrôler des circuits électriques à haute tension à partir de circuits de faible tension. Il est souvent utilisé avec des microcontrôleurs tels que l'Arduino pour contrôler des appareils électriques tels que des moteurs, des lumières et des ventilateurs. Dans ce guide, nous allons explorer comment utiliser un module Relay pour contrôler un volet roulant motorisé.

## Matériel requis

Pour utiliser un module Relay pour le contrôle d'un volet roulant motorisé, vous aurez besoin des éléments suivants :

-   Un module Relay pour Arduino (230v)[MOC3043m]
-   Un Arduino ou tout autre microcontrôleur compatible
-   Un moteur de volet roulant
-   Un interrupteur mural pour contrôler le moteur de volet roulant
-   Des câbles de connexion

## Schéma de câblage

Voici un schéma de câblage de base de votre volet roulant:
![Schéma de câblage d'un volet roulant motorisé](https://europe1.discourse-cdn.com/arduino/optimized/4X/6/a/2/6a27da9bab24b2c3acf428e469918ec4e07f71d9_2_474x500.jpeg)


 Voici celui pour connecter un module Relay à un moteur de volet roulant :
![Schéma de câblage d'un volet roulant motorisé au Relay](https://www.astuces-pratiques.fr/imagesarticles/24/piloter-un-triac-avec-arduino-ou-pic_1.webp)

Comme le montre le schéma, le module Relay est connecté à l'Arduino à l'aide de deux broches : 1, 2(GND). La broche "1" est connectée à une broche de sortie numérique choisis par vos soins sur l'Arduino, tandis que la broches GND est connectés respectivement à la broche GND de l'Arduino.

Pour la documentation: 
[Documentation du relay MOC3043m](https://www.onsemi.com/pdf/datasheet/moc3043m-d.pdf)


## Code Arduino

Une fois que vous avez connecté le module Relay à l'Arduino et le moteur de volet roulant au module Relay, vous pouvez utiliser le code Arduino suivant pour contrôler le mouvement du volet roulant :

```arduino
const int relayPin = 13;

void setup() {
  pinMode(relayPin, OUTPUT);
}

void loop() {
  digitalWrite(relayPin, HIGH);
  delay(5000); // Temps d'ouverture du volet roulant
  digitalWrite(relayPin, LOW);
  delay(5000); // Temps de fermeture du volet roulant
}
``` 

Ce code utilise la broche de sortie numérique 13 de l'Arduino pour activer et désactiver le module Relay, ce qui permet de contrôler l'ouverture et la fermeture du volet roulant. Le délai de 5 secondes permet de régler la durée pendant laquelle le volet roulant reste ouvert ou fermé.

## Conclusion

Le module Relay est un composant électronique utile pour contrôler un volet roulant motorisé à partir d'un microcontrôleur tel que l'Arduino. En utilisant un schéma de câblage approprié et un code Arduino simple, il est facile de contrôler le mouvement du volet roulant en toute