
# Module Relay pour Arduino

Le module Relay est un composant électronique qui permet de contrôler la mise sous tension ou hors tension d'un circuit électrique. Il peut être utilisé pour contrôler des charges électriques telles que des lampes, des moteurs, des appareils électroménagers, etc.

Le module Relay est souvent utilisé avec Arduino pour contrôler des charges électriques à partir d'un microcontrôleur. Il permet à un programme Arduino de contrôler une charge électrique sans que le microcontrôleur ne soit directement connecté au circuit électrique.

## Principe de fonctionnement

Le module Relay est composé d'un relais électromécanique et d'un circuit de commande. Le relais électromécanique est un interrupteur qui est actionné par une bobine électromagnétique. Lorsque la bobine est activée, l'interrupteur se ferme et permet le passage du courant électrique à travers le circuit.

Le circuit de commande permet de contrôler l'activation de la bobine du relais à partir d'un signal électrique. Dans le cas du module Relay pour Arduino, ce signal électrique est fourni par une broche de sortie du microcontrôleur Arduino.

## Connexion du module Relay à Arduino

Le module Relay pour Arduino peut être connecté à une broche de sortie numérique de l'Arduino. Voici un exemple de connexion :

- VCC  ->  5V
- GND  ->  GND
- IN   ->  13 (ou toute autre broche de sortie numérique de l'Arduino)

VCC et GND sont connectés respectivement aux broches d'alimentation 5V et GND de l'Arduino. La broche IN est connectée à une broche de sortie numérique de l'Arduino (dans cet exemple, la broche 13).
(La broche "IN" du module Relay pour Arduino permet de contrôler l'activation du relais électromécanique à partir d'un signal électrique fourni par une broche de sortie numérique de l'Arduino.)

## Utilisation du module Relay avec Arduino

Le module Relay pour Arduino peut être utilisé pour contrôler une charge électrique à partir d'un programme Arduino. Voici un exemple de programme qui allume et éteint une lampe connectée au module Relay :

```arduino
const int relayPin = 13;

void setup() {
  pinMode(relayPin, OUTPUT);
}

void loop() {
  digitalWrite(relayPin, HIGH);
  delay(1000);
  digitalWrite(relayPin, LOW);
  delay(1000);
}
```
Ce programme allume la lampe connectée au module Relay pendant une seconde, puis l'éteint pendant une seconde, et ainsi de suite en boucle.
## Exemples d'utilisation
- [Exemple 1 : Allumer une lampe](exemples/light.md)
- [Exemple 2 : Ouvrir un volet](exemples/volet.md)




## Conclusion

Le module Relay pour Arduino est un composant électronique utile pour contrôler des charges électriques à partir d'un microcontrôleur. Il permet à un programme Arduino de contrôler une charge électrique sans que le microcontrôleur ne soit directement connecté au circuit électrique. Le module Relay est facile à utiliser et peut être connecté à une broche de sortie numérique de l'Arduino.
