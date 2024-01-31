//Number Guessing Game




        import java.util.Random;
        import java.util.Scanner;

    public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        System.out.println("Guess the number!!");
	System.out.println("Your score will be calculated in 3 rounds");
        int rounds = 0;
        int totalScore = 0;

        while (rounds < 3) {
	    int secretNumber = random.nextInt(100) + 1;
            int attempts = 0;
            System.out.println("Round " + (rounds + 1));
            while (true) {
                int guess;
                try {
                    System.out.print("Enter your guess: ");
                    guess = scanner.nextInt();
                } catch (Exception e) {
                    System.out.println("Invalid input. Please enter a valid number.");
                    scanner.next();
                    continue;
                }   
                attempts++;

                if (guess == secretNumber) {
                    System.out.println("Congratulations! You guessed the correct number " + secretNumber +
                            " in " + attempts + " attempts.");
                    totalScore += 10 - attempts;
                    break;
                } else if (guess < 1 || guess > 100) {
                    System.out.println("Enter the number within the range");
                } else if (guess < secretNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }

            rounds++;
        }

        System.out.println("Game over! Your total score is: " + totalScore);
    }}
