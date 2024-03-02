# Metodos-Numericos
Hola Hola 

Bienvenidos al tema dos de Metodos Numericos. Where we learn some thing about bisección , regla falta, interpolación, secante.

Bisección:
	
 El método de Bisección está basado en un concepto muy sencillo, que consiste en tomar un intervalo que encierre la raíz que deseamos calcular, luego subdivimos dicho intervalo por la mitad y tomamos el sub-intervalo que contiene la raíz, descartando la otra mitad que no la contiene.
 
 Example 1:

package ejpackage bisecej2;

import java.util.function.Function;

public class Bisecej2 {


 public static void main(String[] args) {
//       
//        Function<Double, Double> function = x -> x * x - 4;
        Function<Double, Double> function = x -> x + 2 * x * x;

        double a = 0;
        double b = 2;

        double root = bisection(function, a, b, 0.0001);
        System.out.println("La raíz es aproximadamente: " + root);
    }

    public static double bisection(Function<Double, Double> function, double a, double b, double tolerance) {
        double fa = function.apply(a);
        double fb = function.apply(b);

        if (fa * fb > 0) {
            throw new IllegalArgumentException("La función no cambia de signo en el intervalo dado.");
        }

        while ((b - a) / 2.0 > tolerance) {
            double c = (a + b) / 2.0;
            double fc = function.apply(c);

            if (fc == 0.0) {
                return c;
            } else if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }

        return (a + b) / 2.0;
    
    }
    
}
 
 
 Example 2:

 /*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package bisecj3;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Bisecj3 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
       
      Function<Double, Double> function = x -> x + 2 * x / x;

        double a = 3;
        double b = 0;

        double root = bisection(function, a, b, 0.0001);
        System.out.println("La raíz es aproximadamente: " + root);
    }

    public static double bisection(Function<Double, Double> function, double a, double b, double tolerance) {
        double fa = function.apply(a);
        double fb = function.apply(b);

        if (fa * fb > 0) {
            throw new IllegalArgumentException("La función no cambia de signo en el intervalo dado.");
        }

        while ((b - a) / 2.0 > tolerance) {
            double c = (a + b) / 2.0;
            double fc = function.apply(c);

            if (fc == 0.0) {
                return c;
            } else if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }

        return (a + b) / 2.0;
    
    }
    
}
 
 Example 3:

 /*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package bisecej4;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Bisecej4 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
      Function<Double, Double> function = x -> x + 9/x *x*x/x;

        double a = 0;
        double b = 2;

        double root = bisection(function, a, b, 0.0001);
        System.out.println("La raíz es aproximadamente: " + root);
    }

    public static double bisection(Function<Double, Double> function, double a, double b, double tolerance) {
        double fa = function.apply(a);
        double fb = function.apply(b);

        if (fa * fb > 0) {
            throw new IllegalArgumentException("La función no cambia de signo en el intervalo dado.");
        }

        while ((b - a) / 2.0 > tolerance) {
            double c = (a + b) / 2.0;
            double fc = function.apply(c);

            if (fc == 0.0) {
                return c;
            } else if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }

        return (a + b) / 2.0;
    
    }
    
}
 Example 4:

 /*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package bisec5;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Bisec5 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
   Function<Double, Double> function = x -> x + 45 * x / x*x*x;

        double a = 0;
        double b = 2;

        double root = bisection(function, a, b, 0.0001);
        System.out.println("La raíz es aproximadamente: " + root);
    }

    public static double bisection(Function<Double, Double> function, double a, double b, double tolerance) {
        double fa = function.apply(a);
        double fb = function.apply(b);

        if (fa * fb > 0) {
            throw new IllegalArgumentException("La función no cambia de signo en el intervalo dado.");
        }

        while ((b - a) / 2.0 > tolerance) {
            double c = (a + b) / 2.0;
            double fc = function.apply(c);

            if (fc == 0.0) {
                return c;
            } else if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
        }

        return (a + b) / 2.0;
    
    }
    
}

 Regla Falsa:

 El método de la regula falsi (regla del falso) o falsa posición es un método iterativo de resolución numérica de ecuaciones no lineales

 Example 1:

 package ejercicio2;

import java.util.function.Function;

public class Ejercicio2 {
        public static double funcion(double x) {
        return Math.pow(x, 6) - 3;
    }

    public static double reglaFalsa(double a, double b, Function<Double, Double> f, double errorTolerado) {
        double c = 0;
        double fa = f.apply(a);
        double fb = f.apply(b);
        double fc = 0; 
        double error = 0; 
  
        if (fa * fb > 0) { 
            System.out.println("No hay cambio de signo en el intervalo dado.");
            return Double.NaN;
        } 

        
        do {
            c = (a * fb - b * fa) / (fb - fa);
            fc = f.apply(c);

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
            error = Math.abs(fc);
        } while (error >= errorTolerado);

        return c; 
    }

    public static void main(String[] args) {
        double a = 1; //izquierdo
        double b = 3; // derecho
        double errorTolerado = 0.0001; 

        
        double raiz = reglaFalsa(a, b, Ejercicio2::funcion, errorTolerado);
        if (!Double.isNaN(raiz)) {
            System.out.println("Aproximación de la raíz: " + raiz); 
        }
    }
}


 
 Example 2:

 package regfalsa2;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Regfalsa2 {

    /**
     * @param args the command line arguments
     */
    public static double funcion(double x) {
        return Math.pow(x, 8) - 1;
    }

    public static double reglaFalsa(double a, double b, Function<Double, Double> f, double errorTolerado) {
        double c = 0;
        double fa = f.apply(a);
        double fb = f.apply(b);
        double fc = 0; 
        double error = 0; 
  
        if (fa * fb > 0) { 
            System.out.println("No hay cambio de signo en el intervalo dado.");
            return Double.NaN;
        } 

        
        do {
            c = (a * fb - b * fa) / (fb - fa);
            fc = f.apply(c);

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
            error = Math.abs(fc);
        } while (error >= errorTolerado);

        return c; 
    }

    public static void main(String[] args) {
        double a = 1; //izquierdo
        double b = 3; // derecho
        double errorTolerado = 0.0001; 

        
        double raiz = reglaFalsa(a, b, Regfalsa2::funcion, errorTolerado);
        if (!Double.isNaN(raiz)) {
            System.out.println("Aproximación de la raíz: " + raiz); 
        }
    }
}




 Example 3:

 package regfalsa3;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class RegFalsa3 {

    /**
     * @param args the command line arguments
     */
    public static double funcion(double x) {
        return Math.pow(x, 9) - 3;
    }

    public static double reglaFalsa(double a, double b, Function<Double, Double> f, double errorTolerado) {
        double c = 0;
        double fa = f.apply(a);
        double fb = f.apply(b);
        double fc = 0; 
        double error = 0; 
  
        if (fa * fb > 0) { 
            System.out.println("No hay cambio de signo en el intervalo dado.");
            return Double.NaN;
        } 

        
        do {
            c = (a * fb - b * fa) / (fb - fa);
            fc = f.apply(c);

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
            error = Math.abs(fc);
        } while (error >= errorTolerado);

        return c; 
    }

    public static void main(String[] args) {
        double a = 1; //izquierdo
        double b = 3; // derecho
        double errorTolerado = 0.0001; 

        
        double raiz = reglaFalsa(a, b, RegFalsa3::funcion, errorTolerado);
        if (!Double.isNaN(raiz)) {
            System.out.println("Aproximación de la raíz: " + raiz); 
        }
    }
}




 Example 4:

 package regfalsa4;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Regfalsa4 {

    /**
     * @param args the command line arguments
     */
    public static double funcion(double x) {
        return Math.pow(x, 9) +2;
    }

    public static double reglaFalsa(double a, double b, Function<Double, Double> f, double errorTolerado) {
        double c = 0;
        double fa = f.apply(a);
        double fb = f.apply(b);
        double fc = 0; 
        double error = 0; 
  
        if (fa * fb > 0) { 
            System.out.println("No hay cambio de signo en el intervalo dado.");
            return Double.NaN;
        } 

        
        do {
            c = (a * fb - b * fa) / (fb - fa);
            fc = f.apply(c);

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
            error = Math.abs(fc);
        } while (error >= errorTolerado);

        return c; 
    }

    public static void main(String[] args) {
        double a = 1; //izquierdo
        double b = 3; // derecho
        double errorTolerado = 0.0001; 

        
        double raiz = reglaFalsa(a, b, Regfalsa4::funcion, errorTolerado);
        if (!Double.isNaN(raiz)) {
            System.out.println("Aproximación de la raíz: " + raiz); 
        }
    }
}

 Example 5: 

