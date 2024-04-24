// Definición de estructuras para cada producto

#define push_button1 2 //Definimos pin2 para un pulsador 
#define push_button2 3 //Definimos pin3 para un pulsador
#define configPin(pin) pinMode(pin, INPUT)  //Definimos pinMode(pin, INPUT) como configPin(pin)
#define caracter_limit char //Definimos char como caracter_limit
#define struct_code struct //Definimos struct como struct_code 
#define duration delay //Definimos delay como duration
#define print_on_the_same_line Serial.print //definimos Serial.print como print_on_the_same_line
#define print_on_another_line Serial.println //Definimos Serial.println como print_on_another_line
#define condition_if if //Definimos if como condition_if
#define condition_else else //Definimos else como condition_else
#define loop_function void loop //Definimos void loop como function_loop
#define setup_function void setup //Definimos void setup como condition_setup
#define activate_serial_monitor Serial.begin(9600); //Definimos Serial.begin(96009; como activate_serial_monitor
#define read_pin2 digitalRead(2) == HIGH
#define read_pin3 digitalRead(3) == HIGH




struct_code Producto {  //Usamos este comando para escructurar el codigo junto con palabra clave
  caracter_limit nombre[50];  //Damos valores
  byte cantidad;  //Comando para ajustar a futuro las cantidades
  float precio; //Comando para ajustar a futuro los prtecios
  
};


Producto producto1 = {"Galleta CanCan", 25, 12.00};  //Asignamos identificador nombre, cantidad y precio
Producto producto2 = {"Snickers", 25, 11.90};  //Asignamos identificador nombre, cantidad y precio
Producto producto3 = {"Kinder Sorpresa", 25, 17.25};   //Asignamos identificador nombre, cantidad y precio
Producto producto4 = {"Quesifritos", 25, 6.41};  //Asignamos identificador nombre, cantidad y precio



byte X = 1; //Usamos variable con una union con byte
bool Y = true; //Usamos variable con una union con bool



setup_function() { //Usamos esta funcion pàra configurar nuestro codigo e instrucciones
  activate_serial_monitor //Activamos monitor serial
  print_on_another_line("----------------------------------------------------------"); //Mostrar texto de separacion
  print_on_another_line("**********************************************************"); //Mostrar texto de separacion
  print_on_another_line("----------------------------------------------------------"); //Mostrar texto de separacion
  print_on_another_line("Maquina Expendedora"); //Mostrar texto
  print_on_another_line("Bienvenido"); // Mensaje de bienvenida
  print_on_another_line("Pulsador de la izquierda para retroceder, pulsador de la derecha para avanzar"); //Mostrar texto

  configPin(push_button1); //Configuramos pin2 como entrada
  configPin(push_button2); //Configuramos pin3 como entrada
  
}




loop_function() { //Usamos esta funcion para dar un bucle o ciclo de repeticion a nuestro codigo
  
  condition_if (Y) { //Añadimos una condicion
    
    print_on_the_same_line("Producto: "); //Mostrar texto
    condition_if (X == 1) { 
      print_on_another_line(producto1.nombre); //Ubicamos donde poner los textos
      print_on_the_same_line("Cantidad: "); //Mostrar texto
      print_on_another_line(producto1.cantidad); //Ubicamos donde poner los textos
      print_on_the_same_line("Precio: Q"); //Mostrar texto
      print_on_another_line(producto1.precio, 2); //Ubicamos donde poner los textos
      Serial.println("----------------------------------------------------------"); //Mostrar texto de separacion
      
     
    }
    
    condition_if (X == 2) {
      print_on_another_line(producto2.nombre); //Ubicamos donde poner los textos
      print_on_the_same_line("Cantidad: "); //Mostrar texto
      print_on_another_line(producto2.cantidad); //Ubicamos donde poner los textos
      print_on_the_same_line("Precio: Q"); //Mostrar texto
      print_on_another_line(producto2.precio, 2); //Ubicamos donde poner los textos
      print_on_another_line("----------------------------------------------------------"); //Mostrar texto de separacion
    }
    condition_if (X == 3) {
      print_on_another_line(producto3.nombre); //Ubicamos donde poner los textos
      print_on_the_same_line("Cantidad: "); //Mostrar texto
      print_on_another_line(producto3.cantidad); //Ubicamos donde poner los textos
      print_on_the_same_line("Precio: Q"); //Mostrar texto
      print_on_another_line(producto3.precio, 2);  //Ubicamos donde poner los textos
      print_on_another_line("----------------------------------------------------------");//Mostrar texto de separacion
    }
    condition_if (X == 4) {
      print_on_another_line(producto4.nombre); //Ubicamos donde poner los textos
      print_on_the_same_line("Cantidad: "); //Mostrar texto
      print_on_another_line(producto4.cantidad); //Ubicamos donde poner los textos
      print_on_the_same_line("Precio: Q"); //Mostrar texto
      print_on_another_line(producto4.precio, 2);  //Ubicamos donde poner los textos 
      print_on_another_line("----------------------------------------------------------");//Mostrar texto de separacion
    }
    
    Y = false; //Denominamos variable
    
  }
 
  condition_if (read_pin2) { //Usamos condicion y lectura del pin
    duration(50); //Empleamos tiempo para evitar rebotes
   condition_if (X < 4) { //Usamos otra condicion
      X++;  //Usamos variable mas condicion
    } condition_else { //Usamos otra condicion
      X = 1; //Usamos variable
     }
     
    
    Y = true; //Usamos otra variable
     
  }
    
    
  
  
  condition_if (read_pin3) { //Usamos condicion y lectura del pin
    duration(100); //Empleamos tiempo para evitar rebotes
    condition_if (X > 1) { //Usamos otra condicion
      X--; //Usamos variable
   }  condition_else { //Usamos otra condicion
      X = 4; //Usamos variable
      }
    
    
    Y = true; //Usamos variable y condicion true
  
  }
  
  duration(50); //Añadimos tiempo para evitar falsos pulsos
  
}
