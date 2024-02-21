# MetodosOrdenamiento
Metodos Bubble, Selection, Insertion Sort

¿QUÉ ES UN ORDENAMIENTO?
Es la operación de arreglar los elementos en algún orden secuencial de acuerdo a un criterio deordenamiento.
El propósito principal de un ordenamiento es el de facilitar las búsquedas de los miembros del
conjunto ordenado.
Ordenar un grupo de datos significa mover los datos o sus referencias para que queden en una
secuencia por categorías y en forma ascendente o descendente.


Todos los ejemplos a continuación están basados en java...
Linea 19: Bubble
Linea 38: Selection Sort
Linea 68: Insertion Sort



1.- MÉTODO BURBUJA (BUBBLESORT)
  El Ordenamiento de burbuja (BubbleSort) es un algoritmo de ordenamiento simple. El mismo funciona revisando cada elemento de la lista a ordenar con el que le sigue, cambiándolos de posición si están en un orden incorrecto (n>n+1). Es necesario repetir este proceso varias veces hasta que no se necesiten más cambios, lo que significa que la lista quedó ordenada. Consiste en comparar pares de elementos adyacentes en un array y si están desordenanos intercambiarlos hasta que estén todos ordenados.
  Si A es el array a ordenar, se realizan A.length-1 pasadas. Si la variable i es la que cuenta el número de pasadas, en cada pasada i se comprueban los elementos adyacentes desde el primero hasta A.length-i-1 ya que el resto hasta el final del array están ya ordenados. Si los elementos adyacentes están desordenados se intercambian.
  El método de ordenación de la burbuja en java para ordenar un array A es el siguiente:
  
public static void burbuja(int[] A) {
        int i, j, aux;
        for (i = 0; i < A.length - 1; i++) {
            for (j = 0; j < A.length - i - 1; j++) {                                                              
                if (A[j + 1] < A[j]) {
                    aux = A[j + 1];
                    A[j + 1] = A[j];
                    A[j] = aux;
                }
            }
        }



2.- MÉTODO DE SELECCIÓN (SELECTIONSORT)
  El método de ordenación por selección consiste en repetir los siguientes pasos:
  1. Se busca el elemento más pequeño del array y se coloca en la primera posición.
  2. Entre los restantes, se busca el elemento más pequeño y se coloca en la segunda posición.
  3. Entre los restantes se busca el elemento más pequeño y se coloca en la tercera posición.

Este proceso se repite hasta colocar el último elemento, de forma gráfica el proceso sería el siguiente:
Array original a ordenar: [50, 26, 7, 9, 15, 27]

//método java de ordenación por selección
public static void seleccion(int A[]) {
          int i, j, menor, pos, tmp;
          for (i = 0; i < A.length - 1; i++) {      // tomamos como menor el primero
                menor = A[i];                       // de los elementos que quedan por ordenar                    
                pos = i;                            // y guardamos su posición
                for (j = i + 1; j < A.length; j++){ // buscamos en el resto
                      if (A[j] < menor) {           // del array algún elemento
                          menor = A[j];             // menor que el actual
                          pos = j;
                      }
                }
                if (pos != i){                      // si hay alguno menor se intercambia                         
                    tmp = A[i];
                    A[i] = A[pos];
                    A[pos] = tmp;
                }
          }
}


3.- MÉTODO POR INSERCIÓN (INSERTIONSORT)
  Ordenamiento por inserción es un algoritmo muy sencillo para ordenar un conjunto de elementos comparables entre sí. Funciona insertando cada elemento en la posición correcta dentro de un subconjunto ya ordenado hasta que se ordena todo el conjunto.

public static void insertionSort(int[] arreglo)
{
    for (int i = 1; i < arreglo.length; i++)
    {
        int aux = arreglo[i];
        int j;
        for (j = i - 1; j >= 0 && arreglo[j] > aux; j--)
            arreglo[j + 1] = arreglo[j];
        arreglo[j + 1] = aux;
    }
}

La complejidad del peor caso para este algoritmo es O(n²) , esto debido a que se tiene un ciclo for dentro de otro. El ciclo for externo itera n – 1 veces mientras que el ciclo for interno itera, en el peor de los casos, a través de todo el subconjunto ordenado.


Pilar Del Sagrario Mora Gómez - 4P
