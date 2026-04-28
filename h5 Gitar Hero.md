# h5 Gitar Hero

## Tiivistykset

### What is Git?

Git toimii snapshotteina

Tiedostot kulkevat tilojen läpi **modified → staged → committed**

Suurin osa operaatioista tapahtuu paikallisesti ja pull/push hoitaa verkon yli synkronoinnin

Commit on pysyvä tallennus Gitin tietokantaan

---
### Gitin käyttö
**git add --all:** Lisää kaikki muutokset (**uudet, muokatut ja poistetut tiedostot**) staging alueelle.

**git commit:** Tallentaa staging alueen sisällön uutena snapshotina

**git pull:** Hakee muutokset palvelimelta ja tuo ne haluttuun paikkaan

**git push:** Lähettää omat commitit palvelimelle esim. Github

---
## Tehtävät

### a) 
Aloitin tehtävän tekemällä uuden varaston githubissa.

![kuva](kuvat/H5/image12.png)

Annoin uuden varaston nimeksi gitarHero ja laitoin sen kuvaukseen sanan sunshine. Lisäksi asetin täpän päälle missä varaston luonnin yhteydessä sinne lisätään REDME tiedosto. Varaston lisenssiksi asetin GNU lisenssin.

![kuva](kuvat/H5/image11.png)

Seuraavaksi kävin kopioimassa ssh julkisen avaimen. 

![kuva](kuvat/H5/image8.png)

Koska virtuaalikoneen julkinen avain oli jo lisätty minun githubiin niin en voi lisätä sitä enään toista kertaa. Alla olevassa kuvassa näkyy kuitenkin miten sen tekisin eli **settings → Deploy keys**. Julkinen avain menee key kohtaan ja allow write access jos haluat työntää koneelta palvelimelle.

![kuva](kuvat/H5/image10.png)

---
### b
Seuraavaksi kävin kopioimassa varaston ssh avaimen.

![kuva](kuvat/H5/image6.png)

Tämän jälkeen menin koneelle ja kopioin varaston komennolla git clone.

![kuva](kuvat/H5/image4.png)

Seuraavaksi loin varastoon tiedoston **sunshine.txt**. ja työnsin sen palvelimelle komennoilla** git add -–all, git commit ja git push**.

![kuva](kuvat/H5/image1.png)

![kuva](kuvat/H5/image3.png)

---
### c
Tässä kokeilin **git reset –-hard** komentoa. Kirjoitin jotain siansaksaa ja tallensin sen tiedostoon. **Git reset --hard** vaihtoi näköjään tiedoston sisällön takaisin viimeisimmän commitin sisältöön.  

![kuva](kuvat/H5/image15.png)

---
### d
Tässä tarkastelin git logia komennolla git log –patch. Sähköposti ja nimi näkyvät oikein. Kuvassa näkyy myös lisäämäni tiedoston tiedot ja kommentit. 

![kuva](kuvat/H5/image5.png)

---
### e 
Seuraavaksi loin ansible kansioon uuden roolin ja tehtävän.

![kuva](kuvat/H5/image13.png)

Lisäsin tasks hakemistoon main.yml tiedoston minkä sisältö näkyy kuvassa.

Koodin toiminnot:

**name:** pull Git vain kuvaus tehtävälle

**git:** kertoo että käytetään Ansible git moduulia

**repo:** mistä Git repositoriosta haetaan

**dest:** mihin hakemistoon kloonataan palvelimella

**version:** mikä haara (branch) haetaan tässä tilanteessa main

**update:** jos repo on jo olemassa, se päivitetään (git pull)

![kuva](kuvat/H5/image14.png)

Komento suoriutui ilman ongelmia. 

![kuva](kuvat/H5/image9.png)

Testi mielessä kokeilin vielä luomalla uuden tiedoston webissä ja sitten suorittamalla ansible playbookin. Tiedosto vedettiin onnistuneesti koneelle oikeaan paikkaan.

![kuva](kuvat/H5/image7.png)

![kuva](kuvat/H5/image2.png)

<img width="753" height="288" alt="image" src="https://github.com/user-attachments/assets/346040a1-6469-477a-b357-ef7cb482e32e" />

---
### f
pari hankittu

---
## Lähteet 

1.3 Getting Started - What is Git? Luettavissa:https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F Luettu: 27.4.2026

git-add Luettavissa:https://git-scm.com/docs/git-add Luettu: 27.4.2026

git-commit Luettavissa:https://git-scm.com/docs/git-commit Luettu: 27.4.2026

git-pull Luettavissa:https://git-scm.com/docs/git-pull Luettu: 27.4.2026 

git-push Luettavissa:https://git-scm.com/docs/git-push Luettu: 27.4.2026 

d kohdassa käytetty AI apuna.



