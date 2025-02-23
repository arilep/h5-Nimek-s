## Tehtävissä käytetty ympäristö

- Käyttöjärjestelmä: Windows 11 Home 64-bit
- Suoritin: AMD Ryzen 7 5800X 8-Core Processor
- Muisti: 32GB RAM
- Näytönohjain: NVIDIA GeForce RTX 3080
- Virtualisointiohjelmisto: Oracle VM VirtualBox 7.0

- Internet yhteys: DNA Netti 400M (Download 400Mbps / Upload 200Mbps)

## Tehtävä a)

Siirryin GitHub student developer pack -sivulle. 'All Offers' -osion alta löytyi NameCheap ja ensimmäistä linkkiä seuraamalla pääsin jatkamaan tarjoukseen (Domain nimi ilmaiseksi vuoden ajan).

![image](https://github.com/user-attachments/assets/72bfa5cd-120e-4681-817d-cdaa1d47c490)

![image](https://github.com/user-attachments/assets/e17bc479-bb93-44c9-8e6c-a04965e187f6)

Tarjous koski vain .me päätteisiä domain nimiä, joten jatkoin sillä vaihtoehdolla:

![image](https://github.com/user-attachments/assets/d9f103da-65d6-4866-88c8-2729fe96ecf9)

Muutaman klikkauksen ja sähköpostiini tulleen varmenteen jälkeen sain tilauksen tehtyä.

![image](https://github.com/user-attachments/assets/0287fd0e-c9dd-4778-9693-b183491c3e0e)

Kirjauduin NameCheap palveluun luomillani käyttäjätunnuksilla, josta domain nimeni ja 'manage' valikko löytyi.

![image](https://github.com/user-attachments/assets/81d00c6e-58a4-4240-8008-6c3290bcfe69)

'Manage' valikon alta siirryin 'Advanced DNS' välilehdelle

![image](https://github.com/user-attachments/assets/3863674b-d7f9-4e16-bc83-1b6da111eaed)

Listalla oli valmiiksi neljä 'A Record' -tietuetta sekä 'CNAME Record' -tietue, joille ei ole käyttöä. Poistin tietueet ja loin uudet tietueet 'Add New Record' -painikkeesta.
Tietueet ohjaavat domain nimen virtuaalipalvelimen IP-osoitteeseen.

![image](https://github.com/user-attachments/assets/699c92fe-d912-441f-a04b-3d410f8c620c)


## Tehtävä b)

Ensiksi loin uuden hakemistopolun arileppanen.me -sivustolle.

![image](https://github.com/user-attachments/assets/d9fa9f83-2c9c-4daa-a650-b51b3c2c57ed)

loin index.html tiedoston ja lisäsin pätkän html koodia testausta varten. `micro index.html`

![image](https://github.com/user-attachments/assets/14ce1efc-fcd8-401c-941a-d41df256a06f)

Seuraavaksi konfiguraatio tiedoston määritykset. `sudo nano /etc/apache2/sites-available/arileppanen.me.conf`

![image](https://github.com/user-attachments/assets/1379c552-6240-496a-8ddf-6709fa53f588)

`sudo a2ensite arileppanen.me.conf` arileppanen konfiguraatio tiedosto käyttöön

`sudo chmod -R 755 /home/ap` Apachelle pääsy publicsites hakemistoon

`sudo a2dissite 000-default.conf` 000-default.conf pois käytöstä

`sudo a2dissite default-ssl.conf` default-ssl.conf pois käytöstä

`sudo systemctl restart apache2` apache uudelleenkäynnistys

![image](https://github.com/user-attachments/assets/e3a4e55e-7d03-4615-beb3-059067b1568e)

DNS-palvelu vei pitkään, noin tunnin, ennenkuin se alkoi toimimaan.

![image](https://github.com/user-attachments/assets/d2d28db1-4de8-4b09-9627-883c9b79373d)

## Tehtävä c)

kopioidaan index.html tiedostosta kaksi uutta pohjaa nimillä blog.html ja projects.html

![image](https://github.com/user-attachments/assets/90769b5e-5c23-4309-8cd8-2d2b88b99af1)

Lisäsin linkit sivulta toiselle. Tämä tapahtuu elementeillä 'nav'. Lisäsin vastaavat elementit jokaiselle .html -tiedostolle ja vaihdoin otsikot jokaista sivua vastaaviksi.

![image](https://github.com/user-attachments/assets/4aeab35c-7f3c-4a1c-9f0b-af0c12a906c3)


![image](https://github.com/user-attachments/assets/771729d1-fb0b-4a17-8bbd-bae3219fabf2)

Tehtävänannon mukaan sivuja pitää pystyä vielä muokkaamaan ilman pääkäyttäjän oikeuksia, joten lisäsin vielä oikeudet.

`chmod o+w *.html` eli 'others' käyttäjille kirjoitus 'write' oikeudet, *.html -> kaikkiin .html -päättyviin tiedostoihin kyseisessä hakemistossa.

![image](https://github.com/user-attachments/assets/5efc9042-78a1-4aa7-b9ee-260454d7122e)

## Tehtävä d)

Lisäsin uuden A-tietueen (Type: A Record Host: blog Value: 94.237.114.9), osoitetta blog.arileppanen.me varten.

CNAME-tietueen (alias) osoitin kotiosoitteeseen arileppanen.me.

![image](https://github.com/user-attachments/assets/3f6031c8-ccce-4e99-a48f-359e024d2f1f)

Seuraavaksi lisäsin VirtualHost lohkot vielä blog.arileppanen.me & projects.arileppanen.me sivustoille. 

![image](https://github.com/user-attachments/assets/cf8e4c1a-a34c-40ee-b926-51e32ef9fda1)



## Tehtävä e)

### Host
- DNS nimikysely, joka palauttaa sivustolta mm. IPv4-osoitteen, IPv6-osoitteen sekä sähköpostiliikenteen palvelimen.

### Dig
- Ajaa saman asian kuin 'host', mutta tarjoaa enemmän ja tarkempaa tietoa.

      - Esimerkiksi 'ANSWER SECTION' -osio seuraavassa kuvassa:
      - 1. sarake: palvelimen nimi (google.com)
      - 2. sarake: aikaraja, jonka jälkeen tietue päivitetään (212)
      - 3. sarake: kyselyluokka (IN = Internet)
      - 4. sarake: kyselytyyppi (A = Address record)
      - 5. sarake: verkkotunnuksen kanssa liitetty IP-osoite (216.58.209.206)

Aloitin testauksen. Host google.com ei palauttanut mitään. Pikaisen googlaamisen tuloksena selvisi että palvelu on asentamatta, joten:

`sudo apt update && sudo apt install dnsutils`

Tämän jälkeen alkoi tulla tuloksia. Testasin ja ajoin komennot `host google.com` ja `dig google.com`

![image](https://github.com/user-attachments/assets/4e0b2bcc-faca-4c6c-b9f5-14d9eaba1e01)

Tämän jälkeen ajoin 'host' ja 'dig' komennot omalle sivulleni.

![image](https://github.com/user-attachments/assets/8083daec-8ac3-4707-a727-a02b5321ccd0)

Ja lopuksi vielä Tero Karvisen sivut:

![image](https://github.com/user-attachments/assets/b286cd0f-acae-4036-bcb0-5f04aca96f7d)




## Lähteet
Karvinen, T. 3.12.2024. Linux Palvelimet 2025 alkukevät. Luettavissa: https://terokarvinen.com/linux-palvelimet/. Luettu 19.2.2025.

Lehto, S. 14.2.2022. Teoriasta käytäntöön pilvipalvelimen avulla (h4). Luettavissa: https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/. Luettu 19.2.2025.

NameCheap. s.a. Buy a domain name. Luettavissa: https://www.namecheap.com/. Luettu 19.2.2025.

GitHub. s.a. GitHub Student Developer Pack. Luettavissa: https://education.github.com/pack. Luettu 19.2.2025.

CloudFlare. s.a. What is a DNS CNAME record? Luettavissa: https://www.cloudflare.com/learning/dns/dns-records/dns-cname-record/. Luettu 20.2.2025.

Medium. 22.2.2021. How to install nslookup, dig, host commands in Linux. Luettavissa: https://tranzservrsupprtz123.medium.com/how-to-install-nslookup-dig-host-commands-in-linux-3510dac46d99. Luettu 20.2.2025.

Zivanov, S. 23.5.2024. dig Command in Linux with Examples. Luettavissa: https://phoenixnap.com/kb/linux-dig-command-examples. Luettu 22.2.2025.
