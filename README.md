<p>&nbsp;</p>

# Analiza podatkov s programom R, 2020/21


Repozitorij z gradivi pri predmetu APPR v študijskem letu 2020/21

* [![Shiny](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/NikaFurlan/APPR-2020-21/master?urlpath=shiny/APPR-2020-21/projekt.Rmd) Shiny
* [![RStudio](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/NikaFurlan/APPR-2020-21/master?urlpath=rstudio) RStudio

<p>&nbsp;</p>

### Tematika: **Analiza delovno aktivnega prebivalstva Slovenije**


Izbrali si boste temo, s katero se bo vaš projekt ukvarjal.
Tukaj boste napisali, kje ste dobili podatke, ter kakšen je vaš cilj. 

V projektni nalogi bom analizirala delovno aktivno prebivalstvo. Raziskovala bom, kakšna je povezava med delovno aktivnimi osebami glede na stopnjo izobrazbe, področje dejavnosti, starostno skupino in glede na statistično regijo. Poskušala bom ugotoviti, če obstaja korelacija med stopnjo izobrazbe in deležem delovno aktivnih oseb, in kakšna je. Zanimal me bo delež določenih dejavnosti v posameznih statističnih regijah. Ugotoviti bom poskušala tudi, če obstaja povezava med stopnjo izobrazbe in starostno strukturo, glede na posamezno dejavnost oziroma gospodarsko panogo. Poleg tega bom analizirala delež delovno aktivnega prebivalstva v posameznih regijah glede na gospodarske dejavnosti. 

*"Delovno aktivno prebivalstvo so osebe, ki so v zadnjem tednu (od ponedeljka
do nedelje) pred izvajanjem raziskovanja opravile kakršno koli delo za plačilo
(denarno ali nedenarno), dobiček ali za družinsko blaginjo. Med delovno aktivno
prebivalstvo sodijo tudi vse tiste zaposlene ali samozaposlene osebe, ki jih v
zadnjem tednu pred izvajanjem raziskovanja ni bilo na delo. Kot delovno aktivne
obravnavamo tudi zaposlene osebe, ki so začasni ali trajni presežki, in sicer do
prenehanja delovnega razmerja, osebe na porodniškem dopustu ter pomagajoče
družinske člane."* (Rutar in Tomažič, *AKTIVNO IN NEAKTIVNO PREBIVALSTVO*, https://www.stat.si/statweb/File/DocSysFile/7788, 2020, str.4)


<p>&nbsp;</p>

1. tabela: **Delovno aktivni po stopnji dosežene izobrazbe** (https://pxweb.stat.si/SiStatData/pxweb/sl/Data/-/0762104S.px/table/tableViewLayout2/):


    +  *brez izobrazbe oziroma nepopolna osnovnošolska*
    +  *osnovnošolska*
    +  *nižja ali srednja poklicna*
    +  *srednja strokovna, splošna*
    +  *višješolska, visokošolska*

<p>&nbsp;</p>
    
2. tabela: **Delovno aktivni po področjih dejavnosti**  (https://pxweb.stat.si/SiStatData/pxweb/sl/Data/-/0762105S.px/table/tableViewLayout2/):

    +  *kmetijstvo in lov, gozdarstvo, ribištvo*
    +  *rudarstvo*
    +  *predelovalne dejavnosti*
    +  *oskrba z električno energijo*
    +  *oskrba z vodo, ravnanje z odplakami in odpadki, saniranje okolja*
    +  *gradbeništvo*
    +  *trgovina, vzdrževanje in popravila motornih vozil*
    +  *promet in skladiščenje*
    +  *gostinstvo*
    +  *informacijske in komunikacijske dejavnosti*
    +  *finančne in zavarovalniške dejavnosti*
    +  *poslovanje z nepremičninami*
    +  *strokovne, znanstvene in tehnične dejavnosti*
    +  *druge raznovrstne poslovne dejavnosti*
    +  *dejavnost javne uprave in obrambe, dejavnost obvezne socialne varnosti*
    +  *izobraževanje*
    +  *zdravstvo in socialno varstvo*
    +  *kulturne, razvedrilne in rekreacijske dejavnosti*
    +  *druge dejavnosti*
    +  *dejavnost gospodinjstev z zaposlenim hišnim osebjem, proizvodnja za lastno rabo*
    +  *dejavnost eksteritorialnih organizacij in teles*
<p>&nbsp;</p>

3. tabela: **Delovno aktivni po starostnih skupinah** (https://pxweb.stat.si/SiStatData/pxweb/sl/Data/-/0762103S.px/table/tableViewLayout2/):

    *brez izobrazbe oziroma nepopolna osnovnošolska*
    *osnovnošolska*
    *nižja ali srednja poklicna*
    *srednja strokovna, splošna*
    *višješolska, visokošolska*
<p>&nbsp;</p>

4. tabela: **Delovno aktivno prebivalstvo glede na statistične regije** (https://pxweb.stat.si/SiStatData/pxweb/sl/Data/-/0762104S.px/table/tableViewLayout2/):

    +  *Pomurska*
    +  *Podravska*
    +  *Koroška*
    +  *Savinjska*
    +  *Zasavska*
    +  *Posavska*
    +  *Primorsko-notranjska*
    +  *Osrednjeslovenska*
    +  *Gorenjska*
    +  *Goriška*
    +  *Obalno-kraška*
  


## Program

Glavni program in poročilo se nahajata v datoteki `projekt.Rmd`.
Ko ga prevedemo, se izvedejo programi, ki ustrezajo drugi, tretji in četrti fazi projekta:

* obdelava, uvoz in čiščenje podatkov: `uvoz/uvoz.r`
* analiza in vizualizacija podatkov: `vizualizacija/vizualizacija.r`
* napredna analiza podatkov: `analiza/analiza.r`

Vnaprej pripravljene funkcije se nahajajo v datotekah v mapi `lib/`.
Podatkovni viri so v mapi `podatki/`.
Zemljevidi v obliki SHP, ki jih program pobere,
se shranijo v mapo `../zemljevidi/` (torej izven mape projekta).

## Potrebni paketi za R

Za zagon tega vzorca je potrebno namestiti sledeče pakete za R:

* `knitr` - za izdelovanje poročila
* `rmarkdown` - za prevajanje poročila v obliki RMarkdown
* `shiny` - za prikaz spletnega vmesnika
* `DT` - za prikaz interaktivne tabele
* `rgdal` - za uvoz zemljevidov
* `rgeos` - za podporo zemljevidom
* `digest` - za zgoščevalne funkcije (uporabljajo se za shranjevanje zemljevidov)
* `readr` - za branje podatkov
* `rvest` - za pobiranje spletnih strani
* `tidyr` - za preoblikovanje podatkov v obliko *tidy data*
* `dplyr` - za delo s podatki
* `gsubfn` - za delo z nizi (čiščenje podatkov)
* `ggplot2` - za izrisovanje grafov
* `mosaic` - za pretvorbo zemljevidov v obliko za risanje z `ggplot2`
* `maptools` - za delo z zemljevidi
* `tmap` - za izrisovanje zemljevidov
* `extrafont` - za pravilen prikaz šumnikov (neobvezno)

## Binder

Zgornje [povezave](#analiza-podatkov-s-programom-r-202021)
omogočajo poganjanje projekta na spletu z orodjem [Binder](https://mybinder.org/).
V ta namen je bila pripravljena slika za [Docker](https://www.docker.com/),
ki vsebuje večino paketov, ki jih boste potrebovali za svoj projekt.

Če se izkaže, da katerega od paketov, ki ji potrebujete, ni v sliki,
lahko za sprotno namestitev poskrbite tako,
da jih v datoteki [`install.R`](install.R) namestite z ukazom `install.packages`.
Te datoteke (ali ukaza `install.packages`) **ne vključujte** v svoj program -
gre samo za navodilo za Binder, katere pakete naj namesti pred poganjanjem vašega projekta.

Tako nameščanje paketov se bo izvedlo pred vsakim poganjanjem v Binderju.
Če se izkaže, da je to preveč zamudno,
lahko pripravite [lastno sliko](https://github.com/jaanos/APPR-docker) z želenimi paketi.

Če želite v Binderju delati z git,
v datoteki `gitconfig` nastavite svoje ime in priimek ter e-poštni naslov
(odkomentirajte vzorec in zamenjajte s svojimi podatki) -
ob naslednjem zagonu bo mogoče delati commite.
Te podatke lahko nastavite tudi z `git config --global` v konzoli
(vendar bodo veljale le v trenutni seji).
