# Stroke_analiza_danych_R
* Pozyskaną bazę danych poddano analizie w celu ustalenia, czy isnieją jakieś czynniki, które wpływają na zwiększenie ryzyka udaru.
* Dodatkowo przeanalizowano wskaźnik BMI u osób biorących udział w badaniu, w celu sprawdzenia czy miejsce zamieszkania lub rodzaj wykonywanej pracy ma wpływ na poziom tego wskaźnika.

## Baza danych
Przedmiotowa baza danych zawiera informację na temat pacjentów i ich problemów zdrowotnych oraz trybu życia. Baza danych składa się z 12 kolumn i 5111 wierszy. Baza została pobrana ze strony [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) i zawiera informację o:
*    id pacjenta
*    płci
*    nadciśnieniu
*    zawale serca
*    czy był/a kiedykolwiek żonaty/zamężna
*    rodzaju wykonywanej pracy
*    miejscu zamieszkania
*    przeciętym poziomie glukozy
*    BMI
*    jak często pali
*    czy miał już udar

Pełne informacje na temat zawieranych w poszczególnych kolukmnach danych oraz o ich rodzaju znajdują się w utworoznym [opisie](https://github.com/Gdyczko/Stroke_analiza_danych_R/blob/main/Opis.txt)

## Czszczenie danych
* Po wczytaniu bazy danych, sprawdzono jej struktórę oraz watości brakujące. Według zastosowanej funkcji nasze dane nie posiadają wartości brakujący NA jednakże przy zastosowaniu funkcji str() zauważono, że występują wartości NA w kolumnie bmi ale ze względu na zapis "N/A" program R, czyta to jako tekst a nie jako wartość brakujące.
* Wartości barkujące zastąpiono medianą.
* Uporzadkowano klasy zgodnie z posiadanymi danymi oraz usunięto niepotrzebne do analiz kolumny.
* Sprawdzono poprawność zapisu danych.
* Dane zapisane w sposób binarny przekształcono na dane typu Factor i nadano im stosowne etykiety.
* Tam, gdzie było to możliwe proces ten zautomatyzowano.

## Analiza statystyczna
Z przeprowadzonych analiz ststystycznych można wywnioskować, że w badaniach brały udział zarówno dzieci jak i osoby starsze. Najmłodzsze dziecko miało niecały miesiąc (0,08), natomiast najstarsza badana osoba miała 82 lata. Średnia wieku dla badanej grópy wynosi około 43 lata. Odchylenie standardowe mówiące o rozrzucie danych od wartości średniej wynosi 22.61358. Zaobserwowano również, że rozkład analizowanych danych dotyczących wieku przyjmuje lekką asymetrię lewostronną (około -0,14), co oznacza, że w naszej badanej grópie jest trochę wiecej osób z wiekiem powyżej 43 roku życia. Podczas przeprowadzonych badań, połowa respondentów (50%) była w wieku w przedziale 25 - 61 lat.

## Wizualizacja danych
![alt text](https://github.com/Gdyczko/Stroke_analiza_danych_R/blob/main/Number%20of%20people%20by%20employment.png "Rodzaj zatrudnienia")
Wykres przedstawia liczbę badanych, w zależności od rodzaju zatrudnienia. W ramach pięciu zadeklarowanych kategrii obok osób zatrudnionych w prywatnych przedsiębiorstwach (Private) jak i jednostkach rządowych (Government job) oraz samozatrudninych (Self-employed) znalały się osoby, które nigdy nie pracowały (Never worked) oraz grupa dzieci (Children). Z przeprowadzonej analizy wynika, że dominującą grupą w badaniu były osoby, które deklarowały, iż pracują w przedsiębiorstwach prywatnych (blisko 3000 osób), kilkakrotnie przewyższając liczebnie pozostałe kategorie. Grupa osób deklarujących pracę w jednostkach rządowych jest bardzo zbliżona do liczby dzieci biorących udział w badaniu. Nieznacznie liczniejszą grupę stanowią osoby pracujące we własnych firmach (samozatrudnione), jest nieco ponad 800 osób. Natomiast najmniej liczącą grupę stanowiły osoby, kótre nigdny nie pracowały.

![alt text](https://github.com/Gdyczko/Stroke_analiza_danych_R/blob/main/BMI%20level%20by%20place%20of%20residence.png "BMI a miejsce zamieszkania")
Powyższy wykres przedstawia poziom indeksu BMI u badanych osób według miejsca zamieszkania. Dodatkowo na wykresie zaznaczono przerywaną niebieską linię przedstawiającą maksymlany poziom prawidłowego BMI (MAX corect BMI) na poziomie 24.9. Z przeprowadzonej analizy wynika, że większość osób (ok. 75%), niezaleźnie od miejsca zamieszkania, ma poziom BMI powyżej normy. U ludzi mieszkających na wsi występuje większa różnorodność wartości BMI (większy rozrzut danych o ok. 20 pkt) niż u ludzi mieszkających w mieście. Połowa badanych osób, zarówno tych mieszkających na wsi jak i w mieście ma BMI na poziomie od ok. 24 do 33 punktów.

![alt text](https://github.com/Gdyczko/Stroke_analiza_danych_R/blob/main/BMI%20level%20by%20type%20of%20work.png "BMI a rodzaj pracy")
Wykres "BMI level by type of work" przedstawia zakres wartości BMI w zależoności od rodzaju wykonywanej pracy. Również w tym wykresie jak i poprzednim naniesiono dodatkowo czerwoną przerywaną linię, która wskazuje górną granicę prawidłowego poziomu BMI (MAX corect BMI). Z analizowanego wykresu możemy wywnioskować, że większość badanych prezentuje wartość BMI powyżej normy niezależnie od rodzaju ztrudnienia. Jedynie osoby nigdy nie pracujące w ok. 50% mieszczą się w granicach prawidłowego BMI. Wyjątkiem na wykresie jest grupa badanych dzieci, które w znaczenj części (ponad 75% badanych) znajdują się poniżej górnej granicy prawidłowej masy ciała. Grupa badanych, pracująca w sektorze prywatnym prezentuje najszerszy zakres wartości BMI oraz znajdują się osoby z najwyższym wskaźniekiem BMI.

![alt text](https://github.com/Gdyczko/Stroke_analiza_danych_R/blob/main/Corelation%20between%20all%20data.png "korelacja pomiędzy wszytskimi danymi")
Wykres "Corelation between all data" prezentuje wyniki zależnośći pomiędzy wszytskimi badanymi czynikami. Dzięki takiemu zabiegowi wykres sam wskazuje możliwe istneijące korelacje pomiędzy poszczegónymi czynnikami. Z wykresu wynika, że pomiędzy badanymi czynnikami praktycznie nie ma żadnej korelacji lub jest ona bardzo słaba, a w niektórych przypadkach umiarkowana. Wizualizacja głównie przyjmuje wartości dodatnie, ale wystęują również wartości ujemne w przypadku osób, które nie podały statusu palenia. Ze względu
na fak iż badania zebrano w celu przeprowadzenia analiz dotyczących występowania udaru, interpretując powyższy wykres możemy wywnioskować, że nie odnaleziono żadnych czynników (np. palenie tytoniu, zawały serca, nadciśnienie), które miałby by istotny wpływ na pojawienie się tej choroby. Korelacja z żadnym czynnikiem nie przekracza wartości 0,25. Jedyna silna korelacja jak pojawia sie wizualizacji dotyczy wieku i bycia w związku małżeńskim. Jest to korelacja dodatnia i wynosi 0,68. Oznacza to, że im osoba jest starza tym większe prawdopodobieństo, że znajduje się lub znajdowała się w związku małżeńskim.
