#KSlots
###O co chodzi w tym pluginie?
**KSlots** to prosty plugin do wyświetlania fałszywej ilości slotów, dodający też używanie dowolnej ilości MOTD na raz. Wiem, config wydaje się skomplikowany, ale jeśli przeczytasz wszystko, będziesz bez problemu obsługiwał plugin :)

==========
###Domyślny config:
```
enableSlotChange: true
plusChange:
  enable: true
  numUntilChange: 20
  numToAdd: 1
normalNumChange:
  enable: false
  numSlots: 50
enableInfiniteSlots: true
enableMotdChange: true
customMotds:
- 'Custom motd 1'
- 'Custom motd 2'
- 'Add your own if you want!'
- 'You can make as many as you want!'
```
No i właśnie, o co w tym wszystkim chodzi?!
#####Może po kolei:
`enableSlotChange: true` - czy włączyć pokazywanie fałszywych slotów<br>
`plusChange:` - tryb 'plus', o trybach dowiesz się więcej, po zapoznaniu się z całym configiem<br>
`normalNumChange:` - tryb 'num', o nim również więcej, ale trochę później<br>
`enableInfiniteSlots: true` - czy włączyć nieograniczone sloty (gracze wejdą nawet jeśli serwer jest pełny)<br>
`enableMotdChange: true` - czy włączyć zmianę motd na losowe motd z configu (obsługa wielu możliwych motd)<br>
`customMotds` - własne motd, których może być nieskończenie wiele (wyświetlają się losowo); możesz dodawać je w configu, lub komendą z poziomu serwera/konsoli; obsługują kody kolorów jak w Essentials (np. &a, &l) lub moje własne (np. $a, $l)

==========
###Tryby fałszywych slotów:
- **Tryb 'plus':**<br>
Jest to tryb, który uwzględnia 'aspekt psychologiczny' patrzenia na serwery na liście serwerów. Jeśli gracz widzi np. że jest 10/100 osób, prawdopodobnie nie wejdzie na serwer, ponieważ jest on pełny ledwie w 10%. Tryb plus działa tak:<br><br>
_Dopóki na serwerze nie będzie odpowiedniej ilości graczy (**numUntilChange:**), plugin wyświetla liczbę slotów równą liczbie ustawionej w **numUntilChange:**. Jeśli graczy jest więcej, niż liczba ustalona w **numUntilChange:**, plugin pobiera ilość graczy na serwerze, dodaje do niej liczbę ustawioną w **numToAdd** i dopiero wyświetla._<br><br>
**Przykład działania:**<br>
Załóżmy, że mamy serwer 150 slotów, siedzi na nim aktualnie 20 graczy. Mało, prawda?<br>
Jeśli włączymy tryb 'plus', **numUntilChange** ustawimy na 30, a **numToAdd** na 2, to zacznie wyświetlać 20/30.<br>
Jeśli wbije jeszcze 10 osób, w rzeczywistości będzie 30/150, ale plugin doda 2 do liczby graczy i wyświetli 30/32.<br>
Prawdopodobnie ludzie chętniej wejdą na serwer, bo zobaczą, że jest on prawie pełny.<br><br>
- **Tryb 'num':**<br>
Ten tryb działa w prostszy sposób - zawsze wyświetla taką liczbę slotów, jaką mu podamy w **numSlots:**. Chyba nie potrzeba większego opisu :)

=========
###Komendy:
- **/kslots** - główna i jedyna komenda pluginu, zmieniasz jej działanie dodając różne argumenty
- **/kslots reload** - powoduje ponowne wczytanie configu
- **/kslots slots** - włącza/wyłącza wyświetlanie fałszywych slotów
- **/kslots tryb <num/plus>** - zmienia tryb wyświetlania fałszywych slotów
- **/kslots infslots** - włącza/wyłącza nieograniczone sloty
- **/kslots motd** - włącza/wyłącza zmienne motd (to pobierane losowo z configu)
- **/kslots motd list** - wyświetla listę motd z configu wraz z ich numerami ID (przydatne przy usuwaniu motd komendą)
- **/kslots motd remove [ID]** - usuwa z configu motd o konkretnym ID
- **/kslots motd add [motd]** - dodaje do configu nowe motd
