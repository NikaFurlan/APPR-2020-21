<p>&nbsp;</p>

# **Analiza podatkov s programom R, 2020/21**


Repozitorij z gradivi pri predmetu APPR v študijskem letu 2020/21

* [![Shiny](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/NikaFurlan/APPR-2020-21/master?urlpath=shiny/APPR-2020-21/projekt.Rmd) Shiny
* [![RStudio](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/NikaFurlan/APPR-2020-21/master?urlpath=rstudio) RStudio

<p>&nbsp;</p>

### Tematika: **Analiza delovno aktivnega prebivalstva**


Izbrali si boste temo, s katero se bo vaš projekt ukvarjal.
Tukaj boste napisali, kje ste dobili podatke, ter kakšen je vaš cilj. 

V projektni nalogi bom analizirala delovno aktivno prebivalstvo na ravni statističnih regij z vidika starostne strukture delavcev, njihove izobrazbe, vrste dejavnosti v kateri so zaposleni, sektorja (javni, zasebni) in vrsto pogodbe o zaposlitvi. Raziskovala bom povezave med:

* vrsto pogodbe in starostno strukturo zaposlenih,
* vrsto pogodbe in stopnjo izobrazbe,
* stopnjo izobrazbe in sektorjem zaposlitve, med 
* stopnjo izobrazbe in vrsto dejavnosti, 
* vrsto pogodbe in sektorjem,

 
Raziskovala bom, kakšna je povezava med vrsto delovnega razmerja v posameznih panogah glede na doseženo stopnjo izobrazbe in glede na starostno strukturo delovno aktivnega prebivalstva (npr. zanimalo me bo, kdaj, če, v posameznih panogah zaposleni dobijo pogodbo o delovnem razmerju za nedoločen čas - ali je mogoče odvisno od nivoja izobrazbe in starosti). Zanimalo me bo, v katerih dejavnosti je pogodba za nedoločen čas najlažje dosegljiva in v katerih dejavnostih je morda večji delež pogodb za določen čas. Glede na posamezne gospodarske dejavnosti bom analizirala razmerje med pogodbami za nedoločen in določen čas glede na starost zaposlenih. Poleg tega bom razmerja med izobrazbo, starostjo in dejavnostjo raziskala tudi na ravni statističnih regij in vrsto pogodbe primerjala tudi na ravni javnega in zasebnega sektorja.


*"Delovno aktivno prebivalstvo so osebe, ki so v zadnjem tednu (od ponedeljka
do nedelje) pred izvajanjem raziskovanja opravile kakršno koli delo za plačilo
(denarno ali nedenarno), dobiček ali za družinsko blaginjo. Med delovno aktivno
prebivalstvo sodijo tudi vse tiste zaposlene ali samozaposlene osebe, ki jih v
zadnjem tednu pred izvajanjem raziskovanja ni bilo na delo. Kot delovno aktivne
obravnavamo tudi zaposlene osebe, ki so začasni ali trajni presežki, in sicer do
prenehanja delovnega razmerja, osebe na porodniškem dopustu ter pomagajoče
družinske člane."* (Rutar in Tomažič, *AKTIVNO IN NEAKTIVNO PREBIVALSTVO*, https://www.stat.si/statweb/File/DocSysFile/7788, 2020, str.4)


<p>&nbsp;</p>

1. tabela: **Zaposleni glede na vrsto delovnega razmerja, po starostnih razredih in spolu med letoma 2008 in 2019** (oblika CSV):


    
2. tabela: **Delovno aktivno prebivalstvo v javnem in zasebnem sektorju po doseženi izobrazbi in spolu med letoma 2008 in 2019**  (oblika CSV):



3. tabela: **Delovno aktivno prebivalstvo po dejavnosti (SKD 2008), doseženi izobrazbi in spolu med letoma 2008 in 2019** (oblika: HTML):

  


4. tabela: **Delovno aktivno prebivalstvo glede na statistične regije med letoma 2008 in 2019** (oblika CSV):

   
    
  


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
