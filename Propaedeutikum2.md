## Boolsche Datentypen 
Beim letzten Mal haben wir bereits zwei wichtige Datentypen in JavaScript kennengelernt: *String* und *Number*. Nun lernen wir einen weiteren kennen, den Datentyp *Boolean*. Anders als *String*, welcher aus beliebigen Zeichenketten besteht und *Numbers*, welche Zahlen in beliebiger Größe beinhalten, haben *Booleans* nur die zwei Ausprägungen `true` und `false`.  
Eine häufige Art, wie wir boolsche Werte erzeugen, ist über Abfragen mit **Vergleichsoperatoren**.

### Mathematische Vergleichsoperatoren
Vergleichsoperatoren vergleichen, wie der Name andeutet, zwei beliebige Zahlen und weist dem Ergebnis einen boolschen Wert zu. Am besten können wir dies anhand eines Beispiels erläutern:

    let x = 6;
    console.log(x >= 5); // liefert true zurück
    console.log(x < 4); // liefert false zurück

Es gibt 6 mathematische Operatoren, welche es uns erlauben, beliebige Zahlen miteinander zu vergleichen. Es muss beachtet werden, dass nur Werte vom Typ *Number* miteinander verglichen werden dürfen, da es sonst zu unerwarteten Konsequenzen kommen kann. Für unser nachfolgendes Beispiel nehmen wir `x = 5` an.

|Operator | Beschreibung             | Beispiel   |Ergebnis   |
|:-------:|--------------------------|------------|-----------|
|   `==`  | EQUALS TO                |  `x == 5`  |  `true`   |
|   `!=`  | NOT EQUALS TO            |  `x != 5`  |  `false`  |
|   `>`   | GREATER THAN             |  `x > 5`   |  `false`  |
|   `<`   | LESS THAN                |  `x < 6`   |  `true`   |
|   `>=`  | GREATER THAN OR EQUAL    |  `x >= 5`  |  `true`   |
|   `<=`  | LESS THAN OR EQUAL       |  `x <= 4`  |  `false`  |

### Logische Operatoren
Häufig wollen wir boolsche Werte miteinander verknüpfen, um kompliziertere Sachverhalte ausdrücken zu können. Dafür gibt es logische Operatoren. Wir nehmen für dieses Beispiel `x = 5` und `y = 11` an.
|Operator | Beschreibung  | Beispiel                  |Ergebnis   |
|:-------:|---------------|---------------------------|-----------|
|   `&&`  | AND           | `x >= 10 && x <= 20`      |`false`    |
|  `\|\|` | OR            | `x > 20 \|\| x == 5`      |`true`     |
|   `!`   | NOT           | `!(x >= 10 && x <= 20)`   |`true`     |

Wie bereits bei mathematischen Operatoren können wir logische Ausdrücke klammern, wenn wir wollen, dass ein Ausdruck zuerst evaluiert wird. Wenn keine Klammern gesetzt sind, so wird zuerst der **NOT** Operator, dann der **AND** Operator und zum Schluss der **OR** Operator ausgewertet.

## Datentypen und Umwandlung
Bisher haben wir mehrere Datentypen (*Number*, *String*, *Boolean*) und Operatoren gesehen. Dabei ist auffällig, dass wir teilweise die gleichen Operatoren für verschiedene Datentypen benutzen können und alle gemischt vorkommen können. Zum Beispiel können wir eine Zahl und einen String addieren oder auch mal subtrahieren.

    let zahl = 5;
    let string = "3";

    console.log(zahl + string); // Liefert 53
    console.log(zahl - string); // Liefert 2

    console.log(5 == "5") //Liefert true

Damit solche Operationen erfolgreich funktionieren können, wird in JavaScript zuvor eine Typumwandlung vollzogen. In unserem ersten Beipiel wird vor der Addition die Zahl in einen *String* umgewandelt. Da Strings miteinander verkettet werden, werden hier beide nur aneinander gereiht. In unserem zweiten Fall ergibt eine Subtraktion zwischen einer Zahl und einem String streng genommen keinen Sinn. Daher prüft JavaScript vorher, ob sich der String auch zu einer Zahl umwandeln lässt und führt die Rechnung aus. Ist dies nicht der Fall, so wäre unser Ergebnis `NaN` (= *Not a Number*). Es gibt größere und umfangreichere Umwandlungstabellen, die wir hier nicht wiedergeben werden, allerdings ist es stets wichtig, bei Vergleichen oder Operatoren zu beachten, dass wir nicht notwendigerweise den Typ einer Variable kennen. Aus diesem Grund gibt es zwei Vergleichsoperatoren, welche wir hier erwähnen wollen. 

|Operator  | Beschreibung                       | Beispiel                       |Ergebnis           |
|:--------:|------------------------------------|--------------------------------|-------------------|
|   `===`  | EQUAL VALUE AND EQUAL TYPE        |  `5 === "5"`, `"Max === "Max"` |  `false`, `true`  |
|   `!==`  | NOT EQUAL VALUE AND NOT EQUAL TYPE |  `5 !== "5"`, `"Max !== "Max"` |  `true`, `false`  |

