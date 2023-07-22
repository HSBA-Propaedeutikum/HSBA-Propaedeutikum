# JavaScript 

## JavaScript läuft im Browser
JavaScript ist eine Skriptsprache, welche entwickelt wurde, um die Darstellung von Inhalten und Möglichkeiten für die Benutzerinterkation mit Webinhalten zu verbessern. Daher ist es wenig überaschend, dass JavaScript vorrangig im Webbrowser ausgeführt wird. Jede Website besteht auf unterster Ebene aus HTML (Hypertext Markup) Elementen, welche die prinzipielle Anordnung aller Elemente einer Website beschreibt. Diese Elemente sind wie in einem Baumdiagramm angeordnet angeordnet. Jede HTML Website besteht aus einem `head` Element und einem `body` Element. 

	<!DOCTYPE html>
	<html>
	<head>
	  <meta charset="UTF-8">
	  <title>Meine erste Website</title>
	</head>
	<body>
	  Hier ist irgendein Text!
	</body>
	</html>
	
Jede Website besteht aus verschachtelten und mitunter sehr komplizierten Kombinationen solcher HTML Tags. Wir können uns jede beliebige Website in dieser "rohen" Form anzeigen lassen, indem wir im Browser über die `F12` Taste die Developer Tools aufrufen. Um unser erstes HTML Dokument im Browser aufrufen zu können, müssen wir den obigen Code-Abschnitt in ein eigenes HTML File speichern und dann lokal im Browser ausführen. Wir schreiben nun unser erstes JavaScript Programm innerhalb dieses HTML Dokuments. Dazu fügen wir innerhalb der `body` Sektion einen `script` Tag wie folgt ein:

	<!DOCTYPE html>
	<html>
	<head>
	  <meta charset="UTF-8">
	  <title>Meine erste Website</title>
	</head>
	<body>
	  <script>
	  	console.log("Hallo Welt!"); //Hallo Welt 
	  </script>
	</body>
	</html>
	
Wenn wir nun in den Developer Tools die Konsole aufrufen, dann können wir dort unsere Textausgabe sehen. Mit Hilfe des `window.alert("Hallo Welt!");` Befehls könnten wir uns den Text auch direkt in einem Pop-up-Fenster anzeigen lassen. Gratulation, wir haben unser erstes JavaScript Programm geschrieben! Wir müssen unseren JavaScript Code nicht zwingend innerhalb des HTML Files angeben, sondern können auch ein externes Skript verlinken. Dazu erstellt man im gleichen Ordner, in dem auch die *index.html* liegt, eine neue JabaScript Datei (beispielsweise *App.js*) und gibt den Pfad innerhalb des `<script src="App.js"></script>` an. Von nun an verweisen wir ausschließlich auf ein solches externes Skript, um uns den HTML Boilerplate zu sparen. 

## Variablen in JavaScript und Imperative Programmierung
Eine imperative Programmiersprache führt Befehle Zeile für Zeile aus. Ein Befehl wird in JavaScript mit einem Semikolon beendet. Sollte ein Semikolon am Ende einer Zeile fehlen, so wird intern angenommen, dass eins gesetzt wurde. Dennoch ist es guter Programmierstil, stets ein Semikolon am Ende einer Zeile zu setzen.  
Eines der wichtigsten Programmierprinzipien sind Variablen. Es gibt mehrere Möglichkeiten, eine Variable in JavaScript zu definieren. Im Folgendem gehen wir auf einige Varianten ein und erklären kurz die wichtigsten Unterschiede. Eine Variable können wir uns am besten als eine beschriftete Box vorstellen, welche beliebige Daten speichert, um später darauf zurückgreifen zu können. Nehmen wir zum Beispiel an, dass wir den Namen einer Person in einer Variable speichern wollen. Dafür nutzen wir die Synthax `let name = "Bob"`. Zuerst gehen wir auf `let` ein. Dieses ist ein **Schlüsselwort**, welches JavaScript mitteilt, dass wir eine Variable deklarieren wollen. Schlüsselwörter werden später noch sehr relevant sein und dürfen nur in ihrem jeweiligen Kontext verwendet werden. Nach dem `let` vergeben wir einen **Identifier** für die Variable. In unserem Fall ist dies `name`. Das ist der Name, den wir auf unsere Box schreiben. Wir können nahezu beliebige Identifier vergeben, allerdings gibt es einige Regeln zu beachten. Es wird zwischen Groß- und Kleinschreibung unterschieden und ein Identifier darf nicht mit einer Zahl beginnen. Das Gleichheitszeichen nach dem Identifier ist anders als in der Mathematik. Es ist nicht als eine Aussage zu verstehen, sondern weist den Computer an, der deklarierten Variable den Wert hinter dem Gleichheitszeichen zuzuordnen. Das Gleichheitszeichen ist ein **Operator** in JavaScript.  
Wir können nun auf diese Variable ganz einfach zugreifen in dem wir an geeigneten Stellen einfach den Identifier benutzen.

	let name = "Bob";
	console.log("Hallo " + name); //Hallo Bob

