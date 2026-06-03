# Przetwarzanie równoległe - Projekt

Vasil Kusmartsev 156202  
Predmiot: Przetwarzanie równoległe, laboratoria, 6 semestr.  
Temat projektu: Generowanie spójnych grafów całkowitych rzędu n = 17 z liczbą krawędzie k=50.  

## Wstęp teoretyczny

**Temat projektu:** Generowanie spójnych grafów całkowitych rzędu n = 17 z liczbą krawędzi k = 50.

Celem projektu jest znalezienie grafów spełniających jednocześnie cztery ściśle określone warunki
matematyczne. Każdy z nich zostaje omówiony poniżej w sposób przystępny.

***

## 1. Graf — definicja podstawowa

Graf to struktura matematyczna składająca się z **wierzchołków** (punktów) oraz **krawędzi**
(połączeń między punktami). Można go sobie wyobrazić jako mapę miast (wierzchołki) połączonych
drogami (krawędzie). Formalnie graf oznaczamy jako G = (V, E), gdzie V to zbiór wierzchołków,
a E to zbiór krawędzi.

W projekcie rozważamy **grafy proste** — bez pętli (krawędź z wierzchołka do samego siebie)
oraz bez krawędzi wielokrotnych (więcej niż jedno połączenie między tą samą parą wierzchołków).

***

## 2. Rząd grafu — n = 17

**Rząd grafu** to po prostu **liczba wierzchołków**. Warunek n = 17 oznacza, że każdy
rozważany graf musi mieć dokładnie **17 wierzchołków**.

***

## 3. Liczba krawędzi — k = 50

Warunek k = 50 oznacza, że rozważane grafy muszą mieć dokładnie **50 krawędzi**.

Dla porównania:
- Minimalna liczba krawędzi w grafie spójnym o 17 wierzchołkach to **16** (drzewo rozpinające)
- Maksymalna liczba krawędzi to **136** (graf pełny K₁₇)
- Nasze grafy z k = 50 zawierają zatem około **37%** wszystkich możliwych krawędzi —
  są to grafy **rzadkie**, ale wystarczająco gęste, by mogły być spójne.

***

## 4. Graf spójny

**Graf spójny** to graf, w którym dla każdego wierzchołka istnieje droga do każdego
innego wierzchołka. Innymi słowy — z dowolnego punktu można dotrzeć do dowolnego innego punktu,
idąc po krawędziach grafu.

***

## 5. Graf całkowity

**Graf całkowity** (ang. *integral graph*) to graf, którego **wszystkie wartości własne
macierzy sąsiedztwa są liczbami całkowitymi**.

### Co to jest macierz sąsiedztwa?

Macierz sąsiedztwa to tablica 17×17 wypełniona zerami i jedynkami:
- `1` na pozycji (i, j) oznacza, że między wierzchołkiem i oraz j istnieje krawędź
- `0` oznacza brak krawędzi
- Macierz jest symetryczna (bo krawędzie są nieskierowane)

### Co to są wartości własne?

Każda macierz kwadratowa posiada **wartości własne** (ang. *eigenvalues*) — są to liczby
λ spełniające równanie:

$$\det(A - \lambda I) = 0$$

Dla macierzy 17×17 istnieje dokładnie **17 wartości własnych**. Zwykle są to liczby
ułamkowe lub niewymierne, np. 3.1415..., −1.7320..., 2.6457...

### Dlaczego to rzadkie?

Graf jest **całkowity** tylko wtedy, gdy **wszystkie 17 wartości własnych** są liczbami
całkowitymi, np. {−4, −3, −1, 0, 0, 1, 2, 3, ...}. Jest to wyjątkowo rzadka właściwość —
spośród milionów grafów o n = 17 i k = 50 zaledwie nieliczne (lub żaden) spełniają ten warunek.

Wartości własne obliczamy numerycznie metodą **Jacobiego** — iteracyjnym algorytmem
zerującym elementy pozadiagonalne macierzy, aż do uzyskania macierzy diagonalnej,
której elementy diagonalne są szukanymi wartościami własnymi.

***

## 6. Podsumowanie warunków projektu

Szukany graf musi spełniać **jednocześnie** wszystkie poniższe warunki:

| Warunek | Wartość / Opis |
|---|---|
| Rząd grafu | n = 17 wierzchołków |
| Rozmiar grafu | k = 50 krawędzi |
| Spójność | z każdego wierzchołka istnieje ścieżka do każdego innego |
| Całkowitość | wszystkie 17 wartości własnych macierzy sąsiedztwa są całkowite |
| Min. krawędzi spójności | 16 (drzewo rozpinające) |
| Maks. możliwa liczba krawędzi | 136 (graf pełny K₁₇) |

Znalezienie takiego grafu wymaga przeszukania ogromnej przestrzeni rozwiązań —
liczba wszystkich możliwych grafów prostych o n = 17 wynosi $2^{136}$, co jest liczbą
astronomiczną. Z tego powodu kluczowym aspektem projektu jest zastosowanie
**efektywnych algorytmów oraz zrównoleglenia obliczeń** (np. OpenMP lub CUDA).