Wichtig ist zu beachten, dass Vergleichsoperatoren auch für andere gemischte Datentypen unerwartete Ergbnisse lieferen. So ist beispielsweise der Vergleich `"12" < "3"` wahr, weil bei einem String alle Teile alphabetisch einzeln verglichen werden und die `"1"` in `"12"` kleiner als eine `"3"` ist. Wenn wir hingegen den Vergleich `"12" < 3` betrachten, so ist dieser falsch.

## Strukturierte Programmierung 
Selbstverständlich sind boolsche Werte für sich genommen wenig interessant. Aber sie sind wichtige Grundlage der sogenannten strukturierten Programmierung. Bisher haben wir die imperative Programmierung kennengelernt, welche besagt, dass Befehle Zeile für Zeile exakt vom Computer ausgeführt werden. Was ist aber, wenn wir bestimmte Befehle nur unter bestimmten Bedingungen oder sehr häufig ausführen wollen? An dieser Stelle kommt die strukturierte Programmierung ins Spiel. Sie knüpft die Ausführung von Codeblöcken an Bedingungen (in Form von boolschen Werten).

### Bedingte Ausführung
Die einfachste bedingte Anweisung is eine `if` Verzweigung. Wie das Schlüsselwort hier schon andeutet, wird der eingeschlossene Codeblock einer if-Verzweigung nur ausgeführt, falls die zugrundeliegende Bedingung `true` ist.

    let x = 7;

    // Die Bedingung ist wahr und der Code in den Klammern wird ausgeführt.
    if (x > 0) {
        console.log("x ist größer als 0")
    }

    // Die Bedingung if falsch und der Code in den Klammern wird ignoriert.
    if (x > 10) {
        console.log("x ist größer als 10")
    }
    
Das Schlüsselwort `else` können wir direkt nach einer `if`-Verzweigung verwenden und der Code im Inneren wird nur dann ausgeführt, wenn die Bedingung `false`ist.

    let x = 5;

    // Nur der else Fall wird hier ausgeführt.
    if (x == 42) {
        console.log("Die Antwort ist 42");
    } else {
        console.log("Die Antwort ist nicht 42");
    }

Sollten wir mehrere Codeblöcke haben, von denen wir wollen, dass nur einer ausgeführt wird, so gibt es das Schlüsselwort `else if`, welches es uns erlaubt, nach einer `if`-Abfrage weitere Abfragen durchzuführen. Wichtig ist zu beachten, dass alle weiteren `else if` Bedingungen ignoriert werden, falls bereits eine frühere als wahr evaluiert wurde.

    let  x = 10;
     
    if(x % 3 == 0) {
        // Wird nicht ausgeführt.
        console.log("x ist durch 3 teilbar."); 
    } else if (x % 5 == 0) {
        // Wird ausgeführt.
        console.log("x ist durch 5 teilbar."); 
    } else if (x % 2 == 0) {
        // Wird nicht ausgeführt, da die vorherige Bedingung bereits wahr war. 
        console.log("x ist durch 2 teilbar."); 
    } else {
        // Wird nur ausgeführt, wenn keine Bedingung zutrifft.
        console.log("x ist weder durch 2, 3 noch 5 teilbar.");
    }

Eine andere Form der bedingten Ausführung sind `switch` Statements in JavaScript. Von der Synthax her wird bei switch ein Ausdruck ausgewertet und mit vordefinierten Fällen abgeglichen.

    let tag = "Montag";

    switch(tag) {
        case "Montag":
            console.log("Es ist Montag");
            break;
        case "Dienstag":
            console.log("Es ist Dienstag");
            break;
        case "Mittwoch":
            console.log("Es ist Mittwoch");
            break;
        case "Donnerstag":
            console.log("Es ist Donnerstag");
            break;
        case "Freitag":
            console.log("Es ist Freitag");
            break;
        default: 
            console.log("Es ist Wochenende");
    }

Wie wir aus diesem Beispiel entnehmen können, können wir bedingte Ausführungen auch für andere Datentypen als *Number* durchführen. Wichtig ist, dass für den Vergleich der Fälle ein `===` Vergleich benutzt wird. Auch muss nach jedem `case` ein `break` gesetzt wird, da ansonsten nach dem ersten zutreffenden Fall auch alle weiteren Fälle ausgeführt werden. 

### Schleifen und Iteration
Die nächste Art von Steuerelement ist eine `for`-Schleife. Wir brauchen Schleifen oder Iteration stets, wenn wir einen Codeblock sehr häufig mit minimaler oder keiner Anpassung erneut ausführen lassen wollen. Es gibt mehrere Arten von `for` Schleifen. Wir werden hier die gängigste Variante erklären. 

    for(let i = 0; i < 10; i++) {
        console.log("Das ist das " + i + "-te Mal");
    }

