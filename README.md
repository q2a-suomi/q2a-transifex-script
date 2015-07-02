## Skriptin toiminta

1. Skripti vetää Transifexista käännöstiedostot väliaikaiseen repositoryyn palvelimelle suorittamalla skriptin (update-files-to-github.sh)
2. Sieltä samainen skripti puskee gitin avulla muutokset käännöksen repositoryyn.

## Oletukset
Oletuksena on että 

1. sinulla on push oikeus tähän repositoryyn
2. sinulla on SSH avaimet käytössä etkä tarvitse salasanojen syöttöä muutoksien lisäämisessä Githubiin.
3. asennat transifex asiakasohjelman (http://docs.transifex.com/developer/client/)
4. olet asentanut git asiakasohjelman (http://git-scm.com/book/en/Getting-Started-Installing-Git)
5. olet tehnyt .transifexrc tiedoston oman kotihakemistoosi (katso esimerkki alta). 
6. ...

**Esimerkki .transifexrc**

```bash
$ cat /home/kyyberi/.transifexrc 
[https://www.transifex.com]
hostname = https://www.transifex.com
password = omasalasanasi
token = 
username = käyttäjätunnus
```
Huom! Token jää tyhjäksi. 

## .tx kansio

Lisäksi itse repositoryn sisällä on ".tx" kansio, jossa on "config" tiedosto, jossa määritellään muun muassa millä 
nimillä tiedostot tallennetaan ja minne.

## Skriptin suorittaminen

Sen jälkeen asetat skriptin crontabiin tai voit tietysti manuaalisesti ajaa skriptin tyyliin: ```bash $ 
./update-files-to-github.sh ```
