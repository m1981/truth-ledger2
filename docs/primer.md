# Primer — the borrowed vocabulary, for speaking not looking up

Status: **PRIMER — NON-NORMATIVE.** Companion to `docs/lexicon.md`:
the lexicon names the machinery's own parts (bramka, kapsuła,
probacja); this file teaches the surrounding discourse — vocabulary
borrowed from epistemology, logic, measurement, engineering, law and
dialectic, the words an operator and a fresh agent need to SPEAK
precisely about the machinery, not just look things up. Like the
lexicon it names and teaches, justifies nothing: citing this file is
never purchase currency (constitution C1), never an argument in a
ruling, never load-bearing.

Language note: bilingual by design — Polish definitions and usage
sentences, English originals in parentheses where the English term is
the working one. Only this header is English. Sections are ordered by
speech-act, not alphabet: this is a phrasebook ("rozmówki"), not a
dictionary.

- **Reader**: the operator and any fresh agent.
- **Enables**: formulating precise instructions, rulings and findings
  in this system's register.
- **Update trigger**: a borrowed term starts doing real work in
  dialogue.

## 1. Mówienie o prawdzie i dowodzie (Popper, Toulmin)

**Hipoteza (hypothesis)** — zdanie postawione po to, żeby dało się je obalić, nie po to, żeby go bronić. *Użycie:* „Traktuj to jako hipotezę: jeśli korpus przejdzie czerwono, pada zdanie, nie korpus."

**Przesłanka (premise)** — zdanie, na którym wniosek stoi; pada przesłanka — pada wniosek, bez dyskusji o reszcie. *Użycie:* „Twoja rekomendacja stoi na przesłance, że fixture odwzorowuje layout konsumenta — CMP-020 pokazał, że dokładnie ta przesłanka bywa fałszywa."

**Warrant (Toulmin)** — domową definicję trzyma leksykon; w dialogu to pytanie „na jakiej licencji te dane dają tę tezę?", zadawane na głos przy każdym [I], na którym coś stoi. *Użycie:* „Masz pomiar z jednej instalacji, a teza jest o wszystkich — podaj warrant albo zawęź."

**Backing (Toulmin)** — oparcie samego warrantu: skąd wiadomo, że licencja przejścia od danych do tezy w ogóle obowiązuje. *Użycie:* „Warrantem jest «korpus reprezentuje ruch», więc backingiem musi być, skąd ten korpus wzięto — bez tego kończy się jak z listą słów łapiącą framework Jest."

**Defeater** — warunek, którego zajście obala wniosek mimo prawdziwych przesłanek; argument bez defeaterów jest wyznaniem, nie argumentem. *Użycie:* „Wypisz defeatery tej rekomendacji: co musiałoby się zdarzyć, żebyśmy ją cofnęli?"

**Falsyfikowalność (falsifiability)** — cecha zdania: da się nazwać obserwację, która by je obaliła; bez niej zdanie nie podlega pomiarowi, tylko wierze. *Użycie:* „«System jest solidny» nie jest falsyfikowalne — przepisz na zdanie, które `tl2 check` umiałby zaświadczyć albo oblać."

**Operacjonalizacja (operationalization)** — przekład pojęcia na procedurę pomiaru: co dokładnie policzyć, żeby wolno było o nim mówić. *Użycie:* „Zoperacjonalizuj «dryf dokumentacji», zanim zaproponujesz bramkę — inaczej C3 nie ma czego liczyć."

**Empiryczne vs interpretacyjne (empirical vs interpretive)** — cięcie spod etykiet [M]/[I]: zdanie z pomiarem i kotwicą kontra uogólnienie bez falsyfikatora. *Użycie:* „«Day ~200» brzmiało empirycznie, a było interpretacyjne — CMP-003 to cena pomylenia tych rejestrów."

**Kontrprzykład (counterexample)** — pojedynczy przypadek obalający zdanie ogólne; najtańsza forma recenzji. *Użycie:* „Trzy komunikaty o frameworku Jest to kontrprzykład na listę słów pierwszej bramki — a wystarczyłby jeden."

**Aprioryczne (a priori)** — prawdziwe z definicji lub konstrukcji, przed jakimkolwiek pomiarem; nie do obalenia korpusem i nie do kupienia pomiarem. *Użycie:* „To, że fold jest czystą funkcją nad zapisami, jest aprioryczne — nie mierz definicji, mierz jej implementację."

