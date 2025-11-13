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




In the first assignment ( getting ships to also be vertical) I learned to set up a breakpoint, I debugged, and then used "step into" and "step over" and even in the end "step out". I also learned to use the "evaluate expression button" even though it was another place in my version than what the video showed. I also learned to remove a breakpoint and then run the program again to see if it worked. Which it did. I am sure I am going to use all of them from now on, but is especially happy to have learned about the "evaluate expression button" since that is so useful.

In the second assignment it was a bit shorter. Here I used running the program a lot. Other than that I used Step into and step over a few times. All stuff I will be using forward.

In the third I learned about where to find "View breakpoint" and how to use the "java Exception Breakpoints", both really useful when I program.
