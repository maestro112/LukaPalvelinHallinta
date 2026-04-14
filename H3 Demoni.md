# H3 Deemoni


## Tiivistykst

### Karvinen 2026: Apache installed with Ansible - quick notes
- Muutokset laukaisevat handlerin mikä käynnistää apachen uudelleen. 
- Jos DocumentRoot on käyttäjän kotihakemistossa, sivuja voi muokata ilman root/sudo oikeuksia.

### Ansible Community Documentation: Handlers: running operations on change
- Handlerit ovat tehtäviä, jotka suoritetaan vain silloin kun jokin task muuttuu (esim. konfiguraation päivitys → palvelun restart)
- Taskit käyttävät **notify** avainta kutsuakseen handlereita muutoksen tapahtuessa. Sama handler suoritetaan vain kerran vaikka sitä kutsuttaisiin useasti.

### ansible-doc service
- hallitsee palveluita --> **käynnistys, pysäytys, uudelleenkäynnistys ja käynnistyminen bootissa**.
- **enabled** Määrittää käynnistyykö palvelu automaattisesti järjestelmän käynnistyessä **true/false**.
- **name** Palvelun nimi jota hallitaan esim. apache2, nginx
- **state** Palvelun tila esim. **present, started, stopped**.


---
## Tehtävät

a) Aloitin tehtävän asentamalla apachen komennolla **sudo apt install apache2**. Sitten loin uuden tiedoston johon haluan sijoittaa nettisivun **/home/luka/nettisivu/**. 
Seuraavaksi menin **/etc/apache2/sites-avaible/** ja loin tiedoston etusivu.conf ja laitoin sinne kuvassa näkyvän sisällön.

![Lpputulos](kuvat/H3/image1.png)

Tämän jälkeen loin symbolisen linkin /etc/apache2/sites-avaible/rtusivu.conf --> /etc/apache2/sites-enabled/

![Lpputulos](kuvat/H3/image6.png) 

Sitten lisäsin vielä tiedostoille /home/luka/ ajo-oikeudet, /home/luka/nettisivu/ ajo-oikeudet ja /home/luka/nettisivu/index.html kirjoitus ja luku oikeudet kaikille muille kohtiin. 

![Lpputulos](kuvat/H3/image4.png) 

Tämän jälkeen pääsin sivulle ja muut käyttäjät pystyvät muokkaamaan sivua ilman sudoa. 

---
b) Seuraavaksi asensin nginxin samallatavalla kuin apache2. Ainoana erona oli että minun täytyi mennä **/etc/ngixn/sites-avaible/default** ja muutin sieltä document root kohdan kotihakemistooni.

![Lpputulos](kuvat/H3/image8.png) 

Tämän jälkeen käynnistin nginxin uudelleen ja nettisivu toimi. Käytin samaa index.html tiedostoa minkä olin tehnyt apachea varten. Sammutin vain apachen niin kaikki sujui hyvin.

---
c) Viimeisenä aloitin tekemällä kansiot ja tiedostot valmiiksi. 

![Lpputulos](kuvat/H3/image2.png) 

Kopioin **/files/default** config tiedoston mikä toimi kun tein tämän manuaalisesti. Handlers main.yml tiedoston täytin seuraavanlaisesti 

![Lpputulos](kuvat/H3/image7.png) 

ja /tasks/main.yml 

![Lpputulos](kuvat/H3/image5.png) 

Kun suoritin playbookin kaikki meni läpi ilman ongelmia. Menin vielä testimielessä vaihtamaan **/etc/ngixn/sites-avaible/default** tiedostossa root kohdan vääräksi jotta näen että vaihtaako ansible sen oikeaksi.
Playbook suorituksen jälkeen ansible oli kopioinut oikean default tiedoston vanhan päälle ja nettisivu toimi.

---
## Lähteet
Tero Karvinen Apache installed with Ansible - quick notes. Luettavissa:https://terokarvinen.com/apache-ansible/ Luettu: 12.4.2026
Ansible Community Documentation. Luettavissa:https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_handlers.html Luettu: 12.4.2026