## 2. Mówienie o języku i granicach (Tarski, Gödel)

**Język przedmiotowy vs metajęzyk (object language vs metalanguage)** — zdania o repozytorium kontra zdania o tych zdaniach; aparat orzeka w metajęzyku o korespondencji, nigdy w języku przedmiotowym o treści. *Użycie:* „Kapsuła jest metajęzykiem: mówi o zdaniu speca, nie o kodzie, który spec opisuje."

**Samozwrotność (self-reference)** — zdanie mówiące o sobie albo o aparacie, który je sprawdza; tu legalna, ale pilnowana, bo instalacja #1 weryfikuje własne dokumenty. *Użycie:* „Dogfood to kontrolowana samozwrotność: silnik sprawdza repozytorium, w którym sam mieszka, tą samą powierzchnią co u klienta."

**Rozstrzygalność (decidability)** — czy istnieje mechaniczna procedura dająca tak/nie w skończonym czasie; R2 wpuszcza tylko rozstrzygalne. *Użycie:* „«Czy ta dokumentacja jest dobra» jest dla maszyny nierozstrzygalne — dlatego zostaje ludziom, a nie w silniku."

**Inwariant (invariant)** — zdanie prawdziwe w każdym stanie systemu, nie tylko w chwili pomiaru; naruszony inwariant to znalezisko blokujące z definicji. *Użycie:* „Append-only ledgera to inwariant: jeśli jakikolwiek zapis został nadpisany, nie mamy błędu, mamy inny system."

**Partycja (partition)** — parę roster vs partycja trzyma leksykon; w dyskursie to żądanie totalności: klasy rozłączne, suma pełna, „nieprzypisane" jest błędem, nie kategorią. *Użycie:* „open / bought / declined to partycja dyspozycji — skarga bez żadnej z nich ma paść głośno, nie leżeć cicho."

**Dopełnienie (complement)** — wszystko, czego zbiór nie obejmuje; granicę widać dopiero, gdy dopełnienie jest nazwane. *Użycie:* „Pięć odmów w scope to opis dopełnienia produktu: mówimy, czym system NIE jest, żeby reszta była mierzalna."

**Konfluencja (confluence)** — różne kolejności dojścia dają ten sam wynik końcowy; warunek, żeby merge nie zmieniał prawdy. *Użycie:* „Fold ma być konfluentny: po scaleniu zapisów z dwóch sesji stan musi wyjść ten sam, niezależnie od kolejności."

**Idempotencja (idempotence)** — powtórzenie operacji nie zmienia wyniku ponad pierwsze wykonanie. *Użycie:* „Recheck ma być idempotentny: drugi przebieg na tej samej kotwicy nie ma prawa dopisać niczego nowego."

**Domena twierdzenia (domain of a claim)** — zbiór stanów i obiektów, o których zdanie faktycznie orzeka; pomiar jednej instancji nie pokrywa domeny. *Użycie:* „Zanim dasz [M], powiedz, czemu to, co przeczytałeś, rządzi całą domeną twierdzenia — jedna instancja to nie domena (reguła 8)."

**Kwantyfikator (quantifier: each/only)** — „każdy" i „tylko" to dwa różne zdania i dwa różne sprawdzenia; mylenie ich to klasyczny przemyt siły twierdzenia. *Użycie:* „«Each id cytowany» i «only z plików testowych» to dwie bramki, nie jedna — CMP-020 to koszt niedomówionego kwantyfikatora zasięgu."

## 3. Mówienie liczbami (pomiar)

**Precyzja (precision)** — odsetek alarmów słusznych; domowa nazwa: PPV (leksykon). *Użycie:* „Post-commitowy hook v1 umarł przy 3,6% precyzji — to jest liczba, którą C3 każe bramce nosić od urodzenia."

**Recall (czułość)** — odsetek rzeczywistych defektów, które bramka łapie; bez rejestru missów nieznany, a nie „wysoki". *Użycie:* „Nie mów «bramka działa» — powiedz, ile zasianych błędów złapała; recall bez missów to wiara."

