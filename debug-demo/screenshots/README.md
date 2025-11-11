Opgave 1: Debugging i IntelliJ
Formål

Formålet med opgaven var at bruge IntelliJ IDEA’s debug-værktøjer til at finde og rette tre fejl i Battleship-spillet:

Skibet blev kun placeret horisontalt.

Beskeden “Ship sunk!” kom aldrig, selvom alle felter blev ramt.

Programmet kastede ArrayIndexOutOfBoundsException under visse kørseler.


Anvendte teknikker

Jeg brugte IntelliJ’s debug-funktioner:

Breakpoints for at stoppe programmet på specifikke linjer.

Step Into og Step Over for at følge, hvordan værdier ændrede sig.

Evaluate Expression til at inspicere variable (f.eks. startPoint og endPoint).

Exception Breakpoint til automatisk at fange fejlen ArrayIndexOutOfBoundsException.

Fundne fejl og løsninger

Fejl 1 – Kun horisontale skibe
Ved at følge koden i calculateEndPoint() opdagede jeg, at getRandomInteger(1) altid gav 0.
Derfor blev skibet kun placeret vandret.
Fejlen blev løst ved at sikre, at getRandomInteger() returnerede 0 eller 1 korrekt,
og derefter tilføje en metode isWithinGrid(Point p) der tjekker,
om endPoint ligger inden for brættet, før det placeres.

Fejl 2 – “Ship sunk!” blev aldrig vist
I isSunk() stod der return hitCount > BATTLESHIP_LENGTH;
Det betød, at når skibet præcist blev ramt 3 gange (samme som længden),
blev betingelsen falsk.
Det blev rettet til >=, så beskeden vises korrekt.

Fejl 3 – ArrayIndexOutOfBoundsException
Fejlen opstod, når endPoint gik uden for arrayets grænser (f.eks. y = 10).
Ved at bruge isWithinGrid() og et do-while-loop i addBattleship()
sørger programmet nu for at prøve igen, indtil både startPoint og endPoint
ligger inden for det 10x10 bræt.

Resultat

Efter ændringerne virker spillet uden fejl:

Skibet placeres både horisontalt og vertikalt.

“Ship sunk!” vises korrekt efter tre træffere.

Ingen exceptions forekommer under debug-kørsel.