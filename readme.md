# Ejercicio 1: subsidio familiar 
###  escriba una aplicacion para resolver el siguiente enunciado:
escriba una aplicación para resolver el siguiente enunciado. El gobierno ha implementado
como parte de su programa social, un subsidio familiar bajo la siguiente reglamentación:

Las familias que tienen hasta 2 hijos, reciben Q. 70.00, las que tienen hasta 3 y 5 reciben Q. 90.00 y las
que tienen 6 o más reciben Q. 120 mensual. Por cada hijo en edad escolar reciben Q. 10.00 adicionales.
Se considera la edad escolar entre 6 y 18 años. Si la madre de familia fuera viuda, la familia recibe Q.
20.00 adicionales.

Determinar el monto mensual que recibirá una familia de acuerdo a su realidad familiar a través de una
función llamada calcularSubsidio.

### Determinar el monto mensual que recibirá una familia de acuerdo a su realidad familiar a través de una
función llamada calcularSubsidio.
-----
### Codigo fuente en C++  
----- 
    #include <iostream> 	//Biblioteca estándar para entrada/salida.
    #include <algorithm>	// Biblioteca para utilizar algoritmos como min_element y max_element.

    using namespace std;

    // PROCEDIMIENTO DE FUNCIONES--------------------------------------------------------------------------------------------------------------------------
    // Calcula el subsidio total...........................................................................................................................
    double calcularSubsidio(int numHijos, int edadesHijos[], bool madreViuda) {
    double subsidioBase;

    // Determina el subsidio base según el número de hijos.............................................................................................
    if (numHijos <= 2) {
        subsidioBase = 70.00;
    } else if (numHijos <= 5) {
        subsidioBase = 90.00;
    } else {
        subsidioBase = 120.00;
    }

    // Determina  subusidio escolar  si el o los hijos se encuentran en el rango de edad...............................................................
    double adicionalEdadEscolar = 0.00;
    for (int i = 0; i < numHijos; ++i) {
        if (edadesHijos[i] >= 6 && edadesHijos[i] <= 18) {
            adicionalEdadEscolar += 10.00;
        }
    }

    // adjunta el subsidio  si la madre es viuda o no...................................................................................................
    double adicionalMadreViuda = madreViuda ? 20.00 : 0.00;

    // Determina el subsido total que recibirá la familia según los datos ingresados....................................................................
    double montoTotal = subsidioBase + adicionalEdadEscolar + adicionalMadreViuda;

    return montoTotal;
    }

    i nt main() {
    // Proceso del programa-----------------------------------------------------------------------------------------------------------------------------
    cout << " ---------------------------------Gobierno de Guatemala---------------------------------" ;
	cout <<"\n-------------------------------------Programa social------------------------------------";
	cout <<"\n A continuacion se le realizaran una serie de preguntas para determinar El subsidio mensual.";
    // Declaración de variables: Número de hijos........................................................................................................
    int numHijos;
    
    // Obtener número de hijos..........................................................................................................................
    cout << "\nCuantos hijos tiene?  ";
    cin >> numHijos;

    // Determinar las edades de los hijos...............................................................................................................
    int edadesHijos[numHijos];
    for (int i = 0; i < numHijos; ++i) {
        cout << "Ingrese la edad de su(s) hijo(s) " << (i + 1) << ": ";
        cin >> edadesHijos[i];
    }

    // Declaración de la variable: madre viuda..........................................................................................................
    bool madreViuda;

    // Determinar si la madre es viuda..................................................................................................................
    cout << "La madre es viuda (S para si, N para no)? ";
    string respuestaMadreViuda;
    cin >> respuestaMadreViuda;

    // Convertir la respuesta a minúsculas para manejar "S" o "s" y "N" o "n"...........................................................................
    transform(respuestaMadreViuda.begin(), respuestaMadreViuda.end(), respuestaMadreViuda.begin(), ::tolower);

    // Evalua la respuesta..............................................................................................................................
    madreViuda = (respuestaMadreViuda == "s");

    // Ejecutar la sumatoria de los subsidios determinados.............................................................................................
    double subsidio = calcularSubsidio(numHijos, edadesHijos, madreViuda);
    cout << "El Subsidio familiar mensual a recibir es de: " << subsidio << " Quetzales";

    return 0;
    }
  
