---
title: Advent of Code 2016 dzień 9
date: '2016-12-11 20:21:23 +0100'
categories:
- Strefa zadaniowa
excerpt_separator: "<!--more-->"
permalink: "/advent-of-code-2016-dzien-9/"
---
Advent of Code 2016 dzień 9. Dzisiaj trzeba rozpracować algorytm dekompresji. W jednym z plików mogą znajdować się dość ciekawe dane,

# Wprowadzenie
  
{% include aoc-2016-link.md day="9" %}

Advent of Code to inicjatywa, w której codziennie publikowane są zadania algorytmiczne dla programistów. Ich rozwiązywanie pomaga rozwijać umiejętności nie tyko początkujących programistów. W tej serii artykułów pokazuję zadanie opublikowane w ramach Advent of Code 2016 wraz z przykładowym rozwiązaniem.

{% include aoc-2016-leaderboard.md %}

# Dzień 9 zadanie 1
  
[Wczoraj](http://www.samouczekprogramisty.pl/advent-of-code-2016-dzien-8/), dzięki Twojej pomocy udało odczytać to co powinno być wyświetlone na zniszczonym wyświetlaczu. Dzięki temu dostałeś się do chronionej części Kwatery Głównej. Przechadzając się po korytarzach natknąłeś się na port, dzięki któremu możesz dostać się do pozostałej części sieci. Pobieżnie przeskanowałeś interesujące pliki, jeden z nich szczególnie przykuł Twoją uwagę. Plik ten jest skompresowany w pewnym eksperymentalnym formacie. Na szczęście dokumentacja tego formatu znajdowała się niedaleko.

Format kompresuje sekwencje znaków. Białe znaki (spacje, znaki nowej linii itp.) są ignorowane. Aby zaznaczyć, że jakaś sekwencja powinna być powtórzona, umieszcza się przed nią odpowiedni znacznik, na przykład (10x2). Aby zdekompresować następującą po nim sekwencję należy wziąć kolejne 10 znaków i powtórzyć je dwa razy. Następnie należy kontynuować czytanie skompresowanej zawartości po powtórzonej sekwencji. Sam znacznik nie jest dołączany do zdekompresowanego wyjścia.

Jeśli nawiasy, czy inne znaki wystąpią wewnątrz sekwencji, która powinna być powtórzona - wszystko jest w porządku. Należy traktować je jak normalne dane, nie znacznik i kontynuować poszukiwanie znaczników po sekcji, która została powtórzona.

Dla przykładu:

- `ADVENT` nie zawiera żadnych znaczników, więc po dekompresji otrzymamy `ADVENT` bez żadnych zmian, wynik po dekompresji ma długość 6,
- `A(1x5)BC` powtarza tylko B pięć razy, finalnie otrzymujemy `ABBBBBC` o długości 7,
- `(3x3)XYZ` po dekompresji otrzymujemy `XYZXYZXYZ` o długości 9,
- `A(2x2)BCD(2x2)EFG`, powtarzamy znaki `BC` i `EF`, otrzymujemy `ABCBCDEFEFG` o długości 11 znaków,
- `(6xa)(1x3)A` po dekompresji otrzymujemy `(1x3)A`, chociaż `(1x3)` wygląda jak znacznik nie jest przetwarzany bo znajdował się wewnątrz zakresu obsługiwanego przez `(6x1)`, podobnie jak A nie jest traktowany specjalnie. Finalnie otrzymujemy łańcuch o długości 6,
- `X(8x2)(3x3)ABCY` po dekompresji otrzymujemy `X(3x3)ABC(3x3)ABCY` o długości 18 znaków.
  
  
Jaka jest długość zdekompresowanej sekwencji jeśli skompresowane dane zapisane są w [tym pliku](https://raw.githubusercontent.com/SamouczekProgramisty/StrefaZadaniowaSamouka/master/05_aoc_2016/src/main/test/resources/day09_input.txt)?
# Podsumowanie
  
Zachęcam do dalszej zabawy z drugim zadaniem, jego treść pokaże się na stronie AoC2016 po rozwiązaniu pierwszego. Takie zadania pomagają w rozwijaniu umiejętności nie tylko początkujących programistów. Jeśli będziesz miał jakikolwiek problem z rozwiązaniem zadania możesz rzucić okiem do [przykładowego rozwiązania](https://github.com/SamouczekProgramisty/StrefaZadaniowaSamouka/tree/master/05_aoc_2016/src/main/java/pl/samouczekprogramisty/szs/aoc2016/day09), jednak zrób to raczej w ostateczności.

Na koniec mam do Ciebie prośbę - podziel się linkiem do artykułu ze znajomymi, może Oni także będą chcieli pomóc Świętemu Mikołajowi ;) ? Jeśli nie chcesz ominąć kolejnych artykułów proszę zapisz się do mojego newslettera i polub stronę na facebooku. Do następnego razu!

[FM\_form id="3"]

Zdjęcie dzięki uprzejmości https://www.flickr.com/photos/derekl/sets/72157649148835567

&nbsp;

&nbsp;

&nbsp;

&nbsp;
