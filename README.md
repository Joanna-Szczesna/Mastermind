# Mastermind w kosmosie

## Historia
Potężny czarodziej chce zniszczyć Ziemię. Ma swoje powody - regularnie zostaje okradany ze swoich 40% eliksirów. 
Tobie, jako ostatniemu ze szlachetnych daje szansę by Ziemia ocalała.
Proponuje byś złamał jego planetarny kod.
Planety ułożone w określonym porządku dadzą Ci zwycięstwo.
Masz maksymalnie 14 prób i satelity z podpowiedziami.
Gdy zawiedziesz dla Ziemi nie będzie już ratunku.

## Use Case Diagram 

![Use Case Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Joanna-Szczesna/Mastermind/main/use_case.puml)

## Sequence Diagrams

![Sequence Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Joanna-Szczesna/Mastermind/main/sequence_diagram.puml)

![Sequence Diagram](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/Joanna-Szczesna/Mastermind/main/sequence_diagram_save_game.puml)


## Wymagania funkcjonalne


|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**1**| **Odpowiedz zwrotna po próbie odgadnięcia kodu** |**Niezbędne**      |


REQ_FUNC_1.1. Odpowiedz zwrotna formułowana jest w oparciu o bieżącą próbę odgadnięcia

REQ_FUNC_1.2. Odpowiedz zwrotna przekazuje informację ile poprawnych kolorów było umieszczonych we właściwej pozycji (wyrażone przez czarne znaczniki podpowiedzi)

REQ_FUNC_1.3. Odpowiedz zwrotna przekazuje informację ile poprawnych kolorów było umieszczonych w nieprawidłowej pozycji (wyrażone przez białe znaczniki podpowiedzi)

REQ_FUNC_1.4. Odpowiedz zwrotna przekazuje Informację ile niepoprawnych kolorów było umieszczonych w nieprawidłowej pozycji (wyrażone przez brak znacznika podpowiedzi)

REQ_FUNC_1.5. Odpowiedz zwrotna nie może sugerować którego koloru (elementu), której pozycji w kodzie dotyczy (przykład: gracz w dwóch kolejnych próbach układa dokładnie tę samą kombinację kolorów w tych samych pozycjach, dostaje kolejno odpowiedzi zwrotne wyrażone w znacznikach podpowiedzi, których rodzaj jest ten sam, jednak są ułożone w różnej kolejności)