**Fałszywy pozytyw / negatyw (false positive / negative)** — alarm na niewinnym / cisza na winnym; dwa koszty, płacone różnym ludziom (domowy krewny: fałszywy alarm, catch/miss — leksykon). *Użycie:* „555 z 630 rozwiązanych stalingów to fałszywe pozytywy, gorzej niż 3:1 — o tej cenie mówi zmęczenie alarmowe."

**Baseline** — punkt odniesienia, bez którego liczba nie znaczy nic: lepszy niż co? *Użycie:* „Zanim pochwalisz nową bramkę, podaj baseline: ile łapał zwykły grep, zanim cokolwiek zbudowaliśmy?"

**Retrodykcja (retrodiction)** — sprawdzenie mechanizmu wstecz, na zdarzeniach już zapisanych: czy złapałby to, co się naprawdę stało. *Użycie:* „Retrodykcja na żniwach to najtańszy świadek: przepuść kandydata po 45 zakotwiczonych zdarzeniach i policz trafienia, zanim poprosisz o zakup."

**Replikowalność (replicability)** — ten sam pomiar, powtórzony z zapisu, daje ten sam wynik; kapsuła jest recepturą replikacji. *Użycie:* „Jeśli recheck nie odtwarza hasha z kapsuły, zdanie jest stale — replikowalność to nie cnota, to definicja ważności paragonu."

**Proxy** — wielkość mierzona zamiast tej, o którą naprawdę chodzi; użyteczna, dopóki ktoś pamięta, że to zastępnik. *Użycie:* „Liczba krawędzi przychodzących to proxy polegania, nie poleganie — DARK/load-bearing mierzy linki, nie wartość dokumentu."

**Percentyl / p95 (percentile)** — wartość, poniżej której mieści się dany odsetek obserwacji; średnia kłamie grzeczniej niż ogon rozkładu. *Użycie:* „Średni czas checka nic operatorowi nie mówi — podaj p95, bo to ogon uczy ludzi przewijać czerwień."

**Stratyfikacja (stratification)** — dzielenie próbki na warstwy, żeby jedna liczna klasa nie zjadła obrazu całości. *Użycie:* „Rozbij wynik korpusu po rodzajach komunikatów — bramka od «jest» przeszłaby średnią, a poległa w warstwie zdań o frameworkach."

**Inflacja mianownika (denominator inflation)** — powiększanie mianownika przypadkami, których sprawdzenie i tak nie umie oblać, żeby odsetek wyglądał lepiej. *Użycie:* „36/36 id przechodzi mirror czysto — zanim się ucieszysz, sprawdź, czy mianownik nie liczy przypadków, na których bramka strukturalnie nie może być czerwona (CMP-020)."

**Próbka vs populacja (sample vs population)** — to, co zmierzyłeś, kontra to, o czym orzekasz; przeskok bez warrantu to podstawowy przemyt liczbowy. *Użycie:* „Korpus to próbka ruchu, nie ruch — ta sama lekcja trzeci raz: jest, slug-scoping, CMP-020; fixture nie był populacją."

## 4. Mówienie o maszynach i awariach (inżynieria/QA)

**Determinizm (determinism)** — ten sam stan wejścia daje zawsze ten sam wynik; warunek wstępny R2, nie zaleta. *Użycie:* „Jeśli check umie dać dwa różne wyniki na tej samej kotwicy, to nie jest bramka, tylko generator sporów."

**Hermetyczność (hermeticity)** — sprawdzenie widzi tylko to, co zadeklarowane: żadnych ukrytych wejść z sieci, zegara ani cudzego drzewa. *Użycie:* „CMP-003 to hermetyczność powiedziana na głos: watched paths nie sięgają cudzego repozytorium, więc zdanie o v1 nie ma nośnika."

**Fail-open vs fail-closed** — awaria mechanizmu przepuszcza wszystko kontra blokuje wszystko; wybór jest polityką, nie przypadkiem. *Użycie:* „PROVEN / GREEN-ON-BOTH / INCONCLUSIVE istnieje po to, żeby błąd aparatury nie udawał ani zieleni, ani czerwieni — nazwij, w którą stronę twoja bramka pada."

**Regresja (regression)** — powrót defektu już raz naprawionego; dowód, że naprawa nie miała świadka. *Użycie:* „CMP-020 to regresja dyscypliny, nie kodu: poprawka v1 «cytowania tylko z plików testowych» zginęła w tym samym verbie drugi raz, po slug-scopingu."

