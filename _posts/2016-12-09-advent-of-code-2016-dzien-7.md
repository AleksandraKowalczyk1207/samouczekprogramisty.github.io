---
layout: default
title: Advent of Code dzień 7
date: '2016-12-09 16:12:27 +0100'
categories:
- Strefa zadaniowa
excerpt_separator: "<!--more-->"
permalink: "/advent-of-code-dzien-7/"
---
Advent of Code 2016 dzień 7. Tym razem próbujesz podsłuchać ruch sieciowy w Kwaterze Głównej Króliczka Wielkanocnego. Problem w tym, że używa się tam IPv7...

# Wprowadzenie
  
[idea]Oryginalna strona z zadaniami z [Advent of Code 2016](http://adventofcode.com/2016). Zadanie z artykułu dostępne jest pod adresem [http://adventofcode.com/2016/day/7](http://adventofcode.com/2016/day/7)[/idea]

Advent of Code to inicjatywa, w której codziennie publikowane są zadania algorytmiczne dla programistów. Ich rozwiązywanie pomaga rozwijać umiejętności nie tyko początkujących programistów. W tej serii artykułów pokazuję zadanie opublikowane w ramach Advent of Code 2016 wraz z przykładowym rozwiązaniem.

[idea]Jeśli masz ochotę na odrobinę rywalizacji możesz dołączyć do klasyfikacji, którą założyłem na oryginalnej stronie. Aby dołączyć do tej klasyfikacji zaloguj się na [http://adventofcode.com/2016](http://adventofcode.com/2016) i dołącz wpisując kod `124245-88569bd0`.[/idea]

# Dzień 7 zadanie 1
  
[Wczoraj](http://www.samouczekprogramisty.pl/advent-of-code-2016-dzien-6/) odebrałeś tajny kod od Świętego Mikołaja. Dzisiaj nadszedł czas na inwigilację sieci w Kwaterze Głównej Króliczka Wielkanocnego. W trakcie podsłuchiwania ruchu zebrałeś listę [adresów IP](https://en.wikipedia.org/wiki/IP_address) (oczywiście są to adresy IPv7[1. IPv7 w tym momencie nie istnieje.] , [IPv6](https://en.wikipedia.org/wiki/IPv6) jest zbyt ograniczony...). Chciałbyś dowiedzieć się, które z tych adresów wspierają TLS.

Adres IPv7 wspiera TLS jeśli zawiera sekwencję ABBA wewnątrz standardowych części adresu IP. Sekwencja ABBA to czteroznakowa sekwencja, które zawiera parę dwóch różnych znaków, po której znajduje się ta sama para ale odwrócona. Na przykład `xyyx` czy `abba`. Jednak aby adres IPv7 wspierał TLS, sekwencja ABBA nie może znajdować się w żadnej części "hypernet" adresu IP. Części "hypernet" znajdują się między nawiasami `[]`.

Na przykład:

- `abba[mnop]qrst` wspiera TLS, sekwencja ABBA `abba` znajduje się poza nawiasami `[]`,
- `abcd[bddb]xyyx` chociaż sekwencja ABBA `xyyx` jest poza nawiasami, adres ten nie wspiera TLS, sekwencja ABBA znajduje się także wewnątrz nawiasów `bddb`,
- `aaaa[qwer]tyui` nie wspiera TLS, `aaaa` nie jest poprawną sekwencją ABBA,
- `ioxxoj[asdfgh]zxcvbn` wspiera TLS, sekwencja ABBA `oxxo` znajduje się poza nawiasami (nie ma znaczenia to, że znajduje się wewnątrz dłuższego łańcucha).
  
  
Zakładając, że wszystkie adresy IP, które udało Ci się podsłuchać znajdują się na [tej liście](https://raw.githubusercontent.com/SamouczekProgramisty/StrefaZadaniowaSamouka/master/05_aoc_2016/src/main/test/resources/day07_input.txt), ile z nich wspiera TLS?
# Podsumowanie
  
Zachęcam do dalszej zabawy z drugim zadaniem, jego treść pokaże się na stronie AoC2016 po rozwiązaniu pierwszego. Takie zadania pomagają w rozwijaniu umiejętności nie tylko początkujących programistów. Jeśli będziesz miał jakikolwiek problem z rozwiązaniem zadania możesz rzucić okiem do [przykładowego rozwiązania](https://github.com/SamouczekProgramisty/StrefaZadaniowaSamouka/tree/master/05_aoc_2016/src/main/java/pl/samouczekprogramisty/szs/aoc2016/day07), jednak zrób to raczej w ostateczności.

Na koniec mam do Ciebie prośbę - podziel się linkiem do artykułu ze znajomymi, może Oni także będą chcieli pomóc Świętemu Mikołajowi ;) ? Jeśli nie chcesz ominąć kolejnych artykułów proszę zapisz się do mojego newslettera i polub stronę na facebooku. Do następnego razu!

[FM\_form id="3"]

Zdjęcie dzięki uprzejmości https://www.flickr.com/photos/derekl/sets/72157649148835567
