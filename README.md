# Topografi 10 – QGIS-stilar

Tre varianter av Lantmäteriets stilfil `Topografi10_vektor_260605.qlr` för Topografi 10 (vektor, GeoPackage).

| Fil | Färgsättning |
|---|---|
| `Topografi10_vektor_260605_farg.qlr` | Lantmäteriets originalfärger |
| `Topografi10_vektor_260605_farg_ljus.qlr` | Ljusare färgsättning av mark, byggnader och vägar (efter Varbergs kommuns bakgrundskarta) |
| `Topografi10_vektor_260605_nedtonad.qlr` | Nedtonad grå karta, vatten i HMK-Kartografi 2025:s ljusare blå (bilaga B.1.2) |

## Så används de

1. Lägg qlr-filen i samma mapp som GeoPackage-filerna. Filerna ska heta:
   `anlaggningsomrade.gpkg`, `byggnadsverk.gpkg`, `hojd.gpkg`, `hydro.gpkg`, `kommunikation.gpkg`,
   `ledningar.gpkg`, `mark.gpkg`, `militartomrade.gpkg`, `naturvard.gpkg`, `norrapolcirkeln.gpkg`, `text.gpkg`.
   Lantmäteriets nedladdningar heter ofta t.ex. `hydro_kn1234.gpkg` – döp då om dem (ta bort `_knXXXX`)
   eller peka om lagren i QGIS.
2. Dra in qlr-filen i QGIS (*Lager → Lägg till från lagerdefinitionsfil*).
3. Typsnittet **LMTopografisymboler** (från Lantmäteriet) behöver vara installerat för punktsymbolerna.

Kräver QGIS 3.38 eller senare (provat i QGIS 4.2).

## Skillnader mot Lantmäteriets original

- Allt är utformat för 1:10 000. Utzoomat krymper linjer, symboler och text som med en referensskala;
  inzoomat blir de inte tjockare än i 1:10 000.
- Vägarnas bredd växer inzoomat (ungefär verklig vägbredd), men kantlinjen förblir tunn.
- Gatunamn följer vägens bredd inzoomat, men blir aldrig högre än vägsymbolen och aldrig mindre än i 1:10 000.
  Sammanhängande gatusegment slås ihop och långa gator upprepar namnet med ca 100 mm mellanrum.
- Typsnittssymboler (t.ex. prickarna på kraftledningar) döljs när de skulle bli mindre än 0,4 mm,
  så att de inte flyter ihop utzoomat.
- Ortnamn och upplysningstext visas inte utzoomat förbi 1:50 000.
- Symbolen som använde typsnittet Dingbats (Slussport) är ersatt med en enkel markör.
