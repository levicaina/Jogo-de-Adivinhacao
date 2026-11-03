# Jogo-de-Adivinhacao   [ProjetoJava02.java](https://github.com/user-attachments/files/34297199/ProjetoJava02.java)
package academy.devdojo.maratonajava.aula;

import java.util.Scanner;

public class ProjetoJava02 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int numeroSecreto = (int) (Math.random() * 100) + 1;
        int resposta;
        boolean venceu = false;
        for (int i = 1; i < 11; i++) {
            while (true) {
                System.out.println("Escolha um número de 1 a 100 ");
                resposta = scanner.nextInt();
                if (resposta >= 1 && resposta <= 100) {
                    break;
                }
                System.out.println("Erro número invalido! Digite um número de 1 a 100");
            }
            if (resposta == numeroSecreto) {
                venceu = true;
                switch (i) {
                    case 1:
                    case 2:
                    case 3:
                        System.out.println("Você acertou o número supresa com exatamente " + i + " tentativas você é um Mestre Advinhador");
                        break;
                    case 4:
                    case 5:
                    case 6:
                        System.out.println("Você acertou o número supresa com exatamente " + i + " tentativas você é um Bom Jogador");
                        break;
                    case 7:
                    case 8:
                    case 9:
                    case 10:
                        System.out.println("Você acertou o número supresa com exatamente " + i + " tentativas você é um Sortudo ");
                        break;
                }
                break;
            }
            System.out.println();
            if (resposta > numeroSecreto) {
                System.out.println(i + ". tentativa : Número Errado! O número supresa é menor do que " + resposta);
            } else {
                System.out.println(i + ". tentativa : Número Errado! O número supresa é maior do que " + resposta);
            }
        }
        if (!venceu) {
            System.out.println("IHHHH Você perdeu!");
        }
    }
}
