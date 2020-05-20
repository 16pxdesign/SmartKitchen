# SmartKitchen

## Wymagania klienta

Wymagania klienta maja określić najbliższe oczekiwane wersje produktu oraz nakreślenie jak aplikacja powinna działać w pełni swoich możliwości. Nie mniej jednak nie wszystkie funkcjonalności będą wdrażane od początku projektu i należy zwrócić uwagę na fakt iż narzędzia mogą być rozszerzane i wersjonowane. Mając to na uwadze można pisać kod pod tym kontem unikając niepotrzebnego re-factoringu w późniejszej fazie projektu.

### Produkt

Produktem jest aplikacja działająca na rożnych platformach przez co należy rozumieć wsparcie dla aplikacji webowej, aplikacji na urządzenia mobilne oraz wersję desktopową. Wersja webowa i mobilna powinny być dostarczone jako pierwsze, zaś istnienie wersji desktopowej na chwilę obecną jest opcjonalne i nie wymagane na chwilę obecną. Celem aplikacji jest dostarczenie użytkownikom wielu narzędzi do pomocy w codziennych problemach w ich kuchni. Takimi narzędziami do zarządzania mogą być m. in. narzędzie do zarządzania odżywianiem, rachunkami oraz zasobami w kuchni. Aplikacja powinna mieć możliwość łatwego rozszerzania o kolejne funkcje, które wykorzystują podobne dane lub zaimplementowane wcześniej funkcjonalności.

Z założenia aplikacja powinna być tak skonstruowana by działa wersji globalnej lub lokalnie jako serwis `stand-alone`. Oznacza to, że użytkownik będzie miał możliwość korzystania z hostowanego serwisu globalnie, lub pobierając repozytorium skonfigurować własną wersję oprogramowania i zarzadzania jej zasobami we własnym zakresie. Wersja lokalna nie wymaga dostarczenia danych wejściowych tj. produkty lub przepisy, co jest zadaniem użytkownika we własnym zakresie. W obu przypadkach użytkownik powinien mieć możliwość podsiadania i tworzenia kont użytkownika.

Aplikacja powinna być skalowalna i jej poszczególne funkcjonalności powinny mieć możliwość skalowania w zależności od zapotrzebowania na nie. Poprzez skalowalność rozumie się fakt iż w przypadku zwiększonego popytu na jedno z narzędzi, można było łatwo obsłużyć taką grupę użytkowników bez wpływu na wydajność obciążonego narzędzia.

Jako `product owner` rekomenduje użycie w tym celu micro-serwisów jednakże jeżeli team ma inne propozycje możliwe jest rozważenie innych opcji i technologii.

#### Użytkownicy

Użytkownicy logować maja się za pomocą email i hasła lub za pomocą media społecznościowych, chociaż ta druga opcja nie jest wymagana i może być zaimplementowana w późniejszych wersjach. Każdy użytkownik powinien mieć możliwość spersonalizowania swojego konta i ustawień narzędzi, a dane użytkowników powinny być widoczne jedynie dla nich samych; dla osób, którym dane te udostępnia lub dla osób poprzez logowanie za pomocą podłączonych kont.

Za połączone konta rozumie się, współ-domowników, którzy mogą wspólnie uzupełniać, zarządzać i odczytywać dane z ich domostwa. Dane na temat domostwa powinny istnieć tak długo, do póki nie zostaną zlikwidowane lub odłączone wszystkie konta z nim połączone. Kwestia praw do dodawania i zarzadzania podłączonych kont może spoczywać na założycielu lub na wszystkich jednocześnie, nie ma stanowiska w tej sprawie.

#### Pierwsze narzędzia

Pierwsze narzędzia dotyczą dwóch zagadnień takich jak zarządzania produktami oraz książki kucharskiej. Nie wszystkie wymagania są określone we wczesnej implementacji oprogramowania i dopuszcza się dyskusję w ramach wątpliwych aspektów aplikacji. Projekt zakładać ma wdrażanie aplikacji poprzez dodawanie kolejnych narzędzi, które będą razem tworzyły jeden system. Każde narzędzie powinno mieć możliwość wersjonowania i ulepszania w perspektywie czasu i zmieniających się wymagań. Dlatego ważne jest to żeby narzędzia pracowały najbardziej niezależnie od siebie jak się da, a zarazem tworzyły całość w formie zdecentralizowanej aplikacji.

