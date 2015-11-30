![LoFi Brain](http://www.lofirobot.com/wp-content/uploads/lofi_brain1280.jpg)

# LoFi Brain

LOFI BRAIN TO MÓZG NASZEGO ROBOTA. DOWIEDZ SIĘ JAK ON FUNKCJONUJE I JAK WLEWAĆ ROBOTOWI OLEJ DO GŁOWY.

LOFI BRAIN to główny elektroniczny sterownik robotów budowanych z wykorzystaniem zestawu EDUBOX. Jego nazwa jest nieprzypadkowa, bo jeśli porównać robota do żywego organizmu (np. jakiegoś zwierzęcia) to sterownik pełni u niego identyczną rolę jak właśnie MÓZG.


## Jakie są podstawowe funkcje sterownika:

– odczytywanie sygnałów z czujników
– sterowanie tzw. AKTUATORAMI – czyli urządzeniami WYJŚCIA – silnikami, diodami LED, głośniczkiem itp.
– komunikacja z komputerem
– wykonywanie programów

Od strony technicznej płytka LOFI BRAIN to tzw. ADAPTER, umieszczamy na niej moduł kompatybilny z Arduino i podłączamy wszystkie czujniki i aktuatory. W połączeniu z systemem modułowych czujników, LOFI BRAIN zdecydowanie upraszcza dokonywanie elektronicznych połączeń i umożliwia zbudowanie prostego robota (np. światłoluba) dosłownie w kilka chwil.

## Podstawowe elementy sterownika LOFI BRAIN:

1. Moduł PRO MICRO – kompatybilny z Arduino Micro i Leonardo – to na nim znajduje się procesor Atmega32u4, który programujemy
2. Złącza INPUT – cztery białe złącza po lewej stronie płytki umożliwiają odczytywanie danych z czujników (czujnik światła, przycisk, potencjometr)
3. Złącza OUTPUT – czteru białe złącza po prawej stronie płytki – umożliwiają sterowanie AKTUATORAMI (czyli modułami wykonywującymi jakiegoś rodzaju operacje), podłączamy do nich diody LED, miernik, silniki SERWO, UWAGA – ZŁĄCZA OUTPUT NIE SĄ PRZEZNACZONE DO PODŁĄCZANIA SILNIKÓW DC
4. Buzzer – mały głośniczek, wbudowany w płytkę pozwalający generować charakterystyczne piszczące sygnały dźwiękowe (barwy dźwięku buzzera niestety nie jesteśmy w stanie zmieniać)
5. Złącze BLUETOOTH – osadzamy w nim moduł BLUETOOTH wpinając jego nóżki zgodnie z oznaczeniami znajdującymi się na płytce
6. Złącze czujnika odległości HC-SR04 – podłączamy do niego znajujący się w zestawie czujnik odległości
7. Sterownik silników – w płytkę wbudowany jest sterownik silników DC (nazwa sterownika to L293D), umożliwiający obrót silników DC w obydwu kierunkach
8. Złącza silników DC – dwa czarne złącza oznaczone M1 i M2 do których podłączamy silniki DC służące jako napędy kół.
9. Włącznik płytki – działa on kiedy robot funkcjonuje samodzielnie i płytka zasilana jest przez tylko przez powerbank.
Zasilanie

Płytkę LOFI BRAIN zasilamy przez gniazdo MICRO USB przy pomocy znajdującego się w zestawie POWERBANKU lub bezpośrednio z komputera. Do gniazda USB znajdującego się na płytce BRAIN podpinamy POWERBANK, do gniazda znajdującego się na module PRO MICRO podłączamy kabel USB przez który programujemy płytkę.

## LOFI Brain - zasilanie

Jeśli płytka jest podłączona do komptera przez gniazdo modułu PRO MICRO nie jest konieczne podłączanie dodatkowego zasilania z powerbanku. Nie działa wówczas

![](http://www.lofirobot.com/wp-content/uploads/brain_zasilanie-1280x853.jpg)

Kiedy robot jest odłączony od komputera i działa samodzielnie zasilany tylko przez POWERBANK podłączamy go do złącza na płytce LOFI BRAIN.

## Podłączanie modułów

Wszystkie moduły elektroniczne (poza czujnikiem odległości) podłączane są do sterownika LOFI Brain przy pomocy uniwersalnego 3-pinowego złącza.

Moduły dzielimy na:
CZUJNIKI – czujnik światła, przycisk, potencjometr
AKTUATORY – dioda led, miernik napięcia, silnik DC, serwomotory

CZUJNIKI podłączamy do złącz INPUT natomiast aktuatory podłączamy do złącz OUTPUT poza silnikami DC, które podłączamy do złącz M1 i M2

UWAGA! – czarną końcówkę przewodu do podłączenia modułu należy wpiąć do złącza tak aby strona, po której znajdują się blaszki była zwrócona w stronę plastikowej wypustki gniazda INPUT/OUTPUT.

![](http://www.lofirobot.com/wp-content/uploads/podlaczanie-1280x854.jpg)

LOFI Brain - podłączanie modułów

## Tryby pracy

Sterownik robota może funkcjonować w dwóch podstawowych trybach pracy:

1. Sterowanie z komputera – jak np. w przypadku współpracy ze Scratchem, gdy sam program wykonywany jest w komputerze do którego podłączony jest robot a do sterownika wysyłane są tylko instrukcje jak sterować konkretnymi komponentami (silnikami, odczytami z czujników), tryb ten wymaga bezpośredniego połączenia robota z komputerem przez kabel USB lub moduł bluetooth, robot nie jest w stanie działać wówczas samodzielnie.

2. Działanie autonomiczne – kiedy do pamięci sterownika wgrywamy skrypt z konkretnymi instrukcjami (np. przy pomocy programu ARDUINO IDE), wówczas po wgraniu skryptu robota możemy odłączyć od komputera i działa on samodzielnie, w tym trybie robot również może komunikować się z komputerem ale zasadniczy program wykonywany jest w pamięci robota (mikrokontrolera Arduino) i będzie on zapamiętany nawet po odłączeniu zasilania.