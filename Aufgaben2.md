# Aufgaben

1. Initialisiere eine Variable für eine beliebige Zahl. Prüfe anschließend, ob die Zahl eine durch 2 teilbare Zahl zwischen 0 und 100 ist, welche nicht 42 sein soll.

2. Initialisiere eine Variable für eine beliebige Jahreszahl. Prüfe anschließend, ob es sich bei dem Jahr um ein Schaltjahr handelt. Ein Jahr ist ein Schaltjahr genau dann, wenn:
    * Ein Jahr, welches durch 4 teilbar ist, ist ein Schaltjahr. Außer Punkt zwei ist erfüllt.
    * Ein Jahr, welches durch 100 teilbar ist, ist kein Schaltjahr. Außer Punkt drei ist erfüllt.
    * Ein Jahr, welches durch 400 teilbar ist, ist ein Schaltjahr.
    
    Gibt das Ergebnis der Prüfung auf die Konsole aus und prüfe, ob die Jahre 1984, 2017, 2000 und 1900 Schaltjahre sind. Das Ergebnis sollte `true`, `false`, `true`, `false` sein.

3. Bestätige das Ergebnis folgender Reihen und Produkte approximativ:

        1.) log(2) = 1 - 1/2 + 1/3 - 1/4 + 1/5 - 1/6 + ...      (Logarithmus-Reihe)
    
        2.) pi/4 = 1 - 1/3 + 1/5 - 1/7 + 1/9 - 1/11 + ...     (Leibniz-Reihe)

        3.) (pi^2)/6 = 1 + 1/4 + 1/9 + 1/16 + 1/25 + 1/36 + ...    (Euler-Reihe)

    Addiere jeweils 1.000.000 Terme aufeinander und vergleiche die Erbenisse mit den echten Werten. Wir können den Wert von pi über `Math.PI` in die Konsole ausgeben. Für den Logarithmus zur Basis *e* verwenden wir die Funktion `Math.log()`. 

4. Berechne die ersten 5 Nachkommastellen von pi mit dem sogenannten Wallis-Produkt

        pi/2 = (2/1)*(2/3)*(4/3)(4/5)*(6/5)*(6/7)*(8/7)*(8/9) ...     (Wallis-Produkt)

    Benutze dafür eine `while`-Schleife und definiere eine geeignete Abbruchbedingung.
