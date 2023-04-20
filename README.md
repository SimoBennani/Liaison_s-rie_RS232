# Liaison_série_RS232

On se propose de réaliser une interface série RS232 afin d’émettre des données vers un ordinateur via le
port série de la nanoboard . Ces données seront visualisées sur le PC en utilisant le logiciel de
communication Hyperterminal de windows. L’affichage de la donnée, sous hyperterminal, correspondra alors au
code ASCII de la donnée envoyée par la nanoboard. La configuration du port série du PC aura les
caractéristiques suivantes . 

Pour que le PC puisse recevoir correctement une donnée (donnée de 8bits) transmise par la nanoboard, il
faut que la nanoboard émette sur la broche TX de son port série la trame suivante :

![image](https://user-images.githubusercontent.com/91829054/233504213-f6c3b781-b2f2-43ce-8b3b-88612e8acdd8.png)

Dans notre cas, la trame est constituée de 10 bits : Un bit de « start », huit bits de donnée (bit de poids

faible envoyé en premier), un bit de « stop ». La cadence d’envoi est fixée à 9600 bauds. Lorsque la
communication est inactive, la broche TX est à l’état haut. Le port série du PC détecte une communication lorsque
celui-ci reçoit le bit « start » (état bas) . 

![image](https://user-images.githubusercontent.com/91829054/233504397-f1cb9ee5-5d46-48a1-8297-7136c42b2148.png)

La donnée de 8 bits à envoyer sera définie par un instrument virtuel. Un bouton-poussoir de la nanoboard
sera utilisé pour valider l’envoi de la donnée sur la broche TX (Attention : il ne faut pas émettre en permanence la
donnée si le bouton-poussoir reste enfoncé).
