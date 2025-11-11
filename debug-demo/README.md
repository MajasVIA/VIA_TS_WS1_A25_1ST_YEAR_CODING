[![CI](https://github.com/tkgregory/debug-demo/actions/workflows/ci.yml/badge.svg)](https://github.com/tkgregory/debug-demo/actions/workflows/ci.yml)

Battleship game to demonstrate debugging.

Check out the YouTube video for full details. 👇<br/>
[<img src="YouTube thumbail.png" width="500"/>](https://youtu.be/IeUZZoZE3sU)

## How to play

Run the `main` method inside [BattleshipGame](src/main/java/com/tomgregory/BattleshipGame.java) to initiate these steps:

1. Setup a square board with one battleship
2. Create a player
3. Play the game until the ship is sunk or player runs out of turns

The battleship location is revealed at the end.

## Bugs to find

Use IntelliJ IDEA debug to solve these issues:

1. Why does the board only add horizontal but not vertical battleships?
2. Why do we never get message _Ship sunk!_ when log output shows 3 direct hits?
3. Why do we sometimes see `java.lang.ArrayIndexOutOfBoundsException`?

---

## My Debugging Notes

in assignment 1, where I had to figure out why there were only horisontal ships, I used
breakpoints and the step over method to do the tasks.
I used a breakpoint in return switch to see how the method CalculateEndPoint was called.
during debugging
I found out that the max value only were 1, which was why there were only horisontal ships.
I then corrected it, by changing the code in getRandomInteger from maxValue to maxvalue +1.
then I tested again and this time there were both horisontal ships and vertical ships.

in assignment 2, where I had to figure out why it didnt showed "ship sunk" I looked where
the code "ship sunk" by pressing ctrl + shift + F, so I could search for the phrase in the code
Where called. I found that in BattleShipGame.java, and realised that the method isSunk never
returned true, because it said "return hitCount > BATTLESHIP_LENGHT;" since the ship is 3
cells long, this meant that it says ""everytime it is hit 3 times > battleship lenght 3 cells".
which meant it actually said 3>3 in this scenario. so I corrected it with a >= instead. so now
it said "everytime it is hit 3 times >= battleship lenght 3 cells. Then I tested it and now it
showed "ship sunk"

in assignment 3, I used Java Expection Breakpoints to catch an error automatically.
I used "run" and found "view breakpoints" pushed + and choosed "java Exception Breakpoints.
then I put in the exception i was looking for. I made sure that all of the Enabled, Suspend,
all, caught exception, and uncaught exception had a cross. then I debugged, and in
addBattleship I noticed the variable y was 10. and arrays goes
from 0 to 9, so 10 was out of the arrays area. I then changed the loop and now the program
worked and there was no error.
