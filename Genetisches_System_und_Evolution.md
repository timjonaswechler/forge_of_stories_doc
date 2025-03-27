# Genetisches System und Evolution

## Einleitung

In diesem Dokument wird die Idee eines Gensystems anstelle eines Rassensystems vorgestellt und dessen Umsetzung genauer betrachtet.

In Spielen und Büchern des Fantasy-Genres existieren üblicherweise klar definierte Rassen wie Zwerge, Menschen, Elfen usw. Für Mischlinge gibt es meist nur begrenzte Möglichkeiten wie "Halb-Elf" oder "Halb-Ork". An genau diesem Punkt setzt unsere Innovation an: Statt dieser künstlichen Trennung entwickeln wir ein realistisches Gensystem, das wie in der Natur eine vollständige Vermischung zwischen allen Spezies erlaubt und nach wissenschaftlichen Prinzipien aus zwei Genpools einen neuen erzeugt.

Dieser Ansatz ermöglicht nicht nur, dass Zwerge und Orks oder Elfen und Menschen Nachkommen zeugen können, sondern schafft auch die Grundlage für wahrhaft emergente Geschichten. Wenn ein Dorf mit einzigartigen genetischen Merkmalen besondere Fähigkeiten entwickelt, könnte es zum Ziel von Konflikten werden. Wenn ein Kind mit ungewöhnlichen genetischen Eigenschaften geboren wird, könnte dies zu sozialen Spannungen oder neuen kulturellen Entwicklungen führen – all das ohne vordefinierte Handlungsstränge.

Das Ziel dieses Systems ist es, Diversität und Inklusion zu fördern und gleichzeitig die oft unreflektierte Vormachtstellung der menschlichen Rasse im Fantasy-Genre zu hinterfragen.

## 1. Grundprinzipien des genetischen Systems

Das genetische System in "Forge of Stories" basiert auf einer vereinfachten, aber realistischen Interpretation der Vererbungslehre. Im Gegensatz zu traditionellen Fantasy-Settings mit starren Rassenkonzepten und limitierten Hybridmöglichkeiten ermöglicht unser System eine vollständige genetische Durchmischung aller intelligenten Spezies.

### 1.1 Vererbungsmechanismen

Die Genetik folgt primär dem Mendel'schen Prinzip mit:

- **Dominanten und rezessiven Genen**: Bestimmte Merkmale können andere überlagern
- **Diskrete Vererbung**: Die meisten Eigenschaften werden als eigenständige Gene weitergegeben
- **Kontinuierliche Spektren**: Für bestimmte Eigenschaften wie Hautfarbe oder Körpergröße existieren fließende Übergänge    

Bei der kontinuierlichen Vererbung, beispielsweise der Hautfarbe:

1. Die Farben beider Eltern werden in einem zweidimensionalen Farbraum repräsentiert
2. Ein definierter Varianzbereich um diese Werte erlaubt kleine Mutationen
3. Zufällige Werte zwischen 0 und 1 bestimmen die Position im Farbraum, die vererbt wird

### 1.2 Zukünftige Erweiterungen

In späteren Entwicklungsphasen könnte das System um folgende Aspekte erweitert werden:

- **Epigenetik**: Umwelteinflüsse könnten die Genexpression beeinflussen

- Mutaiton: 
	- **Strukturelle Mutationen**: Zusätzliche oder fehlende Körperteile (z.B. ein sechster Finger, fehlende Zähne)
    - **Funktionale Mutationen**: Veränderte Funktionsweise von Organen (z.B. verbesserte Sehfähigkeit, veränderte Stoffwechselprozesse)
    - **Entwicklungsmutationen**: Veränderungen im Wachstum oder in der Entwicklung des Individuums

- **Komplexere Geninteraktionen**: Mehrere Gene könnten zusammenwirken, um ein einziges Merkmal zu bestimmen

## 2. Chromosomen und Gene

Während traditionelle Fantasy-Systeme mit vorgefertigten "Rassentabellen" arbeiten, definiert unser System die Individuen durch ihre spezifischen genetischen Merkmale, die in Chromosomen organisiert sind.

### 2.1 Chromosomen-Struktur

