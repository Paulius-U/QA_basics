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


# Testavimo atvejai apims šiuos reikalavimus:

Aš kaip vartotojas, noriu pakoreguoti patiekalą (vartotojo)

Aš kaip vartotojas, noriu ištrinti patiekalą (vartotojo)


# Vartotojo patiekalų redagavimas

Tikslas: Patikrinti ar vartotojas gali redaguoti / pakeisti patiekalą savo sąraše ir ar sistema tinkamai tvarkys pakeitimus

 

Testo apimtis: Šis bandymų planas apims naudotojo patiekalų redagavavimas ir galimos pasekmės padarius pakeitimus

 

Išankstinės sąlygos:

Vartotojas turi būti prisijungęs

Vartotojas turi asmeninę paskyrą 

 

1 Testo atvejis: sėkmingai pakeistas patiekalas

Testo etapai:

Naudotojas prisijungia su savo vartotoju 

Nueinama į pagrindinį puslapį kuriame matomas sąrašas visų užrašytų patiekalų

Naudotojas paspaudžia ant pieštuko paveikslėlio sąrašę

Pasirenkamas patiekalas kurį koreguosime 

Pakeičiame patiekalą į kitą norimą 

Patvirtinamas pakeitimas (paspaudžiama išsaugoti)

 

Laukiami rezultatai:

Vartotojas pakeičia vieną patiekalą kitu 

Maistinė vertė pakeičiama nauja pagal patiekalų sąrašą 

Vartotojas gražinamas į pagrindinį puslapį

 

2 Testo atvejis: Neišsaugojama redaguoto patiekalo pakeitimas

Testo etapai:

Naudotojas prisijungia su savo vartotoju 

Nueinama į pagrindinį puslapį kuriame matomas sąrašas visų užrašytų patiekalų

Naudotojas paspaudžia ant pieštuko paveikslėlio sąrašę

Pasirenkamas patiekalas kurį koreguosime 

Pakeičiame patiekalą į kitą norimą 

Grįštama į pagrindinį puslapį

Laukiami rezultatai:

Vartotojas grąžinamas į pagrindinį puslapį

patiekalų sąrašas išlieka nepakeistas

Maistinė vertė nėra pasikeitusi

 

3 Bandymo atvejis:  Redagavimas patiekalų sąrašo neprisijungus

Bandymo etapai:

Vartotojas nėra prisijungęs prie paskyros

Einame į pagrindinį puslapį

Laukiami rezultatai:

Vartotojas bus neleistas eitį į pagrindinį puslapį 

Vartotojas liks login / register puslpyje



# Vartotojas pridėjęs patiekalą kolorijų kiekis padidėje


Tikslas: šiuo bandymu metu patikrinsime ar pridėjus naują patiekalą kolorijų kiekis padidėję 

Testo apimtis: Šis testas apima vartotojo patiekalų įdėjimą į patiekalų sąrašą.

Išankstinės sąlygos:

Vartotojas turi būti prisijungęs 

Vartotojas turi turėti savo paskyrą 

 

1 Senarijus: Pridedamas patiekas su žinomom energinėm vertėm (kolorijom it t.t.)

Testo data:

Patiekalai:

Kiaušinienė (90 cal)

šoninė (42 cal)

skrudinta bulka / Toast (74 cal)

Laukiami rezultatai:

Kalorijų skaičiavimo kiekis yra 90 + 42 + 74 = 206 cal

 

2 Senarijus: Pridedami patiekalai su 0 kalorijų

Testo data:

Patiekalai:

vanduo (0 cal)

Laukiami rezultatai:

Kalorijų skaičiavimo kiekis nepasikeičia

3 Senarijus: Nepridedama joks patiekalas

Testo data:

Patiekalai:

Neprideda joks patiekalas

Laukiami rezultatai:

Kalorijų kiekis išlieka toks koks buvo prieštai



# Review Template

:check_mark::cross_mark: Reikalavimas pilnai aprašytas

:check_mark::cross_mark: Yra įvykdyti visi priėmimo kriterijai

:check_mark::cross_mark: Reikalavimas konkretus (nesipina su kitais reikalavimais)

:check_mark::cross_mark: Aprašytas testavimo planas/scenarijus

:check_mark::cross_mark: Reikalavimas ištestuojamas

:check_mark::cross_mark: Reikalavime nėra dviprasmybių/nėra skirtingai interperuotojas

:check_mark::cross_mark: Reikalavimas atitinka sistemos dalykinę sritį



# Reikalavimuose matomos rizikos
Vartotojo

Aš kaip vartotojas, noriu ištrinti paskyrą:

