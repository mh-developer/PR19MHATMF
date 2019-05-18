# Analiza video iger ter platform

## Ekipa
* Mitja Hrovatič
* Anže Tomažin
* Matej Fortuna


## Podatki
Vir podatkov: 
* https://www.kaggle.com/juttugarakesh/video-game-data
<!-- * https://www.kaggle.com/lava18/google-play-store-apps -->

Podatke smo pridobili iz strani Kaggle v formatu "csv".
Zbirka podatkov *Video game sales* vsebuje podatke o video igrah od leta 1980 do 2016.
<!-- Zbirka podatkov *Google Play Store Apps* vsebuje podatke o aplikacijah iz Google Play Store trgovine.  -->

*Video game sales* vključujejo atribute:

* Rank - Uvrstitev celotne prodaje
* Name - Ime igre
* Platform - Igra izdana za platformo (npr. PC, PS4 itd.)
* Year - Leto izdaje igre
* Genre - Žanr igre
* Publisher - založnik igre
* NA_Prodaja - Prodaja v Severni Ameriki (v milijonih)
* EU_Prodaja - Prodaja v Evropi (v milijonih)
* JP_Prodaja - Prodaja na Japonskem (v milijonih)
* Other_Sales - Preostala prodaja (v milijonih)
* Global_Sales - Skupna svetovna prodaja.
* Critic_score - Povprečna ocena vseh kritikov
* Critic_count - Število kritikov, ki so oddali svojo oceno
* User_score - Povprečna ocena vseh uporabnikov
* User_count - Število uporabnikov, ki so dali oceno
* Developer - Izdelovalec igre
* Rating - ESRB starostne kategorije

<!-- *Google Play Store Apps* vključujejo atribute: -->

### Analiza strukture podatkov
Analizira smo podatke in ugotovili, da pri posameznih atributih prihaja do pomankljivosti. Pri nekaterih igrah ni podatka za leto izdaje ali pa nimajo znanega Critic_Score ali User_Score ali Developer ali Rating ter so označene z *NA* ali pa je polje prazno.

**Izpis prvih petih vrstic podatkov**

Rank | Name | Platform | Year_of_Release | Genre | Publisher | NA_players | EU_players | JP_players | Other_players | Global_players | Critic_Score | Critic_Count | User_Score | User_Count | Developer | Rating
---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ----
1 | Wii Sports | Wii | 2006 | Sports | Nintendo | 41.36 | 28.96 | 3.77 | 8.45 | 82.53 | 76 | 51 | 8 | 322 | Nintendo | E
2 | Super Mario Bros. | NES | 1985 | Platform | Nintendo | 29.08 | 3.58 | 6.81 | 0.77 | 40.24 | NA | NA |  | NA |  | 
3 | Mario Kart Wii | Wii | 2008 | Racing | Nintendo | 15.68 | 12.76 | 3.79 | 3.29 | 35.52 | 82 | 73 | 8.3 | 709 | Nintendo | E
4 | Wii Sports Resort | Wii | 2009 | Sports | Nintendo | 15.61 | 10.93 | 3.28 | 2.95 | 32.77 | 80 | 73 | 8 | 192 | Nintendo | E
5 | Pokemon Red/Pokemon Blue | GB | 1996 | Role-Playing | Nintendo | 11.27 | 8.89 | 10.22 | 1 | 31.37 | NA | NA |  | NA |  | 

<br>

**Pregled števila posameznih atributov**

Število platform | Število iger | Število žanrov | Število založnikov | Skupno število prodanih iger (v milijonih)
---------------- | ------------ | -------------- | ------------------ | ----------------------------
31               | 11563        | 13             | 582                | 8920.3

<br>

**Pregled iger po številu izdaj**

Naziv igre | Število izdaj | Leta izdaje | Razvijalec | Založnik 
 --------- | ------------- | ----------- | ----------- | --------
