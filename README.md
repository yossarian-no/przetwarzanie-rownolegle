# Przetwarzanie równoległe - Projekt

Vasil Kusmartsev 156202  
Predmiot: Przetwarzanie równoległe, laboratoria, 6 semestr.  
Temat projektu: Generowanie spójnych grafów całkowitych rzędu n = 17 z liczbą krawędzie k=50.  

## Wstęp teoretyczny

**Temat projektu:** Generowanie spójnych grafów całkowitych rzędu n = 17 z liczbą krawędzi k = 50.

Przedmiotem projektu jest generowanie grafów o ściśle określonych właściwościach strukturalnych.
Przez **rząd grafu** rozumiemy liczbę jego wierzchołków – w niniejszym projekcie wynosi ona **n = 17**.
**Rozmiar grafu** to liczba krawędzi, która w badanym przypadku równa się **k = 50**.

## Graf całkowity (prosty)

**Graf całkowity** (nazywany również grafem prostym) to graf, w którym nie występują:
- **pętle** – krawędzie łączące wierzchołek z samym sobą,
- **krawędzie wielokrotne** – więcej niż jedna krawędź między tą samą parą wierzchołków.

Każda para wierzchołków może być połączona co najwyżej jedną krawędzią. Maksymalna liczba krawędzi
w grafie prostym rzędu n wyraża się wzorem:

$$k_{max} = \frac{n(n-1)}{2}$$

Dla n = 17 maksymalna liczba krawędzi wynosi:

$$k_{max} = \frac{17 \cdot 16}{2} = 136$$

Liczba k = 50 oznacza zatem, że rozważane grafy są **rzadkie** – zawierają około 37% wszystkich
możliwych krawędzi.

## Graf spójny

**Graf spójny** to graf, w którym dla każdego wierzchołka istnieje droga do każdego innego wierzchołka.
Innymi słowy, graf spójny składa się z dokładnie jednej **składowej spójności** – nie istnieją wierzchołki
ani grupy wierzchołków izolowane od reszty grafu.

Minimalna liczba krawędzi gwarantująca spójność grafu rzędu n to **n − 1**, co odpowiada strukturze
**drzewa rozpinającego**. Dla n = 17 minimalna liczba krawędzi spójnego grafu wynosi zatem **16**.

## Podsumowanie warunków

Generowane w projekcie grafy muszą spełniać jednocześnie trzy warunki:

| Właściwość | Wartość / Opis |
|---|---|
| Rząd grafu (liczba wierzchołków) | n = 17 |
| Rozmiar grafu (liczba krawędzi) | k = 50 |
| Graf prosty | brak pętli i krawędzi wielokrotnych |
| Graf spójny | każde dwa wierzchołki są połączone ścieżką |
| Minimalna liczba krawędzi spójności | 16 (drzewo rozpinające) |
| Maksymalna możliwa liczba krawędzi | 136 (graf pełny K₁₇) |

