---
title: Advent of Code 2016 dzień 22
date: '2016-12-24 07:46:18 +0100'
categories:
- Strefa zadaniowa
permalink: /advent-of-code-2016-dzien-22/
header:
    teaser: /assets/images/2016/12/aoc_2016_dzien_22_artykul.jpg
    overlay_image: /assets/images/2016/12/aoc_2016_dzien_22_artykul.jpg
    caption: "[&copy; derekl](https://www.flickr.com/photos/derekl/sets/72157649148835567)"
excerpt: Advent of Code 2016 dzień 22. Uzyskałeś dostęp do potężnego klastra, musisz zdobyć pewne dane znajdujące się na jednej z maszyn. Aby to zrobić musisz lepiej poznać sposób w jaki dane rozłożone są w klastrze.
disqus_page_identifier: 707 http://www.samouczekprogramisty.pl/?p=707
---

## Wprowadzenie

{% include aoc-2016-link.md day="22" %}

## Dzień 22 zadanie 1

Dzięki Twojej pomocy poprzednio udało się [utworzyć odpowiednie hasło]({% post_url 2016-12-23-advent-of-code-2016-dzien-21 %}). Hasło to pozwoliło Ci się dostać do potężnego klastra maszyn. Każdy komputer w tym klastrze połączony jest maksymalnie z czterema najbliższymi maszynami (trzema jeśli jest na krawędzi lub dwoma jeśli jest w rogu).

Bezpośrednio możesz dostać się tylko do maszyny `/dev/grid/node-x0-y0`, ale możesz także przeprowadzić pewne, ograniczone operacje na pozostałych maszynach w klastrze:

- możesz dostać informacje na temat zużycia dysku (dzięki [`df`](https://en.wikipedia.org/wiki/Df_(Unix)#Example)), wynik tego polecenia jest wejściem do programu,
- możesz poinstruować maszynę aby przeniosła całe dane na sąsiednią maszynę (oczywiście jeśli maszyna docelowa ma wystarczająco dużo miejsca do przyjęcia danych). Maszyna z której przenosisz dane zostaje pusta w wyniku takiej operacji.

Maszyny mają nazwy, które pozwalają poznać ich położenie w klastrze. Na przykład maszyna o nazwie `node-x10-y10` sąsiaduje z maszynami `node-x9-y10`, `node-x11-y10`, `node-x10-y9` i `node-x10-y11`.

Zanim zaczniesz kombinować z klastrem musisz zrozumieć ułożenie danych na maszynach w klastrze. Chociaż możesz tylko przenosić dane pomiędzy sąsiadującymi maszynami będziesz potrzebował przenieść sporo danych aby dostać się do tych, które potrzebujesz. Aby to zrobić musisz dowiedzieć się jak możesz przenosić dane pomiędzy maszynami.

Aby to zrobić, musisz poznać liczbę poprawnych par maszyn, między którymi możesz kopiować dane. Poprawna para maszyn (A, B) niezależnie od tego czy są bezpośrednio połączone czy nie, to para, w której:

- maszyna A nie jest pusta (kolumna `Used` nie zawiera 0),
- maszyny A i B nie są tą samą maszyną,
- dane na maszynie A (kolumna `Used`) zmieszczą się na maszynie B (kolumna `Avail`).

Zakładając, że lista opisująca maszyny w klastrze znajduje się w [tym pliku](https://raw.githubusercontent.com/SamouczekProgramisty/StrefaZadaniowaSamouka/master/05_aoc_2016/src/main/test/resources/day22_input.txt), ile poprawnych par maszyn jest w klastrze?

## Podsumowanie

Zachęcam do dalszej zabawy z drugim zadaniem, jego treść pokaże się na stronie AoC2016 po rozwiązaniu pierwszego. Takie zadania pomagają w rozwijaniu umiejętności nie tylko początkujących programistów. Jeśli będziesz miał jakikolwiek problem z rozwiązaniem zadania możesz rzucić okiem do [przykładowego rozwiązania](https://github.com/SamouczekProgramisty/StrefaZadaniowaSamouka/tree/master/05_aoc_2016/src/main/java/pl/samouczekprogramisty/szs/aoc2016/day22), jednak zrób to raczej w ostateczności.

Na koniec mam do Ciebie prośbę - podziel się linkiem do artykułu ze znajomymi, może Oni także będą chcieli pomóc Świętemu Mikołajowi ;) ? Jeśli nie chcesz ominąć kolejnych artykułów proszę zapisz się do mojego newslettera i polub stronę na facebooku. Do następnego razu!