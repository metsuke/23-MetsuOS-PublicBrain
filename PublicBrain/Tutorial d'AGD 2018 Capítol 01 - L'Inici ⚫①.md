---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: CA
translations: 
created: 2025-06-02T21:45:37.355Z
modified: 2025-06-10T05:07:49.164Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 15
nav_primary: 
nav_secondary: 
tags:
---
# Tutorial d'AGD 2018 Capítol 01 - L'Inici ⚫①

![Menú Principal d'AGD](PublicBrain/_resources/d331958696fd5f055f430f879c2d361e_MD5.jpg)

```
CONTINGUT EXPERIMENTAL
```

* [[Tutorial de AGD 2018 Edition ⚫①|Tutorial d'AGD Edició 2018]]
* [[Tutorial de AGD 2018 Capitulo 02 - Qué son los tiles ⚫①|Següent >>]]

## AGD: Capítol u

Hola a tothom! Comencem aquí un tutorial.

Fa temps que una part de la comunitat de parla hispana desitjava aquest tutorial, que no és altre que la versió en català dels [coneguts vídeos de Paul Jenkinson 🌐🟡③](http://randomkak.blogspot.com.es/p/agd-video-tutorials.html) sobre aquest fantàstic creador de jocs.

A més de la qüestió de l'idioma, hi ha la qüestió de la versió. Aquells tutorials són de l'any 2012 i es refereixen a l'AGD 3.0.

En el moment d'escriure aquestes línies, estic utilitzant la versió 4.7 i he considerat, per tant, interessant agafar el relleu i començar aquesta actualització - traducció d'aquests tutorials.

Tot i això, no tot serà idèntic. Seguiré l'ordre assenyadament indicat als vídeos originals, però hi haurà canvis.

Amb l'ajuda d'en Sergio 'thEpOpE' i altres companys, intentaré ampliar i complementar aquest curs amb articles extres i diversos trucs.

Però anem per passos, primer, aquesta fase :)

## Per què un tutorial d'AGD en text i no en vídeo? (almenys per ara) 

![Símbol internacional de la sordesa](PublicBrain/_resources/271247068c96f3430cde1413b03b2207_MD5.jpeg) 

Sens dubte, l'objectiu final és disposar de totes dues versions. 

Tanmateix, qualsevol vídeo realment accessible ha de comptar amb transcripció i/o subtítols per a persones amb discapacitat auditiva. 

Atesos els objectius universals d'aquest tutorial, he cregut convenient crear-lo primer en text. 

Més endavant, pretenc utilitzar aquesta versió com a transcripció del vídeo. 

Un cop fetes les dues coses, l'obra estarà completa. 

(Nota 2025: La generació de la versió en vídeo podria ser un exercici interessant per practicar amb IA aplicada al retro) A més de la qüestió d'accessibilitat, hi ha la qüestió del guió. No vull improvisar més del compte per ensenyar com fer-ho, de manera que aquesta primera versió també servirà com a guió per als vídeos. 

Dit això, anem al gra! 
## Què és l'AGD? 

![Avatar de Facebook de Jonathan Cauldwell](PublicBrain/_resources/5b26752dfaeefe317c30063efa24f28e_MD5.jpeg) 

Si has arribat fins aquí, segurament ja ho saps, però tot i així ho explicaré: **AGD** (sigles d'_Arcade Game Designer_, o "Dissenyador de Jocs Arcade") és un programari creat per [Jonathan Cauldwell 🌐🟡③](https://www.facebook.com/jonathan.cauldwell) que serveix per crear jocs arcade. Compta amb diferents eines, s'executa a la màquina per a la qual desenvolupem el nostre joc i fins i tot inclou una mena de BASIC que ens permet definir i controlar la lògica de la nostra petita obra. 

Hi ha diferents versions, però en aquest tutorial ens centrarem en la **versió 4.7 per a ZX Spectrum**, l'última disponible en el moment d'escriure aquestes línies. Al fòrum d'AGD (en anglès) - ttp://arcadegamedesigner.proboards.com/ - pots _*(Nota 2025: "podries", actualment no està disponible)*_ estar al dia de tot el que es cou al voltant d'aquesta eina. ## Al gra: Com utilitzo l'AGD? 

![Caixa del ZX-UNO](PublicBrain/_resources/cd88d7ac98116b1ab537a3e8e411153a_MD5.jpg)

Res més fàcil. Després de [descarregar el nostre Kit d'Iniciació 🟡③](https://metsuke.com/assets/dnld/AGD_Starter_Kit_0_3.zip) i descomprimir-lo, podem observar que l'AGD ve en format `.tap`, de manera que només cal carregar-lo al teu emulador o màquina habitual. 

L'únic que cal tenir en compte és que l'AGD va ser dissenyat originalment per al **ZX Spectrum 128k**, per la qual cosa es recomana carregar-lo en aquest mode. Tot i això, jo el faig servir amb _Retro Virtual Machine_ en una màquina _+2 Gris_ i no he tingut problemes, excepte algunes corrupcions de memòria en utilitzar l'editor de codi i de textos. No puc afirmar que sigui a causa del canvi de model, però tampoc no costa gaire respectar aquest requisit per estar del costat segur. 

Tot i així, no es pot afirmar amb rotunditat que utilitzar un altre model causi problemes concrets, de manera que queda a les mans de cadascú seguir o no aquesta recomanació. 

Mentre carregueu la cinta, us vull comentar un aspecte important: **l'AGD no és retrocompatible**. El que es just amb l'AGD 4.6 no es pot modificar amb l'AGD 4.7, per tant: 

1. Guarda versions de tots els AGD que utilitzis. 
2. Tria molt bé quina versió fas servir per a un joc, perquè un cop començat no podràs canviar a una altra sense reescriure-ho tot. 
 
### D'acord, i ara? La càrrega inicial 

Després de la càrrega apareixerà la pantalla del menú principal que hem vist al començament d'aquest capítol. Aquesta conté accessos mitjançant dreceres de teclat a totes les opcions que ofereix aquesta eina. 

A més de la llista d'opcions, a la pantalla del menú apareix: 

- La versió actual de l'AGD a la canton ada superior esquerra. 
- La memòria lliure restant a la superior dreta. És important revisar aquesta memòria regularment per assegurar-nos que el consum de memòria per als diferents elements del nostre joc és equilibrat. Si no ho controlem, podem trobar-nos que ens quedem sense memòria a mig desenvolupament. 

Tot i que acabarem recorrent-les totes, per fer la corba d'aprenentatge el més senzilla possible seguirem l'ordre "lògic" establert per l'autor dels vídeos en anglès, que em sembla molt encertat. En primer lloc, prestarem atenció a: 

- **A - Editor de Caràcters (Character Editor)** 
- **W - Àrea de Joc (Window Area)** 
- **K - Tecles (Keys)** 
- 
## A - Editor de Caràcters (Character Editor) 

![Tutorial d'AGD: Editor de Caràcters](PublicBrain/_resources/a6d36f600620a940d92a720cce91d663_MD5.jpeg)

Tot i que no ens hi aturarem gaire, ja que és força autoexplicatiu, per motius de completesa d'aquest tutorial d'AGD cal dir que en aquesta pantalla podrem redefinir la font per defecte del Spectrum per crear tant les nostres pròpies lletres com números i símbols. 

Per accedir-hi, premem **A** des del menú principal. Veurem tota la graella de caràcters disponibles del joc, així com l'àrea on editarem el caràcter seleccionat.

Per avançar i retrocedir utilitzarem **N** (Next/Següent) i **P** (Previous/Anterior). Un cop seleccionat el caràcter que volem editar, utilitzarem les tecles del cursor per moure'ns pel caràcter i la tecla **Espai** per posar o treure píxels. 

Un cop tot estigui al nostre gust, amb **Intro** tornem al menú principal, així de senzill. 

L'editor compta amb opcions per carregar i desar fonts de cinta, però no ho explicarem aquí perquè queda fora de l'objectiu d'aquest tutorial introductori. 

## W - Àrea de Joc (Window Area) 

![Tutorial d'AGD: Pantalla de definició de l'àrea de joc](PublicBrain/_resources/8c7f55f86445b877886888a838756bc6_MD5.jpeg) 

El primer que hem d'indicar en el nostre joc realitzat amb AGD és l'àrea de pantalla. No s'ha de triar a la lleugera, ja que un cop definida, si la canviem, l'AGD esborrarà gran part del treball realitzat fins al moment. 

Prenem-nos el temps per decidir si volem un joc horitzontal o, en general, qualsevol de les configuracions possibles. 

Per definir-la, l'AGD ens ho posa molt fàcil: tan senzill com utilitzar les tecles: 

```pre
TECLATS 
======= ------------------------------------- 
- 1/2 per augmentar o disminuir la mida horitzontal. 
- Q/A per variar la mida vertical. 
- 5/6/7/8 per moure el bloc (format pels quadrats vermells i negres) per la pantalla.
```

És en aquesta àrea de quadres de color on el nostre joc cobrarà vida. Un cop definida, tan senzill com prémer **Intro** i tornem al menú principal.

**Recordeu**: Si la canvieu, l'AGD esborrarà totes les pantalles creades i les posicions dels sprites (gràcies, Sergio), així que decidiu amb cura com serà la vostra àrea de joc abans de llançar-vos a desenvolupar la resta!

## K - Tecles (Keys)

![Tutorial d'AGD: Pantalla de selecció de tecles](PublicBrain/_resources/9a5009f7fac27c93f249c9d87e11ca89_MD5.jpeg)

Per concloure aquesta primera part del nostre tutorial d'AGD, direm a l'entorn quines seran les nostres tecles de control.

Per fer-ho, premem **K** i el sistema ens demanarà (atenció, que aquí demana les tecles en un ordre quan menys poc habitual):

- Dreta
- Esquerra
- Avall
- Amunt
- Dispar
- 2 més assignades com a 6 i 7 que poden servir per a qualsevol propòsit que vulguem.

Un cop finalitzada la selecció, l'editor ens porta automàticament al menú principal.

Tinguem en compte que aquestes seran les tecles que l'AGD detecti quan creem el codi que controla el nostre protagonista. Per això, tingueu cura en definir-les i, sobretot, **apunteu-les en algun lloc** per poder consultar-les, ja que l'AGD no ofereix cap manera de "visualitzar" quines són les tecles definides actualment.

Això serà tant més important quan comencem a utilitzar tecles per a accions que, a priori, no siguin les mateixes per a les quals van ser pensades.

## Resumint

![Pantalla de càrrega de The Big Javis Adventure](PublicBrain/_resources/944ab7fdce26b6a4483ee2fd581eabd7_MD5.jpeg)

En aquesta primera aproximació hem après el maneig bàsic de l'editor, així com a definir caràcters, l'àrea de joc i les tecles.

En la segona part continuarem el nostre camí per aconseguir crear el nostre primer joc amb AGD.

Només una cosa més: us prego que no us limiteu a seguir els passos d'aquest tutorial d'AGD com a autòmats. Experimenteu, proveu, perdeu la por a trencar, perquè és l'única manera d'aprendre: perdre de vista la costa i, si cal, tornar nedant.

## I ara què?

- [[Tutorial d'AGD 2018 Capítol 01 - L'Inici ⚫①|Si el normal és que no facis tiles, queda't a la pàgina 1]]
- [[Tutorial d'AGD 2018 Capítol 02 - Què són els tiles ⚫①|Si tiles i lleons són tots campions, passa a la pàgina 2]]

## Referències Bibliogràfiques

- [Els vídeos sobre AGD de Paul Jenkinson 🌐🟡③](http://randomkak.blogspot.com.es/p/agd-video-tutorials.html)

## Lang
* **[[Tutorial d'AGD 2018 Capítol 01 - L'Inici ⚫①|CA]]** | [[AGD 2018 Tutorial Chapter 01 - The Beginning ⚫①|EN]] | [[Tutorial de AGD 2018 Capitulo 01 - El Comienzo ⚫①|ES]]