package regfalsa5;

import java.util.function.Function;

/**
 *
 * @author benit
 */
public class Regfalsa5 {

    /**
     * @param args the command line arguments
     */
   public static double funcion(double x) {
        return Math.pow(x, 12)-3;
    }

    public static double reglaFalsa(double a, double b, Function<Double, Double> f, double errorTolerado) {
        double c = 0;
        double fa = f.apply(a);
        double fb = f.apply(b);
        double fc = 0; 
        double error = 0; 
  
        if (fa * fb > 0) { 
            System.out.println("No hay cambio de signo en el intervalo dado.");
            return Double.NaN;
        } 

        
        do {
            c = (a * fb - b * fa) / (fb - fa);
            fc = f.apply(c);

            if (fa * fc < 0) {
                b = c;
                fb = fc;
            } else {
                a = c;
                fa = fc;
            }
            error = Math.abs(fc);
        } while (error >= errorTolerado);

        return c; 
    }

    public static void main(String[] args) {
        double a = 1; //izquierdo
        double b = 3; // derecho
        double errorTolerado = 0.0001; 

        
        double raiz = reglaFalsa(a, b, Regfalsa5::funcion, errorTolerado);
        if (!Double.isNaN(raiz)) {
            System.out.println("Aproximación de la raíz: " + raiz); 
        }
    }
}


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




