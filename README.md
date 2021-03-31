# DB-Test
## Aufgabe 1
Stelle Entitäten mittels Chen-Notation und Min,Max Notation dar.
Wähle ein sinnvolles Beispiel!

A:  Player---(1)----spielen---(N)--Game

## Aufgabe 2
Kann eine Beziehung Attribute haben?
A:Ja
Wenn ja, wie stelle ich es im ERD dar?
A: {Player}---1---<playing>--N---{Game}--1------<choosing>-----------1--{Map}
[PID#,Nickname,Score]     [GID#,Gamename,Rounds,Gametype] [MapID#,Mapname]

## Aufgabe 3
Welche Codd'schen Anforderungen gibt es (Nenne mindestens 5)
A: Intergration,Operation,Katalog,Benutzerschichten,Datenschutz,Datensicherung

## Aufgabe 4
Nenne den Unterschied zwischen Konzeptuellen und Logischem Schema
A:
Konzeptuelles(DBS unabhängig)             Logisches(DBS orientoiert)
    [extern ]                [ extern ]     [ extern  ]    [ extern ]
     |                               \        |       /
    [konz.]                            \      |      /
     |                                   [  logisch  ]
    [intern]                                       |
     |                                   [   intern  ] 
    [daten]                                /       \
                                    [daten]       [daten]
                                    
## Aufgabe 5
Welche 3 Bestandteile gibt es im Entity Relationship Model
A:Objekt,Objekt-Atribute,Beziehung

## Aufgabe 6
Welche Datentypen gibt es in MySQL? (Nenne mindestens 5)
A:integer,varchar,char,small-integer,float,double,date,boolean

## Aufgabe 7
Welche Arten von Schlüsseln gibt es und welche Eigenschaften besitzen diese?
A:
Primiär einzigartig kann nur einmal benutzt werden,Fremdschlüssel kann mehrmals benutzt werden.
[prim# >zahl] [name]          [fremd# >zahl] [name]     [Familie]   [familienmitglieder]
 1        alex                      1           alex        bider           4
                                    1           Linda       bider           4
 man kann bei prim. nie gleiche inputs haben.
 
## Aufgabe 8
Welche Arten von Beziehungen gibt es? Zeichne für jede ein Beispiel auf
A:
1 zu 1      ein Spieler kann auf einer Platform spielen. 
1 zu N      ein Spieler kann mehere Spiele spielen.
N zu M      ein Spiel kann mehrere inhalte besitzen.

## Aufgabe 9
Was bedeutet der Begriff Kardinalität und welche Kardinalitäten gibt es?
A:
Ist eine Mengenangabe für Objekt-beziehungs Diagramme
Es gibt Vier Kardinalitäten.
(0,n:1,1)       (1,1)    (1,N)  (N,M)

## Aufgabe 10
Was bedeutet der Begriff Datenintegrität und worin unterscheidet sich Integrität und referentielle Integrität?
A: korrektheit,vollständigkeit,konsistänz der  daten.
A:referentielle Integrität kann einen datensatz eines Fremdschlüssel aufweisen und nur dann gespeichert werden, wenn der Wert des Fremdschlüssels einmalig in der referenzierten Tabelle existiert.

## Aufgabe 11
Erkläre die 3 Normalformen
nf1
[player][game][type][time]  [score]     
 alex     COD  shooter  3h      153000
 
nf2
[player][time]
 alex   3h
 
[game]
COD

[type]
shooter

[score]
153000

nf3
[player]
alex

[game]
COD

[time]
3h

[type]
shooter

[score]
153000

## Aufgabe 12
Erkläre den Unterschied zwischen starken und Schwachen Entitäten und erstelle ein Beispiel.
A:
die starke Entität ist der schwachen übergeordnet.
schwache Entität können auch ohne starken Entitäten exestieren.

## Aufgabe 13
Welche Grundregeln gibt es im Relationenmodell? (Nenne mindestens 4)
1)Jede Zeile ist eindeutig.
2)Die ordnung der Zellen ist nicht bedeutenswert wegen ihrer reihenfolge.
3)Die ordnung der Spalten ist nicht bedeutenswert da sie einen eindeutigen Namen haben.
4)Alle Datenwerte innerhalb einer Relation sind atomare Datenelemnte.
5)Es kann nur einen primiärschlüssel exestieren.

## Aufgabe 14
Wie löst man eine M:N Beziehung auf? Erstelle ein Beispiel
{Kunde}-n--<kauf vom spiel>--m--{companies}
  
durch eine 1 zu n beziehung
  {Kunde}-1--kauf vom spiel--n--{companies}
  
## Aufgabe 15
Ein Handelsbetrieb verkauft ein Sortiment von Artikeln, die er von verschiedenen Herstellern bezieht. Der Handelsbetrieb hat einen bestimmten Kundenkreis, der regelmäßig Bestellungen aufgibt. Eine Bestellung kann mehrere Artikel umfassen. Ein Artikel kann von mehreren Lieferanten bezogen werden und ein Lieferant liefert natürlich meist mehr als einen Artikel. Erstelle ein ERD und ein Relationenmodell, welches der 3. Normalform entspricht.

A:Bild

## Aufgabe 16
Welche Anomalien kennst du und was beschreiben sie?
A:
Insert> fügt daten in einer tabelle hinzu 
Update> ändert daten in einer tabelle
Select> Daten aus einer tabele auswählen
Delete> löscht daten aus einer tabelle

## Aufgabe 17
Modellieren Sie den angeführten Realitätsausschnitt einer Fluggesellschaft mit Hilfe eines Entity Relationship- Diagramms. Treffen Sie, falls notwendig, sinnvolle Annahmen und dokumentieren Sie diese nachvollziehbar in Ihrer Lösung. Der zu betrachtende Realitätsausschnitt der Fluggesellschaft umfasst folgenden
Sachverhalt:
Flughäfen haben ein Kürzel (= Schlüssel) und gehören zu einer Stadt (z.B. „FRA“ für Frankfurt, „FCO“ für Roma Fiumicino).
Flüge haben eine Flugnummer (z.B. „LH 306“), führen von einem Flughafen zu einem anderen, mit jeweils einer festen Abflugs- und Ankunftszeit (z.B. ab Frankfurt um 07:30 nach Roma Fiumicino mit Ankunft um 09:15).
Jeder Flugzeugtyp hat einen Namen (z.B. „747-400“) und eine Sitzanzahl (z.B. 430 Sitze).
Piloten haben einen Namen (z.B. „Meier“), ein Geburtsdatum (z.B. „1.1.1960“) und eine Berechtigung, bestimmte Flugzeugtypen zu fliegen (z.B. „747-400“ und „A310“).
Jedes einzelne Flugzeug ist von einem bestimmten Flugzeugtyp (z.B. „747-400“) und hat einen Namen (z.B. „Mozart“).
Bei einem Flug-Einsatz wird ein Flug (z.B. „LH 306“) an einem bestimmten Datum (z.B. „6.2.2011“) von einem bestimmten Piloten (z.B. „Meier“) mit einem bestimmten Flugzeug (z.B. „Mozart“) geflogen.
Bilden Sie das konzeptuelle Schema in ein relationales Schema ab. Das relationale Schema soll der 3. Normalform genügen
A: Bild 
