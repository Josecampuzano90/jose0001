// Clase Nodo
public class Nodo
{
    public int Dato;
    public Nodo Siguiente;

    public Nodo(int dato)
    {
        Dato = dato;
        Siguiente = null;
    }
}

// Clase Lista Enlazada
public class ListaEnlazada
{
    private Nodo cabeza;

    public ListaEnlazada()
    {
        cabeza = null;
    }

    // Método para agregar un nodo al inicio
    public void Agregar(int dato)
    {
        Nodo nuevoNodo = new Nodo(dato);
        nuevoNodo.Siguiente = cabeza;
        cabeza = nuevoNodo;
    }

    // Ejercicio 1: Calcular el número de elementos en la lista
    public int ContarElementos()
    {
        int contador = 0;
        Nodo actual = cabeza;
        while (actual != null)
        {
            contador++;
            actual = actual.Siguiente;
        }
        return contador;
    }

    // Ejercicio 2: Invertir la lista enlazada
    public void InvertirLista()
    {
        Nodo previo = null;
        Nodo actual = cabeza;
        while (actual != null)
        {
            Nodo siguiente = actual.Siguiente;
            actual.Siguiente = previo;
            previo = actual;
            actual = siguiente;
        }
        cabeza = previo;
    }

    // Método para mostrar la lista
    public void MostrarLista()
    {
        Nodo actual = cabeza;
        while (actual != null)
        {
            Console.Write(actual.Dato + " -> ");
            actual = actual.Siguiente;
        }
        Console.WriteLine("null");
    }
}

// Programa principal
class Program
{
    static void Main(string[] args)
    {
        ListaEnlazada lista = new ListaEnlazada();

        // Agregar elementos a la lista
        lista.Agregar(40);
        lista.Agregar(30);
        lista.Agregar(20);
        lista.Agregar(10);

        Console.WriteLine("Lista original:");
        lista.MostrarLista();

        // Ejercicio 1: Calcular el número de elementos
        Console.WriteLine("Número de elementos en la lista: " + lista.ContarElementos());

        // Ejercicio 2: Invertir la lista
        lista.InvertirLista();
        Console.WriteLine("Lista invertida:");
        lista.MostrarLista();
    }
}
