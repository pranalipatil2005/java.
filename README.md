# java.
import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
   boolean playAgain = true;
  while (playAgain) {
       int numberToGuess = random.nextInt(100) + 1; 
            int attempts = 0;
            boolean hasGuessedCorrectly = false;

   System.out.println("Welcome to the Number Guessing Game!");
            System.out.println("I have chosen a number between 1 and 100. Try to guess it!");

   while (!hasGuessedCorrectly) {
                System.out.print("Enter your guess: ");
                int userGuess = scanner.nextInt();
                attempts++;

  if (userGuess < numberToGuess) {
                    System.out.println("Too low! Try again.");
                } else if (userGuess > numberToGuess) {
                    System.out.println("Too high! Try again.");
                } else {
                    System.out.println("Congratulations! You guessed the number in " + attempts + " attempts.");
                    hasGuessedCorrectly = true;
                }
            }

   System.out.print("Do you want to play again? (yes/no): ");
            String response = scanner.next().toLowerCase();
            playAgain = response.equals("yes");
        }

  System.out.println("Thanks for playing! Goodbye.");
        scanner.close();
    }
}