Auf den ersten Blick sieht eine `for`-Schleife sehr kompliziert aus, daher gehen wir auf alle Details ein. Um eine `for`-Schleifen auszuführen, müssen wir drei Befehle angeben. Der erste Ausdruck wird nur einmal zu Beginn der Schleife ausgeführt. Der zweite Ausdruck stellt eine Bedingung dar, welche vor jeder erneuten Ausführung erneut geprüft wird. Evaluiert die übergebene Bedingung zu `false`, so wird die Schleife abgebrochen, andernfalls wird der Codeblock im Inneren ausgeführt. Die `for`-Schleife hat den Vorteil, dass wir eine eigene Variable nur für die Lebensdauer der Schleife definieren können, welche es uns erlaubt, genau zu bestimmen, in welcher Iteration wir uns befinden. Wenn wir aber einen Codeblock nur solange wiederholen wollen, wie eine bestimmte Bedingung gegeben ist, so eignet sich in diesem Fall eine `while`-Schleife besser.

    let bedingung1 = true;
    let bedingung2 = true;

    while(bedingung1 || bedingung2) {
        console.log("Eine weitere Wiederholung");
        
        if(!bedingung1) {
            bedingung2 = false;
            console.log("Zweite Bedingung ist falsch");
        }
        if(bedingung1) {
            bedingung1 = false;
            console.log("Erste Bedingung ist falsch");
        }
    }

Letztendlich kann man jede `for`-Schleife auch als `while`-Schleife schreiben und umgekehrt. Somit ist es unerheblich für welche Variante man sich entscheidet.

## Funktionen 

Eine Funktion erlaubt uns, einen Codeblock zu definieren, der erst aufgerufen wird, wenn die Funktion selbst aufgerufen wird. Von der Synthax her können wir eine Funktion in JavaScript mit dem Schlüsselwort `function` definieren. 

    function speak() {
        console.log("Ich bin eine Funktion!");
    }

    console.log("Jetzt rufen wir die Funktion auf.)
    speak();
    Console.log("Jetzt rufen wir die Funktion nochmal auf.");
    speak();

Wir können eine Funktion beliebig oft aufrufen. Wird die Funktion nicht aufgerufen, so wird alles, was im Inneren der Funktion steht, ignoriert. 
Parameter erlauben uns, einer Funktion einen Wert zu übergeben, der auf die Ausführung der Funktion Einfluss nimmt. Wenn wir einen Parameter definieren, so schreiben wir diesen einfach innerhalb der Klammern.

    function speak(message) {
        console.log("Wichtige Nachricht: " + message);
    }

    speak("Bananen sind gelb");

Wenn wir wollen, dass eine Funktion ein Ergebis zurückgibt, welches wir weiter verwenden, so müssen wir unsere Funktion dazu anweisen. Dafür gibt es ein besonderes Schlüsselwort `return`. Am besten können wir das an einem Beispiel verdeutlichen.

    function add(a, b) {
        return a + b;
    }
    let result = add(10, 15);
    console.log(result); // 25 

Nachdem wir einen Wert in einer Funktion zurückgegeben haben, können keine weiteren Befehle mehr in der Funktion angegeben werden. Wenn wir weitere Befehle nach dem `return` angeben, so wird ein *unreachable code error* geworfen.

## Lebensdauer (Scope) von Variablen 
Selbstverständlich können wir auch Variablen innerhalb einer Funktion deklarieren. Wichtig ist zu verstehen, dass diese Variablen nur innerhalb der Funktion zugänglich sind. Außerhalb von der Funktion ist eine solche Variable nicht deklariert und sie wird nach Ausführung der Funktion wieder gelöscht. Jeder Wert, den diese Variable hatte, ist danach verloren, solange bis die Funktion wieder ausgeführt wird.

    function func() {
        let a = 1;
    }

    console.log(a); // Wirft eine Fehlermeldung!

Das gilt aber nicht, falls wir in einer Funktion einer Variablen einen Wert zuweisen, ohne, dass diese vorher initialisiert wurde. JavaScript geht dann implizit davon aus, dass diese Variable außerhalb global initialisiert wurde und macht diese auch außerhalb der Funktion verfügbar.


    function func() {
        a = 1;
    }

    console.log(a); // Achtung funktioniert!

## Rekursion
Selbstvertändlich können wir in einer Funktion auch andere Funktionen aufrufen, solange diese darüber definert wurden. Überraschend ist es hingegen, dass wir eine Funktion auch in sich selbst aufrufen können. Eine solche Selbstreferenz bezeichnet man als **Rekursion**. Rekursionen sind auf den ersten Blick ein wenig verwirrend, erlauben uns aber eine schwierige Berechnung auf einen einfacheren Fall zurückzuführen. Wichtig ist bei Rekursion darauf zu achten, dass man nicht aus Versehen eine Endlosschleife auslöst und das Programm zum Absturz bringt. Am besten können wir dies an einem Beispiel verdeutlichen. Angenommen wir wollen die Fakultät `n = n*(n-1)*(n-2)*...*1` einer Zahl berechnen. So könnten wir dies mit einer rekursiven Funktion lösen.

    function fakultaet(n) {
        if(n == 0) {
            return 1
        } else {
            return n * fakultaet(n - 1);
        }
    }






