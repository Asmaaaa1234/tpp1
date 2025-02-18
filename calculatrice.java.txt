import java.util.Scanner;

class Calculatrice {
    // Méthode d'addition
    public double addition(double a, double b) {
        return a + b;
    }

    // Méthode de soustraction
    public double soustraction(double a, double b) {
        return a - b;
    }

    // Méthode de multiplication
    public double multiplication(double a, double b) {
        return a * b;
    }

    // Méthode de division avec gestion de l'erreur de division par zéro
    public double division(double a, double b) {
        if (b == 0) {
            System.out.println("Erreur : Division par zéro !");
            return Double.NaN; // Renvoie NaN pour indiquer une erreur
        }
        return a / b;
    }
}

public class Test {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Calculatrice calc = new Calculatrice();

        while (true) { // Boucle infinie pour permettre plusieurs calculs
            System.out.println("\nChoisissez une opération :");
            System.out.println("1. Addition");
            System.out.println("2. Soustraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Quitter");
            System.out.print("Votre choix : ");
            
            int choix = scanner.nextInt();
            
            if (choix == 5) { // Quitter le programme
                System.out.println("Au revoir !");
                break;
            }

            // Demander les nombres à l'utilisateur
            System.out.print("Entrez le premier nombre : ");
            double num1 = scanner.nextDouble();
            System.out.print("Entrez le deuxième nombre : ");
            double num2 = scanner.nextDouble();
            double resultat = 0;

            // Exécuter l'opération choisie
            switch (choix) {
                case 1:
                    resultat = calc.addition(num1, num2);
                    break;
                case 2:
                    resultat = calc.soustraction(num1, num2);
                    break;
                case 3:
                    resultat = calc.multiplication(num1, num2);
                    break;
                case 4:
                    resultat = calc.division(num1, num2);
                    break;
                default:
                    System.out.println("Choix invalide. Veuillez essayer encore.");
                    continue; // Reprendre la boucle
            }

            System.out.println("Résultat : " + resultat);
        }
        
        scanner.close(); // Fermer le scanner
    }
}