Need for Speed: Most Wanted | 12 | 2005 (PS2), 2012 (PS3), 2012 (X360), 2005 (X360), 2005 (XB), 2012 (PSV), 2005 (GC), 2005 (PC), 2013 (WiiU), 2005 (DS), 2005 (GBA), 2012 (PC) | EA Canada, , Black Box | Electronic Arts
LEGO Marvel Super Heroes | 9 | 2013 (X360), 2013 (PS3), 2013 (PS4), 2013 (XOne), 2013 (3DS), 2013 (WiiU), 2013 (PSV), 2013 (DS), 2013 (PC) | TT Games,  | Warner Bros. Interactive Entertainment
FIFA 14 | 9 | 2013 (PS3), 2013 (X360), 2013 (PS4), 2013 (XOne), 2013 (PSV), 2013 (PC), 2013 (Wii), 2013 (3DS), 2013 (PSP) | EA Canada,  | Electronic Arts
Ratatouille | 9 | 2007 (DS), 2007 (PS2), 2007 (PSP), 2007 (PS3), 2007 (Wii), 2007 (X360), 2007 (GBA), 2007 (GC), 2007 (PC) | , Asobo Studio, Locomotive Games, Heavy Iron Studios, Helixe | THQ
Madden NFL 07 | 9 | 2006 (PS2), 2006 (X360), 2006 (XB), N/A (PSP), 2006 (GC), 2006 (PS3), 2006 (Wii), 2006 (DS), 2006 (GBA) | EA Sports, EA Tiburon, EA Canada, Exient Entertainment | Electronic Arts, Unknown
LEGO Harry Potter: Years 5-7 | 8 | N/A (Wii), N/A (X360), N/A (PS3), N/A (DS), N/A (3DS), N/A (PSP), N/A (PC), 2012 (PSV) | Traveller's Tales | Warner Bros. Interactive Entertainment
LEGO Jurassic World | 8 | 2015 (PS4), 2015 (X360), 2015 (PS3), 2015 (XOne), 2015 (3DS), 2015 (WiiU), 2015 (PSV), 2015 (PC) | TT Games | Warner Bros. Interactive Entertainment
The LEGO Movie Videogame | 8 | 2014 (X360), 2014 (PS3), 2014 (3DS), 2014 (PS4), 2014 (WiiU), 2014 (XOne), 2014 (PSV), 2014 (PC) | TT Games | Warner Bros. Interactive Entertainment
Lego Batman 3: Beyond Gotham | 8 | 2014 (PS4), 2014 (X360), 2014 (PS3), 2014 (3DS), 2014 (WiiU), 2014 (XOne), 2014 (PSV), 2014 (PC) | TT Games | Warner Bros. Interactive Entertainment
FIFA 15 | 8 | 2014 (PS4), 2014 (PS3), 2014 (X360), 2014 (XOne), 2014 (PSV), 2014 (Wii), 2014 (3DS), 2014 (PC) | EA Sports | Electronic Arts
LEGO The Hobbit | 8 | 2014 (PS4), 2014 (PS3), 2014 (X360), 2014 (XOne), 2014 (3DS), 2014 (WiiU), 2014 (PSV), 2014 (PC) | TT Games,  | Warner Bros. Interactive Entertainment
Terraria | 8 | 2013 (X360), 2013 (PS3), 2011 (PC), 2013 (PSV), 2016 (3DS), 2014 (PS4), 2014 (XOne), 2016 (WiiU) | Engine Software, Re-Logic, Engine Software, Re-Logic | 505 Games, Unknown, Screenlife
Angry Birds Star Wars | 8 | 2013 (3DS), 2013 (PS3), 2013 (X360), 2013 (Wii), 2013 (PS4), 2013 (XOne), 2013 (WiiU), 2013 (PSV) | Exient Entertainment | Activision
FIFA Soccer 13 | 8 | 2012 (PS3), 2012 (X360), 2012 (Wii), 2012 (WiiU), 2012 (PSV), 2012 (PC), 2012 (PSP), 2012 (3DS) | Electronic Arts | Electronic Arts
Madden NFL 08 | 8 | 2007 (PS2), 2007 (X360), 2007 (PS3), 2007 (Wii), 2007 (PSP), 2007 (XB), 2007 (DS), 2007 (GC) | EA Tiburon, Exient Entertainment | Electronic Arts
Cars | 8 | 2006 (PS2), 2006 (PSP), 2006 (GBA), 2006 (DS), 2006 (GC), 2006 (Wii), 2006 (X360), 2006 (XB) | Rainbow Studios, Locomotive Games, Helixe | THQ
LEGO Star Wars II: The Original Trilogy | 8 | 2006 (PS2), 2006 (PSP), 2006 (DS), 2006 (GC), 2006 (X360), 2006 (XB), 2006 (GBA), 2006 (PC) | Traveller's Tales, Amaze Entertainment | LucasArts, Activision
Monopoly | 8 | 1994 (PC), 2008 (Wii), 1997 (PS), 2008 (X360), 2008 (PS2), 2008 (PS3), 2010 (DS), 1999 (N64) | , Electronic Arts, EA Bright Light | Hasbro Interactive, Electronic Arts
LEGO Marvel's Avengers | 7 | 2016 (PS4), 2016 (XOne), 2016 (X360), 2016 (PS3), 2016 (WiiU), 2016 (3DS), 2016 (PSV) | TT Games | Warner Bros. Interactive Entertainment
Lego Star Wars: The Force Awakens | 7 | 2016 (PS4), 2016 (XOne), 2016 (PS3), 2016 (WiiU), 2016 (3DS), 2016 (X360), 2016 (PSV) | TT Games | Warner Bros. Interactive Entertainment



<br>
<br>

**Število iger proizvedenih po letih.** <br>
Lahko vidimo, da je bil trend rasti do leta 2009, nato pa se je proizvodnja začela upočasnjevati.
<img src="slike/stevilo_iger_proizvedenih_na_leto.png" alt="Število iger proizvedenih na leto">

**Število iger po žanrih** <br>
Kot lahko vidimo iz grafa, je največ akcijskih iger.
<img src="slike/stevilo_iger_po_žanrih.png" alt="Število iger po žanrih">


## Cilji in vprašanja
Tekom analize izbranih podatkov, bomo poizkušali doseči spodnje cilje oz. odgovoriti na naslednja vprašanja:

<!-- * Napovedovanje konca prodaje iger za posamezno platformo -->
* Toplotno karto prodaje vseh iger (USA, JP, EU, other)
* Če ima igra določene žanre, kakšna je verjetnost, da je izdana na določeni konzoli
* Ali so posamezni žanri iger bolj podvrženi določenim platformam?
* Sistem za priporočanje igre. Ideja je, da uporabnik izbere žanr, igralno platformo, starostno skupino in mu na podlagi filtriranih rezultatov sistem priporoči igro na podanih parametrih. Za priporočilo igre se izračuna razmerja critic_scora, user_scora, prodaje. Uteži posameznih kategorij se izračuna glede na število podanih ocen (več je ocen, večjo utež ima slednji atribut).
