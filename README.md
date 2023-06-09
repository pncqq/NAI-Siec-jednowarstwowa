# NAI-Siec-jednowarstwowa

Celem projektu jest stworzenie sieci jednowarstwowej identyfikującej język, w jakim na-
pisany jest tekst wejściowy.
W plikach lang.train.csv i lang.test.csv znajduje się zbiór tekstów w czterech ję-
zykach – angielskim, niemieckim, polskim i hiszpańskim. Aby zaklasyfikować dany tekst
należy zliczyć częstotliwość występowania każdej z liter alfabetu łacińskiego. Na potrzeby
tego zadania można zignorować wszystkie niestandardowe litery (znaki diakrytyczne, etc.)
i zliczać tylko częstości wystąpień 26 podstawowych liter alfabetu, pomijając wszystkie
inne znaki.
Dla każdego tekstu wejściowego należy wygenerować 26-elementowy wektor zawierający
liczbę wystąpień każdej z liter i następnie go znormalizować:

v̂ = v / |v|

Wyjście sieci powinno mieć reprezentację lokalną: do każdego neuronu przypisujemy jeden
z języków. Dla danego tekstu wartość wyjściową 1 powinien mieć neuron reprezentujący
język tekstu, a pozostałe wartość 0.
Można wykorzystać funkcję aktywacji progową lub liniową (f (net) = net) (w przypadku
obu funkcji reguła modyfikacji wag jest identyczna, ponieważ dla funkji liniowej f ′ (net) =
1). Aby klasyfikować język tekstu, wybieramy perceptron z maksymalną aktywacją.
Program powinien:
- Trenować sieć danymi z pliku lang.train.csv i następnie wypisać dokładność kla-
syfikacji dla danych z pliku lang.test.csv.
- Dostosować się do dowolnego zbioru danych w podobnym formacie, np. z inną liczbą
języków.
- Zapewniać interfejs umożliwiający wklejenie nowego tekstu (np. w konsoli) i rozpo-
znanie języka.
- (Opcjonalnie) wypisać te teksty ze zbioru testowego, dla których klasyfikacja była
błędna.

Wskazówki:
- W tekstach mogą znajdować się przecinki, więc przy wczytywaniu plików nie zadzia-
ła dzielenie każdej linii split(",") (ale można użyć np. split(",", 1) (Python)
lub split(",", 2) (Java)).
- Użycie liniowej funkcji aktywacji zmniejsza szanse na niejednoznaczną wartość wyj-
ściową sieci (kiedy więcej niż jeden perceptron ma wartość wyjściową 1).
- Warto normalizować także wektory wag.
- Można wykorzystać implementację perceptronu z wcześniejszego projektu, lub im-
plementować sieć od początku przy użyciu operacji na macierzach.
