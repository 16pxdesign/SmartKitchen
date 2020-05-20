# SmartKitchen

## Wymagania klienta

### Produkt

Produktem jest aplikacja działająca na rożnych platformach przez co należy rozumieć wsparcie dla aplikacji webowej, aplikacji na urządzenia mobilne oraz wersję desktopową. Wersja webowa i mobilna powinny być dostarczone jako pierwsze, zaś istnienie wersji desktopowej na chwilę obecną jest opcjonalne i nie wymagane na chwilę obecną. Celem aplikacji jest dostarczenie użytkownikom wielu narzędzi do pomocy w codziennych problemach w ich kuchni. Takimi narzędziami do zarządzania mogą być m. in. narzędzie do zarządzania odżywianiem, rachunkami oraz zasobami w kuchni. Aplikacja powinna mieć możliwość łatwego rozszerzania o kolejne funkcje, które wykorzystują podobne dane lub zaimplementowane wcześniej funkcjonalności.

Z założenia aplikacja powinna być tak skonstruowana by działa wersji globalnej lub lokalnie jako serwis `stand-alone`. Oznacza to, że użytkownik będzie miał możliwość korzystania z hostowanego serwisu globalnie, lub pobierając repozytorium skonfigurować własną wersję oprogramowania i zarzadzania jej zasobami we własnym zakresie. Wersja lokalna nie wymaga dostarczenia danych wejściowych tj. produkty lub przepisy, co jest zadaniem użytkownika we własnym zakresie. W obu przypadkach użytkownik powinien mieć możliwość podsiadania i tworzenia kont użytkownika.

Aplikacja powinna być skalowalna i jej poszczególne funkcjonalności powinny mieć możliwość skalowania w zależności od zapotrzebowania na nie. Poprzez skalowalność rozumie się fakt iż w przypadku zwiększonego popytu na jedno z narzędzi, można było łatwo obsłużyć taką grupę użytkowników bez wpływu na wydajność obciążonego narzędzia.

#### Użytkownicy

Użytkownicy logować maja się za pomocą email i hasła lub za pomocą media społecznościowych, chociaż ta druga opcja nie jest wymagana i może być zaimplementowana w późniejszych wersjach. Każdy użytkownik powinien mieć możliwość spersonalizowania swojego konta i ustawień narzędzi, a dane użytkowników powinny być widoczne jedynie dla nich samych; dla osób, którym dane te udostępnia lub dla osób poprzez logowanie za pomocą podłączonych kont.

Za połączone konta rozumie się, współ-domowników, którzy mogą wspólnie uzupełniać, zarządzać i odczytywać dane z ich domostwa. Dane na temat domostwa powinny istnieć tak długo, do póki nie zostaną zlikwidowane lub odłączone wszystkie konta z nim połączone. Kwestia praw do dodawania i zarzadzania podłączonych kont może spoczywać na założycielu lub na wszystkich jednocześnie, nie ma stanowiska w tej sprawie.

#### Pierwsze narzędzia

Pierwsze narzędzia dotyczą dwóch zagadnień takich jak zarządzania produktami oraz książki kucharskiej. Nie wszystkie wymagania są określone we wczesnej implementacji oprogramowania i dopuszcza się dyskusję w ramach wątpliwych aspektów aplikacji. Projekt zakładać ma wdrażanie aplikacji poprzez dodawanie kolejnych narzędzi, które będą razem tworzyły jeden system. Każde narzędzie powinno mieć możliwość wersjonowania i ulepszania w perspektywie czasu i zmieniających się wymagań. Dlatego ważne jest to żeby narzędzia pracowały najbardziej niezależnie od siebie jak się da, a zarazem tworzyły całość w formie zdecentralizowanej aplikacji.

##### Zarządzanie produktami 

