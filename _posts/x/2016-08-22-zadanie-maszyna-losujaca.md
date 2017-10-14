---
title: Maszyna losująca
date: '2016-08-22 16:32:48 +0200'
categories:
- Strefa zadaniowa
excerpt_separator: "<!--more-->"
permalink: "/maszyna-losujaca/"
---
Artykuł ten jest pierwszym z artykułów w Strefie Zadaniowej Samouka. Programowania najlepiej jest się uczyć na przykładach, ten artykuł opisuje właśnie jeden z takich przykładów. Specyfikuje dokładnie sposób zachowania prostego programu i przedstawia jego przykładowe rozwiązanie. Zapraszam do lektury.

# Opis zadania
  
W dzisiejszej części napiszesz program, który użyłem do rozstrzygnięcia konkursu, w którym Samouczek Programisty rozdawał książki. W konkursie należało wypełnić prostą ankietę, wśród uczestników zostały rozlosowane dwie książki. Każdy, kto uzupełnił ankietę dostawał jeden los. Dodatkowo, jeśli osoba wskazała kogoś innego jako polecającego, polecający dostawał dodatkowy los w loterii.

Ankieta została przeprowadzona przy pomocy narzędzia Google Forms, z którego następnie wyniki zostały wyeksportowane do pliku CSV (ang. _comma separated values_). Plik CSV to jeden z formatów plików tekstowych, w którym jedna linijka odpowiada jednemu rekordowi. Plik ten zawiera kilka kolumn, których zawartość oddzielona jest przecinkami. Plik zawiera też nagłówek, opisujący nazwy kolumn.

W przykładzie poniżej mamy dwa rekordy z takiego pliku. Irek dostaje dwa losy, Mateusz jeden. Dzieje się tak ponieważ Irek polecił Samouczka Mateuszowi.

    "Timestamp","Jak masz na imię?","Jaki jest Twój adres e-mail?","Temat artykułu","Kto polecił Ci stronę www.samouczekprogramisty.pl (podaj adres e-mail)?""2016/08/15 7:16:38 PM GMT+2","Irek","xxx@gmail.com","Scrum lub Agile","""2016/08/15 7:33:13 PM GMT+2","Mateusz","yyy@gmail.com","Algorytmika","xxx@gmail.com"

  
Twoim zadaniem jest napisanie programu, który pobierze od użytkownika dwa argumenty:
- ścieżkę do pliku wejściowego w formacie CSV na dysku opisanym powyżej (możesz ściągnąć [przykładowy plik](http://www.samouczekprogramisty.pl/wp-content/uploads/2016/08/zadanie_maszyna_losujaca_input.csv), który dla Ciebie przygotowałem),
- liczbę N \>= 1 przedstawiającą liczbę wygrywających.
  
  
Program powinien wczytać zawartość pliku, wyłuskać adresy email a następnie wśród tych adresów wylosować N wygranych. Dla uproszczenia zakładamy, że format pliku jest poprawny oraz, że uczestnicy konkursu nie oszukiwali (nie było podwójnych losów). Sytuacja w której jeden uczestnik wygrywa dwie książki jest dopuszczalna.
# Wskazówki
  
Dla uproszczenia pokażę Ci parę fragmentów kodu czy metod, które mogą Ci się przydać w rozwiązaniu tego zadania.

Aby podzielić rekord na poszczególne pola możesz użyć metody [`String.split`](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-) jak w przykładzie poniżej

    String[] fields = line.split(",");

  
Aby z pola otoczonego znakami `""` uzyskać wyłącznie jego zawartość możesz użyć wyrażeń regularnych. Na tym etapie proszę użyj przykładowego kodu, o tym czym są wyrażenia regularne przeczytasz w innym artykule.

    private final static Pattern FIELD_PATTERN = Pattern.compile("^\"(.+)\"$");private static String parseField(String field) { Matcher fieldMatcher = FIELD_PATTERN.matcher(field); if (fieldMatcher.matches()) { return fieldMatcher.group(1); } return null;}

  
Metoda ta jako argument przyjmuje wartość pola i zwraca to co znajduje się wewnątrz `""` bądź `null` jeśli pole nie było uzupełnione.

Aby wybrać losowo X wartości musisz losowo rozłożyć adresy email z pliku. Pomóc Ci w tym może metoda [`Collections.shuffle`](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#shuffle-java.util.List-), która w losowy sposób miesza elementy listy.

Z tymi narzędziami jesteś przygotowany do napisania swojej pierwszej maszyny losującej :) Jeśli będziesz miał jakiekolwiek pytania możesz zasugerować się [przykładowym rozwiązaniem](https://github.com/SamouczekProgramisty/StrefaZadaniowaSamouka/tree/master/01_lottery_machine/src/pl/samouczekprogramisty/szs), które dla Ciebie przygotowałem. Jak zwykle zachęcam jednak do samodzielnego rozwiązania zadania, w ten sposób nauczysz się najwięcej.

# Podsumowanie
  
Jeśli tego typu sposób nauki Ci się spodobał proszę daj znać ;) Rozwiązując zadania tego typu w praktyczny sposób przećwiczysz wiedzę, którą zdobyłeś do tej pory. Z biegiem czasu będziesz w stanie rozwiązać zadania o coraz większym poziomie trudności. Wszystko przed Tobą ;)

Na koniec mam do Ciebie prośbę. Zależy mi na dotarciu do jak największego grona czytelników, proszę pomóż mi w tym :) Udostępnij link do bloga na FB swoim znajomym, możesz także zapisać się do newslettera jeśli nie chcesz pominąć kolejnych artykułów. Do następnego razu!

[FM\_form id="3"]

Zdjęcie dzięki uprzejmości https://www.flickr.com/photos/mikolski