**Wyścig (race)** — wynik zależy od kolejności zdarzeń, której nikt nie kontroluje. *Użycie:* „Dwie sesje dopisujące równolegle do capsules.jsonl to wyścig — porozmawiajmy o single-writer, zanim to zaboli."

**Single-writer** — dokładnie jeden zapisujący do danego rejestru; najtańsza eliminacja całej klasy wyścigów. *Użycie:* „Operator komituje, agenci stage'ują — reguła 6 to single-writer na historii repozytorium."

**Sandbox** — środowisko, w którym wolno się mylić bez kosztu; naturalne siedlisko zasianych błędów. *Użycie:* „Świadka czerwieni zasiewaj w mktemp, nie w żywym drzewie — CMP-020 mierzył w sandboxie, na obu layoutach."

**Dryf (drift)** — powolne rozjeżdżanie się zapisu i rzeczywistości bez pojedynczego zdarzenia-winowajcy; klasa szkód, na którą ten produkt poluje. *Użycie:* „Dryf nie ma commita-sprawcy, dlatego łapie się go czujką i TTL, a nie code review."

**Fixture** — utrwalony stan testowy, na którym sprawdzenie pracuje; reprezentatywność fixture'a jest osobnym twierdzeniem, do osobnego dowodu. *Użycie:* „Świadkowie narodzin mirrora mieli fixture bez spec `.md` w drzewie — bramkę zaświadczono na świecie, który u konsumenta nie istnieje."

**Idempotentny seed (idempotent seed)** — inicjalizacja stanu, którą można puścić wielokrotnie bez podwajania danych. *Użycie:* „Jeśli ponowne otwarcie sesji dopisuje te same wiersze drugi raz, seed nie jest idempotentny — napraw to, zanim ktokolwiek policzy metryki."

## 5. Mówienie władzą (prawo/governance)

**Norma (norm)** — zdanie nakazujące, mierzone przestrzeganiem, nie prawdziwością; normy wiążą tu różnie mocno (reguła vs prawo — leksykon). *Użycie:* „AGENTS to normy postępowania: CMP-001 zmierzył, że norma bez bramki nie związała nawet własnego autora."

**Precedens (precedent)** — rozstrzygnięcie przeszłe używane jako argument w nowym przypadku; tu ma siłę perswazji, nigdy waluty. *Użycie:* „«Tak zrobiliśmy przy CMP-005» to precedens, nie kupno — nowy mechanizm i tak potrzebuje własnej skargi (C1)."

**Kontrasygnata (countersignature)** — drugi podpis, bez którego akt pierwszego nie wchodzi w życie; tu: operator przy każdym kupnie. *Użycie:* „Dyspozycja «bought» bez kontrasygnaty operatora to propozycja, nie zakup — CMP-020 wszedł, bo ją miał."

**Wykładnia (interpretation of law)** — odczytanie, co norma znaczy w przypadku, którego nie przewidziała; tu należy do operatora, nie do agenta. *Użycie:* „Jeśli scope nie odpowiada wprost, odpowiedź brzmi «nie» — pytanie o wykładnię idzie do paczki decyzji, nie do własnej głowy."

**Derogacja (derogation)** — uchylenie normy przez akt późniejszy. *Użycie:* „Od orzeczenia z 2026-08-31 «lekcja v1» nie kupuje już niczego — to derogacja drugiej waluty założycielskiej, nie erratum."

**Mandat (mandate)** — zakres działania powierzony aktem; ruch poza nim jest samowolą, choćby słuszną. *Użycie:* „Okno bezorzeczeniowe daje mandat na żniwa i konserwację — nowy mechanizm w tym oknie to przekroczenie mandatu, nie inicjatywa."

**Jurysdykcja (jurisdiction)** — granice, w których dany organ w ogóle może orzekać. *Użycie:* „O treści pracy ten aparat nie ma jurysdykcji — sufit orzeka o formie zapisu i tam jurysdykcja się kończy."

**Akt (performatyw) vs deklaracja (performative vs declaration)** — zdanie, które czyni (datowane orzeczenie, ratyfikacja, kupno), kontra zdanie, które opisuje; README jest deklaracją i podlega regule 12. *Użycie:* „«ACCEPTED — operator ruling of 2026-08-31» to performatyw: ta linijka nie opisuje prawa, ona je stanowi."

