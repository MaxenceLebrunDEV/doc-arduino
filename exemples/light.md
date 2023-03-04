
## Introduction

Le module Relay est un composant électronique couramment utilisé pour contrôler des circuits électriques à haute tension à partir de circuits de faible tension. Il est souvent utilisé avec des microcontrôleurs tels que l'Arduino pour contrôler des appareils électriques tels que des moteurs, des lumières et des ventilateurs. Dans ce guide, nous allons explorer comment utiliser un module Relay pour contrôler un volet roulant motorisé.
Voici la documentation pour contrôler une lumière à l'aide d'un MOC3043 et d'un Arduino :

## Matériel requis :

-   Arduino Uno
-   MOC3043
-   Lampe AC
-   Résistance de 220 ohms
-   Breadboard
-   Fils de connexion

### Étapes de câblage :

1.  Connectez la broche 1 (anode) du MOC3043 à une broche de sortie numérique de l'Arduino (par exemple, la broche 13).
2.  Connectez la broche 2 (cathode) du MOC3043 à la masse (GND) de l'Arduino.
3.  Connectez une résistance de 220 ohms entre la broche 1 (anode) du MOC3043 et la broche 5 (LED cathode) de l'Arduino (facultatif, pour indiquer l'état de la sortie).
4.  Connectez la broche 4 (MT1) du MOC3043 à la phase de l'alimentation AC.
5.  Connectez la broche 6 (MT2) du MOC3043 à la charge AC (par exemple, la lampe).
6.  Connectez la phase de l'alimentation AC à la charge AC (par exemple, la lampe).
7.  Connectez la masse (GND) de l'Arduino à la masse de l'alimentation AC.

Schéma de câblage :

![Schéma de câblage de la lumière](https://www.astuces-pratiques.fr/imagesarticles/24/piloter-un-triac-avec-arduino-ou-pic_1.webp)

### Code Arduino :



```arduino
const int mocPin = 13;

void setup() {
  pinMode(mocPin, OUTPUT);
}

void loop() {
  digitalWrite(mocPin, HIGH);
  delay(5000);
  digitalWrite(mocPin, LOW);
  delay(5000);
}
```
Ce code allume la lumière pendant 5 secondes, puis l'éteint pendant 5 secondes, en boucle.

Notez que le MOC3043 est conçu pour fonctionner avec des charges AC, donc soyez prudent lorsque vous manipulez des tensions AC et assurez-vous de prendre les mesures de sécurité appropriées.