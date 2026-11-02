# 10korun: přehled změn

## 3.15.2 (3. 11. 2026)
- Android: formuláře mají zase jen placeholdery místo popisků kolonek. Popisky se po změně písma (3.15.0) omylem ukázaly znovu vedle placeholderů.
- Android: pole IČO (s tlačítkem ARES) má také jen placeholder, ne popisek vedle něj; pole ve formulářích oken jsou samostatné kapsle.

## 3.15.1 (3. 11. 2026)
- iPhone: ve spodní liště se useknul spodek písmen; oprava výšky řádku popisků.

## 3.15.0 (3. 11. 2026)
- Apple: tlačítka jako v iOS 26 (kapsle, průsvitné „sklo“, hlavní tlačítko v barvě aplikace, stisk bez zdvihu), kulatější karty, okna a nabídky; písmo zůstává systémové (SF Pro) bez ručního prostrkání nadpisů.
- Android: tlačítka podle Material 3 (vedlejší jsou textová bez výplně), písmo Google Sans Flex (hostované v aplikaci, licence OFL) a stupnice Material 3.
- Hranice telefon / tablet je sjednocená na 767 / 768 px (na šířce přesně 768 px se rozložení už nepřekrývají).

## 3.13.0 (3. 11. 2026)
- Rozbalovací bloky (accordiony) se rozbalují a sbalují jako roleta: obsah se odvíjí shora dolů a stejně se svine. Respektuje nastavení „omezit pohyb“.
- Výraznější šipka: v zavřeném stavu míří na text, v otevřeném dolů (otáčí se plynule).
- 10korun: rozbalení kontaktů a řádků účetnictví; u řádků přibyla šipka.

## 3.12.1 (3. 11. 2026)
- Záhlaví bottom sheetu: nadpis a křížek jsou ve stejné výšce (v 10space a 10base byl křížek o 10 px níž kvůli zbytku starého pravidla).

## 3.12.0 (3. 11. 2026)
- Okna na mobilu: dialog (potvrzení, krátký formulář) nahoře, menu a formuláře s mnoha kolonkami jako bottom sheet bez držátka s pevným záhlavím (nadpis a křížek), vyjíždí zespodu a zajíždí dolů. Vynucení: atributy data-sheet a data-dialog.
- Tlačítka: Apple (iPhone, iPad, desktop) jedna sada, Android (telefon, tablet) jedna sada. Pilulky, výšky 38 px (akce v řádku 38 px, přihlášení 44 px, filtry 30 px), Apple tučnost 600, Android 500, barva podle akcentu aplikace.
- Zavírací křížek: Apple skleněné kolečko 34 px, Android samotný křížek (dotyková plocha 40 px).
- Oprava: v oknech, která se na telefonu mění na bottom sheet, se na tabletu a počítači objevoval neostylovaný křížek (chyba z 3.11.0).
- 10korun: „+ Přidat“ a přihlášení jsou na Androidu plné (stejně na telefonu i tabletu), tlačítko Google je pilulka 44 px na všech velikostech.

## 3.11.0 (2. 11. 2026)
- Okna na mobilu mají pravidla: potvrzení a krátký formulář s jedním polem jsou nahoře jako modální okno (nezakryje je klávesnice), menu, seznamy a formuláře s mnoha kolonkami jsou bottom sheet bez držátka, s křížkem a tlačítky dole. Sheet vyjíždí zespodu a zajíždí dolů, dialog sjíždí shora.
- Tažení okna dolů už nic nedělá (a v 10base nespouští obnovení stránky).

## 3.10.0 (2. 11. 2026)
- Formuláře na mobilu jsou bottom sheet: okno se vysune zespodu, má držátko a zavře se tažením dolů (tablet a počítač beze změny).

## 3.9.0 (2. 11. 2026)
- 10korun je instalovatelná aplikace: manifest s ikonami (192/512 px), ikona pro plochu iPhonu/iPadu a celoobrazovkový režim. Instalace: Chrome/Android „Nainstalovat aplikaci“, iOS Safari Sdílet → Přidat na plochu. Bez offline režimu (data jsou vždy živá).

## 3.8.0 (2. 11. 2026)
- Záloha účetnictví (Nastavení → Záloha, jen hospodář): „Zálohovat na 10space“ (do vybrané složky; složku lze vybrat ze stromu složek 10space nebo vytvořit novou), „Stáhnout zálohu“ (ZIP: data.json, přehled v Excelu, nahrané doklady) a „Obnovit ze zálohy“ (nahraný ZIP; před obnovou se stáhne záloha současného stavu, čítače čísel se nevrací zpět).
- Upomínka na Přehledu, když poslední záloha je starší než 14 dní nebo žádná nebyla.

## 3.7.0 (2. 11. 2026)
- Doklad (foto nebo PDF) lze nahrát při přidání nového dokladu v Účetnictví (Pokladna i Bankovní účet) a u přijaté faktury; u už uloženého záznamu nebo přijaté faktury ho lze doplnit nebo vyměnit v úpravách. Foto se zmenší, soubor se ukládá do stejné složky jako účtenky z náhrad. Otevření: „Doklad (sken)“ u záznamu a v nabídce faktury.