##### Zarządzanie produktami - Globalna Baza

Większość narzędzi odnosi się do produktów dlatego jednym z początkowych narzędzi będzie to narzędzie do zarządzania produktami. Należy tu zaznaczyć, iż zbiór produktów odnosi się do rzeczywistych produktów jakie można zakupić w sklepach spożywczych i nie tylko. Zbiór produktów powinien mieć zasięg globalny co oznacza, że każdy użytkownik powinien móc wybierać z niego produkty za pomocą innych narzędzi.

> Dla przykładu użytkownik powinien mieć możliwość wybrania kilku produktów z listy i dodać je do swojego zbioru produktów np. w lodówce.

Produkty powinny być odpowiednio pogrupowane względem ich cech indywidualnych oraz znormalizowane. Oznacza to ze produkty mogą należeć do kategorii `nabiał`. Należy zauważyć tu też fakt, iż produkt `mleko` może mieć różnych producentów, nie mniej jednak produkty te nadal powinny być dostępne i widoczne jako `mleko`, a inna odmiana `mleka` tj. kokosowe powinno być oddzielnym produktem, ponieważ nie jest `mlekiem` w potocznym znaczeniu tego słowa.

> Nabiał - Mleko - Łaciate
> Nabiał - Mleko - Terravita
> Nabiał - Mleko kokosowe - Koko-Polska

Dodane produkty powinny zawierać wszystkie informacje takie jak wielkość, `units`, ilość, kod kreskowy, producent itd. Za dodawanie, edytowanie i usuwanie produktów odpowiada administrator systemu. W pierwszej wersji powinno odbywać się to manualnie prawdopodobni za pomocą formularza, co w późniejszej wersji powinno być rozszerzone przez dodatkowe opcje takie jak: dodatkowych narzędzi, dodawanie ich przy pomocy zewnętrznych baz danych lub zewnętrznych API. Dodawanie produktów do bazy globalnej również będzie odbywać się przy pomocy innego narzędzia, które pozwoli użytkownikom proponowania dodania nowych produktów do bazy globalnej, które będą musiały zostać wcześniej zaakceptowane. Akceptowanie będzie odbywać się ręcznie, AI lub prostym skryptem walidacji.

##### Spiżarnia użytkownika

Kolejnym narzędziem, tym razem przeznaczonym dla zwykłego użytkownika jest narzędzie pozwalające na zarządzaniem produktami, które użytkownik faktycznie posiada. Użytkownik powinien być w stanie podzielić swoja `spiżarnie` na kilka kategorii. Proponowane kategorie to kategorie związane z miejscem ich przechowywania np. lodówka, pod zlewem, kantorek lub szafka. Nie mniej jednak użytkownik powinien mieć możliwość dodawania własnych kategorii i nazywania ich jak chce. 

Użytkownik z tego miejsca powinien mieć możliwość dodawania produktów z **globalnej bazy** jak i tworzenia własnych produktów lokalnych. Ma to rozwiązać problem w którym produkt, który chce dodać użytkownik nie istnieje w bazie. Lokalne produkty podobnie jak produkty w bazie globalnej powinny spełniać te same wymagania.

> Wspomniane wcześniej dodawanie / proponowanie lokalnych produktów do globalnej bazy danych przez użytkowników nie jest **w tym momencie** celem tego narzędzia.

Produkty i ich ilość powinny być przypisane do odpowiednich kategorii ale nie jest to wymagane. Mogą być produkty, które nie należą do żadnej kategorii ale wciąż występują w gospodarstwie domowym. Kategorie powinny również mieć możliwość `przypięcia` produktów do odpowiedniej kategorii, oznacza to ze użytkownik może chcieć mieć produkt w kategorii pomimo `zerowej` ilości produktu w domu. Ma to zapobiec ciągłemu rozmieszczaniu produktów po kategoriach przy każdym dodawaniu go do spiżarni. W tym przypadku po dodaniu produktu, który jest przypięty, zwiększy się ilość produktu już przypiętego, a w przypadku większej ilości przypięć tego samego produktu zapyta go `o określenie kategorii` a następnie zwiększy w niej ilość.