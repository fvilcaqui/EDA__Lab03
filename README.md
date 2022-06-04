<div align="center">
<table>
    <theader>
        <tr>
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/epis.png?raw=true" alt="EPIS" style="width:50%; height:auto"/></td>
            <th>
                <span style="font-weight:bold;">UNIVERSIDAD NACIONAL DE SAN AGUSTIN</span><br />
                <span style="font-weight:bold;">FACULTAD DE INGENIERÍA DE PRODUCCIÓN Y SERVICIOS</span><br />
                <span style="font-weight:bold;">DEPARTAMENTO ACADÉMICO DE INGENIERÍA DE SISTEMAS E INFORMÁTICA</span><br />
                <span style="font-weight:bold;">ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS</span>
            </th>
            <td><img src="https://github.com/rescobedoq/pw2/blob/main/abet.png?raw=true" alt="ABET" style="width:50%; height:auto"/></td>
        </tr>
    </theader>
    <tbody>
        <tr><td colspan="3"><span style="font-weight:bold;">Formato</span>: INFORME DE LABORATORIO</td></tr>
        <tr><td><span style="font-weight:bold;">Aprobación</span>:  2022/03/01</td><td><span style="font-weight:bold;">Código</span>: GUIA-PRLD-001</td><td><span style="font-weight:bold;">Página</span>: 1</td></tr>
    </tbody>
</table>
</div>
<div align="center">
<span style="font-weight:bold;">GUÍA DE LABORATORIO</span><br />
</div>

<table>
<theader>
<tr><th colspan="6">INFORMACIÓN BÁSICA</th></tr>
</theader>
<tbody>
<tr><td>ASIGNATURA:</td><td colspan="5">Estructura de Datos y Algoritmos</td></tr>
<tr><td>TÍTULO DE LA PRÁCTICA:</td><td colspan="5">Pilas y Colas</td></tr>
<tr>
<td>NÚMERO DE PRÁCTICA:</td><td>02</td><td>AÑO LECTIVO:</td><td>2022 A</td><td>NRO. SEMESTRE:</td><td>III</td>
</tr>
<tr>
<td>FECHA INICIO::</td><td>01-Junio-2022</td><td>FECHA FIN:</td><td>5-Junio-2022</td><td>DURACIÓN:</td><td>02 horas</td>
</tr>
<tr><td colspan="6">RECURSOS:
</td>
</<tr>
  <tr><td colspan="6">ALUMNO:
<ul>
<li>Frank's Vilca Quispe - fvilcaqui@unsa.edu.pe</li>
</ul>
</td>
</<tr>
<tr><td colspan="6">DOCENTES:
<ul>
<li>Richart Smith Escobedo Quispe - rescobedoq@unsa.edu.pe</li>
</ul>
</td>
</<tr>
</tdbody>
</table>

#
   ## SOLUCION Y RESULTADOS
#

