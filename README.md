# Metodos-Numericos
Hola Hola 

Bienvenidos al tema dos de Metodos Numericos. Where we learn some thing about bisección , regla falta, interpolación, secante.

Bisección:
	
 El método de Bisección está basado en un concepto muy sencillo, que consiste en tomar un intervalo que encierre la raíz que deseamos calcular, luego subdivimos dicho intervalo por la mitad y tomamos el sub-intervalo que contiene la raíz, descartando la otra mitad que no la contiene.
 
[Ejemplo 1](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/6fccdafdf0d913a4adbcd4b09475be611fec0bb1/Bisecci%C3%B3n%20ejemplo%201)




[Ejemplo 2](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/245a6a7f0f2eb9a8aa7192720499bac3c55f5e52/bisecci%C3%B3n%202)


[Ejemplo 3](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/111acab745bb8982b07a83116d0e999d4d7eb133/bisection%203)

[Ejemplo 4](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/7a1a6ce0680f3a570a0cf4d19629008a95e9216e/bisection%204)



 Regla Falsa:

 El método de la regula falsi (regla del falso) o falsa posición es un método iterativo de resolución numérica de ecuaciones no lineales
  
[Ejemplo 1]( https://github.com/Wenceslaobeni/Metodos-Numericos/blob/ac9bb5d837dcbba38aac88e5b101c79bb52e0f18/regla%20falsa%201)




[Ejemplo 2](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/33ad7f084e0d2daaada59971dd95b54581476e82/regla%20falsa%202)


[Ejemplo 3](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/decd7cac7cfeeff3362ae624eea6b86745d50727/regla%20falsa%202)

[Ejemplo 4](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/7cd7fa77d0a9f838031272470346e2867685d093/regla%20falsa%204)
[Ejemplo 5](https://github.com/Wenceslaobeni/Metodos-Numericos/blob/684b720042e6a23a0a421075951d439035f3bad5/relga%20falsa%205)


 Interpolación:

 El método de Newton-Raphson, permite hallar una raíz de una ecuación no-lineal siempre y cuando se parta de una buena estimación inicial de la misma.

 
 Example 1:

 package ejercicio3;

public class Ejercicio3 {
public static double funcion(double x) {
        return Math.sin(x);  
    }
   
    public static double newtonRaphson(double xInicial, double tolerancia) {
        double xActual = xInicial;

        do {
         
            double valorFuncion = funcion(xActual);
           
            double pendienteFuncion = 2 * xActual;
            
          
            double xSiguiente = xActual - valorFuncion / pendienteFuncion;
            
            // Actualizamos el valor de xActual
            xActual = xSiguiente;
            
        } while (Math.abs(funcion(xActual)) > tolerancia); 

        return xActual; 
    }

    public static void main(String[] args) {
        double xInicial = 5.0; 
        double tolerancia = 0.0001; 
        double raiz = newtonRaphson(xInicial, tolerancia);
        
        System.out.println("La raíz encontrada es: " + raiz);
    }     
}
 
 Example 2:

 package newton2;

/**
 *
 * @author benit
 */
public class Newton2 {

    /**
     * @param args the command line arguments
     */
  public static double funcion(double x) {
        return Math.sin(x-3);  
    }
   
    public static double newtonRaphson(double xInicial, double tolerancia) {
        double xActual = xInicial;

        do {
         
            double valorFuncion = funcion(xActual);
           
            double pendienteFuncion = 2 * xActual;
            
          
            double xSiguiente = xActual - valorFuncion / pendienteFuncion;
            
            // Actualizamos el valor de xActual
            xActual = xSiguiente;
            
        } while (Math.abs(funcion(xActual)) > tolerancia); 

        return xActual; 
    }

    public static void main(String[] args) {
        double xInicial = 5.0; 
        double tolerancia = 0.0001; 
        double raiz = newtonRaphson(xInicial, tolerancia);
        
        System.out.println("La raíz encontrada es: " + raiz);
    }     
}
 Example 3:

 package newton3;

/**
 *
 * @author benit
 */
public class Newton3 {

    /**
     * @param args the command line arguments
     */
 public static double funcion(double x) {
        return Math.sin(x/3);  
    }
   
    public static double newtonRaphson(double xInicial, double tolerancia) {
        double xActual = xInicial;

        do {
         
            double valorFuncion = funcion(xActual);
           
            double pendienteFuncion = 2 * xActual;
            
          
            double xSiguiente = xActual - valorFuncion / pendienteFuncion;
            
            // Actualizamos el valor de xActual
            xActual = xSiguiente;
            
        } while (Math.abs(funcion(xActual)) > tolerancia); 

        return xActual; 
    }

    public static void main(String[] args) {
        double xInicial = 5.0; 
        double tolerancia = 0.0001; 
        double raiz = newtonRaphson(xInicial, tolerancia);
        
        System.out.println("La raíz encontrada es: " + raiz);
    }     
}

 Example 4:

 package newton4;

/**
 *
 * @author benit
 */
public class Newton4 {

    /**
     * @param args the command line arguments
     */
public static double funcion(double x) {
        return Math.sin(x*2);  
    }
   
    public static double newtonRaphson(double xInicial, double tolerancia) {
        double xActual = xInicial;

        do {
         
            double valorFuncion = funcion(xActual);
           
            double pendienteFuncion = 2 * xActual;
            
          
            double xSiguiente = xActual - valorFuncion / pendienteFuncion;
            
            // Actualizamos el valor de xActual
            xActual = xSiguiente;
            
        } while (Math.abs(funcion(xActual)) > tolerancia); 

        return xActual; 
    }

    public static void main(String[] args) {
        double xInicial = 5.0; 
        double tolerancia = 0.0001; 
        double raiz = newtonRaphson(xInicial, tolerancia);
        
        System.out.println("La raíz encontrada es: " + raiz);
    }     
}


 Example 5: 

 package newton5;

/**
 *
 * @author benit
 */
public class Newton5 {

    /**
     * @param args the command line arguments
     */
public static double funcion(double x) {
        return Math.sin(x*2/3);  
    }
   
    public static double newtonRaphson(double xInicial, double tolerancia) {
        double xActual = xInicial;

        do {
         
            double valorFuncion = funcion(xActual);
           
            double pendienteFuncion = 2 * xActual;
            
          
            double xSiguiente = xActual - valorFuncion / pendienteFuncion;
            
            // Actualizamos el valor de xActual
            xActual = xSiguiente;
            
        } while (Math.abs(funcion(xActual)) > tolerancia); 

        return xActual; 
    }

    public static void main(String[] args) {
        double xInicial = 5.0; 
        double tolerancia = 0.0001; 
        double raiz = newtonRaphson(xInicial, tolerancia);
        
        System.out.println("La raíz encontrada es: " + raiz);
    }     
}
 Secante

 El método de la secante es un método para encontrar los ceros de una función de forma iterativa.

  Example 1:

 package secej5;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Secej5 {

    /**
     * @param args the command line arguments
     */
 public static double findRoot(Function<Double, Double> function, double x0, double x1, double tolerance, int maxIterations) {
        double x2 = 0;
        int iterations = 0;
        
        do {
            x2 = x1 - ((function.apply(x1) * (x1 - x0)) / (function.apply(x1) - function.apply(x0)));
            x0 = x1;
            x1 = x2;
            iterations++;
        } while (Math.abs(function.apply(x2)) > tolerance && iterations < maxIterations);
        
        return x2;
    }

    public static void main(String[] args) {
        
        Function<Double, Double> function = x -> x /34*x; 
        
        double x0 = 0.5;
        double x1 = 1.0;
        
        double tolerance = 0.0001;
        int maxIterations = 1000; 
        
        double root = findRoot(function, x0, x1, tolerance, maxIterations);
        
        System.out.println("Raíz encontrada: " + root);
    }    
}

 Example 2:

 package secejr2;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Secejr2 {

    /**
     * @param args the command line arguments
     */
   
        // TODO code application logic here
 public static double findRoot(Function<Double, Double> function, double x0, double x1, double tolerance, int maxIterations) {
        double x2 = 0;
        int iterations = 0;
        
        do {
            x2 = x1 - ((function.apply(x1) * (x1 - x0)) / (function.apply(x1) - function.apply(x0)));
            x0 = x1;
            x1 = x2;
            iterations++;
        } while (Math.abs(function.apply(x2)) > tolerance && iterations < maxIterations);
        
        return x2;
    }

    public static void main(String[] args) {
        
        Function<Double, Double> function = x -> x * x - 3; 
        
        double x0 = 0.5;
        double x1 = 1.0;
        
        double tolerance = 0.0001;
        int maxIterations = 1000; 
        
        double root = findRoot(function, x0, x1, tolerance, maxIterations);
        
        System.out.println("Raíz encontrada: " + root);
    }    
}

 Example 3:

 package secejr3;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Secejr3 {

    /**
     * @param args the command line arguments
     */
   public static double findRoot(Function<Double, Double> function, double x0, double x1, double tolerance, int maxIterations) {
        double x2 = 0;
        int iterations = 0;
        
        do {
            x2 = x1 - ((function.apply(x1) * (x1 - x0)) / (function.apply(x1) - function.apply(x0)));
            x0 = x1;
            x1 = x2;
            iterations++;
        } while (Math.abs(function.apply(x2)) > tolerance && iterations < maxIterations);
        
        return x2;
    }

    public static void main(String[] args) {
        
        Function<Double, Double> function = x -> x - 20; 
        
        // Definir los puntos iniciales  
        double x0 = 0.5;
        double x1 = 1.0;
        
        // Definir la tolerancia y el número máximo de iteraciones
        double tolerance = 0.0001;
        int maxIterations = 1000; 
        
        // Encontrar la raíz
        double root = findRoot(function, x0, x1, tolerance, maxIterations);
        
        // Imprimir el resultado
        System.out.println("Raíz encontrada: " + root);
    }    
}

 Example 4:

 package secejr4;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Secejr4 {

    /**
     * @param args the command line arguments
     */
public static double findRoot(Function<Double, Double> function, double x0, double x1, double tolerance, int maxIterations) {
        double x2 = 0;
        int iterations = 0;
        
        do {
            x2 = x1 - ((function.apply(x1) * (x1 - x0)) / (function.apply(x1) - function.apply(x0)));
            x0 = x1;
            x1 = x2;
            iterations++;
        } while (Math.abs(function.apply(x2)) > tolerance && iterations < maxIterations);
        
        return x2;
    }

    public static void main(String[] args) {
        
        Function<Double, Double> function = x -> x * x+ 43; 
        
        double x0 = 0.5;
        double x1 = 1.0;
        
        double tolerance = 0.0001;
        int maxIterations = 1000; 
        
        double root = findRoot(function, x0, x1, tolerance, maxIterations);
        
        System.out.println("Raíz encontrada: " + root);
    }    
}
 Example 5: 