Erwähnenswert ist, dass wir in unserem letzten Codebeispiel einen weiteren Operator, den `+` Operator benutzt haben. Dieser hat je nach Kontext eine verschiedene Wirkunsgweise. Wenn eine Variable einmal deklariert ist, so kann ihr auch später ein anderer Wert zugeschrieben werden. Dazu weisen wir ihr einfach mit dem Zuweisungsoperator einen neuen Wert zu. 

	let name = "Bob";
	console.log("Hallo " + name); //Hallo Bob
	name = "Frank";
	console.log("Hallo " + name); //Hallo Frank

Wichtig ist, dass bei einer erneuten Zuweiseung das Schlüsselwort `let`nicht erneut aufgerufen werden darf, da die Variable `name` bereits initialisiert worden ist. Es ist auch möglich, die Initialisierung und Zuweisung von Variablen vollständig zu trennen. So ist 

	let name;
	name = "Bob";
	console.log("Hallo " + name); //Hallo Bob
 
 vollkommen äquivalent zu unserem ersten Beispiel. Es gibt noch zwei weitere Beipspiele für eine Variablendeklaration, welche der Vollständigkeit halber erwähnt werden sollten. Statt mit dem Schlüsselwort `let` können wir eine Variable auch mit `const` und `var` initialisieren. Da `var` mittlerweile veraltet ist und einige Nebeneffekte hat, sollte diese Art nicht mehr verwendet werden. Dahingegen ist `const` noch gebräuchlich und wird verwendet. Der Unterschied zu `let` ist, dass eine mit `const` zugewiesene Variable nicht wieder zugewiesen werden darf. Sie ist konstant mit einem Wert belegt. Anders als eine mit `let` initialisierte Variable, muss eine Konstante auch direkt mit einem Wert belegt werden. 
 
	const name = "Bob";
	name = "Frank" // Stürzt mit einem TypeError "Assignment to constant variable." ab. 

## Mathematische Operatoren
Bisher haben wir in Variablen nur Text (sogennante *Strings*) gespeichert. Natürlich können wir aber auch Zahlen *Numbers* in Variablen speichern und mit Zahlen rechnen. Um mit Zahlen rechnen zu können, brauchen wir Operatoren. Es gibt 8 mathematische Operatoren in JavaScript. 

|Operator | Beschreibung             | Beispiel                                                      |
|:-------:|--------------------------|---------------------------------------------------------------|
|   `+`   | Addition                 | `let result = 8 + 3; //result ist 11`                         |
|   `-`   | Subtrakion               | `let result = 5 - 11; //result ist -6`                        |
|   `*`   | Multiplikation           | `let result = 7 * 8; //result ist 42`                         |
|   `**`  | Exponentiation           | `let result = 2 ** 8; //result ist 254`                       |
|   `/`   | Division                 | `let result = 2 / 4; //result ist 0.5`                        |
|   `%`   | Modulo                   | `let result = 24 % 7; //result ist 3`                         |
|   `++`  | Inkrement                | <code>let result = 5; </br> result++; //result ist 6</code>   |
|   `--`  | Dekrement                | <code>let result = 5; </br> result--; //result ist 4</code>   |

Selbstverständlich können wir auch Klammern setzen, wenn wir wollen, dass eine Berechnung mit Vorrang ausgeführt wird. 
	
	let firstResult = (2 + 7) * 9; // firstResult ist 81
	let secondResult = 2 + 7 * 9 // secondResult ist 65

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









