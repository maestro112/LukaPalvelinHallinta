# h5 Gitar Hero

## Tiivistykset


## Tehtävät

### a) 
Aloitin tehtävän tekemällä uuden varaston githubissa.

![kuva](kuvat/H5/image12.png)

Annoin uuden varaston nimeksi gitarHero ja laitoin sen kuvaukseen sanan sunshine. Lisäksi asetin täpän päälle missä varaston luonnin yhteydessä sinne lisätään REDME tiedosto. Varaston lisenssiksi asetin GNU lisenssin.

![kuva](kuvat/H5/image11.png)

Seuraavaksi kävin kopioimassa ssh julkisen avaimen. 

![kuva](kuvat/H5/image8.png)

Koska virtuaalikoneen julkinen avain oli jo lisätty minun githubiin niin en voi lisätä sitä enään toista kertaa. Alla olevassa kuvassa näkyy kuitenkin miten sen tekisin eli settings → Deploy keys. Julkinen avain menee key kohtaan ja allow write access jos haluat työntää koneelta palvelimelle.

![kuva](kuvat/H5/image10.png)

---
### b
Seuraavaksi kävin kopioimassa varaston ssh avaimen.

![kuva](kuvat/H5/image6.png)

Tämän jälkeen menin koneelle ja kopioin varaston komennolla git clone.

![kuva](kuvat/H5/image4.png)

Seuraavaksi loin varastoon tiedoston sunshine.txt. ja työnsin sen palvelimelle komennoilla git add -–all, git commit ja git push.

![kuva](kuvat/H5/image1.png)

![kuva](kuvat/H5/image3.png)

---
### c
Tässä kokeilin git reset –hard komentoa. Kirjoitin jotain siansaksaa ja tallensin sen tiedostoon. Git reset –hard vaihtoi näköjään tiedoston sisällön takaisin viimeisimmän commitin sisältöön.  

![kuva](kuvat/H5/image15.png)

---
### d
Tässä tarkastelin git logia komennolla git log –patch. Sähköposti ja nimi näkyvät oikein. Kuvassa näkyy myös lisäämäni tiedoston tiedot ja kommentit. 

![kuva](kuvat/H5/image5.png)

---
### f 
Seuraavaksi loin ansible kansioon uuden roolin ja tehtävän.

![kuva](kuvat/H5/image13.png)

Lisäsin tasks hakemistoon main.yml tiedoston minkä sisältö näkyy kuvassa.

Koodin toiminnot:

name: Pull Git → vain kuvaus tehtävälle

git: → kertoo, että käytetään Ansible git moduulia

repo: https://github.com/Supajohn/Sunshine.git → mistä Git-repositoriosta haetaan koodi

dest: /Sunshine → mihin hakemistoon koodi kloonataan palvelimella

version: main → mikä haara (branch) haetaan tässä tilanteessa main

update: yes → jos repo on jo olemassa, se päivitetään (git pull)
