# MATRIZ

```java
public class testMatrizIrregular {
	static final int ANIOS = 3;
	static final int MESES = 12;
	static final int CANTIDAD = 6;

	public static void main(String[] args) {
		float[][] mmPrecipitaciones = new float[ANIOS][MESES];
		mmPrecipitaciones[0][0] = 10;
		mmPrecipitaciones[0][1] = 11;
		mmPrecipitaciones[0][2] = 12;
		mmPrecipitaciones[0][3] = 13;
		mmPrecipitaciones[0][4] = 14;
		mmPrecipitaciones[0][5] = 15;
		mmPrecipitaciones[0][6] = 16;
		mmPrecipitaciones[0][7] = 17;
		mmPrecipitaciones[0][8] = 18;
		mmPrecipitaciones[0][9] = 19;
		mmPrecipitaciones[0][10] = 20;
		mmPrecipitaciones[0][11] = 21;

		mmPrecipitaciones[1][0] = 30;
		mmPrecipitaciones[1][1] = 31;
		mmPrecipitaciones[1][2] = 32;
		mmPrecipitaciones[1][3] = 33;
		mmPrecipitaciones[1][4] = 34;
		mmPrecipitaciones[1][5] = 35;
		mmPrecipitaciones[1][6] = 36;
		mmPrecipitaciones[1][7] = 37;
		mmPrecipitaciones[1][8] = 38;
		mmPrecipitaciones[1][9] = 39;
		mmPrecipitaciones[1][10] = 40;
		mmPrecipitaciones[1][11] = 41;

		mmPrecipitaciones[2][0] = 60;
		mmPrecipitaciones[2][1] = 61;
		mmPrecipitaciones[2][2] = 62;
		mmPrecipitaciones[2][3] = 63;
		mmPrecipitaciones[2][4] = 64;
		mmPrecipitaciones[2][5] = 65;
		mmPrecipitaciones[2][6] = 66;
		mmPrecipitaciones[2][7] = 67;
		mmPrecipitaciones[2][8] = 68;
		mmPrecipitaciones[2][9] = 69;
		mmPrecipitaciones[2][10] = 70;
		mmPrecipitaciones[2][11] = 71;

		/*
		 * recorrer una matriz de manera convencional por filas (Año) y luego columna
		 * (Mes)
		 */
		/* float[][] mmPrecipitaciones = new float[Fila = ANIOS][ Columna = MESES]; */
		double[] acumXAnio = new double[mmPrecipitaciones.length];
		for (int fila = 0; fila < mmPrecipitaciones.length; fila++) {
			for (int columna = 0; columna < mmPrecipitaciones[fila].length; columna++) {
				System.out.print(mmPrecipitaciones[fila][columna] + " - ");
				acumXAnio[fila] += mmPrecipitaciones[fila][columna];
			}
			System.out.println();
			System.out.printf("%n % d - El valor acum de precip del Año %d juntando los %d meses es de =  %f %n", fila,
					fila + 1, MESES, acumXAnio[fila]);
		}

		System.out.println("---------");

		/*
		 * recorrer una matriz de manera inversa primero por columnas (Meses) y luego
		 * por fila (Año) cuando la matriz es regular, es decir que las columnas de las
		 * filas siempre son las mismas. Acumular los valores por meses de los distintos
		 * años.
		 */
		/* float[][] mmPrecipitaciones = new float[Fila = ANIOS][ Columna = MESES]; */
		double[] acumXMes = new double[mmPrecipitaciones[0].length];
		for (int columna = 0; columna < mmPrecipitaciones[0].length; columna++) {
			for (int fila = 0; fila < mmPrecipitaciones.length; fila++) {
				System.out.print(mmPrecipitaciones[fila][columna] + " - ");
				acumXMes[columna] += mmPrecipitaciones[fila][columna];
			}
			System.out.println();
			System.out.printf("%n % d - El valor acum de precip del mes %d juntando los %d años es de =  %f %n",
					columna, columna + 1, ANIOS, acumXMes[columna]);

		}

		System.out.println("---------");
		System.out.println("---------");

		// siempre y cuando sea una matriz regular fijo en la fila un valor de la
		// matriz, ej quiero mostrar solo el 2do anio
		/* float[][] mmPrecipitaciones = new float[Fila = ANIOS][ Columna = MESES]; */
		System.out.println("SOLO MUESTRO LOS VALORES DEL SEGUNDO ANIO");
		for (int mes = 0; mes < mmPrecipitaciones[0].length; mes++) {
			System.out.print(mmPrecipitaciones[1][mes] + " - ");
		}

		// siempre y cuando sea una matriz regular fijo en la columna un valor de la
		// matriz, ej quiero mostrar solo el 2do mes (ej febrero mes 2-1 nos da el
		// indice 1)
		/* float[][] mmPrecipitaciones = new float[Fila = ANIOS][ Columna = MESES]; */
		System.out.println("\nSOLO MUESTRO LOS VALORES DEL SEGUNDO MES");
		for (int anio = 0; anio < mmPrecipitaciones.length; anio++) {
			System.out.print(mmPrecipitaciones[anio][1] + " - ");
		}

	}

	public static void main_v2(String[] args) {

		// [Fila][Columna] {Fila 0} { Fila 1} {Fila 2} { Fila 3} length = 4
		int[][] matrizIreg = { { 1, 2, 3 }, { 4, 5, 6, 7, 8, 9, 10 }, { 7, 8 }, { 10, 11, 12 } };

		/* Mostrar por pantalla la fila y cuantas columnas tiene cada una de ellas */
		for (int f = 0; f < matrizIreg.length; f++) {
			System.out.printf("Fila: %d, Columnas: %d %n", f, matrizIreg[f].length); // le pido la extension de la fila
																						// en la q se
			// encuentra i.
		}
		/* Mostrar por pantalla el valor que tiene cada espacio en la matriz */

		System.out.println("");
		System.out.println("#######################");
		System.out.println("");

		for (int f = 0; f < matrizIreg.length; f++) {
			System.out.printf("La fila %d tiene %d columnas %n", f, matrizIreg[f].length);
			for (int c = 0; c < matrizIreg[f].length; c++) {
				System.out.printf("Columna %d, tiene el valor : %d %n", c, matrizIreg[f][c]);

			}
		}

	}

}

	public static void main(String[] args) {
		int[] vDatos;
		int[][] mDatos = new int[valor.values().length][5];
		vDatos = dameDatos();
		mDatos[vDatos[0] - 1][vDatos[1] - 1] = vDatos[2];

		for (int i = 0; i < mDatos.length; i++) {
			System.out.printf("Fila N° %d %n", i);
			for (int y = 0; y < mDatos[i].length; y++) {
				System.out.printf("Columna N° %d = Valor %d %n", y, mDatos[i][y]);
			}
		}

```
## ENUM ARRAY 
``` java
// usar el enum para recorrer 
		int i = 1;
		for (Mes mes : Mes.values()) {
			System.out.println(i);
			i++;
		}
// enum a String
mes.Enero.toString()

// obtener longitud de los ENUM 
		System.out.println(valor.values().length);}
// obtener indice de los ENUM 
		System.out.println(valor.VALOR100.ordinal());
```

