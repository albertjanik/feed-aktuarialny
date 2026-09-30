# Feed Aktuarialny

Fiszki do egzaminów aktuarialnych KNF w formie nieskończonego feedu. Przełączasz moduł, scrollujesz, klikasz kafelek — z tyłu jest rozwiązanie.

**Na żywo:** https://albertjanik.github.io/feed-aktuarialny

## Co jest w środku

| Moduł | Egzaminy | Kafelki |
|---|---|---|
| Zarządzanie ryzykiem zakładu ubezpieczeń | 87–96 | zadania otwarte (5p każde) z pełnymi rozwiązaniami |
| Matematyka pozostałych ubezpieczeń osobowych i majątkowych | 81–96 | pytania A–E z wyprowadzeniami |

Trzy typy kafelków: **zadanie** (klik → rozwiązanie krok po kroku), **wzór**, **fakt/definicja**.

Każde rozwiązanie kończy się sekcją **Pułapki** — gdzie realnie traci się punkty. Przy zadaniach wielokrotnego wyboru pułapki nazywają, pod jaką konkretną pomyłkę skonstruowano każdy dystraktor.

## Błędy w kluczach KNF

Każdy wynik liczbowy został przeliczony niezależnie (symbolicznie, numerycznie, a gdzie się dało również Monte Carlo) zamiast przepisany z klucza. Ponad dwadzieścia rozbieżności z oficjalnymi kluczami jest opisanych w kafelkach w ramce *Uwaga do klucza KNF* — od ucinania zamiast zaokrąglania, przez pominięte składniki, po jeden błąd merytoryczny w alokacji Eulera.

Rozwiązania podają wartość poprawną, nie tę z klucza.

## Struktura

```
index.html     aplikacja (HTML + CSS + JS, bez frameworka)
cards.json     baza kafelków
katex/         renderowanie wzorów (KaTeX 0.16.11)
marked.min.js  parser markdown (marked 12.0.2)
```

Zero zależności do zainstalowania i zero kroku budowania — biblioteki leżą w repo, więc strona działa też bez internetu.

Strona to zwykły statyczny plik — działa też po otwarciu przez serwer lokalny (`python3 -m http.server`). Samo dwuklikowe otwarcie `index.html` z dysku nie zadziała, bo przeglądarka zablokuje wczytanie `cards.json` przez `file://`.

## Uzupełnianie bazy

Kafelki są generowane z oficjalnych arkuszy KNF. Brakuje jeszcze: ryzyko 84–86, ryzyko 87–88 (zadania 7–10), ryzyko 89/90/92 (zadanie 10), majątek 80, oraz trzy zadania z majątku 87, których skan był nieczytelny.
