I den här mappen finns data i form av csv-filer (i zip-format pga storleken) för den statistik som presenteras på KB:s sida [Öppen tillgång i siffror](https://www.kb.se/samverkan-och-utveckling/oppen-tillgang-och-bibsamkonsortiet/oppen-tillgang/oppen-tillgang-i-siffror.html). Data består av Swepub-data ([dump juli 2022](https://swepub-qa.kb.se/bibliometrics/datadump)) matchat på DOI med data från [Unpaywall](https://unpaywall.org/) (insamlat via API under perioden 2022-07-08 till 2022-07-10). Data är filtrerat till publicerade sakkunniggranskade artiklar enligt Swepub. Informationen om öppen tillgång (KB:s variabler i nyckeln nedan) är beräknade genom Unpaywall-data, se varje variabel för detaljer. Tidigare års data finns i respektive mapp.

Det finns en totalfil var för publiceringsåren 2017 till 2021 (oa_2022_results_xxxx.zip), samt ytterligare två filer för publiceringsår 2021 fördelat på lärosäten (oa_2022_results_orgs_2021.zip) och forskningsämnen på 1-siffernivå enligt [Standard för svensk indelning av forskningsämnen](https://www.scb.se/dokumentation/klassifikationer-och-standarder/standard-for-svensk-indelning-av-forskningsamnen/) (oa_2022_results_subj_2021.zip).

Observera att filerna är konstruerade så att om flera organisationer som levererar data till Swepub levererat samma artikel och artikeln inte fångats upp i dedupliceringsprocessen blir det en ny rad för varje levererande lärosäte (gäller årsfilerna). Därtill blir det en rad för varje typ av öppen tillgång som Unpaywall identifierat (gäller alla filer). De två filerna med lärosäten respektive forskningsämnen är uppbyggda så att om en artikel är affilierad (observera - inte levererad utan affilierad) till flera organisationer finns en rad per organisation och typ av öppen tillgång via Unpaywall. Motsvarande gäller för forskningsämnena, om en artikel är klassificerad till flera forskningsämnen finns en rad per forskningsämne och typ av öppen tillgång via Unpaywall. I dessa båda filer finns även DOI:er som inte matchats i Unpaywall, dessa rader har NA angivet för Unpaywall-data. En artikel förekommer alltså på flera rader, med unik information för varje rad.

Underlag för KB:s statistik för öppen tillgång utgörs av variablerna *all_oa*, *journal_is_in_doaj*, *hybrid*, *repo* och *only_repo*.

**Variabelnyckel**<br>
För alla filer i bokstavsordning.<br>
Vissa av variablerna finns endast i vissa filer.<br>
Inom parentes anges källa för variabeln.<br>
För Unpaywall-variablerna finns mer information här: https://unpaywall.org/data-format<br>
För Swepub-variablerna finns mer information här: https://www.kb.se/samverkan-och-utveckling/swepub/datamodell/swepub-bibframe.html<br>
<br>
*aff (Swepub)*: auktoriserad affiliering till upphovsperson i Swepub.<br>
*all_oa (KB)*: all typ av öppen tillgång enl KB:s kriterier, dvs artikel i DOAJ-indexerad tidskrift, hybridartikel eller en publicerad eller accepterad version av artikeln i ett repositorium.<br>
*change_date (Swepub)*: datum då posten ändrades i organisationskällan.<br>
*content_type (Swepub)*: innehållsmärkning, här refereegranskat (https://id.kb.se/term/swepub/svep/ref).<br>
*creation_date (Swepub)*: datum då posten skapades i organisationskällan.<br>
*creator_count (Swepub)*: antal upphovspersoner.<br>
*deliver_org (Swepub)*: organisationskod för den organisation som levererat data.<br>
*doi (Unpaywall/Swepub)*: DOI:er i Swepubs dump är inte alltid angivna i korrekt format beroende på hur lärosätena registrerat dem. Unpaywalls API hanterar vissa formatfel, exv versaler/gemener men är DOI felaktig blir det ingen träff.<br>
*embargo (Swepub)*:  end för 2019 och 2020. Om det finns information om embargo från levererande organisation finns den angiven här.<br>
*endpoint.id (Unpaywall)*: Unpaywalls id.<br>
*evidence (Unpaywall)*: hur den öppet tillgängliga artikeln har hittats.<br>
*host_type (Unpaywall)*: vilken typ av värd, förlag eller repositorium, som står bakom artikelversionen.<br>
*hybrid (KB)*: hybridartikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: journal_is_in_doaj = FALSE och host_type = publisher och licensen är en CC-BY-variant.<br>
*is_best (Unpaywall)*: den bästa platsen för öppen tillgång enligt Unpaywalls kriterier.<br>
*is_oa (Unpaywall)*: finns öppet tillgänglig version enligt Unpaywalls kriterier.<br>
*journal_is_in_doaj (Unpaywall)*: är artikeln publicerad i en DOAJ-indexerad tidskrift.<br>
*license (Unpaywall)*: licensieringen för den här versionen.<br>
*licencing (KB)*: licensiering enligt post i Swepub.<br>
*nr_publs (Swepub)*: anger hur många levererade poster som bygger upp den sammanslagna posten, deduplicerade posten i Swepub. Dedupliceringsprocessen i Swepub är under utveckling.<br>
*nr_of_contr (KB)*: kontrollsiffra för att kontrollera Swepubs dedupliceringsprocess.<br>
*nr_uka1 (KB)*: hur många forskningsämnen på 1-siffernivå som artikeln har angivet.<br>
*oa (Swepub)*: information om öppen tillgång enligt levererande organisationer. Beroende på lokalt system kan möjligheten att leverera den här typen av information variera mellan organisationerna.<br>
*oa_date (Unpaywall)*: det datum artikeln först blev tillgänglig via den här platsen.<br>
*only_repo (KB)*: om artikeln endast finns i repo, alltså inte är publicerad i en DOAJ-indexerad tidskrift och inte som hybrid markeras detta genom den här variabeln för att kunna särskilja dessa i statistiken.<br>
*output_type (Swepub)*: outputtyp, här tidskriftsartikel (https://id.kb.se/term/swepub/publication/journal-article).<br>
*pmh_id (Unpaywall)*: OAI-PMH endpoint för den här platsen.<br>
*publ_date (Swepub)*: publiceringsår.<br>
*publ_id (Swepub)*: id för artikelposten från levererande organisation. I de sammanslagna, deduplicerade, posterna anges publ_id för den levererande organisation som utgör grund för masterposten. Dedupliceringsprocessen i Swepub är under utveckling.<br>
*publ_language (Swepub)*: språkkod.<br>
*publ_status (Swepub)*: publiceringsstatus, här publicerad (https://id.kb.se/term/swepub/Published).<br>
*publ_title (Swepub)*: artikelns titel.<br>
*publ_year (KB)*: extracted publication year from publ_date.<br>
*publisher (Swepub)*: förlag enligt levererande organisation.<br>
*repo (KB)*: parallellpublicerad artikel enl KB:s kriterier, beräknad via Unpaywall-data enligt följande: host_type = repository och versionen är antingen publishedVersion eller acceptedVersion.<br>
*repository_institution (Unpaywall)*: värd för repositoriet.<br>
*swedish_list (Swepub)*: poster med värdet https://id.kb.se/term/swepub/swedishlist/peer-reviewed är med i svenska listan.<br>
*updated  (Unpaywall)*: tidpunkt när data för den här artikeln senast uppdaterades.<br>
*uka_code (Swepub)*: forskningsämne på 1-siffernivå.<br>
*url (Unpaywall)*: URL för PDF om den finns, annars URL för landningssida.<br>
*url_for_landing_page (Unpaywall)*: URL för landningssidan som beskriver den öppet tillgängliga artikeln.<br>
*url_for_pdf (Unpaywall)*: URL med öppet tillgänglig PDF-version av artikeln.<br>
*version (Unpaywall)*: vilken version av artikeln som finns tillgänglig.<br>

Har du frågor eller kommentarer? Kontakta <openaccess@kb.se>