REQ_FUNC_1.6. Odpowiedz zwrotna określa czy gra się kończy (możliwe stany: wygrana, przegrana lub kontynuacja rozgrywki tj. podejmowanie kolejnej próby odgadnięcia)

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**2**| **Rozpoczęcie rozgrywki (warunki początkowe** |**Niezbędne**      |

REQ_FUNC_2.1. Rozpoczęcie rozgrywki następuje w wyniku akcji ze strony użytkownika przez wybór przycisku "START"

REQ_FUNC_2.2. Kod składający się z kolorów w określonych pozycjach jest losowany jednorazowo przy rozpoczęciu rozgrywki i jest stały w trakcie całej gry

REQ_FUNC_2.3. Wylosowany kod nie jest widoczny dla gracza

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**3**| **Zakończenie rozgrywki (warunki końcowe** |**Niezbędne**      |

REQ_FUNC_3.1. Gra kończy się w momencie gdy bieżąca próba odgadnięcia zakończy się rozszyfrowaniem wylosowanego kodu (wygrana)

REQ_FUNC_3.2. Gra kończy się gdy graczowy nie powiedzie się odgadniecie kodu w ostatniej, maksymalnie 14stej próbie (przegrana)

REQ_FUNC_3.3. Gra kończy się gdy użytkownik wybierze przycisk "Automatyczne wysadzenie Ziemii! Nie ruszaj!" (przegrana)

REQ_FUNC_3.4. W momencie zakończenia gry prezentowany(ujawniany) jest kod wylosowany na początku rozgrywki

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**4**| **Ustalanie kodu** |**Niezbędne**      |

REQ_FUNC_4.1. Na kod składa się kombinacja kolorów w określonych pozycjach

REQ_FUNC_4.2. Użytkownik wybiera ilość pozycji (ilość pól) kodu, którą będzie zgadywał

REQ_FUNC_4.3. Kod może składać się z 5-7 pozycji (pól)

REQ_FUNC_4.1.Ilosć pól kodu jest znana użytkownikowi

REQ_FUNC_4.2. Ilość możliwych kolorów jest stała i wynosi 8 kolorów

REQ_FUNC_4.3.  kolory w kodzie mogą się powtarzać

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**5**| **Możliwe modyfikacje ze strony użytkownika** |**Opcjonalne**      |

REQ_FUNC_5.1. Przed rozpoczęciem rozgrywki aplikacja umożliwia definiowanie ilości pól kodu (5-7pól)

REQ_FUNC_5.2. Przed rozpoczęciem rozgrywki aplikacja umożliwia definiowanie ilości możliwych prób (10-14)

REQ_FUNC_5.3. [rozszerzenie] Przed rozpoczęciem rozgrywki aplikacja umożliwia wczytanie zapisanego stanu gry  

REQ_FUNC_5.4. [rozszerzenie] Po rozpoczęciu rozgrywki aplikacja umożliwia zapisanie stanu gry 

REQ_FUNC_5.5. <![endif]>[rozszerzenie] Zapis gry zawiera nazwę nadaną przez użytkownika

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**6**| **Punktacja rozgrywki** |**Opcjonalne** |

REQ_FUNC_6.1. Każda z rozgrywek jest punktowana

REQ_FUNC_6.2. Podliczenie następuje w momencie zakończenia gry

REQ_FUNC_6.3. Za każdy kolor ułożony w dobrej pozycji użytkownik dostaje 2pkt

REQ_FUNC_6.4. Za poprawny kolor ułożony w niepoprawnej pozycji użytkownik dostaje 1pkt

REQ_FUNC_6.5. Za rozszyfrowanie całego kodu użytkownik dostaje dodatkowo ilość punktów równą różnicy pomiędzy maksymalną ilością prób (14) a ilością prób w której udało się kod rozszyfrować

REQ_FUNC_6.6. Wynik rozgrywki zapisywany jest w rankingu wszystkich rozgrywek

|              |Przykłady punktacja                          |
|----------------|-------------------------------|
|**Wygrana**| |
|| za każdą planetę w dobrym miejscu ilość ułożonych planet planet*2pkt (dobry kolor i miejsce)     
||   ilość prób maksymalna(zawsze 14) - w ilu próbach udało się odgadnąć|
|| `Przykład: udało się rozszyfrować kod za trzecim razem:`|
|| `5planet * 2pkt = 10 pkt`|
|| `14 - 3podejscia = 11pkt`|
|| `Razem 10 +11 = 21 pkt za rozgrywkę`|
|**Przegrana**|  |
|| za każdą planetę w dobrym miejscu ilość ułożonych planet planet * 2pkt (dobry kolor i miejsce)|
|| za poprawny kolor planety w nieprawidłowej pozycji ilość planet *1pkt (dobry kolor, zła pozycja)|
|| `Przykład: <![endif]--> dwie planety w dobrym kolorze i pozycji, jedna w dobrym kolorze i nieprawidłowej pozycji, 2 nieprawidłowy kolor i pozycja`|
|| `2 planety * 2pkt(dobry kolor i pozycja) = 4pkt`|
|| `1 planeta * 1pkt (dobry kolor zła pozycja) = 1pkt`|
|| `2 planety * 0pkt (zły kolor zła pozycja) = 0pkt`|
|| `Razem 4+1+0=5pkt za rozgrywkę`|



|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**7**| **Rejestracja** |**Opcjonalne** |

REQ_FUNC_7.1. Do rejestracji wymagane jest podanie adresu mailowego, nazwy użytkownika, hasła

REQ_FUNC_7.2. Pola adres mailowy, nazwa użytkownika jak i hasło są walidowane

REQ_FUNC_7.3. Hasło wymóg: znaki alfanumeryczne oraz znaki specjalne

REQ_FUNC_7.4. Minimalna długość hasła: 8 znaków

REQ_FUNC_7.5. Minimum jedna mała I jedna wielka litera w haśle

REQ_FUNC_7.6. Minimum jedna cyfra w haśle

REQ_FUNC_7.7. Minimum jeden znak specjalny w haśle

REQ_FUNC_7.8. W momencie rejestracji użytkownik dostaje informacje zwrotną czy jego hasło spełnia wymogi

REQ_FUNC_7.9. W informacji zwrotnej nt hasła jest informacja, który z wymogów nie jest jeszcze spełniony

REQ_FUNC_7.10. Nazwa użytkownika może składać się ze znaków alfanumerycznych. Znaki specjalne są zabronione

EQ_FUNC_7.11. Adres mailowy musi zawierać znak "@"

REQ_FUNC_7.12. Po weryfikacji jako poprawnych pól adresu mailowego, nazwy użytkownika, hasła na adres mailowy użytkownika zostaje wysłany mail z potwierdzeniem rejestracji

REQ_FUNC_7.13. Potwierdzenie rejestracji przez użytkownika jest niezbędne do skorzystania z opcji logowania

|   lp            |nazwa grupy:                          |priorytet                         |
|----------------|-------------------------------|-----------------------------|
|**8**| **Logowanie** |**Opcjonalne** |

REQ_FUNC_8.1. Aplikacja umożliwia logowanie się użytkownika

REQ_FUNC_8.2. Logowanie za pomocą nazwy użytkownika oraz ustalonego przez niego hasła

REQ_FUNC_8.3. Poprawne zalogowanie jest warunkiem skorzystania z możliwości wczytania gry i zapisu