## I. SOLUCION DE EJERCICIOS/PROBLEMAS
   EJERCICIO 1:
   Tiene tres pilas de cilindros donde cada cilindro tiene el mismo diámetro, pero pueden variar en altura. Puede cambiar la altura de una pila quitando y descartando    su cilindro superior tantas veces como desee.
   Encuentre la altura máxima posible de las pilas de modo que todas las pilas tengan exactamente la misma altura.
   Esto significa que debe eliminar cero o más cilindros de la parte superior de cero o más de las tres pilas hasta que tengan la misma altura y luego devolver la        altura.
   
   #Resolucion: 
     En este ejercicio lo que decidi fue primero implementar 3 array con los valores que iran en las pilas y ala vez que decidi crear sus respectivas pilas.
      
        int[] cantidad1 = {1,1,1,2,3};
		int[] cantidad2 = {2,3,4};
		int[] cantidad3 = {1,4,1,1};
        
		Stack pila1 = new Stack();
		Stack pila2 = new Stack();
		Stack pila3 = new Stack();
     
     Luego se creo un metodo el cual se encargara de ingresar el valor de cada array en su respectiva pila
     
        public static void DarValores(Stack pila, int[] a) {
		   for(int i=0;i<a.length;i++) {
			   pila.push(a[i]);
		   }
	    }
        
     Y para saber el tamaño de cada cilindro un metodo que sumara los valores de cada array
    
       public static int suma(int[] a) {
		int suma=0;
		for(int i=0;i<a.length;i++) {
			suma += a[i];
		}
		return suma;
	}
    
    Finalmente, se creo el metodo equalStack el cual se encargara de volver todos los cilindros del mismo tamaño
    
    	int vi1=d,vi2=e,vi3=f; //Guardamos los primeros valores para utilizarlos luego
		//Creamos este ciclo while hasta que uno de los valores sea cero o todos sean iguales
		while((0<=d && 0<=e && 0<=f) || (d==e && e==f)) { 
			//en cada condicion es por si uno de los valores mayor que los otros y quitarle su ultimo valor
			//y a la suma de cada pila quitarle ese valor
			if(d>e || d>f) {
	              d = d - (int)a.pop(); 
			}else if(e>d || e>f) {
				  e = e - (int)b.pop(); 
			}else if(f>d || f>e) {
				  f = f - (int)c.pop();
			}else if(d==e && e==f) { //si son iguales acabaremos el bucle con break, y utilizaremos los valores
				System.out.println(vi1 + " - " + (vi1-d) + " = " + d);    //copeados al inicio para la respuesta
				System.out.println(vi2 + " - " + (vi2-e) + " = " + e);
				System.out.println(vi3 + " - " + (vi3-f) + " = " + f);
				System.out.println("Las 3 pilas tienen ahora la altura de: " + d);
				break;
			}
		}
	}
    
    # Resultados:
    
    ![image](https://user-images.githubusercontent.com/87882802/171967618-77c4f489-b1c3-47e8-97ba-c33db325f407.png)

   EJERCICIO 2:
   Implementa una pila usando POO con tipos genéricos siguiendo los estándares de Java (los métodos para una pila) verifique:
   
   #Resolucion: 
     Primero creamos la pila y le damos sus respectivos valores:
     
     Stack pila = new Stack();
		pila.push(50);
		pila.push(23);
		pila.push(15);
		pila.push("Franks");
		pila.push("Programacion");
		
        //utilizaremos el metodo "search" para buscar la posicion de un elemento;
		System.out.println("La posicion del elemento 23 es: " + pila.search(23));
		
		//En caso que no exista el elemento colocara -1
		System.out.println("La posicion del elemento 58 es: " + pila.search(58));

		//utilizaremos el metodo "peek" para ver el ultimo valor de nuestra pila
		System.out.println("Usando el metodo peek, el ultimo elemento es: " + pila.peek());
		
		//Utilizaremos el metodo "empty" para ver si la pila esta vacia
		while(pila.empty()==false) {
			//Utilizaremos el metodo "pop" para ver el ultimo elemento en la lista y eliminarla
			System.out.println(pila.pop());
		}   
        
        #Resultados:
	
        ![image](https://user-images.githubusercontent.com/87882802/171968011-98700c84-c057-4f5c-8b8e-0136bf4e0fc7.png)

   
   EJERCICIO 3:
   Implementa una cola usando POO con tipos genéricos siguiendo los estándares de Java (los métodos para una cola) verifique:
        //Ingresamos los valores de la cola
		for(int i=1; i<8; i++) {
			//Este metodo inserta un elemento a la cola con el metodo "offer"
			cola.offer(i);
		}
		//utilizaremos el metodo "remove" que tambien recupera y elimina un valor
		  cola.remove();
		  
		  //El metodo "element" recupera pero no elimina el valor de la cola
		  System.out.println("El elemento recuperado con element es: " + cola.element());
		  
		/*Utilzaremos el metodo "peek" que recupera el encabezado de la cola
		 y si no hay un valor te dara null por lo que lo utilizaremos para imprimir
		 los valores de esta cola */
		while(cola.peek() != null) {
	
			//Con el metodo "poll" recuperamos el encabezado y lo eliminamos de la cola
			System.out.println(cola.poll());
			//La diferencia entre el metodo "remove" y "poll" es que cuando esta vacio el metodo poll da null
		}
        
        #Resultados:
	
        ![image](https://user-images.githubusercontent.com/87882802/171967997-1be79f2a-074b-4296-a9f1-5157d09a68de.png)



## II. SOLUCION DEL CUESTIONARIO

¿Qué similitudes hay entre una Lista Enlazada y una Pila?

  - En ambos casos se pueden llenar los valores con distintos tipos de variables, de manera
    secuencial y donde el limite vendría a ser el espacio de tu dispositivo.
    
¿En que casos seria favorable/desfavorable utilizar Pila/Cola?
   - El uso de esos métodos nos ayudaría sobre todo cuando vayamos a trabajar con datos ordenados,
     donde estrictamente es necesario usar a partir de los extremos, ya que no podemos utilizar los 
     datos que se encuentran el medio.
   - Individualmente para su uso la pila es mejor usar cuando el paradigma es In-First-Out(LIFO) y 
      una cola cuando es al reves First-in-First-Out (FIFO).


#

   ## BIBLIOGRAFIA
   https://www.w3schools.com/java/
   
   https://www.eclipse.org/downloads/packages/release/2022-03/r/eclipse-ide-enterprise-java-and-web-developers
   
   https://docs.oracle.com/javase/8/docs/api/java/util/Stack.html
   
   https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html

   
#

  
