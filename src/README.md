Number Guessing Game

A simple console-based number guessing game implemented in Java. The game generates a random number between 1 and 100, and the player must guess the number within a limited number of attempts.

Features

-Game Setup: Create a Java program that generates a random number between a specified range.
-User Input: Prompt the player to guess the number and provide feedback if it's too high or too low.
-Limited Attempts: Allow a limited number of guesses to make the game challenging.
-Win Condition: Inform the player upon successful guessing.
-Replay Option: Give the player a chance to play again for added engagement.

Code Overview

NumberGuessingGame.java
This Java program implements the number guessing game. Below is a detailed explanation of the code:

1. Import Statements

import java.util.Scanner;
import java.lang.Math;
import java.util.Scanner;: Imports the Scanner class used for reading user input from the console.
import java.lang.Math;: Imports the Math class, which provides methods for mathematical operations like generating random numbers.

2. Main Method

public class NumberGuess {
  public static void main(String[] args) {
    int secretNumber = (int)(Math.random() * 100) + 1;
    int remainingAttempts = 5;
    Scanner userInput = new Scanner(System.in);
    boolean isGuessed = false;
    System.out.println("I'm thinking of a number between 1 and 100.");
    System.out.println("You have 5 attempts to guess the number.");
int secretNumber = (int)(Math.random() * 100) + 1; 
Generates a random number between 1 and 100. Math.random() produces a floating-point number between 0.0 and 1.0. 
Multiplying by 100 scales it up, and (int) truncates the decimal part to get an integer. 
Adding 1 ensures the number falls within the range 1 to 100.
int remainingAttempts = 5;: Initializes the number of attempts the player has to guess the number.
Scanner userInput = new Scanner(System.in);: Creates a Scanner object for reading user input from the console.
boolean isGuessed = false;: A flag to track if the number has been guessed correctly.

3. Game Loop

    while (remainingAttempts > 0) {
      System.out.println("Enter your guess: ");
      int userGuess = userInput.nextInt();
      if (userGuess == secretNumber) {
        System.out.println("Congratulations! You've guessed the number. You win!");
        isGuessed = true;
        break;
      } else if (userGuess > secretNumber) {
        System.out.println("Your guess is too high. You have " + (remainingAttempts - 1) + " attempts left.");
      } else {
        System.out.println("Your guess is too low. You have " + (remainingAttempts - 1) + " attempts left.");
      }
      remainingAttempts--;
    }
while (remainingAttempts > 0): The game continues running as long as the player has remaining attempts.
int userGuess = userInput.nextInt();: Reads the player's guess from the console.
if (userGuess == secretNumber): Checks if the player's guess matches the secret number. 
If true, prints a winning message and sets isGuessed to true.
else if (userGuess > secretNumber): Provides feedback if the guess is too high.
else: Provides feedback if the guess is too low.
remainingAttempts--: Decreases the number of remaining attempts by one after each guess.

4. Game End

    if (!isGuessed) {
      System.out.println("You've run out of attempts. You lose!");
    }
  }
}
if (!isGuessed): 
Checks if the number was not guessed correctly after all attempts. If true, prints a losing message.