







## Tehtävät

a) Aloitin tehtävän asentamalla apachen komenolla sudo apt install apache2. Sitten loin uuden tiedoston johon haluan sijoittaa nettisivun /home/luka/nettisivu/. 
Seuraavaksi menin /etc/apache2/sites-avaible/ ja loin tiedoston etusivu.conf ja laitoin sinne kuvassa näkyvän sisällön.

![Lpputulos](kuvat/H3/image1.png)

Tämän jälkeen loin symbolisen linkin /etc/apache2/sites-avaible/rtusivu.conf --> /etc/apache2/sites-enabled/

![Lpputulos](kuvat/H3/image6.png) 

Sitten lisäsin vielä tiedostoille /home/luka/ ajo-oikeudet, /home/luka/nettisivu/ ajo-oikeudet ja /home/luka/nettisivu/index.html kirjoitus ja luku oikeudet. 

![Lpputulos](kuvat/H3/image4.png) 
a) Apassi. Asenna Apache 2 käsin. Weppisivun tulee näkyä palvelimen etusivulla. Sivun tulee olla tavallisen käyttäjän muokattavissa, ilman root- tai sudo-oikeuksia.
b) Moottorix. Asenna Nginx käsin. Weppisivun tulee näkyä palvelimen etusivulla. Sivun tulee olla tavallisen käyttäjän muokattavissa, ilman root- tai sudo-oikeuksia. (Muista sammuttaa Apache ensin.)
c) Automoottorix. Automatisoi Nginx asennus Ansiblella. Ylläpitäjän osuus Ansiblella riittää, itse HTML-weppisivut voi tehdä käsin.