In "Forge of Stories" wird jedes Lebewesen durch mehrere spezialisierte Chromosomen definiert:

- **Körperbau-Chromosom**: Speichert die physische Struktur des Körpers entsprechend der hierarchischen Baumstruktur:
    
    ```
    Becken
    ├── Hals
    │   └── Kopf
    │       ├── Mund (Zähne 1-32, Zunge)
    │       ├── Augen (Augenlider, Iris, Netzhaut)
    │       └── Ohren (Trommelfell)
    ├── Bauch (Magen, Darm, Leber, Nieren)
    ├── Brustkorb
    │   ├── Lunge
    │   ├── Herz
    │   ├── Schulter_L
    │   │   └── Oberarm_L → Unterarm_L → Hand_L (5 Finger)
    │   └── Schulter_R
    │       └── Oberarm_R → Unterarm_R → Hand_R (5 Finger)
    ├── Oberschenkel_R → Unterschenkel_R → Fuß_R (5 Zehen)
    └── Oberschenkel_L → Unterschenkel_L → Fuß_L (5 Zehen)
    ```
    
- **Attribute-Chromosom**: Enthält Gene für die grundlegenden Charaktereigenschaften
    
    - **Physische Eigenschaften**: Stärke, Ausdauer, Beweglichkeit, etc.
    - **Mentale Eigenschaften**: Intelligenz, Kreativität, Willenskraft, etc.
    - **Soziale Eigenschaften**: Empathie, Führungsqualität, Charisma, etc.
- **Persönlichkeits-Chromosom**: Enthält Gene für Verhaltensneigungen und Temperament
    
- Weitere Chromosomen können für andere Aspekte hinzugefügt werden
### 2.2 Gene

Jedes Chromosom enthält verschiedene Gene:

```
Gen {
    id: String,            // Eindeutiger Identifikator
    name: String,          // Beschreibender Name
    value: f32,            // Wert zwischen 0.0 und 1.0
    expression: Expression // Dominant, Rezessiv oder Kodominant
}
```

Der Gen-Wert (0.0 - 1.0) entspricht direkt dem Startwert für die entsprechende Eigenschaft des Charakters und wird bei der Geburt festgelegt.
### 2.3 Beispiel für Gene in einem Attribute-Chromosom

```
Attribute-Chromosom:
  Physische Eigenschaften:
    - Stärke: {value: 0.45, expression: Kodominant}
    - Ausdauer: {value: 0.50, expression: Kodominant}
    - Beweglichkeit: {value: 0.48, expression: Rezessiv}
  Mentale Eigenschaften:
    - Intelligenz: {value: 0.55, expression: Kodominant}
    - Kreativität: {value: 0.60, expression: Dominant}
    - Willenskraft: {value: 0.49, expression: Kodominant}
  Soziale Eigenschaften:
    - Empathie: {value: 0.62, expression: Kodominant}
    - Charisma: {value: 0.53, expression: Rezessiv}
```

Die Werte dieser Gene dienen als Ausgangsbasis für die Charakterattribute. Sie können sich im Laufe der Zeit leicht nach oben oder unten verändern (im Rahmen der Epigenetik, die in späteren Versionen implementiert wird).


### 2.4 Initiale Genpools der Hauptspezies

Zu Beginn der Simulation existieren vordefinierte Genpools, die den klassischen Fantasy-Archetypen entsprechen. Diese dienen als Ausgangspunkt für die evolutionäre Entwicklung und genetische Vermischung.

### 2.5 Flexible genetische Durchmischung

Eine Kernkomponente des Systems ist die vollständige genetische Kompatibilität zwischen allen intelligenten Spezies. Es gibt keine biologischen Barrieren für Reproduktion - nur kulturelle und soziale Faktoren können die Vermischung von Genpools einschränken.

Nach Beginn der Simulation werden sich die ursprünglichen Genpools zunehmend vermischen, was zu einzigartigen Individuen führt. Das System protokolliert nicht den "Rassenanteil" (z.B. "Halb-Elf"), sondern speichert ausschließlich die tatsächlichen genetischen Merkmale.

Mit der Zeit können sich aus diesen Vermischungen neue kulturelle Identitäten und soziale Gruppen entwickeln, die ihre eigene genetische Identität entwickeln.


