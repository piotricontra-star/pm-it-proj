1. Cel projektu (SMART)

Celem projektu jest stworzenie do 15 grudnia 2025 prostej aplikacji webowej do śledzenia wydatków domowych, umożliwiającej:

dodawanie nowych wydatków (kwota, opis, kategoria),

wyświetlanie listy wydatków,

generowanie podsumowania miesięcznego (suma + liczba wydatków),

eksport danych do pliku CSV.

Wskaźniki sukcesu:

dodanie pojedynczego wydatku trwa ≤ 10 sekund,

aplikacja zwraca poprawne wyniki podsumowania z ostatnich 30 dni,

eksport CSV działa bez błędów,

błędy krytyczne nie przekraczają 1 na 100 uruchomień,

wszystkie scenariusze akceptacyjne zostaną spełnione.

Cel jest: konkretny, mierzalny, osiągalny, realistyczny, terminowy (SMART).

2. Zakres projektu
Zakres — IN (co projekt obejmuje)

Prosty backend (Python, np. FastAPI / Flask).

Przechowywanie danych w pliku (JSON, CSV).

UI umożliwiający:

dodawanie wydatków,

przegląd listy wydatków,

podgląd sumy i liczby wydatków z ostatnich 30 dni.

Eksport danych do CSV.

Proste funkcje API:

POST /expense – dodanie wydatku,

GET /expenses – pobranie listy,

GET /summary – podsumowanie ostatnich 30 dni,

GET /export/csv – eksport danych.

Testy jednostkowe najważniejszych funkcji.

CI/CD (GitHub Actions: lint + testy).

Dokumentacja (Charter, backlog, user stories, AC, raport).

Zakres — OUT (czego projekt NIE obejmuje)

Systemu logowania i obsługi wielu użytkowników.

Integracji bankowych (API, pliki wyciągów).

Rozbudowanych wykresów i paneli statystycznych.

Użycia baz danych SQL/NoSQL.

Aplikacji mobilnej lub PWA.

Zaawansowanych filtrów (po kategoriach, datach).

Modułów powiadomień (email, push).

Bezpieczeństwa klasy produkcyjnej (OAuth/SSO).

Zakres OUT zabezpiecza projekt przed tzw. scope creep.

3. Interesariusze projektu
Interesariusz	Rola / znaczenie
Prowadzący (klient)	definiuje wymagania, akceptuje projekt
PM zespołu studenckiego	prowadzi backlog, organizuje prace
Developerzy	implementacja funkcji aplikacji
Testerzy	wykonanie testów funkcjonalnych i akceptacyjnych
DevOps (opcjonalnie)	konfiguracja CI/CD

W projekcie studenckim jedna osoba może pełnić wiele ról.

4. Kryteria sukcesu projektu

Projekt uznaje się za zakończony sukcesem, jeśli:

Dostarczono działające MVP zgodnie z zakresem IN.

Aplikacja poprawnie obsługuje dodawanie, podgląd i eksport wydatków.

Wyniki podsumowania miesięcznego są poprawne.

CI/CD działa poprawnie (testy i lint przechodzą na zielono).

Spełniono wszystkie wymagania z dokumentu
docs/ACCEPTANCE_CRITERIA.md.

Raport końcowy jest kompletny i zawiera backlog, US, ryzyka, screeny CI.

Projekt zostanie pozytywnie zademonstrowany klientowi (prowadzącemu).

5. Założenia projektu

Projekt realizowany jednoosobowo lub w małym zespole (2–4 osoby).

Realizacja w jednym sprincie trwającym 2 tygodnie.

Aplikacja działa lokalnie (localhost).

Wykorzystywane są tylko narzędzia open-source (Python, GitHub).

Dane użytkownika są nieistotne z punktu widzenia wrażliwości (projekt dydaktyczny).

6. Główne ryzyka i ich monitorowanie
ID	Ryzyko	Prawdopodobieństwo	Wpływ	Reakcja (mitigation)	Monitorowanie
R1	Opóźnienia w implementacji funkcji	średnie	wysokie	rozbicie zadań na małe elementy	sprawdzanie postępu co 2 dni
R2	Błędy w zapisie danych do JSON	wysokie	średni	testy jednostkowe, walidacja	monitoring logów
R3	Problemy z konfiguracją CI/CD	średnie	wysokie	stopniowe budowanie konfiguracji Actions	status pipeline
R4	Brak zgodności z kryteriami akceptacji	niskie	wysokie	użycie checklisty AC przed demo	przegląd kodu
R5	Scope creep (dodawanie „fajnych funkcji”)	niskie	średnie	trzymanie się listy IN/OUT	PM + backlog review
R6	Problemy lokalne (Python, zależności)	średnie	średnie	używanie wersji LTS	dokumentacja instalacji