## INCIALIZAR TDAS 
```JAVA
private ListaOrdenada<Key, Objeto> nombreDeLista = new ListaOrdenadasDeJuegosPorPrecio();
private Cola<String> nombreDeCola= new ColaNodos<>();
private Pila<String> nombreDePila= new PilaNodos<>();;
```

## RECORRER COLA

```JAVA
private void recorrerCola() {
		String centinela = null;

		cola.add(centinela);
		String aux = this.cola.remove();

		while (aux != centinela) {
			System.out.println(aux);
			this.cola.add(aux);
			aux = this.cola.remove();
		}
	}
// 2do parcial

	private void listarErroresOcurridos() {
		System.out.println("--------------------------------------");
		System.out.println("Pedidos con error");
		String centinela = null;

		pedidosConError.add(centinela);
		String aux = this.pedidosConError.remove();

		while (aux != centinela) {
			System.out.println(aux);
			this.pedidosConError.add(aux);
			aux = this.pedidosConError.remove();
		}
  }
```


## RECORRER PILA
```JAVA
public void recorrerPila(){
    	pilaAux = new PilaNodos<Elemento>();
    	ele = new Elemento();
    	while(!pilaElementos.isEmpty()){
    		ele = pilaElementos.desapilar();
    				// acá va la logica de lo que sea que quieras hacer con este recorrido
    				pilaAux.apilar(ele);
    		}
    	while(!pilaAux.isEmpty()){
    		pilaElementos.apilar(pilaAux.desapilar());
    		}
    	}
```


## LISTAS ORDENADAS COMPARE

