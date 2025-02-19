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

Listalla oli valmiiksi neljä 'A Record' -tiedostoa sekä 'CNAME Record' -tiedosto, joille ei ole käyttöä. Poistin tiedostot ja loin uudet tiedostot 'Add New Record' -painikkeesta.
Tiedostot ohjaavat domain nimen virtuaalipalvelimen ip-osoitteeseen.

![image](https://github.com/user-attachments/assets/699c92fe-d912-441f-a04b-3d410f8c620c)


## Tehtävä b)

![image](https://github.com/user-attachments/assets/d9fa9f83-2c9c-4daa-a650-b51b3c2c57ed)

luodaan index.html tiedosto ja lisätään pätkä html koodia testausta varten. `micro index.html`

![image](https://github.com/user-attachments/assets/14ce1efc-fcd8-401c-941a-d41df256a06f)

`sudo nano /etc/apache2/sites-available/arileppanen.me.conf`

![image](https://github.com/user-attachments/assets/1379c552-6240-496a-8ddf-6709fa53f588)

`sudo a2ensite arileppanen.me.conf` arileppanen konfiguraatio tiedosto käyttöön

`sudo chmod -R 755 /home/ap` Apachelle pääsy publicsites hakemistoon

`sudo a2dissite 000-default.conf` 000-default.conf pois käytöstä

`sudo a2dissite default-ssl.conf` default-ssl.conf pois käytöstä

`sudo systemctl restart apache2` apache uudelleenkäynnistys

![image](https://github.com/user-attachments/assets/e3a4e55e-7d03-4615-beb3-059067b1568e)


## Tehtävä c)
## Tehtävä d)
## Tehtävä e)

## Lähteet
