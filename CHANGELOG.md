# 10korun: přehled změn

## 3.19.1 (13. 11. 2026)
- Razítko má na všech dokumentech (faktura, zálohová faktura, opravný doklad, pokladní doklady, výkazy v PDF i v Excelu) velikost, při které se celý obrázek včetně podpisu vejde do pole razítka Trodat Printy 4913 (58 × 22 mm): 47,6 × 22 mm (omezuje výška). Dřív se měřil tmavý blok textu na 58 mm a celý obrázek byl 62,1 × 28,7 mm, tedy větší než pole. Výkazy mají podpisový řádek zpět na původním rozměru.

## 3.19.0 (13. 11. 2026)
Zálohové a opravné doklady.
- **Zálohová faktura (ZF):** ve formuláři vystavené faktury volba Faktura / Zálohová faktura, vlastní řada ZF2026001, PDF „ZÁLOHOVÁ FAKTURA“ s upozorněním, že nejde o účetní ani daňový doklad (vystavitel není plátce DPH). Neuhrazená záloha se nepočítá do pohledávek. Po úhradě (spárování s příjmem) jde z ní vystavit **konečnou fakturu**: položky se předvyplní, záloha se na faktuře odečte (zbývá uhradit rozdíl), záloha se označí jako zúčtovaná. Pohledávka z konečné faktury je jen zbývající částka.
- **Opravný doklad k faktuře (dobropis OD):** u vystavené faktury „Vystavit opravný doklad“, u přijaté „Zaevidovat opravný doklad dodavatele“ (řada OP). Snížení zmenší zbývající částku; co přesahuje nebo už bylo uhrazeno, vzniká jako částka k vrácení (OD = závazek vůči odběrateli, OP = pohledávka za dodavatelem) a uzavře se spárováním s platbou. PDF opravného dokladu odkazuje na opravovanou fakturu, důvod a novou částku. Plně opravená neuhrazená faktura se označí „Opravena opravným dokladem“.
- **Opravný doklad k zápisu (§ 35 zákona o účetnictví):** u číslovaného dokladu tlačítko „Opravný doklad“: zadá se správná částka, rozdíl se zaúčtuje novým dokladem s odkazem na původní (záporná částka = snížení, jako červené storno), původní doklad zůstane beze změny. PDF ukazuje původně / správně / rozdíl, důvod, osobu a podpisová pole. V seznamu je štítek OPRAVA a v peněžním deníku záporná částka ve stejném sloupci a kategorii.
- Pohledávky a závazky v přehledu o majetku a závazcích, v knize a v inventurním soupisu počítají zbývající částku (po záloze a opravách) a zahrnují částky k vrácení. Spárování nabízí k příjmu faktury, zálohy a opravné doklady dodavatelů, k výdaji faktury přijaté a opravné doklady vystavené.

## 3.18.0 (13. 11. 2026)
Opravy z kontroly souladu se zákonem o účetnictví (zpráva v `audit-10korun/SOULAD-SE-ZAKONEM-2026-11-13.md`).
- **Uzávěrka období:** v Nastavení lze období uzavřít a znovu otevřít (s důvodem). V uzavřeném období nejde přidávat, upravovat, stornovat ani párovat doklady a faktury, nahoře je pruh „Období je uzavřeno“. Historie uzavření a otevření se ukládá u období. Před uzavřením aplikace upozorní, že chybí inventura kasy nebo inventurní soupis a že jsou doklady bez podkladu. Zámek platí v aplikaci, databázová pravidla ho nevynucují.
- **Inventurní soupis** (tlačítko „Inventura k rozvahovému dni“ v Účetnictví): hotovost (podle uložené inventury kasy z povoleného období), banka (porovnání s výpisem), pohledávky a závazky z neuhrazených faktur plus ostatní řádky, majetek, způsob zjištění, zahájení a ukončení, podpisy provedl / zkontroloval / schválil statutární orgán. Ukládá se do `orgs/10men/inventury` a vzniká PDF (A4). Ukazuje i příjmy za rok proti limitu 3 000 000 Kč pro jednoduché účetnictví spolku.
- **Kniha pohledávek a závazků** (tlačítko ve Fakturách): PDF se všemi fakturami období, úhradou (datum a doklad) a zbývající částkou k datu, součty zvlášť pro pohledávky a závazky.
- **Protistrana je povinná** u dokladu v pokladně a v bance (účastník účetního případu), v novém dokladu i při úpravě.
- **Typ podkladu** u dokladu (faktura, účtenka, smlouva / dohoda, jen výpis z banky, jiný). Bankovní doklad bez přílohy, spárované faktury, žádosti o náhradu a bez volby „jen výpis“ má v seznamu štítek „bez podkladu“.

