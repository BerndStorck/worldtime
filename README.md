# worldtime 

Mit dem Skript kann man schnell im Terminal die Uhrzeit für ferne Orte abfragen.

## Installation

1. Die Skriptdatei `worldtime` muss in einer der Verzeichnisse des Suchpfades liegen, der mit `echo $PATH` angezeigt werden kann.

2. Die Datendatei `timezones` muss im Verzeichnis `/usr/local/share` liegen.

## Bedienung


Das Skript kennt die Zeitzone einer kleinen Auswahl von Städten der Welt.

### Aufruf ohne Argumente

Wird das Skript ohne Argumente aufgerufen, dann zeigt es die Orte an, die es kennt, und fordert dazu auf, einen der Ortsnamen einzugeben, um danach die aktuelle Uhrzeit des eingegebenen Ortes anzuzeigen.

Bei der Eingabe eines Ortsnamens kann der Anwender Groß- und Kleinschreibung vernachlässigen. 

### Aufruf mit Ortsnamen

Alternativ kann man gleich beim Start des Skripts einen einzelnen Ortsnamen angeben.

#### Beispiele

```bash
worldtime Istanbul
```

```bash
worldtime new york
```

## Bereits definierte Orte

Das Skript kennt bisher die Zeitzonen zu den folgenden Orten:

>  "Amsterdam" "Athen" "Auckland" "Bagdad" "Beirut" "Belgrad" "Berlin"
>  "Brüssel" "Bukarest" "Chicago" "Denver" "Detroit" "Dublin" "Havanna"
>  "Hong Kong" "Istanbul" "Jerusalem" "Kiew" "Lissabon" "London" "Los
>  Angeles" "Luxemburg" "Madrid" "Melbourne" "Moskau" "New York" "Oslo"
>  "Paris" "Phoenix" "Prag" "Riga" "Rom" "Seoul" "Stockholm" "Sydney"
>  "Teheran" "Tokyo" "Wien" "Zürich"

## Anpassung - eine eigene Ortsliste erstellen

Das Programm ermittelt die Zeitzone, dessen Zeit es anzeigt, aus der Datei `/usr/local/share/timezones`. Die mitgelieferte Datei kann man leicht ergänzen oder sich eine eigene alternative Datei schreiben.

### Aufbau der Datei `timezones`

Der Anfang der mitgelieferten Datei:

```
Amsterdam:Europe/Amsterdam
Athen:Europe/Athens
Auckland:Pacific/Auckland
Bagdad:Asia/Baghdad
Beirut:Asia/Beirut
```

In dieser Datei steht in jeder Zeile ein Paar aus Schlüssel und Zeitzonenbezeichnung, die Datenfelder in jeder Zeile sind durch einen Doppelpunkt voneinander abgegrenzt: 

```
Schlüssel:Zeitzonenbezeichnung
```

Der Schlüssel ist im Standardfall ein Ortsname. Die Zeitzonenbezeichnung muss der oben beispielhaft gezeigten Art sein, beispielsweise "Europe/Helsinki" oder "Asia/Dubai".

### Arbeitsweise des Programms

Das Programm śucht in der Datei `/usr/local/share/timeszones` die Zeile, die mit dem eingegebenen Schlüssel beginnt und zeigt dann die aktuelle Uhrzeit der hinter dem Schlüssel stehenden Zeitzone an.

 ### Die Datei ergänzen

Die Datei `timezones` ist alphabetisch sortiert. Man kann sie mit einem einfachen Texteditor erweitern, indem man an der richtigen Stelle eine zusätzliche Zeile einfügt. Ist man beispielweise nach Australien verzogen und möchte die Zeitabfrage für seinen Heimatort Heidelberg verfügbar haben, dann ergänzt man die Datei:

> […]
>
> Dublin:Europe/Dublin
>
> Havanna:America/Havana
>
> **Heidelberg:Europe/Berlin**
>
> Hong Kong:Asia/Hong_Kong
>
> Istanbul:Europe/Istanbul
>
> […]

**Der Ortsname muss eindeutig sein, darf also nur einmal in der Datei vorkommen. Er darf aus einem oder maximal zwei Wörter bestehen. Der erste Buchstabe jedes der Namenswörter muss groß geschrieben werden.** 

### Eine individuelle Datei erstellen

Da das Programm freilich nicht weiß, was ein Schlüssel bedeutet, muss der Schlüssel kein Ortsname sein. Das eröffnet die Möglichkeit, sich eine individuelle Datei `timeszones` mit den Namen von Familienangehörigen oder anderen Kontakten und der Zeitzone anzulegen, in der sie wohnen oder arbeiten.

> […]
>
> David:Asia/Jerusalem
>
> Mam:Europe/Berlin
>
> Onkel Robert:Australia/Sydney
>
> […]
### Zeitzonenlisten
Um eine Erweiterung der Datei `timezones` oder die Erstellung einer indviduellen Datei zu erleichtern, habe ich zwei Listen angefertigt.

| Datei          | Inhalt                                                       |
| -------------- | ------------------------------------------------------------ |
| long_by_town   | Eine lange alphabetisch nach Städtenamen sortierte Liste, die englische Städtenamen ihrer Zeitzone zuordnet. |
| long_by_region | Einen lange alphabetisch nach der Region sortiere Liste, die englische Städtenamen ihrer Zeitzone zuordnet. |

## Programmautor

Bernd Storck, https://www.facebook.com/BStLinux