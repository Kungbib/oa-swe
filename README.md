
Här finns data i form av zippade csv-filer för den statistik som presenteras på KB:s sida [Öppen tillgång i siffror](https://www.kb.se/samverkan-och-utveckling/oppen-tillgang-och-bibsamkonsortiet/oppen-tillgang/oppen-tillgang-i-siffror.html). Data består av Swepub-data ([dump maj 2026](https://bibliometri.swepub.kb.se/bibliometrics/datadump)) matchat på DOI med data från [Unpaywall](https://unpaywall.org/) (insamlat via API under perioden 2026-05-07 till 2026-05-16). Data är filtrerat till publicerade sakkunniggranskade artiklar enligt Swepub. Informationen om öppen tillgång (KB:s variabler i nyckeln nedan) är beräknade genom Unpaywall-data, se varje variabel för detaljer. Tidigare års data finns i respektive mapp.

Nytt för i år är att uppgifter från [Bibsamkonsortiets publiceringsfil](https://github.com/Kungbib/oa-tskr/tree/master/Bibsam_artikeldata) och [OpenAPC](https://github.com/OpenAPC/openapc-de/tree/master/data) har använts som komplement till Unpaywall för uppgifter om öppen tillgång. Fyra nya variabler har som en följd av detta lagts till i tabellen nedan, *bibsam_oa_type*, *oa_final*, *open_apc_oa_type* och *up_oa*. Se beskrivning av dem i variabelnyckeln nedan.

Underlag för KB:s statistik för öppen tillgång utgörs av variablerna <br>
*all_oa*, *bibsam_oa_type*, *hybrid*, *journal_is_in_doaj*, *only_repo*, *open_apc_oa_type*, *repo* och *up_oa*, och presenteras i kolumnen *oa_final*.

Det finns en totalfil vardera för publiceringsåren 2021 till 2025 (oa_2026_results_xxxx.zip), samt ytterligare två filer för publiceringsår 2025 fördelat på lärosäten (oa_2026_results_orgs_2025.zip) och forskningsämnen på 1-siffernivå enligt [Standard för svensk indelning av forskningsämnen](https://www.uka.se/statistik-och-analys/om-var-statistik/information-om-statistiken?plusbox=12_16cf0f8c1849df46622a1f_button) (oa_2026_results_subj_2025.zip).

Observera att filerna är konstruerade så att om flera organisationer som levererar data till Swepub levererat samma artikel och artikeln inte fångats upp i dedupliceringsprocessen blir det en ny rad för varje levererande lärosäte (gäller årsfilerna). Därtill blir det en rad för varje typ av öppen tillgång som Unpaywall identifierat (gäller alla filer). De två filerna med lärosäten respektive forskningsämnen är uppbyggda så att om en artikel är affilierad (observera - inte levererad utan affilierad) till flera organisationer finns en rad per organisation och typ av öppen tillgång via Unpaywall. Motsvarande gäller för forskningsämnena, om en artikel är klassificerad till flera forskningsämnen finns en rad per forskningsämne och typ av öppen tillgång via Unpaywall. I dessa båda filer finns även DOI:er som inte matchats i Unpaywall, dessa rader har NA angivet för Unpaywall-data. En artikel förekommer alltså på flera rader, med unik information för varje rad.

I sammanställningarna har från 2024 uppgifter om vilka lärosäten som rapporterat publikationen till Swepub använts som utgångspunkt för öppen tillgång per lärosäte.

**Variabelnyckel**<br>
För alla filer i bokstavsordning.<br>
Vissa av variablerna finns endast i vissa filer.<br>
Inom parentes anges källa för variabeln.<br>
För Unpaywall-variablerna finns mer information här: https://unpaywall.org/data-format<br>
För Swepub-variablerna finns mer information här: https://www.kb.se/samverkan-och-utveckling/swepub/datamodell/swepub-bibframe.html<br>
<br>
| Variabel | Beskrivning |
| :------ | :--------- |
| *all_oa (KB)* | All typ av öppen tillgång enl KB:s kriterier, dvs artikel i DOAJ-indexerad tidskrift, hybridartikel eller en publicerad eller accepterad version av artikeln i ett repositorium.<br> |
| *bibsam_oa_type* | Typ av öppen tillgång enligt [Bibsamkonsortiets publiceringsfil](https://github.com/Kungbib/oa-tskr/tree/master/Bibsam_artikeldata).<br> |
| *content_type (Swepub)* | Innehållsmärkning, här refereegranskat (https://id.kb.se/term/swepub/svep/ref).<br> |
| *creator_count (Swepub)* | Antal upphovspersoner.<br> |
| *doi (Unpaywall/Swepub)* | DOI:er i Swepubs dump är inte alltid angivna i korrekt format beroende på hur lärosätena registrerat dem. Unpaywalls API hanterar vissa formatfel, exv versaler/gemener men är DOI felaktig blir det ingen träff.<br> |
| *embargo (Swepub)* |  Om det finns information om embargo från levererande organisation.<br> |
| *endpoint_id (Unpaywall)* | Unpaywalls id.<br> |
| *evidence (Unpaywall)* | Hur den öppet tillgängliga artikeln har hittats.<br> |
| *host_type (Unpaywall)* | Vilken typ av värd, förlag eller repositorium, som står bakom artikelversionen.<br> |
| *hybrid (KB)* | Hybridartikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: journal_is_in_doaj = FALSE och host_type = publisher och licensen är en CC-BY-variant.<br> |
| *is_best (Unpaywall)* | Den bästa platsen för öppen tillgång enligt Unpaywalls kriterier.<br> |
| *is_oa (Unpaywall)* | Finns öppet tillgänglig version enligt Unpaywalls kriterier. NA om doi inte återfunnits hos Unpaywall.<br> |
| *journal_is_in_doaj (Unpaywall)* | Om artikeln finns publicerad i en DOAJ-indexerad tidskrift.<br> |
| *license (Unpaywall)* | Licensieringen för den här versionen.<br> |
| *licencing (Swepub)* | Licensiering enligt post i Swepub.<br> |
| *master_org (Swepub)* | Organisationskod för den organisation vars post utgör master i Swepub.<br> |
| *nr_publs (Swepub)* | Anger hur många levererade poster som bygger upp den sammanslagna posten, deduplicerade posten i Swepub. Dedupliceringsprocessen i Swepub är under utveckling.<br> |
| *nr_ssif_1 (KB)* | Hur många forskningsämnen på 1-siffernivå som artikeln har angivet.<br> |
| *oa (Swepub)* | Information om öppen tillgång enligt levererande organisationer. Beroende på lokalt system kan möjligheten att leverera den här typen av information variera mellan organisationerna.<br> |
| *oa_date (Unpaywall)* | Det datum artikeln först blev tillgänglig via den här platsen.<br> |
| *oa_final (KB)* | Sammanvägd klassificering av typ av öppen tillgång, kan vara gold, hybrid, only_repo, closed.<br> |
| *only_repo (KB)* | Om artikeln endast finns i repo, alltså inte är publicerad i en DOAJ-indexerad tidskrift och inte som hybrid markeras detta genom den här variabeln för att kunna särskilja dessa i statistiken.<br> |
| *open_apc_oa_type (OpenAPC)* | Typ av öppen tillgång enligt [OpenAPC](https://github.com/OpenAPC/openapc-de/tree/master/data), möjliga värden gold eller hybrid. <br>|
| *org (Swepub)* | Organisation som registrerat publikationen, används för beräkning av andel öppen tillgång per lärosäte. <br> |
| *output_type (Swepub)* | Outputtyp, här tidskriftsartikel (https://id.kb.se/term/swepub/publication/journal-article).<br> |
| *pmh_id (Unpaywall)* | OAI-PMH endpoint för den här platsen.<br> |
| *publ_date (Swepub)* | Publiceringsdatum.<br> |
| *publ_id (Swepub)* | Id för artikelposten från levererande organisation. I de sammanslagna, deduplicerade, posterna anges publ_id för den levererande organisation som utgör grund för masterposten. Dedupliceringsprocessen i Swepub är under utveckling.<br> |
| *publ_language (Swepub)* | Språkkod.<br> |
| *publ_status (Swepub)* | Publiceringsstatus, här publicerad (https://id.kb.se/term/swepub/Published).<br> |
| *publ_title (Swepub)* | Artikelns titel.<br> |
| *publ_year (KB)* | Publiceringsår baserat på publiceringsdatum i Swepub.<br> |
| *publisher (Swepub)* | Förlag enligt levererande organisation.<br> |
| *publisher_up (Unpaywall)* | Förlag enligt Unpaywall.<br> |
| *repo (KB)* | Parallellpublicerad artikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: host_type = repository och versionen är antingen publishedVersion eller acceptedVersion.<br> |
| *repository_institution (Unpaywall)* | Värd för repositoriet.<br> |
| *ssif_code (Swepub)* | Forskningsämne på 1-siffernivå.<br> |
| *swedish_list (Swepub)* | Poster med värdet https://id.kb.se/term/swepub/swedishlist/peer-reviewed är med i svenska listan.<br> |
| *up_oa (KB)* | Sammanvägd bedömning av olika vägar till öppen tillgång enligt Unpaywall per artikel <br>|
| *updated  (Unpaywall)* | Tidpunkt när data för den här artikeln senast uppdaterades.<br> |
| *url (Unpaywall)* | URL för PDF om den finns, annars URL för landningssida.<br> |
| *url_for_landing_page (Unpaywall)* | URL för landningssidan som beskriver den öppet tillgängliga artikeln.<br> |
| *url_for_pdf (Unpaywall)* | URL med öppet tillgänglig PDF-version av artikeln.<br> |
| *version (Unpaywall)* | Vilken version av artikeln som finns tillgänglig.<br> |

<!--- | *aff (Swepub)* | Auktoriserad affiliering till upphovsperson i Swepub.<br> | --->

Har du frågor eller kommentarer? Kontakta <openaccess@kb.se>

Uppdaterad 15 juni 2026.
