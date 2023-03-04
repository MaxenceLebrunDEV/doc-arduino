
  

# Gestion de l'EEPROM sur ESP32

  

L'ESP32 possède une EEPROM interne qui permet de stocker des données de configuration ou d'état qui doivent être conservées même après la mise hors tension du microcontrôleur.

  

## Configuration

  

L'EEPROM de l'ESP32 est basée sur la mémoire flash et est organisée en pages de 4096 octets. Il est possible de réserver une certaine quantité d'espace dans l'EEPROM en utilisant la commande suivante dans le code :

  

```arduino

`EEPROM.begin(taille);

```

  

La taille est le nombre d'octets à réserver pour l'EEPROM. Par exemple, si vous souhaitez réserver 512 octets pour l'EEPROM, utilisez la commande suivante :

  

```arduino

EEPROM.begin(512);

```

  

## Écriture et lecture de données

  

L'écriture et la lecture de données dans l'EEPROM se font en utilisant des adresses mémoire. Par exemple, pour écrire un entier de valeur 42 à l'adresse 0 de l'EEPROM, utilisez la commande suivante :

  

```arduino

int valeur = 42;

EEPROM.write(0, valeur);

```

  

Pour lire cet entier depuis l'EEPROM, utilisez la commande suivante :

  

```arduino

int valeur = EEPROM.read(0);

```

  

Il est également possible d'écrire et de lire des tableaux de données dans l'EEPROM en utilisant les commandes suivantes :

  

```arduino

byte tableau[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

  

// Écrire le tableau dans l'EEPROM à partir de l'adresse 0

for (int i = 0; i < 10; i++) {

EEPROM.write(i, tableau[i]);

}

  

// Lire le tableau depuis l'EEPROM à partir de l'adresse 0

for (int i = 0; i < 10; i++) {

tableau[i] = EEPROM.read(i);

}

```

  

Il est également possible d'écrire et de lire des des strings via une conversion dans l'EEPROM voici un exemple pour la gestion de ssid et mot de passe wifi pour un esp32/esp8266:

  

La taille du mot de passe est de 64 octets et celle du SSID est de 32 octets.

Ecriture:

SSID

```arduino

String qsid = "ssid";

for (int i = 0; i < qsid.length(); ++i)

{

EEPROM.write(i, qsid[i]);

Serial.println(qsid[i]);

}

```

Mot de passe

```arduino

String qpass = "password";

for (int i = 0; i < qpass.length(); ++i)

{

EEPROM.write(32 + i, qpass[i]);

Serial.print("Wrote: ");

Serial.println(qpass[i]);

}
```

  

Lecture:

SSID

```arduino

String esid;

for (int i = 0; i < 32; ++i)

{

esid += char(EEPROM.read(i));

}

```

MOT DE PASSE

```arduino

String epass = "";

for (int i = 32; i < 96; ++i)

{

epass += char(EEPROM.read(i));

}

```

  

## Sauvegarde des données

  

Une fois que les données ont été écrites dans l'EEPROM, il est important de les sauvegarder pour qu'elles soient préservées même après une coupure de courant ou une mise hors tension de l'ESP32. Pour cela, utilisez la commande suivante :

  

```arduino

EEPROM.commit();`

```

Cette commande sauvegarde les données de l'EEPROM dans la mémoire flash interne de l'ESP32.

  

## Effacement des données

  

Si vous souhaitez effacer les données de l'EEPROM, utilisez la commande suivante :

  

```arduino

EEPROM.clear();

```

Cette commande efface toutes les données stockées dans l'EEPROM. N'oubliez pas de sauvegarder les données avant d'effacer l'EEPROM.