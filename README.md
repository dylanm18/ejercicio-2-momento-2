# ejercicio-2-momento-2
/**
 * Ejercicios en Java - Programación Básica
 * 
 * Autor: nombre de la persona
 * Fecha:fecha para entregar
 * Descripción: Solución de los ejercicios de ciclos y condicionales en Java.
 */

import java.util.Scanner;

// Clase principal que ejecuta todos los ejercicios
public class Ejercicios {
    public static void main(String[] args) {
        registroNotas();
        juegoAdivinarNumero();
        conteoParesImpares();
        promedioNumerosPositivos();
    }
    
    /**
     * Registro de notas de estudiantes
     * Se ingresan notas entre 0 y 100. Se cuentan los aprobados (>=60) y reprobados.
     */
    public static void registroNotas() {
        Scanner scanner = new Scanner(System.in);
        int aprobados = 0, reprobados = 0;
        
        while (true) {
            System.out.print("Ingrese la nota del estudiante (-1 para terminar): ");
            int nota = scanner.nextInt();
            if (nota == -1) break;
            if (nota >= 60) aprobados++;
            else reprobados++;
        }
        
        System.out.println("Estudiantes aprobados: " + aprobados);
        System.out.println("Estudiantes reprobados: " + reprobados);
    }
    
    /**
     * Juego para adivinar un número entre 1 y 20.
     * Indica si el número ingresado es mayor o menor hasta que el usuario acierta.
     */
    public static void juegoAdivinarNumero() {
        Scanner scanner = new Scanner(System.in);
        int numeroSecreto = (int) (Math.random() * 20) + 1;
        int intentos = 0, numero;
        
        do {
            System.out.print("Adivine el número (1-20): ");
            numero = scanner.nextInt();
            intentos++;
            if (numero < numeroSecreto) System.out.println("Es mayor.");
            else if (numero > numeroSecreto) System.out.println("Es menor.");
        } while (numero != numeroSecreto);
        
        System.out.println("¡Correcto! Lo lograste en " + intentos + " intentos.");
    }
    
    /**
     * Cuenta la cantidad de números pares e impares en una lista de 10 números.
     */
    public static void conteoParesImpares() {
        Scanner scanner = new Scanner(System.in);
        int pares = 0, impares = 0;
        
        for (int i = 0; i < 10; i++) {
            System.out.print("Ingrese un número: ");
            int numero = scanner.nextInt();
            if (numero % 2 == 0) pares++;
            else impares++;
        }
        
        System.out.println("Números pares: " + pares);
        System.out.println("Números impares: " + impares);
    }
    
    /**
     * Calcula el promedio de números positivos ingresados hasta que se ingresa 0.
     */
    public static void promedioNumerosPositivos() {
        Scanner scanner = new Scanner(System.in);
        int suma = 0, contador = 0;
        
        while (true) {
            System.out.print("Ingrese un número (0 para finalizar): ");
            int numero = scanner.nextInt();
            if (numero == 0) break;
            if (numero > 0) {
                suma += numero;
                contador++;
            }
        }
        
        if (contador > 0) {
            System.out.println("Promedio de números positivos: " + (suma / (double) contador));
        } else {
            System.out.println("No se ingresaron números positivos.");
        }
    }
}