----
### Codigo fuente en python   
----
     # Calcula el monto total del subsidio familiar mensual
    def calcular_subsidio(num_hijos, edades_hijos, madre_viuda):
    subsidio_base = 0.0

    # Determina el subsidio base según el número de hijos
    if num_hijos <= 2:
        subsidio_base = 70.00
    elif num_hijos <= 5:
        subsidio_base = 90.00
    else:
        subsidio_base = 120.00

    # Determina el subsidio escolar si el o los hijos se encuentran en el rango de edad
    adicional_edad_escolar = sum(10.00 for edad in edades_hijos if 6 <= edad <= 18)

    # Determina el subsidio si la madre es viuda o no
    adicional_madre_viuda = 20.00 if madre_viuda else 0.00

    # Determina el subsidio total que recibirá la familia según los datos ingresados
    monto_total = subsidio_base + adicional_edad_escolar + adicional_madre_viuda

    return monto_total


    def main():
    # Proceso del programa
    print(" ---------------------------------Gobierno de Guatemala---------------------------------")
    print("-------------------------------------Programa social------------------------------------")
    print(" A continuacion se le realizaran una serie de preguntas para determinar El subsidio mensual.")

    # Obtener número de hijos
    num_hijos = int(input("¿Cuántos hijos tiene? "))

    # Determinar las edades de los hijos
    edades_hijos = [int(input(f"Ingrese la edad del hijo {i + 1}: ")) for i in range(num_hijos)]

    # Determinar si la madre es viuda
    respuesta_madre_viuda = input("La madre es viuda (S para sí, N para no)? ").lower()
    madre_viuda = respuesta_madre_viuda == 's'

    # Ejecutar la sumatoria de los subsidios determinados
    subsidio = calcular_subsidio(num_hijos, edades_hijos, madre_viuda)
    print(f"El Subsidio familiar mensual a recibir es de: {subsidio} Quetzales")


    if __name__ == "__main__":
    main()
------
### Ejecucion de los programas
- C++
  
 ![Ejercicio 1 ](https://drive.google.com/file/d/1qhoOT0-fBsQsN8MrIz209jwPUVoI--pU/view).
 - python
  
 ![Ejercicio 1 ](https://drive.google.com/file/d/1BHtHK3lWJS58IHtc2_jTIkfueCwB9DQB/view).
------
# Ejercicio 2: Vectores
###  escribir una aplicación que solicite al usuario un número que será la longitud de dos vectores que se deben llenar aleatoriamente, sume los valores e indique si ocurre cualquiera de los siguientes escenarios. 
a) Son iguales

b) vector A es menor a B 

c) vector B es menor a A

----
### Codigo fuente en C++

    #include <iostream>  // Librería estándar para entrada/salida..............................................................
    #include <vector>    // Librería para utilizar la clase vector.............................................................
    #include <cstdlib>   // Librería estándar para funciones generales.........................................................
    #include <ctime>     // Librería para manipulación de tiempo...............................................................

    using namespace std;

    int main() {
    // Generador de números aleatorios.....................................................................................
    srand(time(0));

    // Solicitar al usuario la longitud de los vectores....................................................................
    int longitud;
    cout << "Ingrese la longitud de los vectores: ";
    cin >> longitud;

    // Vector A(Crea y llena el vector aleatoriamnte)......................................................................
    vector<int> vectorA(longitud);
    for (int i = 0; i < longitud; ++i) {
        vectorA[i] = rand() % 100; // Números aleatorios ..................................................................
    }

    // Vector B(Crea y llena el vector aleatoriamnte)......................................................................
    vector<int> vectorB(longitud);
    for (int i = 0; i < longitud; ++i) {
        vectorB[i] = rand() % 100; // Números aleatorios...................................................................
    }

    // Muestra en pantalla los vectores....................................................................................
    cout << "Vector A: ";
    for (int i = 0; i < longitud; ++i) {
        cout << vectorA[i] << " ";
    }
    cout << endl;

    cout << "Vector B: ";
    for (int i = 0; i < longitud; ++i) {
        cout << vectorB[i] << " ";
    }
    cout << endl;

    // Suma cada valor de los vectores......................................................................................
    int sumaA = 0, sumaB = 0;
    for (int i = 0; i < longitud; ++i) {
        sumaA += vectorA[i];
        sumaB += vectorB[i];
    }

    // Compara las sumas y muestra el resultado.............................................................................
    if (sumaA == sumaB) {
        cout << "Los vectores son iguales." << endl;
    } else if (sumaA < sumaB) {
        cout << "El vector A es menor que el vector B." << endl;
    } else {
        cout << "El vector B es menor que el vector A." << endl;
    }

    return 0;
    }

