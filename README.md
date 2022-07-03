# CeneoWebScrapper


## Analiza struktury opinii w serwisie [Ceneo.pl](https://www.ceneo.pl/)

|Składowa|Selektor|Zmienna|Typ zmiennej|
|--------|--------|-------|------------|
|opinia|div.js_product-review|review|bs4.element.Tag|
|identyfikator opinii|\[data-entry-id\]|review_id|str|
|autor|span.user-post__author-name|author|str|
|rekomendacja|span.user-post__author-recomendation > em|recommendation|bool/NoneType|
|liczba gwiazdek|span.user-post__score-count|stars|float|
|treść|div.user-post__text|content|str|
|data wystawienia|span.user-post__published > time:nth-child(1)\[datetime\]|publish_date|str|
|data zakupu|span.user-post__published > time:nth-child(2)\[datetime\]|purchase_date|str|
|dla ilu przydatna|button.vote-yes[data-total-vote]<br>button.vote-yes > span<br>span[id^=votes-yes]|useful|int|
|dla ilu nieprzydatna|button.vote-no[data-total-vote]<br>button.vote-no > span<br>span[id^=votes-no]|useless|int|
|lista zalet|div.review-feature__title--positives ~ div.review-feature__item <br>div.review-feature__col:has( > div.review-feature__title--positives) > div.review-feature__item|pros|list\(str\)|
|lista wad|div.review-feature__title--negatives ~ div.review-feature__item <br>div.review-feature__col:has( > div.review-feature__title--negatives) > div.review-feature__item|cons|list\(str\)|

## Etapy prac nad projektem

1) Pobranie składowych pojedynczej opinii do niezależnych zmiennych<br>
2) Zapisanie wszystkich składowych opinii do słownika<br>
3) Pobranie wszystkich opinii z pojedynczej strony i zapisanie ich na liście w postaci słowników<br>
4) Pobranie wszystkich opinii o wskazanym produkcie i zapisanie ich do pliku<br> 
5) Wczytanie opinii o wskazanym produkcie z pliku do obiektu DataFrame<br>
6) Wyliczenie podstawowych statystyk<br>
7) Przedstawienie struktury opinii o produkcie na wykresach<br>
8) Stworzenie struktury dla wersji obiektowej<br>
9) Implementacja i wykorzystanie micro Framework'a Flask<br>
10) Rozbudowanie konstrukcji obiektowej o informacje o autorze, layoucie tworzonej strony i wyszukiwanych produktach (Produkt, Opinia)<br>
11) Modyfikacja routingu i widoku<br>
12) Dodanie informacji o wykorzystanych bibliotekach do pliku README.md<br>
13) Dodanie biblioteki markdown w celu konwersji danych z pliku README.md na stronę html


## Lista wykorzystywanych bibliotek i pakietów

1) beautifulsoup4 - biblioteka ułatwiająca zbieranie informacji ze stron internetowych (plików HTML i XML), zapewnia idiomatyczne sposoby nawigacji oraz wyszukiwanie i modyfikowanie drzewa analizy<br>
2) certifi - zapewnia wyselekcjonowaną kolekcję certyfikatów Mozilli; pozwala na weryfikację wiarygodności certyfikatów SSL<br>
3) charset-normalizer - biblioteka pozwalająca na czytanie tekstu z nieznanego kodowania zestawu znaków<br>
4) click - pakiet Pythona do tworzenia interfejsów wiersza poleceń w sposób taki, by wykorzystywano tylko tyle kodu, ile to konieczne<br>
5) colorama - moduł Pythona pozwalający na wyświetlanie tekstu w różnych kolorach<br>
6) Flask - micro framework w Python; zaprojektowany tak, by rozpoczęcie pracy było szybkie i łatwe, z możliwością skalowania do złożonych aplikacji<br>
7) fonttools - biblioteka służąca do manipulowania czcionkami w Python; pozwala na konwersję fontów TrueType i OpenType na (i z) formatu XML<br>
8) idna - biblioteka wspierająca protokół Domain Names in Applications (IDNA) <br>
9) importlib-metadata - biblioteka pozwalająca na dostęp do zainstalowanych metadanych pakietu<br>
10) Jinja2 - szybki, rozszerzalny silnik szablonów; umożliwia pisania kodu podobnego do składni Pythona<br>
11) kiwisolver - wydajna implementacja algorytmu ograniczeń Cassowary (C++)<br>
12) MarkupSafe - pakiet implementujący obiekt tekstowy i zastępujący znaki, dzięki czemu można go bezpiecznie używać w HTML i XML<br>
13) matplotlib - kompleksowa biblioteka do tworzenia statycznych, animowanych i interaktywnych wizualizacji w Pythonie<br>
14) numpy - biblioteka służąca do pracy z tablicami; posiada również funkcje do pracy w dziedzinie algebry liniowej, transformaty Fouriera i macierzy<br>
15) packaging - biblioteka dostarcza narzędzi, które implementują specyfikacje interoperacyjności, które mają wyraźnie jedno poprawne zachowanie (np. PEP 440) lub czerpią duże korzyści z posiadania jednej wspólnej implementacji (np.: PEP 425)<br>
16) pandas - biblioteka oprogramowania napisana dla języka programowania Python do manipulacji i analizy danych. W szczególności oferuje struktury danych i operacje służące do manipulowania tabelami liczbowymi i szeregami czasowymi<br>
17) Pillow - biblioteka zapewnia obszerną obsługę formatów plików, wydajną reprezentację wewnętrzną i dość potężne możliwości przetwarzania obrazu<br>
18) pyparsing - moduł pyparsing udostępnia bibliotekę klas, których kod klienta używa do konstruowania gramatyki bezpośrednio w kodzie Pythona<br>
19) python-dateutil - moduł dateutil zapewnia potężne rozszerzenia standardowego modułu datetime, dostępnego w Pythonie<br>
20) pytz - pytz przenosi bazę danych Olson tz do Pythona. Ta biblioteka umożliwia dokładne i międzyplatformowe obliczenia stref czasowych za pomocą Pythona<br>
21) requests - bliblioteka, która stanowi standard tworzenia żądań HTTP w Pythonie<br>
22) six - biblioteka kompatybilności z Pythonem 2 i 3; zapewnia funkcje narzędziowe do wygładzania różnic między wersjami Pythona w celu napisania kodu, który jest kompatybilny z obiema wersjami Pythona<br>
23) soupsieve - biblioteka selektorów CSS zaprojektowana do użytku z Beautiful Soup 4. Ma na celu zapewnienie wybierania, dopasowywania i filtrowania przy użyciu nowoczesnych selektorów CSS<br>
24) urllib3 - potężny, przyjazny dla użytkownika klient HTTP dla Pythona<br>
25) Werkzeug - zbiór bibliotek, które można wykorzystać do stworzenia aplikacji internetowej zgodnej z WSGI (Web Server Gateway Interface) w Pythonie<br>
26) zipp - opakowanie obiektów Zipfile zgodne z biblioteką pathlib. Oficjalny backport standardowej biblioteki obiektu Path<br>
27) markdown - biblioteka słuząca do konwersji pliku w formacie md do strony HTML