**Vacatio legis** — odstęp między ustanowieniem normy a jej wejściem w życie. *Użycie:* „Między napisaniem bramki a prawem blokowania jest jej vacatio legis: C2 każe zaświadczyć czerwień i korpus, zanim wolno jej odmawiać."

**Klauzula (clause)** — nazwany, adresowalny fragment aktu, na który można się powołać bez cytowania całości. *Użycie:* „Powołuj się klauzulą: «R5» i «C2» wystarczą w dialogu — od tego są adresy."

## 6. Mówienie w sporze (dialektyka recenzji)

**Zarzut (objection)** — nazwane twierdzenie recenzenta przeciw tezie, z adresem i wagą; nie nastrój i nie „mam wątpliwości". *Użycie:* „Sformułuj zarzut tak, żeby dało się go obalić: które zdanie, przy której kotwicy, jakim pomiarem."

**Obrona (defense)** — odpowiedź na zarzut w jego własnych kategoriach: obalenie, koncesja albo zawężenie — nigdy zmiana tematu. *Użycie:* „«Ale intencja była dobra» nie jest obroną — na zarzut o liczbę odpowiada się liczbą."

**Koncesja (concession)** — jawne oddanie punktu przeciwnikowi, z zapisem; oddany punkt przestaje wracać. *Użycie:* „Erratum w konstytucji to koncesja na piśmie: dwa z sześciu zapisów były fałszywe i tak zostało powiedziane."

**Zawężenie (narrowing)** — ratowanie tezy przez skurczenie jej domeny do tego, co pomiar naprawdę pokrywa. *Użycie:* „Po pomiarze na kuchni teza «mirror pilnuje obu kierunków» zawęziła się uczciwie do «w tym layoucie żywy jest tylko ORPHAN» — i dopiero ta wersja poszła do operatora (CMP-020)."

**Obalenie (rebuttal)** — wykazanie fałszywości tezy lub zarzutu wprost, pomiarem albo kontrprzykładem; koniec sporu, nie jego eskalacja. *Użycie:* „Recenzja zewnętrzna obaliła «day ~200» jednym pomiarem na drzewie v1 — czterokrotność, sprawa zamknięta erratą."

**Ciężar dowodu (onus probandi)** — kto ma dowodzić: tu zawsze wnioskodawca mechanizmu, nigdy sceptyk. *Użycie:* „Nie żądaj od recenzenta dowodu, że bramka nie działa — ciężar dowodu leży na tym, kto chce, żeby wolno jej było blokować (C2)."

**Steelman** — najmocniejsza wersja cudzego argumentu, zbudowana przed atakiem; przeciwieństwo słomianej kukły. *Użycie:* „Zanim odrzucisz zarzut recenzenta, ubierz go w steelmana — trzy najlepsze znaleziska tego repozytorium przyszły od ludzi z innym kontekstem, nie od klonu autora."

**Adwersarz (adversary)** — recenzent obsadzony po to, żeby obalać, nie żeby aprobować; klon autora to podłoga, nie standard. *Użycie:* „Zmierzono: adwersarz z tego samego modelu dał piętnaście znalezisk i przegapił trzy najlepsze — obsadzaj falsyfikację różnorodnie (reguła 9)."

**Argument z milczenia (argumentum ex silentio)** — wniosek z tego, że czegoś nie zapisano; tu prawie zawsze nadużycie, bo rejestr bez missów zawyża każdą bramkę. *Użycie:* „«Brak skarg na mirror» nie znaczyło, że mirror działa — to argument z milczenia; CMP-020 znalazł przegląd, nie rejestr."

**Przemyt (smuggling)** — wnoszenie twierdzenia bez płacenia jego ceny dowodowej: mocny kwantyfikator w słabym zdaniu, [I] w ubraniu [M]. *Użycie:* „«Day ~200» to podręcznikowy przemyt: cudza retoryka przemycona jako pomiar, w dokumencie otwieranym jako pierwszy."

**Teza nośna (load-bearing claim)** — zdanie, na którym stoi decyzja lub mechanizm; jego upadek nie jest kosmetyką, tylko demolką. *Użycie:* „Wskaż w raporcie tezę nośną i pilnuj jej najmocniej — o nią zapyta operator, reszta jest ornamentem."

