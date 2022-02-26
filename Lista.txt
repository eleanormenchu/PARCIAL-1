package ParcialI;

import java.util.Scanner;

public class Ordenes {
static Scanner sc = new Scanner(System.in);
static int[] numeros = new int [10];

public void pedir_numero(){
    for (int i=0; i<10;i++){
    System.out.println("Ingrese 10 números");
    numeros [i]= sc.nextInt();
    }
    for (int i=0; i<10;i++){
        System.out.println(numeros[i]);
    }
}

public void menu(int eleccion){
    boolean salir = false;
    
    while(!salir){
    System.out.println("Seleccione qué desea hacer");
    System.out.println("1. Ordenar de forma ascendente");
    System.out.println("2. Ordenar de forma descendente");
    System.out.println("3. Salir");
    
    eleccion = sc.nextInt();
    switch (eleccion){
        case 1: mostrar_ascendente();
                break;
        case 2: mostrar_descendente();
                break;
        case 3: salir=true;
                break;
        case 4: default: System.out.println("La opción que seleccionó no existe, seleccione otra");
                break;
    }
    }
}

public void mostrar_ascendente(){
    System.out.println("Orden de forma ascendente:");
    ascendente(numeros);
    for (int orden:numeros){
        System.out.println(orden);
    }
    menu(0);
}
public void ascendente(int[] arreglo){
    for (int i = 0; i<arreglo.length - 1; i++){
        int min = i;
        
        for(int c = i+1; c<arreglo.length;c++){
            if(arreglo[c]<arreglo[min]){
                min=c;
            }
        }
        
        if (i !=min){
            int aux = arreglo[i];
            arreglo[i]=arreglo[min];
            arreglo[min]=aux;
        }
    }
}

public void mostrar_descendente(){
     System.out.println("Orden de forma descendente:");
    descendente(numeros);
    for (int orden:numeros){
        System.out.println(orden);
    }
}

public void descendente(int[] arreglo){
     for (int i = 0; i<arreglo.length - 1; i++){
        int max = i;
        
        for(int c = i+1; c<arreglo.length;c++){
            if(arreglo[c]>arreglo[max]){
                max=c;
            }
        }
        
        if (i !=max){
            int aux = arreglo[i];
            arreglo[i]=arreglo[max];
            arreglo[max]=aux;
        }
    }
}

}