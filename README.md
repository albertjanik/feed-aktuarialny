# Feed Aktuarialny

Fiszki do egzaminów aktuarialnych KNF w formie nieskończonego feedu. Przełączasz moduł, scrollujesz, klikasz kafelek — z tyłu jest rozwiązanie.

**Na żywo:** https://albertjanik.github.io/feed-aktuarialny

## Co jest w środku

**826 kafelków** z 30 arkuszy egzaminacyjnych — wszystkie zadania, komplet:

| Moduł | Egzaminy | Zadania | Format |
|---|---|---|---|
| Zarządzanie ryzykiem zakładu ubezpieczeń | 84–96 | 130 | otwarte, po 5 pkt |
| Matematyka pozostałych ubezpieczeń osobowych i majątkowych | 80–96 | 170 | wielokrotny wybór A–E |

Trzy typy kafelków: **zadanie** (klik → rozwiązanie krok po kroku), **wzór**, **fakt/definicja**. Filtry u góry pozwalają zawęzić feed do jednego typu albo jednego tematu — od teorii ruiny po alokację kapitału.

Każde rozwiązanie kończy się sekcją **Pułapki** — gdzie realnie traci się punkty. Przy zadaniach wielokrotnego wyboru pułapki nazywają, pod jaką konkretną pomyłkę skonstruowano każdy dystraktor.

## Błędy w kluczach KNF

Każdy wynik liczbowy został przeliczony niezależnie (symbolicznie, numerycznie, a gdzie się dało również metodą Monte Carlo) zamiast przepisany z klucza. Kilkadziesiąt rozbieżności z oficjalnymi kluczami jest opisanych w kafelkach w ramce *Uwaga do klucza KNF*:

- ucinanie zamiast zaokrąglania oraz kwantyl 2,57 zamiast 2,5758 — najczęstsze, kosmetyczne;
- pominięte składniki sum, przestawione cyfry, przesunięty przecinek;
- błędy merytoryczne, m.in. cały człon krzyżowy przypisany jednej linii w alokacji Eulera, odwrócone równanie w portfelu replikującym, VaR odczytany z niewłaściwej statystyki pozycyjnej.

Rozwiązania podają wartość poprawną, nie tę z klucza.

Dwa arkusze (majątek 80 i 87) istnieją wyłącznie jako skany — ich treść odczytano z obrazów stron, nie z warstwy tekstowej.

## Struktura

```
index.html     aplikacja (HTML + CSS + JS, bez frameworka)
cards.json     baza kafelków
katex/         renderowanie wzorów (KaTeX 0.16.11)
marked.min.js  parser markdown (marked 12.0.2)
```

Zero zależności do zainstalowania i zero kroku budowania — biblioteki leżą w repo, więc strona działa też bez internetu.

Sama strona to zwykły plik statyczny. Lokalnie uruchamiasz ją serwerem (`python3 -m http.server`) — dwuklikowe otwarcie z dysku nie zadziała, bo przeglądarka zablokuje wczytanie `cards.json` przez `file://`.