## 3.17.0 (13. 11. 2026)
- Pokladní doklady PPD a VPD mají vzhled tištěné listiny: pole s linkami (datum, přijato od / vyplaceno komu, účel platby, projekt / kód), částka číslem v rámečku i **slovy**, podpisová pole (pokladník, odevzdal / převzal) a razítko. Vznikají **dvě PDF ve formátu A5 na šířku**: kopie pro pokladnu a kopie pro druhou stranu. Náhled má záložky obou kopií, „Stáhnout PDF“ stáhne zobrazenou kopii a „Stáhnout obě kopie“ obě naráz (`PD2026001 – kopie pro pokladnu.pdf`, `PD2026001 – kopie pro druhou stranu.pdf`).
- Vystavená faktura a protokol o inventuře mají nový, střízlivější vzhled: bílá stránka, tenké linky, červená jen jako krátký akcent, dodavatel vlevo a odběratel vpravo, tabulka položek bez barevné hlavičky, celkem k úhradě jako velké tmavé číslo, platební údaje s QR kódem a razítko v jedné řadě, patička s údaji organizace. Popis položky faktury se do PDF vkládá ošetřený.
- PDF mají skutečné rozměry: faktura a protokol A4 (595 × 842 pt), doklady A5 na šířku (595 × 420 pt). Dřív byla stránka asi 373 × 528 mm, takže se hodilo jen tisknout „přizpůsobit stránce“.
- Razítko (Trodat Printy 4913, otisk 58 × 22 mm) má na všech dokumentech skutečnou velikost: faktura, pokladní doklady, výkazy v PDF a v Excelu. Celý obrázek s podpisem měří 62,1 × 28,8 mm. Ve výkazech zůstala podpisová čára na původní výšce stránky.
- Tlačítko „Spočítat kasu“ je nad kartou Pokladna (na telefonu nad kartou, jen na záložce Pokladna), ne v její hlavičce. Obě karty mají zase stejně vysokou hlavičku.

## 3.16.0 (13. 11. 2026)
- Počítání kasy: v záložce Účetnictví > Pokladna je tlačítko „Spočítat kasu“. Okno má tabulku 12 nominálů od mince 1 Kč po bankovku 5 000 Kč (počet kusů × nominál), mezisoučty mincí a bankovek a vždy viditelný součet. Napočítaná částka se porovná se stavem pokladny z účetnictví (stejné číslo jako zůstatek Pokladny) a ukáže se rozdíl: Sedí / Přebytek / Manko. Enter přeskočí na další nominál, rozepsané počty se při zavření nezahodí bez dotazu.
- „Uložit a vytvořit PDF“ uloží inventuru (datum, počty, součet, stav účetnictví, rozdíl, poznámka, kdo počítal) do orgs/10men/cashCounts a otevře náhled PDF protokolu o inventuře s místem pro podpis „Počítal / Zkontroloval“. V okně je historie posledních 20 inventur s PDF ke každé. Inventury vidí a zapisuje jen hospodář (stávající pravidla databáze, nic se nenasazuje).

## 3.15.2 (3. 11. 2026)
- Android: formuláře mají zase jen placeholdery místo popisků kolonek. Popisky se po změně písma (3.15.0) omylem ukázaly znovu vedle placeholderů.
- Android: pole IČO (s tlačítkem ARES) má také jen placeholder, ne popisek vedle něj; pole ve formulářích oken jsou samostatné kapsle.
- Apple: všechna okna (formuláře, seznamy, volby) jsou plovoucí karta nahoře místo bottom sheetu, jako okno odškrtnutí docházky. Android zůstává u bottom sheetu.
- Oprava (Apple, 10space): primární a nebezpečná tlačítka v dialozích (modal-btn-primary, modal-btn-danger) se vykreslovala jako bílé sklo místo barvy aplikace.
- Tlačítka: jedna velikost na Apple (38 px, písmo 14 px; na počítači s myší kompaktních 34 px), na Androidu 40 px. Nebezpečné tlačítko na Androidu je tonální červené, v patičce okna červený text.
- Okna na Apple (karta): pevné záhlaví a zápatí s tlačítky při rolování, v každém okně křížek, jednotné odsazení aspoň 20 px nahoře i dole.
- Spodní lišta na iPhonu v aplikaci přidané na plochu: zaoblení soustředné s rohem displeje (odsazení R − 32 px podle modelu iPhonu).
- Přístupnost: rozbalovací bloky a rozbalovací řádky jdou ovládat klávesnicí (role, tabindex, aria-expanded, Enter a mezerník).

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
