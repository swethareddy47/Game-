# Game-
import java.util.Scanner;

public class TextAdventureGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        startGame(scanner);
        scanner.close();
    }

    public static void startGame(Scanner scanner) {
        System.out.println("Welcome to the Text Adventure Game!");
        System.out.println("You wake up in a mysterious forest...");

        // Begin the game
        exploreForest(scanner);
    }

    public static void exploreForest(Scanner scanner) {
        System.out.println("\nYou're standing at a crossroads. Do you go 'left' or 'right'?");
        String decision = scanner.nextLine().toLowerCase();

        switch (decision) {
            case "left":
                goLeft(scanner);
                break;
            case "right":
                goRight(scanner);
                break;
            default:
                System.out.println("Invalid input. Please enter 'left' or 'right'.");
                exploreForest(scanner);
                break;
        }
    }

    public static void goLeft(Scanner scanner) {
        System.out.println("\nYou chose to go left and found a hidden cave.");
        System.out.println("Do you 'enter' the cave or 'continue' on your path?");
        String decision = scanner.nextLine().toLowerCase();

        switch (decision) {
            case "enter":
                enterCave(scanner);
                break;
            case "continue":
                continuePath(scanner);
                break;
            default:
                System.out.println("Invalid input. Please enter 'enter' or 'continue'.");
                goLeft(scanner);
                break;
        }
    }

    public static void goRight(Scanner scanner) {
        System.out.println("\nYou chose to go right and stumbled upon an abandoned house.");
        System.out.println("Do you 'explore' the house or 'ignore' it?");
        String decision = scanner.nextLine().toLowerCase();

        switch (decision) {
            case "explore":
                exploreHouse(scanner);
                break;
            case "ignore":
                ignoreHouse(scanner);
                break;
            default:
                System.out.println("Invalid input. Please enter 'explore' or 'ignore'.");
                goRight(scanner);
                break;
        }
    }

    public static void enterCave(Scanner scanner) {
        System.out.println("\nInside the cave, you found a treasure chest!");
        System.out.println("Congratulations! You've won the game.");
    }

    public static void continuePath(Scanner scanner) {
        System.out.println("\nYou continued on the path and encountered a group of friendly travelers.");
        System.out.println("You join them on their journey.");
        System.out.println("The game ends here.");
    }

    public static void exploreHouse(Scanner scanner) {
        System.out.println("\nAs you explore the house, you discover a valuable artifact.");
        System.out.println("Congratulations! You've won the game.");
    }

    public static void ignoreHouse(Scanner scanner) {
        System.out.println("\nYou decided to ignore the house and keep moving forward.");
        System.out.println("The game ends here.");
    }
}
