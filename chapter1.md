---
title: 'Wie R funktioniert'
description: 'Mit kleinen Schritten zu den Basics in R'
---

## Hallo und herzlich Willkommen!

```yaml
type: NormalExercise
key: 2bafef99a3
lang: r
xp: 100
skills: 1
```

Sie sind unser/e neue/r Mitarbeiter/in in dem **Team Business Intelligence & Data Analytics der Bambergus Airuber GmbH**, einem Unternehmen das Segelflieger und Motorenflugzeuge produziert und verkauft. Um neue Geschäftsfelder zu erschließen wurde die Firma Airuber GmbH Anfang Q1 2019 akquiriert. Die Firma entwickelt Paketdrohnen und wird ins Stammunternehmen eingegliedert. Sie sollen im Zuge der Akquisition erste Umsatzzahlen analyisieren, bei Fragen und Problemen zur Datenintegration aushelfen und einen Report erstellen. 

Im Zuge dieser Anforderungen befassen Sie sich mit der Programmiersprache R, da sich diese für die statistische Auswertung besonders gut eignet, frei zugänglich ist und in Ihrem Team damit vorrangig gearbeitet wird. 

![Inhalt_l](https://assets.datacamp.com/production/repositories/5035/datasets/85c15e1bd4babd4fceb2be3825e291fc99348dc9/Inhalt_l%C3%A4ngs.PNG)

`@instructions`
Ihr Chef Herr Müller ist mit der Akquisition sehr beschäftigt und hat für Sie direkt verschiedene Aufgaben, die zeitnah erledigt werden müssen. Lassen Sie uns beginnen!

- Wir fangen mit einem kleinen Testprogramm an, sodass Sie mit der Console vertraut werden:
	- Dafür schreiben Sie bitte: **print("Start!")** in das Skript und drücken bitte auf 'Submit Answer'.
    

**#** Mit diesem Zeichen werden Kommentare gekennzeichnet.

**script.R** ist ihre Kommandozeile mit der Sie Ihre Befehle und Ihren Code in der Programmiersprache R eingeben, die in der Console darunter ausgegeben werden. Mithilfe des Buttons **Run Code** kompilieren Sie nur den Code; mit **Submit Answer** führen Sie ihn aus.

`@hint`
Keine Angst - einfach ```
print("Start!")
``` in das Skript schreiben und auf 'Submit Answer' drücken.

Im Bereich **Instruktionen** bekommen Sie ihre Aufgabe, die Sie auch mit Unterstützung dieser Hints lösen sollen.

**script.R** ist ihre Kommandozeile mit der Sie Ihre Befehle und Ihren Code in der Programmiersprache R eingeben, die in der Console darunter ausgegeben werden.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Ihr erstes Programm:

```

`@solution`
```{r}
# Ihr erstes Programm: "Start!"
print("Start!")
```

`@sct`
```{r}
ex() %>% check_output("Start!", fixed=TRUE, missing_msg= "So ist das nicht ganz richtig. Beachten Sie Fehler im Code und auch mögliche Tippfehler. R ist eine case sensitive Programmiersprache!")
success_msg("Ihr erstes Programm ist vollendet - Gut gemacht! Nun geht es richtig los!")
```

---

## Rechnen mit R

```yaml
type: TabExercise
key: a06101a9c2
xp: 100
```

R kann in seiner Basisfunktion als Rechner verwendet werden. Beachten Sie folgende arithmetische Rechenoperatoren:	 

Nützliche Operatoren:

```
 Addition: + 
 Subtraktion: - 
 Multiplikation: *
 Division: / 
 Potenzierung: ^
 Modulo: %%
```

 Wichtig: Der 'Kommaseperator' ist in R der Punkt . und nicht das Komma ,!

`@pre_exercise_code`
```{r}

```

***

```yaml
type: NormalExercise
key: 947a8214db
xp: 50
```

`@instructions`
- 1. Sie sollen die Umsätze der letzten drei Monate der Bambergus Airuber GmbH errechnen und somit den Umsatz für das Quartal Q1 2019 erstellen und analysieren, wie sich der Umsatz durch den Zukauf entwickelt hat.

```
Umsatz in €: Januar 2500000 | Februar 2780000 | März 3200000
```

Beachten Sie, dass es Unterschiede in den Zeilen gibt - sie beinhalten Code und mit dem **'#'** werden Kommentare gekennzeichnet.

`@hint`
Stellen Sie sicher, dass Sie die Summe aus ```
2500000 + 2780000 + 3200000 
``` in einer neuen Zeile eingefügt haben. Starten Sie die Zeile nicht mit einem '#'-Zeichen, ansonsten wird der geschriebene Code nicht wie gewünscht ausgeführt, da damit Kommentare gekennzeichnet werden!

`@sample_code`
```{r}
# 1.Quartalsumsatz Q1:

```

`@solution`
```{r}
# Quartalsumsatz Q1:
2500000 + 2780000 + 3200000
```

`@sct`
```{r}
#ex() %>% check_output(145, fixed=TRUE, missing_msg= "So ist das nicht richtig - Sie müssen sich verrechnet haben!")
ex() %>% check_output(8480000, fixed=TRUE, missing_msg="Sie müssen sich verrechnet haben. Beachten Sie auch mögliche Tippfehler!")
success_msg("Ja, genau - der Umsatz im ersten Quartal beträgt 8480000€!")
```

***

```yaml
type: NormalExercise
key: 587cdaa1b2
xp: 50
```

`@instructions`
- 2. Die Umsätze steigen laut Prognose im Quartal Q2 2019 aufgrund der verzögerten, aber positiven Marktresonanz der Drohnen um **2.2% im Monat**. Welches realistische Umsatzziel geben Sie für das Ende Q2 2019 ab? Nehmen Sie den Ausgangswert von **8480000** am Ende von Q1 2019 an.

`@hint`
Beachten Sie, dass das Wachstum von 2.2% **im Monat** stattfindet und ein Quartal aus drei Monaten besteht. Hier kommt die Zinzeszinsrechnung zur Einsatz - ein exponentielles, kein lineares Wachstum! Achten Sie auch auf die richtige Umrechnung der Prozentzahl.

![Zinseszinsformel](https://assets.datacamp.com/production/repositories/5035/datasets/0e7c37e673c699f3cd9b26cf769aca5676d94a6c/ZInseszinsformel.PNG)

Beachten Sie, dass in R anstatt dem Komma als Dezimaltrennzeichen der Punkt verwendet wird!

`@sample_code`
```{r}
# Umsatzprognose Q2

```

`@solution`
```{r}

8480000*(1.022^3)
```

`@sct`
```{r}
ex() %>% check_output(9052083, fixed=TRUE, missing_msg="So ist das nicht ganz richtig - haben Sie jeweils das monatliche Umsatzwachstum für das Quartal berechnet?")
success_msg("Richtig - die Zinsen wachsen exponentiell an! Und nun zum nächsten Inhaltsblock - den Variablen! (1/6 abgeschlossen)")
```

---

## Variablen

```yaml
type: NormalExercise
key: b4a9e5c4e3
xp: 100
```

Ein grundlegendes Konzept in der (statistischen) Programmierung sind Variablen. Eine Variable ermöglicht es einen Wert (z.B. 8) oder eine Zeichenkette (z.B. "Funktionsbeschreibung") in R zu speichern. Später können Sie den Namen der Variablen nutzen, um einfach auf den Wert oder das Objekt zuzugreifen.

- Beispiel: So können Sie der Variable my_var den Wert 8 zuweisen: ```
my_var <- 8
```

![Variablen vergleichen](https://assets.datacamp.com/production/repositories/5035/datasets/31809ce821fec1a9a0931f929b8f83aa4bfb34a0/Variablen%20vergleichen.PNG)

`@instructions`
Ist es richtig, dass das letzte Halbjahr 2018 erfolgreicher war als das Halbjahr 2019 sich zu entwickeln scheint, wie Herr Müller vermutet, da die Kunden mit dem Kauf der Paketdrohnen zögern und ein Forderungsausfall sich in Q1 2019 auch negativ auf den Umsatz auswirkt?

1. Um besser die Werte vergleichen zu können, ordnen Sie bitte die Quartalszahlen aus **2019 Q1: 8480000** und **Q2: 9052083** den Variablen **x** und **y** zu.

2. In der Variable **z** wurden die Quartalszahlen aus **Q3 & Q4 2018** bereits hinterlegt und zugewiesen. Überprüfen Sie die Vermutung von Herrn Müller und lassen Sie sich bzgl. der Aussage einen booleschen Wert (TRUE oder FALSE) ausgeben.

`@hint`
Schauen Sie bitte in die Exercisebox. Hier ist die Zuweisung anhand eines Beispiels verdeutlicht. Lesen Sie bitte genau die Instruktionen. Der Wert für Variable z wurde bereits im System hinterlegt und der Variable z zugewiesen. 

Entwickeln Sie den Code so, dass ein boolescher Wert (TRUE oder FALSE) ausgegeben wird.

`@pre_exercise_code`
```{r}
z <- 15550000
```

`@sample_code`
```{r}
# 1.Q1:

# Q2

# 2.Vergleich der halbjährlichen Umsätze aus 2018 und 2019: 

```

`@solution`
```{r}
# Q1
x <- 8480000
# Q2
y <- 9052083
# 2.Vergleich der Umsätze
z > (x+y)
```

`@sct`
```{r}
ex() %>% check_object("x") %>% check_equal(8480000)
ex() %>% check_object("y") %>% check_equal(9052083)
ex() %>% check_output("FALSE", fixed=TRUE, missing_msg= "Da haben Sie etwas falsch verglichen bei Aufgabe 2 oder die Aussage von Herrn Müller nicht konkret überprüft!")
success_msg("Ja, genau. Es sieht so aus als hätten Sie die Variablenzuweisung verstanden und Herr Müller lag mit seiner Prognose falsch. Kommen wir zum nächsten Inhaltsblock, den Datentypen (2/6 abgeschlossen)")
```

---

## Datentypen in R

```yaml
type: TabExercise
key: 7196732eac
xp: 100
```

R arbeitet mit zahlreichen Datentypen und ist sensitiv auf Groß- und Kleinschreibung. Einige der grundlegendsten Datentypen sind:

![Datentypen](https://assets.datacamp.com/production/repositories/5035/datasets/191a79dc42ee4882a386eb662bea0623f92ba0bb/Basisdatentypen_%C3%9Cbersicht_final.PNG.png)

**Wichtig:** Zeichenketten werden in "Anführungszeichen" gesetzt.

Von der Tochtergesellschaft hat Ihr Chef Herr Müller einen Datensatz der Mitarbeiter angefordert, um einen Überblick über die hinzugewonnen Mitarbeiter und deren Personaldaten zu bekommen. Er sagt Ihnen, dass die Mitarbeiter dort noch nicht vertraut mit dem kürzlich eingeführten ERP-System seien und Fehler bei den Datentypen, die im Zuge der Datenintegration wahrscheinlich passiert sind, schon aufgefallen seien. Deswegen sollen Sie sich nun mit den Personaldaten und den Datentypen beschäftigen.

`@pre_exercise_code`
```{r}
Anzahl_Mitarbeiter <- "Fabian Jung"
```

***

```yaml
type: NormalExercise
key: 9b9235a1da
xp: 50
```

`@instructions`
Schauen Sie sich bitte zuerst den Datentyp an.
- 1. Die Variable **Anzahl_Mitarbeiter** müsste natürlich ein numerischer Basisdatentyp sein. Überprüfen Sie dies bitte, da dort in letzter Zeit häufig Fehler aufgetreten sind.

`@hint`
Schreiben Sie bitte den Code so, damit als Output ein boolescher Wert (TRUE oder FALSE) ausgegeben wird! Schauen Sie in die Übersichtstabelle in der Zeile **Abfrage (Query)** nach.

`@sample_code`
```{r}
#1.Überprüfung Datentyp Anzahl_Mitarbeiter:

```

`@solution`
```{r}
#1.Überprüfung Variable Anzahl_Mitarbeiter:
is.numeric(Anzahl_Mitarbeiter)
```

`@sct`
```{r}
ex() %>% check_output(c(FALSE, "character"), fixed=TRUE, missing_msg= "Da stimmt etwas nicht. Schreiben Sie bitte den Code so, damit als Output ein boolescher Wert ausgegeben wird! Beachten Sie weiterhin die case sensitivität von R")
success_msg("Super, es ist keine numerische Variable hinterlegt, da muss bei der Datenintegration der Tochtergesellschaft etwas falsch zugewiesen worden sein!")
```

***

```yaml
type: NormalExercise
key: 35d2c7f521
xp: 50
```

`@instructions`
Da ist wohl bei der Datenintegration im System etwas mit der Zuordnung schief gelaufen.
- 2. Lassen Sie sich bitte die Variable **Anzahl_Mitarbeiter** ausgeben. Wenn nicht die Anzahl von **17** hinterlegt ist, sorgen Sie bitte dafür, dass diese Zahl ausgegeben wird. 

Klicken Sie zur Zwischenausgabe auf 'Run Code'.

`@hint`
Eine Zuweisung (<-) funktioniert mit diesem Zeichen in R. Weisen Sie der Variablen den numerischen Wert 17 zu.

`@sample_code`
```{r}
#1.numerische Variable?
is.numeric(Anzahl_Mitarbeiter)
#Den Befehl class(Anzahl_Mitarbeiter) können Sie auch verwenden. Durch ihn wird direkt der Datentyp ausgegeben.
#Ausgabe
print(Anzahl_Mitarbeiter)
#2.Zuweisung:

```

`@solution`
```{r}
#2.1 Ausgabe und ggf. neue Zuweisung
print(Anzahl_Mitarbeiter)

Anzahl_Mitarbeiter <- 17
```

`@sct`
```{r}
ex() %>% check_code(c("Anzahl_Mitarbeiter<-17", "17->Anzahl_Mitarbeiter"), fixed=TRUE, missing_msg= "Nicht richtig. Schreiben Sie bitte den Code so, damit als Output 17 ausgeben wird!")
success_msg("Super, nun ist der richtige Wert zugewiesen worden!")
```

---

## Datentypen (Q)

```yaml
type: PureMultipleChoiceExercise
key: 20bea22cf1
xp: 50
```

Sie sehen in der Personaldatenbank, dass die Büronummern der Mitarbeiter nicht einheitlich gepflegt sind. Welchen Datentyp würden Sie für die Büronummern, z.B. ```
Air2/03.077
``` 
verwenden?

- 1: einen booleschen Datentyp (logical).
- 2: eine Ganz- oder Fließkommazahl (numeric).
- 3: eine Zeichenkette (character).
- 4: eine Kategorie (fact).

_Sie können den Tipp (HINT) wählen, um eine erneute Übersicht zu bekommen._

`@hint`
Hier haben Sie noch einmal eine Übersicht mit Beispielen. 

- zu 1: Boolesche Werte: TRUE, FALSE
- zu 2: Ganzzahlen: 1; 1.5
- zu 3: Zeichenkette: "Hallo", "09:45 Uhr"
- zu 4: Kategorie: A

`@possible_answers`
- 1
- 2
- [3]
- 4

`@feedback`
- Nicht richtig, da liegen Sie völlig falsch. Boolesche Werte geben als Ausgabe nur TRUE oder FALSE Werte.
- Leider nicht richtig, es kommen Zahlen vor, jedoch nicht ausschließlich!
- Richtig - eine Zeichenkette (character) eignet sich hier als Datentyp, da sowohl Zahlen als auch Buchstaben vorkommen und bei Zeichenketten/Strings eine Zuordnung möglich ist. Sie haben schon einiges erledigt - die Hälfte haben Sie geschafft **(3/6 abgeschlossen)!** Weiter geht es nun mit **Vektoren!**
- Leider nicht richtig, überlegen Sie noch einmal! Nein es ist keine Kategorie. Korridore z.B. B könnten mit dem Datentyp fact bezeichnet werden.

---

## Vektoren

```yaml
type: TabExercise
key: 7c2138919d
xp: 100
```



`@pre_exercise_code`
```{r}

```