## 3.6.0 (2. 11. 2026)
- Počítač a tablet po vzoru telefonu: tlačítka a (na Applu) kolonky formulářů mají přesně 38 px a tvar kapsle, přepínače a filtry 30 px; zaoblení karet a oken se nemění.
- Apple: všechna akční tlačítka jsou kapsle na každé velikosti, položky bočního panelu mají jednotné zaoblení.
- Android tablet: spodní lišta je schovaná, ovládá se jen bočním panelem (stejně jako na iPadu); pole formulářů mají každé vlastní kapsli.
- Sbalený boční panel nemá logo, začíná profilovým obrázkem.
- Tablet: karty (faktury, náhrady, projekty, přehled) se řadí vedle sebe, kde se vejdou; v 10korun je Účetnictví o řádek kratší a při sbaleném panelu jsou karty Pokladna a Bankovní účet vedle sebe.

## 3.5.0 (1. 11. 2026)
- Apple: spodní lišta se při posunu stránky dolů zmenší a schová popisky, při posunu nahoru se vrátí; vybranou záložku (kapku skla) jde chytit a přetáhnout prstem na jinou záložku.

## 3.4.0 (1. 11. 2026)
- Tlačítka ve dvojicích na mobilu: výchozí je půl na půl, ale když by se delší text zalomil, kratší tlačítko se zúží na šířku svého textu. Platí i pro dialogy sestavené za běhu.

## 3.3.1 (1. 11. 2026)
- Mobil: tlačítko „+ Nový doklad“ v Účetnictví (Pokladna i Bankovní účet) drží odsazení 16 px od okrajů karty, už se nedotýká okrajů.

## 3.3.0 (1. 11. 2026)
- Animace: po přepnutí sekce se karty zobrazují postupně od nejvyšší dolů, karty níže naskočí při scrollování; rozbalovací nabídky se rozbalují jako roleta shora.
- Mobil: bottom sheet Nový doklad a nabídka u faktury vyjíždějí zdola s animací.

## 3.2.5 (1. 11. 2026)
- Přepínače (Pokladna / Bankovní účet, Příjem / Výdaj, filtry Faktur) jsou menší než tlačítka: 30 px.

## 3.2.4 (1. 11. 2026)
- Oprava: pravidlo pro samostatná tlačítka nově přeskakuje řádky tabulek a seznamů, aby je nerozhodilo.

## 3.2.3 (1. 11. 2026)
- Apple: přepínače (Pokladna / Bankovní účet, Příjem / Výdaj, filtry Faktur) jsou zaoblené do pilulek.

## 3.2.2 (1. 11. 2026)
- Apple (iOS 26): větší zaoblení oken a karet, pilulková tlačítka, zavírání ikonou ✕ / ✓ místo textu Zavřít / Hotovo, nadpisy sekcí ve větném tvaru, zaoblená pole, systémové písmo SF Pro a číslice stejné šířky u částek.
- Tlačítka na mobilu mají jednotnou výšku 38 px; samostatné tlačítko je přes celou šířku.
- Karta tranzitního účtu je na mobilu vycentrovaná; Stáhnout výkazy přes celou šířku.

## 3.2.1 (1. 11. 2026)
- Tlačítka na mobilu: jednotná mřížka (1 = celá šířka, 2 = vedle sebe, 3 = hlavní nahoře a pod ním dvě, 4 = dvě a dvě, 5 = hlavní nahoře a pod ním dvě a dvě); spodní tlačítka oken zůstávají vidět při posouvání.
- Android: hlavní tlačítko je plná pilulka, ostatní jsou textová tlačítka (jako u Google).

## 3.2.0 (1. 11. 2026)
- Opraveno odsazení a přetékání stránky ve všech PDF (žádost o náhradu, palivo, faktury, doklady, přehledy), když byla stránka odscrollovaná.
- Ochrana oken: ✕, Zrušit i Esc se u formuláře s rozepsanými změnami nejdřív zeptají „Zahodit neuložené změny?“; klik mimo okno dál jen zatřese.

## 3.1.10 (1. 11. 2026)
- PDF přehledů: opraveno velké odsazení nahoře a přetékající tabulka při odscrollované stránce.

## 3.1.9 (1. 11. 2026)
- Stáhnout výkazy: roletka s volbou Excel nebo PDF; nové PDF přehledů (2 strany).
- Razítko v Excelu (D43 v Přehledu o P a V, D32 v Přehledu o M a Z); „V likvidaci“ vyplněno NE.

## 3.1.8 (1. 11. 2026)
- Opraveno stahování výkazů do Excelu: soubor se v Excelu (Windows, iPhone) hlásil jako poškozený.

## 3.1.6 (1. 11. 2026)
- Apple: profilové menu ve stylu Liquid Glass (jako spodní lišta).

## 3.1.5 (1. 11. 2026)
- Designový audit: ikonová tlačítka na počítači, větší klikací plochy na dotyku, správná ikona čísla faktury na Androidu.

## 3.1.3 (1. 11. 2026)
- Kompaktní prostředí na počítači: menší pole a písmo, užší okna a formuláře ve sloupcích, hustší tabulky; faktury a náhrady ve dvou sloupcích.

## 3.1.2 (1. 11. 2026)
- Android: spodní lišta je nižší, ikony a popisky jsou menší a aktivní záložka má barvu aplikace.

## 3.1.1 (1. 11. 2026)
Vzhled Androidu podle Material Design 3 (Apple se nemění) a nové formuláře.
- Spodní lišta na Androidu jde od kraje ke kraji a navazuje na spodní hranu.
- Písmo Roboto / Google Sans, ploché plochy bez stínů a rámečků, bílé pozadí a světle šedé karty, zaoblení karet 28 px, tlačítka a pole jako pilulky, nové dialogy.
- Formuláře v oknech: popisek je zástupný text v poli s ikonou, pole za sebou tvoří jeden blok, výběry a soubory jsou pilulky.
- Okna s formulářem se klikem mimo nezavírají, jen se zatřesou.