```JAVA
// float
public class ListaOrdenadax extends ListaOrdenadaNodos<Key, Objeto> {
    @Override
    public int compare(Objeto dato1, Objeto dato2) {
        return this.compareByKey(dato1.getPrecioDeVenta(), dato2);
    }

    @Override
    public int compareByKey(Key clave, Objeto elemento) {
        return Float.compare(clave, elemento.getPrecioDeVenta());
    }

// forma ascendente
public class ListaOrdenadax extends ListaOrdenadaNodos<Integer, Objeto> {
    @Override
    public int compare(Objeto dato1, Objeto dato2) {
        return dato1.getInt() - dato2.getInt();
    }

    @Override
    public int compareByKey(Int clave, Objeto elemento) {
        return clave - elemento.getInt();
    }

// forma descendente
public class ListaOrdenadax extends ListaOrdenadaNodos<Integer, Objeto> {
    @Override
    public int compare(Objeto dato1, Objeto dato2) {
        return -(dato1.getInt() - dato2.getInt());
    }

    @Override
    public int compareByKey(Int clave, Objeto elemento) {
        return -(clave - elemento.getInt());
    }
// string
public class OrdenadaPorString extends ListaOrdenada<String, Elemento> { 
  @Override public int compare(Elemento elemento1, Elemento elemento2) { 
    return elemento1.getClave().compareTo(elemento2.getClave()); 
    } 
  @Override public int compareByKey(String clave, Elemento elemento) { 
    return clave.compareTo(elemento.getClave()); 
    } 
  }
```

## BUSCAR EN LISTA ORDENADA
```java
// el search recibe como parametro la key y te retorna el elemento si lo encuentra, sino null.
lista.search(Key);

// buscar con un while
		while (idx < listaDeJuegosPorPrecio.size()
				&& listaDeJuegosPorPrecio.get(idx).getPrecioDeVenta() <= precioMaximo) {
			juego = listaDeJuegosPorPrecio.get(idx);

			if (juego.getPrecioDeVenta() >= precioMinimo) {
				cantidad++;
			}
			idx++;
		}
```

## EXCEPCIONES CON MENSAJES
```java

	private static final String MSG_JUEGO_NULO = "No se pudo fabricar Juego o Cupon nulo.";
	private static final String MSG_TIPO_DE_JUEGO = "Error de parametros incorporando tipos de juegos";
	private static final String MSG_TOTALES = "La venta total fue: $%8.2f\n";
	public static final String MENSAJE_FABRICA_POR_TIPO = "Se han fabricado: %d RPG, %d Aventura, %d Plataformas y %d Carreras\n";

// lanzar excepciones y guardar el mesaje en una cola.
		if (juego == null || cupon == null) {
			this.pedidosConError.add(MSG_JUEGO_NULO);
			throw new RuntimeException(MSG_JUEGO_NULO);
		}

		if (!veritificarStockDeCupones(cupon, juego.getTipo())) {
			String mensaje = "No se pudo ingresar " +  juego.getClass().getSimpleName() + " por falta de cupon " + cupon.getNombre();
			this.pedidosConError.add(mensaje);
			throw new RuntimeException(mensaje);
		}
		if (cupon == null || tipoDeJuego == null || cantidad < 1) {
			throw new RuntimeException(MSG_TIPO_DE_JUEGO);
		}

    // EN EL TEST

    private static void ingresoNulo(TiendaDeJuegos laTiendaDeJuegos, Cupon cupon) {
		try {
			laTiendaDeJuegos.ingresarPedido(null, cupon);
		} catch (Exception exception) {
			System.out.println(exception.getMessage());
		}
	}

	private static void pedirJuegoClasico(TiendaDeJuegos laTiendaDeJuegos, String nombre, float costoBase, float porcentajeGanancia,
										  TipoDePlataforma tipoDePlataforma, Cupon cupon, TipoDeJuego tipoDeJuego) {
		try {
			laTiendaDeJuegos.ingresarPedido(new JuegoClasico(nombre, costoBase, porcentajeGanancia, tipoDePlataforma, tipoDeJuego), cupon);
		} catch (Exception exception) {
			System.out.println(exception.getMessage());
		}
	}

	private static void pedirJuegoEdicionEspecial(TiendaDeJuegos laTiendaDeJuegos, String nombre, float costoBase, float porcentajeGanancia,
												  int anioLanzamiento, ContenidoAdicional contenidoAdicional, Cupon cupon, TipoDeJuego tipoDeJuego) {
		try {
			laTiendaDeJuegos.ingresarPedido(new JuegoEdicionEspecial(nombre, costoBase, porcentajeGanancia, anioLanzamiento, contenidoAdicional, tipoDeJuego),
					cupon);
		} catch (Exception exception) {
			System.out.println(exception.getMessage());
		}
	}

	private static void pedirJuegoMultijugador(TiendaDeJuegos laTiendaDeJuegos, String nombre, float costoBase, float porcentajeGanancia,
											   long cantidadJugadores, ContenidoAdicional contenidoAdicional, Cupon cupon, TipoDeJuego tipoDeJuego) {
		try {
			laTiendaDeJuegos.ingresarPedido(new JuegoMultijugador(nombre, costoBase, porcentajeGanancia, cantidadJugadores, contenidoAdicional, tipoDeJuego),
					cupon);
		} catch (Exception exception) {
			System.out.println(exception.getMessage());
		}
	}

```

