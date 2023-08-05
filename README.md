import java.util.Scanner;
import java.util.Random;

public class RockPaperScissorGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        String[] choices = {"rock", "paper", "scissor"};
        String playAgain;

        do {
            System.out.println("WELCOME TO ROCK PAPER SCISSORS GAME!.");
            String userChoice = scanner.nextLine().toLowerCase();
            int computerChoiceIndex = random.nextInt(3);
            String computerChoice = choices[computerChoiceIndex];
            System.out.println("Computer chose: " + computerChoice);

            if (userChoice.equals(computerChoice)) {
                System.out.println("IT'S A TIE");
            } else if ((userChoice.equals("rock") && computerChoice.equals("scissors"))
                    || (userChoice.equals("paper") && computerChoice.equals("rock"))
                    || (userChoice.equals("scissor") && computerChoice.equals("paper"))) {
                System.out.println("CONGRATULATIONS! YOU WON");
            } else {
                System.out.println("COMPUTER WON! BETTER LUCK NEXT TIME");
            }

            System.out.println("Do you want to play again? (yes/no)");
            playAgain = scanner.nextLine().toLowerCase();
        } while (playAgain.equals("yes"));

        System.out.println("Thanks for playing! Goodbye.");
        scanner.close();
    }
}
