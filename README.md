# Avalia-o-1

import java.util.Scanner;

public class SistemaEscolar {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double[] notas = new double[8];

        // Entrada das 8 notas
        System.out.println("=== SISTEMA ESCOLAR ===");
        for (int i = 0; i < 8; i++) {
            System.out.print("Digite a nota " + (i + 1) + ": ");
            notas[i] = input.nextDouble();
        }

        // Cálculo das médias trimestrais (2 notas por trimestre)
        double[] mediasTrimestres = new double[4];
        for (int i = 0; i < 4; i++) {
            mediasTrimestres[i] = (notas[i * 2] + notas[i * 2 + 1]) / 2.0;
        }

        // Cálculo das médias semestrais
        double media1Semestre = 0, media2Semestre = 0;
        for (int i = 0; i < 4; i++) {
            media1Semestre += notas[i];
            media2Semestre += notas[i + 4];
        }
        media1Semestre /= 4.0;
        media2Semestre /= 4.0;

        // Cálculo da média final
        double mediaFinal = (media1Semestre + media2Semestre) / 2.0;

        // Saída dos resultados
        System.out.println("\n=== RESULTADOS ===");
        for (int i = 0; i < 4; i++) {
            System.out.printf("Média do %dº trimestre: %.2f\n", (i + 1), mediasTrimestres[i]);
        }

        System.out.printf("\nMédia do 1º semestre: %.2f\n", media1Semestre);
        System.out.printf("Média do 2º semestre: %.2f\n", media2Semestre);
        System.out.printf("\nMÉDIA FINAL: %.2f\n", mediaFinal);

        input.close();
    }
}

import java.util.Scanner;

public class ConversaoTemperatura {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("=== CONVERSOR DE TEMPERATURA ===");
        System.out.print("Digite a temperatura em graus Celsius: ");
        double celsius = input.nextDouble();

        // Conversão para Kelvin
        double kelvin = celsius + 273.15;

        // Conversão para Fel-Watt (Fórmula fictícia: FW = (Celsius * 1.8) + 100)
        double felWatt = (celsius * 1.8) + 100;

        // Exibição dos resultados
        System.out.println("\n=== RESULTADOS ===");
        System.out.printf("Temperatura em Celsius: %.2f ºC\n", celsius);
        System.out.printf("Temperatura em Kelvin: %.2f K\n", kelvin);
        System.out.printf("Temperatura em Fel-Watt: %.2f ºFW\n", felWatt);

        input.close();
    }
}
