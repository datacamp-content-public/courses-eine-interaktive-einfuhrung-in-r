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
