I den här mappen finns data i form av csv-filer (i zip-format pga storleken) för den statistik som presenteras på KB:s sida [Öppen tillgång i siffror](https://www.kb.se/samverkan-och-utveckling/oppen-tillgang-och-bibsamkonsortiet/oppen-tillgang/oppen-tillgang-i-siffror.html). Data består av Swepub-data ([dump juni 2024](https://bibliometri.swepub.kb.se/bibliometrics/datadump)) matchat på DOI med data från [Unpaywall](https://unpaywall.org/) (insamlat via API under perioden 2024-06-07 till 2024-06-14). Data är filtrerat till publicerade sakkunniggranskade artiklar enligt Swepub. Informationen om öppen tillgång (KB:s variabler i nyckeln nedan) är beräknade genom Unpaywall-data, se varje variabel för detaljer. Tidigare års data finns i respektive mapp.

Det finns en totalfil var för publiceringsåren 2019 till 2023 (oa_2024_results_xxxx.zip), samt ytterligare två filer för publiceringsår 2023 fördelat på lärosäten (oa_2024_results_orgs_2023.zip) och forskningsämnen på 1-siffernivå enligt [Standard för svensk indelning av forskningsämnen](https://www.scb.se/dokumentation/klassifikationer-och-standarder/standard-for-svensk-indelning-av-forskningsamnen/) (oa_2024_results_subj_2023.zip).

Observera att filerna är konstruerade så att om flera organisationer som levererar data till Swepub levererat samma artikel och artikeln inte fångats upp i dedupliceringsprocessen blir det en ny rad för varje levererande lärosäte (gäller årsfilerna). Därtill blir det en rad för varje typ av öppen tillgång som Unpaywall identifierat (gäller alla filer). De två filerna med lärosäten respektive forskningsämnen är uppbyggda så att om en artikel är affilierad (observera - inte levererad utan affilierad) till flera organisationer finns en rad per organisation och typ av öppen tillgång via Unpaywall. Motsvarande gäller för forskningsämnena, om en artikel är klassificerad till flera forskningsämnen finns en rad per forskningsämne och typ av öppen tillgång via Unpaywall. I dessa båda filer finns även DOI:er som inte matchats i Unpaywall, dessa rader har NA angivet för Unpaywall-data. En artikel förekommer alltså på flera rader, med unik information för varje rad.

Underlag för KB:s statistik för öppen tillgång utgörs av variablerna <br>
*all_oa*, *journal_is_in_doaj*, *hybrid*, *repo* och *only_repo*.

**Variabelnyckel**<br>
För alla filer i bokstavsordning.<br>
Vissa av variablerna finns endast i vissa filer.<br>
Inom parentes anges källa för variabeln.<br>
För Unpaywall-variablerna finns mer information här: https://unpaywall.org/data-format<br>
För Swepub-variablerna finns mer information här: https://www.kb.se/samverkan-och-utveckling/swepub/datamodell/swepub-bibframe.html<br>
<br>
| Variabel | Beskrivning |
| :------ | :--------- |
<!--- | *aff (Swepub)* | Auktoriserad affiliering till upphovsperson i Swepub.<br> | --->
| *all_oa (KB)* | All typ av öppen tillgång enl KB:s kriterier, dvs artikel i DOAJ-indexerad tidskrift, hybridartikel eller en publicerad eller accepterad version av artikeln i ett repositorium.<br> |
| *change_date (Swepub)* | Datum då posten ändrades i organisationskällan.<br> |
| *content_type (Swepub)* | Innehållsmärkning, här refereegranskat (https://id.kb.se/term/swepub/svep/ref).<br> |
| *creation_date (Swepub)* | Datum då posten skapades i organisationskällan.<br> |
| *creator_count (Swepub)* | Antal upphovspersoner.<br> |
| *deliver_org (Swepub)* | Organisationskod för den organisation som levererat data.<br> |
| *doi (Unpaywall/Swepub)* | DOI:er i Swepubs dump är inte alltid angivna i korrekt format beroende på hur lärosätena registrerat dem. Unpaywalls API hanterar vissa formatfel, exv versaler/gemener men är DOI felaktig blir det ingen träff.<br> |
| *embargo (Swepub)* |  Om det finns information om embargo från levererande organisation finns den angiven här.<br> |
| *endpoint.id (Unpaywall)* | Unpaywalls id.<br> |
| *evidence (Unpaywall)* | Hur den öppet tillgängliga artikeln har hittats.<br> |
| *host_type (Unpaywall)* | Vilken typ av värd, förlag eller repositorium, som står bakom artikelversionen.<br> |
| *hybrid (KB)* | Hybridartikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: journal_is_in_doaj = FALSE och host_type = publisher och licensen är en CC-BY-variant.<br> |
| *is_best (Unpaywall)* | Den bästa platsen för öppen tillgång enligt Unpaywalls kriterier.<br> |
| *is_oa (Unpaywall)* | Finns öppet tillgänglig version enligt Unpaywalls kriterier.<br> |
| *journal_is_in_doaj (Unpaywall)* | Om artikeln finns publicerad i en DOAJ-indexerad tidskrift.<br> |
| *license (Unpaywall)* | Licensieringen för den här versionen.<br> |
| *licencing (KB)* | Licensiering enligt post i Swepub.<br> |
| *nr_publs (Swepub)* | Anger hur många levererade poster som bygger upp den sammanslagna posten, deduplicerade posten i Swepub. Dedupliceringsprocessen i Swepub är under utveckling.<br> |
| *nr_of_contr (KB)* | Kontrollsiffra för att kontrollera Swepubs dedupliceringsprocess.<br> |
| *nr_uka1 (KB)* | Hur många forskningsämnen på 1-siffernivå som artikeln har angivet.<br> |
| *oa (Swepub)* | Information om öppen tillgång enligt levererande organisationer. Beroende på lokalt system kan möjligheten att leverera den här typen av information variera mellan organisationerna.<br> |
| *oa_date (Unpaywall)* | Det datum artikeln först blev tillgänglig via den här platsen.<br> |
| *only_repo (KB)* | Om artikeln endast finns i repo, alltså inte är publicerad i en DOAJ-indexerad tidskrift och inte som hybrid markeras detta genom den här variabeln för att kunna särskilja dessa i statistiken.<br> |
| *output_type (Swepub)* | Outputtyp, här tidskriftsartikel (https://id.kb.se/term/swepub/publication/journal-article).<br> |
| *pmh_id (Unpaywall)* | OAI-PMH endpoint för den här platsen.<br> |
| *publ_date (Swepub)* | Publiceringsår.<br> |
| *publ_id (Swepub)* | Id för artikelposten från levererande organisation. I de sammanslagna, deduplicerade, posterna anges publ_id för den levererande organisation som utgör grund för masterposten. Dedupliceringsprocessen i Swepub är under utveckling.<br> |
| *publ_language (Swepub)* | Språkkod.<br> |
| *publ_status (Swepub)* | Publiceringsstatus, här publicerad (https://id.kb.se/term/swepub/Published).<br> |
| *publ_title (Swepub)* | Artikelns titel.<br> |
| *publ_year (KB)* | Extracted publication year from publ_date.<br> |
| *publisher (Swepub)* | Förlag enligt levererande organisation.<br> |
| *repo (KB)* | Parallellpublicerad artikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: host_type = repository och versionen är antingen publishedVersion eller acceptedVersion.<br> |
| *repository_institution (Unpaywall)* | Värd för repositoriet.<br> |
| *source (Swepub)* | Organisation som registrerat publikationen, används för beräkning av andel öppen tillgång per lärosäte. <br> |
| *swedish_list (Swepub)* | Poster med värdet https://id.kb.se/term/swepub/swedishlist/peer-reviewed är med i svenska listan.<br> |
| *updated  (Unpaywall)* | Tidpunkt när data för den här artikeln senast uppdaterades.<br> |
| *uka_code (Swepub)* | Forskningsämne på 1-siffernivå.<br> |
| *url (Unpaywall)* | URL för PDF om den finns, annars URL för landningssida.<br> |
| *url_for_landing_page (Unpaywall)* | URL för landningssidan som beskriver den öppet tillgängliga artikeln.<br> |
| *url_for_pdf (Unpaywall)* | URL med öppet tillgänglig PDF-version av artikeln.<br> |
| *version (Unpaywall)* | Vilken version av artikeln som finns tillgänglig.<br> |

Har du frågor eller kommentarer? Kontakta <openaccess@kb.se>