**Znalezisko blokujące vs kosmetyczne (blocking vs cosmetic finding)** — rozróżnienie wag: co zatrzymuje ruch do czasu naprawy, a co czeka w kolejce; jedna etykieta na trzy rzędy wielkości nie niesie informacji. *Użycie:* „Terminuj osobno: blokujące — robię teraz; kosmetyczne — odpuszczam z powodem albo wiersz rejestru; nigdy jedna kupka."

## 7. Czasowniki domowego dialektu

**Orzec** — wydać datowany akt operatorski, który stanowi, a nie opisuje; agent nie orzeka nigdy. *Użycie:* „To nie jest moja decyzja — dopisuję pozycję do paczki i operator orzeknie."

**Terminować** — zakończyć znalezisko dokładnie jednym z trzech: robię / Twoja decyzja / odpuszczam z powodem. *Użycie:* „Masz w raporcie dwa niesterminowane wiersze — terminuj D3 i D7, zero niesklasyfikowanych (reguła 11)."

**Kupić (mechanizm)** — legitymizować mechanizm skargą i kontrasygnatą; jedyny sposób, w jaki cokolwiek tu wchodzi. *Użycie:* „Nie pytaj, czy warto zbudować — pytaj, która skarga to kupuje; bez CMP nie budujesz (C1)."

**Zaświadczyć (czerwień)** — pokazać zapisanego świadka: zasianą czerwień i zielony korpus, zanim bramce wolno blokować. *Użycie:* „Bramka jest napisana, ale niezaświadczona — zasiej błąd, puść korpus i dopiero wtedy ją podłączaj (C2)."

**Wycofać (z następcą)** — zdjąć rekord z obiegu tombstonem ze wskazaniem przyczyny i następcy; nigdy nie kasować. *Użycie:* „Najpierw następca przy nowej kotwicy, potem wycofaj stary rekord ze wskazaniem — successor-first, id z bieżącego checka, nie z pamięci."

**Wchłonąć** — zamknąć kandydata przez przejęcie jego treści przez coś już kupionego, zamiast budować osobno. *Użycie:* „Jeśli nowy verb robiłby to, co mirror już robi po CMP-020, nie kupuj drugiego — wchłoń i odnotuj w candidates."

**Pinować** — przywiązać instalację do konkretnego taga silnika; re-pin to świadomy akt, nie aktualizacja w tle. *Użycie:* „Konsument stoi na starszym tagu — zgłoś re-pin jako pozycję paczki, nie podnoś mu silnika po cichu."

**Kotwiczyć** — przybić zdanie do commita-świadka: „przy tym stanie świata to było prawdą". *Użycie:* „Liczba bez kotwicy to anegdota — zakotwicz pomiar commitem i plikiem, inaczej etykieta spada do [I]."

**Naginać** — dopasowywać obserwacje do zapisu zamiast zapisu do obserwacji; choroba atraktorów i ratyfikowanych planów. *Użycie:* „Zdarzenie nie pasuje do katalogu? Katalog ustępuje — zdarzeń się nie nagina (klauzula falsyfikatora)."

**Degradować (do suspect)** — mechanicznie odebrać zdaniu zaufanie, gdy zmienia się coś, na czym ono stoi; „nie ufaj, aż ktoś spojrzy". *Użycie:* „Edytowałeś obserwowane źródło — ogniwa na nim stojące degradują się do suspect, aż recheck albo człowiek zdejmie flagę."

**Odpuścić (z powodem)** — zamknąć znalezisko jawną rezygnacją z zapisanym powodem; bez powodu to nie odpuszczenie, tylko zgubienie. *Użycie:* „Odpuszczam D5 — z powodem: klasa bez nośnika w tym modelu, jak orzekł CMP-003; jeśli powód padnie, wraca jako skarga."

**Doręczyć (w moment działania)** — dostarczyć wiedzę dokładnie tam i wtedy, gdzie zapada ruch, zamiast liczyć na pamięć o prozie. *Użycie:* „Whisper doręcza: «te zdania obserwują plik, który zaraz tkniesz» — bo CMP-001 zmierzył, że proza sama z siebie nie wiąże."
