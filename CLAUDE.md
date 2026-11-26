# Szkolny Kącik – instrukcja dla Claude

Strona z materiałami do nauki dla córki użytkownika (klasa 5 szkoły podstawowej, Polska).
Działa na GitHub Pages: https://lewandowskitomasz01-cyber.github.io/szkolny-kacik/
Wszystkie treści po polsku, na poziomie 5 klasy (nie wyżej).

## Struktura
- `index.html` – lista materiałów (kafelki). Tablica `MATERIALS` w skrypcie: nowe pozycje dopisujemy NA GÓRZE.
  Pola: `id` (używane też w adresie `#id`), `file`, `subject` („Przedmiot · klasa 5”), `title`, `meta`, `icon` (klucz z `ICONS`), `tone` (`hist` / `eng` / `math` – kolory zdefiniowane w `:root` i w dwóch blokach ciemnego motywu).
- Każdy materiał to osobny, samodzielny plik HTML (własne style i skrypt, bez zewnętrznych bibliotek), otwierany w ramce na stronie głównej.
  - `grecja.html` – historia: quiz „Starożytna Grecja” (478 pytań, 6 tematów).
  - `przymiotniki.html` – angielski: stopniowanie przymiotników, 3 ćwiczenia jak na kartce (baza zdań, losowe zestawy).
  - `skala.html` – matematyka: skala i plan, generator zadań z losowymi liczbami, 3 poziomy, rozwiązania krok po kroku.
- `sw.js` – działanie offline. Przy KAŻDEJ zmianie: dopisz nowe pliki do `FILES` i podbij wersję `CACHE` (szkolny-kacik-vN).
- `manifest.webmanifest`, `icons/` – instalacja jako aplikacja na telefonie.

## Dodawanie nowego materiału
1. Nowy plik `nazwa.html` (pełny dokument HTML, mobile-first, czytelny dla 11-latki, wyniki w localStorage w try/catch).
2. Wpis w `MATERIALS` w `index.html` (+ ewentualnie nowa ikona w `ICONS` i kolor `tone`).
3. Plik w `FILES` w `sw.js` + nowa wersja `CACHE`.
4. Sprawdź w przeglądarce (Playwright) na szerokości telefonu, potem commit i push na `main`.

## Zasady
- Poprawność merytoryczna przede wszystkim; zadania generowane losowo – przetestuj generator na wielu losowaniach.
- Po każdej odpowiedzi pokazuj poprawną odpowiedź i krótkie wyjaśnienie.
- Strona jest publiczna – żadnych danych osobowych córki.
