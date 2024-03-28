# QA_basics

Užduotis:

Sukurti reikalavimo validavimo kriterijus pagal PS specifiką. Pasirinkti bent 5-8 reikalavimų kokybės kriterijus ir 1-3 reikalavimo atitikimus dalykinei sričiai/verslo sričiai. Mokėti pagrįsti jų pasirinkimą 

Atlikti reikalavimų, jų tikimo kriterijų peržiūrą ir inspektavimą taikant patikrinimo sąrašus (checklist). 

Kiekvienam studentui sudaryti/paimti iš specifikacijos 6 reikalavimus: vartotojo (2), nefunkcinių (2), sistemos/funkciniai (2). Tai atlikti Jira BackLog arba DevOps BackLog aplinkoje, Confluence Requirement Template.

Iš visų 6 reikalavimų 3 reikalavimai yra pilna

# Reikalavimo validavimo kriterijai
# Reikalavimų kokybės kriterijai:

Aiškumas: Visi reikalavimai turėtų būti aiškiai suformuluoti, užtikrinant, kad ir naudotojai, ir kūrėjai tiksliai suprastų sistemos elgseną ir naudotojų sąveiką.

Konkretumas: Kiekvienas reikalavimas turėtų būti konkretus ir nedviprasmiškas, nepaliekant vietos interpretacijoms ar neatitikimui naudotojų lūkesčiams.

Šie kriterijai yra esminiai, siekiant užtikrinti, kad visi reikalavimai būtų aiškiai apibrėžti ir būtų išvengta nesusipratimų ir klaidingų interpretacijų kūrimo ir naudojimo metu.

Išmatuojamumas: Kiekvieno reikalavimo sėkmės kriterijai turėtų būti išmatuojami, kad būtų galima atlikti veiksmingą testavimą ir patikrinimą.

Išmatuojamų sėkmės kriterijų turėjimas yra būtinas veiksmingam testavimui ir patvirtinimui, siekiant patikrinti, ar sistema veikia taip, kaip tikimasi.

Išbaigtumas: Reikalavimai turėtų būti išsamūs, apimantys visus funkcionalumo aspektus, įskaitant sąveiką, apribojimus ir klaidų tvarkymą.

Išsamūs reikalavimai sumažina funkcionalumo spragų ar praleidimų tikimybę, todėl pagerėja bendra naudotojų patirtis.

Nuoseklumas: Užtikrinkite, kad visi reikalavimai atitiktų vienas kitą ir bendrą sistemos dizainą, kad būtų išvengta konfliktų ir užtikrinta darni naudotojo patirtis.

Reikalavimų ir sistemos dizaino nuoseklumas užtikrina nuoseklią ir patogią naudoti programą.

 

# Reikalavimų atitikimas dalykinei sričiai / verslo sričiai:

Aktualumas: Patikrinkite, ar visi reikalavimai atitinka dalykinės srities arba verslo srities tikslus, uždavinius ir patiekalų sekimo paskirtį.

Reikšmingumo patvirtinimas užtikrina, kad visi reikalavimai tiesiogiai prisideda prie sistemos suderinamumo su dalykinės srities tikslais.

Efektyvumas: Įvertinkite, ar sistemos funkcijos užtikrina veiksmingą maitinimo stebėjimą, kad naudotojai galėtų veiksmingai tvarkyti savo maitinimą.

Efektyvumo kriterijai garantuoja, kad sistemos funkcionalumas padeda efektyviai sekti maistą ir didina naudotojų pasitenkinimą.

Tikslumas: Užtikrinkite, kad sistemos skaičiavimai ir stebėjimas tiksliai atspindėtų maistinę informaciją ir kalorijų skaičių, kad būtų patenkinti naudotojų mitybos poreikiai.

Mitybos skaičiavimų ir kalorijų skaičiavimo tikslumo užtikrinimas yra labai svarbus, kad sistema veiksmingai atliktų savo paskirtį.

# Reikalavimai:
Vartotojo

Aš kaip vartotojas, noriu ištrinti paskyrą.

Aš kaip vartotojas, noriu pakoreguoti patiekalą.

Aš kaip vartotojas, noriu ištrinti patiekalą.

Aš kaip vartotojas, noriu kad prisijungimo duomenys būtų prisimenami (Prisiminti vartotoją)

 

Funkciniai (sistemos)

Pridėjus patiekalą, bendras kalorijų kiekis padidėja.

Administratorius turi teisę pridėti/atimiti teises iš kitų varotojų.

Prisijungus yra matomas tikslus tos dienos suvartotų ir likusių kalorijų kiekis.

Administratorius gali: pridėti naują kategoriją (pusryčiai, pietūs, vakarienė ir t.t.), ją pakoreguoti arba ištrinti.

Administratorius atlikus bet kokius pokyčius, šie pokyčiai matosi log’uose.

 

Nefunkciniai

Vartotojui susikūrus paskyrą, paskyra validuojama per 3 sekundes.

Administatoriui atlikus pokyčius, šie pokyčiai log’uose atsiranda per 2 sekundes.

Vartotojo vardas, pavardė, slaptažodis yra saugomas šifruotoje duomenų bazėje.

Sistema neleidžia sukurti vartotojo su tuo pačiu prisijungimo vardu (angl. username).
