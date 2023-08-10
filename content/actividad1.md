---
title: "Actividad1"
date: 2023-08-10T16:08:37-05:00
draft: false
---

Ejercicio 1: 

#include <stdio.h>

float funcion1(float numero){
    return numero*numero;
}

float funcion2(float numero){
    return (numero*numero) + (1000*(numero));
}

float funcion3(float numero){
    
    if(numero<=0){
        return 10;
    }
    if(numero>0 && numero<5){
        return (numero*numero) - (numero + 1);
    }
    if(numero>=5){
        return (numero*2) - 1;
    }
}

int main()
{
    float numero;
    int opcion;
    float f1;
    float f2;
    float f3;
    printf("ingrese un numero decimal: ");
    scanf("%f", &numero);
    
    printf("Ingrese un numero del 1 al 3: ");
    scanf("%d", &opcion);
    
    switch(opcion){
        case 1:
        f1=funcion1(numero);
        printf("%f El resultado de la funcion 1 es: ",f1);
        break;
        
        case 2:
        f2=funcion2(numero);
        printf("%f El resultado de la funcion 2 es: ",f2);
        break;
        
        case 3: 
        f3=funcion3(numero);
        printf("%f El resultado de la funcion 3 es: ",f3);
        break;
        
        default:
        printf("jdjfdj");
        break;
    }
    
   

    return 0;
}


ejercicio 2: 

#include <stdio.h>

float funcion1(float numero){
    return (5/9)*(numero-32.0);
}

float funcion2(float numero){
    return ((9/5)*numero)+32.0;
}



int main()
{
    char opcion;
    float numero;
    float f1;
    float f2;
  
    
    
    printf("Ingrese si desea Convetir grados fahrenheit f o celsium c ");
    scanf("%c", &opcion);
    
    switch(opcion){
        case 'f':
        printf("ingrese la cantidad de celsium para la conseguir f ");
        scanf("%f",&numero);
        f1=funcion1(numero);
        printf(" El resultado de la conversion es: %f ",f1);
        break;
        
        case 'c':
        printf("ingrese la cantidad de Fahrenheit para la conseguir c ");
        scanf("%f",&numero);
        f2=funcion2(numero);
        printf(" El resultado de la conversion es: %f ",f2);
        break;
        
        
        default:
        printf("jdjfdj");
        break;
    }
    
   

    return 0;
}


ejercicio 3: 

#include <stdio.h>

float normalizar(float x, float xmin, float xmax, float a, float b) {
    if (xmax == xmin) {
        return x;
    }
    return a + ((x - xmin) * (b - a)) / (xmax - xmin);
}

int main() {

    int lambdas[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20};
    int num_lambdas = sizeof(lambdas) / sizeof(lambdas[0]);

    float intervalo1_a = -1.0;
    float intervalo1_b = 1.0;

    float intervalo2_a = 1.0;
    float intervalo2_b = 10.0;

    float intervalo3_a = 0.5;
    float intervalo3_b = 1.0;

    for (int i = 0; i < num_lambdas; i++) {
        float lambda = (float)lambdas[i];
        float x = lambda * lambda + lambda + 1;

       
        float normalizar1 = normalizar(x, x, x, intervalo1_a, intervalo1_b);

       
        float normalizar2 = normalizar(x, x, x, intervalo2_a, intervalo2_b);

  
        float normalizar3 = normalizar(x, x, x, intervalo3_a, intervalo3_b);

        printf("Lambda: %d, Original: %.2f, Intervalo [-1, 1]: %.2f, Intervalo [1, 10]: %.2f, Intervalo [0.5, 1]: %.2f\n",
               lambdas[i], x, normalizar1, normalizar2, normalizar3);
    }

    return 0;
}