Nepilnas ištrynimas: Rizika, kad naudotojo paskyra gali būti nevisiškai ištrinta iš sistemos, todėl gali likti asmeninės informacijos.

Atsitiktinis ištrynimas: Vartotojai gali netyčia ištrinti savo paskyras, o atkūrimo mechanizmas gali būti nepakankamas.

Aš kaip vartotojas, noriu pakoreguoti patiekalą:

Duomenų sinchronizavimas: Mitybos pakeitimai gali būti nesinchronizuojami visose atitinkamose programos dalyse, todėl gali atsirasti duomenų neatitikimų.

Aš kaip vartotojas, noriu ištrinti patiekalą:

Duomenų vientisumas: Patiekalo ištrynimas gali turėti įtakos istoriniams duomenims, todėl netinkamai tvarkant duomenis gali kilti problemų dėl duomenų vientisumo.

Patiekalo ištrynimas gali paveikti patiekalų planus, į kuriuos tas patiekalas įtrauktas.

Aš kaip vartotojas, noriu kad prisijungimo duomenys būtų prisimenami (Prisiminti vartotoją):

Susirūpinimas dėl saugumo: prisijungimo duomenų saugojimas automatinio prisijungimo sistemoje gali kelti pavojų saugumui, jei jie nėra tinkamai apsaugoti.

 

Funkciniai (sistemos)

Pridėjus patiekalą, bendras kalorijų kiekis padidėja:

duomenų patvirtinimas: neišsamūs (neužpildžius visus laukelius) arba nenuoseklūs patiekalų duomenys gali lemti netikslius kalorijų skaičiavimus.

Administratorius turi teisę pridėti/atimiti teises iš kitų varotojų:

Neteisėta prieiga: administratoriaus teisės nėra tinkamai valdomos, neįgalioti vartotojai gali gauti prieigą prie jautrių funkcijų ar duomenų.

Atsitiktinis pašalinimas: administratorius gali atsitiktinai pašalinti naudotojų teises, todėl gali sutrikti naudotojų prieiga.

Piktnaudžiavimas: vienas administratorius gali atmiti visas kito administratoriaus teises, nes rolė nėra skirstoma pagal lygius - super admin ir t.t.

Prisijungus yra matomas tikslus tos dienos suvartotų ir likusių kalorijų kiekis:

Yra rizika, kad kalorijų skaičiavimams naudojami duomenys gali būti netikslūs arba neišsamūs, todėl suvartotų ir likusių kalorijų vertės gali būti neteisingos.

Jei sistema susiduria su sunkumais, ieškodama duomenų kalorijų skaičiavimams, gali vėluoti arba naudotojui gali būti rodoma neteisinga informacija.

Administratorius gali: pridėti naują kategoriją (pusryčiai, pietūs, vakarienė ir t.t.), ją pakoreguoti arba ištrinti:

Duomenų praradimas: dėl kategorijų ištrynimo be tinkamo patvirtinimo ar atsarginių kopijų darymo procedūrų gali būti prarasti duomenys, o tai gali turėti įtakos maitinimo planams ir naudotojų patirčiai.

Administratorius atlikus bet kokius pokyčius, šie pokyčiai matosi log’uose:

Yra rizika, kad saugojimo sistema gali neužfiksuoti visų administratoriaus veiksmų arba juos užregistruoti netiksliai. Dėl to gali būti nepastebėti esminiai pakeitimai.

Jei registravimo sistema neužfiksuoja visos svarbios informacijos apie administratoriaus veiksmus (pvz., kas, kada ir ką pakeitė), gali būti sudėtinga veiksmingai šalinti problemas ar atlikti auditą.

 

Nefunkciniai

Vartotojui susikūrus paskyrą, paskyra validuojama per 3 sekundes:

Jei patvirtinimo procesas užtrunka ilgiau nei 3 sekundes, tai gali lemti prastą naudotojų patirtį ir nusivylimą.

Administatoriui atlikus pokyčius, šie pokyčiai log’uose atsiranda per 2 sekundes:

Dėl vėluojančio žurnalų atnaujinimo gali būti neįmanoma veiksmingai sekti ir audituoti administratoriaus veiksmų.

Vartotojo vardas, pavardė, slaptažodis yra saugomas šifruotoje duomenų bazėje:

Dėl netinkamų šifravimo metodų gali būti pažeistas vartotojų duomenų saugumas.

Sistema neleidžia sukurti vartotojo su tuo pačiu prisijungimo vardu (angl. username):

Vartotojai, turintys panašius vardus ar vartotojo vardus, gali likti nepatenkinti registracijos proceso metu, nes jų dažniausiai naudojamas username yra užimtas, o tai gali turėti įtakos naudotojo patirčiai.