------
### Codigo fuente en python
    import random

    # Generador de números aleatorios
        random.seed()

    # Solicitar al usuario la longitud de los vectores
    longitud = int(input("Ingrese la longitud de los vectores: "))

    # Vector A (Crea y llena el vector aleatoriamente)
    vectorA = [random.randint(0, 99) for _ in range(longitud)]

    # Vector B (Crea y llena el vector aleatoriamente)
    vectorB = [random.randint(0, 99) for _ in range(longitud)]

    # Muestra en pantalla los vectores
    print("Vector A:", *vectorA)
    print("Vector B:", *vectorB)

    # Suma cada valor de los vectores
    sumaA = sum(vectorA)
    sumaB = sum(vectorB)

    # Compara las sumas y muestra el resultado
    if sumaA == sumaB:
    print("Los vectores son iguales.")
    elif sumaA < sumaB:
    print("El vector A es menor que el vector B.")
    else:
    print("El vector B es menor que el vector A.")
------
### Ejecucion de los programas
- C++
  
 ![Ejercicio 2 en c++](https://drive.google.com/file/d/1HTS9MacZdKcpcE-SmsmjpQUG8h1ZqIl9/view).

 - python
  
 ![Ejercicio 2 en python](https://drive.google.com/file/d/15WHX6mPyM2u0DrCqnGLlgd5pPUFIt7SY/view).


------
# Ejercicio 3: Estadistica descrpitiva
###  en estadística descriptiva, se define el rango de un conjunto de datos reales como la diferencia entre el mayor y el menor de los datos. Por ejemplo, si los datos son: [5.96, 6.74, 7.43, 4.99, 7.20, 0.56, 2.80], entonces el rango es 7.43 − 0.56 = 6.87.
----
### Codigo fuente en C++
    #include <iostream>  // Biblioteca estándar para entrada/salida..........................................................................
    #include <vector>    // Biblioteca para utilizar el contenedor vector....................................................................
    #include <algorithm> // Biblioteca para utilizar algoritmos como min_element y max_element...............................................

    using namespace std; 

    int main() {
	
	cout <<"Estadistica descriptiva";
    // a) Preguntar al usuario cuántos valores serán ingresados...........................................................................
    int n;
    cout << "\nIngrese la cantidad de valores que desea: ";
    cin >> n;

    // Verificar que la cantidad de valores sea válida....................................................................................
    if (n <= 0) {
        cerr << "Ingrese una cantidad válida de datos." << endl;
        return 1; // Terminar el programa con error.......................................................................................
    }

    // b) Pedir al usuario ingresar los datos uno por uno.................................................................................
    vector<double> datos;
    for (int i = 0; i < n; ++i) {
        double dato;
        cout << "Ingrese el valor #" << (i + 1) << ": ";
        cin >> dato;
        datos.push_back(dato);
    }

    // Calcular el rango de los datos.....................................................................................................
    double minDato = *min_element(datos.begin(), datos.end()); // Encontrar el valor mínimo.
    double maxDato = *max_element(datos.begin(), datos.end()); // Encontrar el valor máximo.
    double rango = maxDato - minDato;

    // Mostrar el resultado...............................................................................................................
    cout << "El rango de los valores ingresados es: " << rango << endl;

    return 0; 
    }

----
### Codigo fuente en phyton
def main():
    print("Estadistica descriptiva")

    # a) Preguntar al usuario cuántos valores serán ingresados.
    n = int(input("Ingrese la cantidad de valores que desea: "))

    # Verificar que la cantidad de valores sea válida.
    if n <= 0:
        print("Ingrese una cantidad válida de datos.")
        return 1  # Terminar el programa con error.

    # b) Pedir al usuario ingresar los datos uno por uno.
    datos = []
    for i in range(n):
        dato = float(input(f"Ingrese el valor #{i + 1}: "))
        datos.append(dato)

    # Calcular el rango de los datos.
    min_dato = min(datos)  # Encontrar el valor mínimo.
    max_dato = max(datos)  # Encontrar el valor máximo.
    rango = max_dato - min_dato

    # Mostrar el resultado.
    print("El rango de los valores ingresados es:", rango)

    if __name__ == "__main__":
    main()
------
### Ejecucion de los programas
- C++
  
 ![Ejercicio 3 en c++](https://drive.google.com/file/d/1XrOFBtCdmtfzqiNbZhiHUbYerxwtJetd/view).

 - python
  
 ![Ejercicio 3 en python](https://drive.google.com/file/d/1IiiztFY9RCRG7n9lHZiLfNMIQV5xCqNo/view).


------
# Ejercicio 4: Cudrado dimensional
###   solicite al usuario ingresar un número que será el lado de un cuadrado y escriba un programa que dibuje dicho cuadrado de la siguiente manera: suponga que el usuario ingresó 4 
---

### Codigo fuente en C++
    #include <iostream>		// Biblioteca estándar para entrada/salida......................................................................

    using namespace std;

    int main() {
    char continuar;
	//bucle para que se pueda repetir...................................................................................................
    do {
        // Solicitar al usuario las dimensiones del cuadrado............................................................................
        int lado;
        cout << "Ingrese las dimensiones del cuadrado: ";
        cin >> lado;

        // trazar el cuadrado...........................................................................................................
        for (int i = 0; i < lado; ++i) {
            for (int j = 0; j < lado; ++j) {
                // Si estamos en la primera o última fila, o en la primera o última columna, imprimir '*'...............................
                if (i == 0 || i == lado - 1 || j == 0 || j == lado - 1) {
                    cout << "* ";
                } else {
                    // De lo contrario, imprimir un espacio en blanco...................................................................
                    cout << "  ";
                }
            }
            // Saltar a una nueva línea después de cada fila............................................................................
            cout << endl;
        }

        cout << "¿Desea dibujar otro cuadrado? (s/n): ";
        cin >> continuar;
    } while (continuar == 's' || continuar == 'S');

    return 0;
    }
-----
### Codigo fuente en python

    while True:
    # Solicitar al usuario las dimensiones del cuadrado
    lado = int(input("Ingrese las dimensiones del cuadrado: "))

    # trazar el cuadrado
    for i in range(lado):
        for j in range(lado):
            # Si estamos en la primera o última fila, o en la primera o última columna, imprimir '*'
            if i == 0 or i == lado - 1 or j == 0 or j == lado - 1:
                print("* ", end="")
            else:
                # De lo contrario, imprimir un espacio en blanco
                print("  ", end="")
        # Saltar a una nueva línea después de cada fila
        print()

    continuar = input("¿Desea dibujar otro cuadrado? (s/n): ")
    if continuar.lower() != 's':
        break
----
### Ejecucion de los programas
- C++
  
 ![Ejercicio 4 en c++](https://drive.google.com/file/d/1WC32ogDOjfQ05HjZT74PndwvPk6RiNds/view).

 - python
  
 ![Ejercicio 4 en python](https://drive.google.com/file/d/1vCS_28kdWmvUMcEgX22r8rGOeSTkpPKT/view).


------