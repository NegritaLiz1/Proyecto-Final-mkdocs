# ALARMA INTEGRADA CON CÓDIGO DE SEGURIDAD REPRESENTADA EN UN CIRCUITO

Para el diseño de este circuito utilizaremos los programas Proteus y Pic C Copiler, ya que nos seran de suma importancia para ejecutar la idea que busca  poner en marcha el inicio de un sistema de seguridad creado en base a un prototipo de simulación que determinará la mayoria de los componentes necesarios para replicarlos físicamente, debido a que, al ser una simulación en un programa varía significativamente ciertos valores y componentes con respecto al circuito físico.

* Pic C Copiler

![Visualización](https://automatizacionduoc.files.wordpress.com/2017/09/images.jpg)

Clic para más información sobre este programa. [Más información](http://codigoelectronica.com/blog/introduccion-a-pic-c-compiler).

* Proteus

![Visualización](https://softwaredescargas.com/wp-content/uploads/2021/08/proteus-professional-v810-sp0-build-292030-espanol.webp.webp)

Clic para más información sobre este programa. [Más información](https://www.hubor-proteus.com/proteus-pcb/proteus-pcb/2-proteus.html).

Este diseño comenzó con la elección de un microcontrolador para determinar la funcionalidad de cada componente conectado mediante sus puertos, cada pin seleccionado deberá cumplir la función de conectarse a la alarma que suena cuando hay un error de clave, a un LCD que imprime la información en donde indica que se debe ingresar un número, el teclado por donde se inserta la clave, resistencias, capacitores y un crystal que determinan el paso de frecuencia y corriente entre todo el circuito.

## MATERIALES

    *PIC16F877A
    *1 Cristal (4MHz)
    *2 capacitores (22pF) y un capacitor de cerámica (10u)
    *1 resistencia (330)
    *LCD 16x2
    *Teclado matricial
    *LED
    *LED ROJA


Comenzamos armando el circuito en Proteus utilizando los componenetes detallados en la siguiente imagen, así como, también, empezamos a conectarlos estructurando sus puertos a las entradas tando de la alarma, el LCD y teclado.

![Visualización](https://scontent.floh3-1.fna.fbcdn.net/v/t39.30808-6/277757930_513559650388346_7949498111047992871_n.jpg?_nc_cat=104&ccb=1-5&_nc_sid=730e14&_nc_eui2=AeFd1p-CVJfgLToUH3AIvwwy-gRyoWEagN_6BHKhYRqA39wZNsborwCwF8DfmBLKjuxcrgCYhIm4GZ0D-dSvlURC&_nc_ohc=6n1Wp4kPeEsAX8l3Z1o&_nc_ht=scontent.floh3-1.fna&oh=00_AT-4iT9tCp-7-r29NAx8OL4E70fRmZRerB96OdvrIeDefw&oe=624D108A)

Utlizamos el puerto_d para asignarlo a la conexion hecha con el LCD, todos los pines del puerto D fueron utilizados exepto el pin D3.
El puerto_b fue utilizado para conectar sus pines con los pines del teclado matricial.
Del puerto_a se seleccionó el pin A0 y A1 para la conexion de la alarma, obteniendo el siguiete resultado.

![Visualización](https://scontent.floh3-1.fna.fbcdn.net/v/t39.30808-6/277753995_513558457055132_1712395369225395010_n.jpg?_nc_cat=106&ccb=1-5&_nc_sid=730e14&_nc_eui2=AeF1E9wYBSbZgl7Cn98g2Gp4_In3hMWIDwT8ifeExYgPBF-0N4pFI4GrSKttVy4ciIPcYlUxwJQoZChDi5ulKI34&_nc_ohc=Fjtnp8HIoOwAX-sKA6Y&_nc_ht=scontent.floh3-1.fna&oh=00_AT8FG_QQuoVwyiFvTNN5PQGD_CUZmAeT-1TeKjRgLGVCIQ&oe=624CDAC0)

«En esta imagen se presenta la primera fase de ejecución de la alarma, en donde en la pantalla LCD se muestra la informacion que indica que debe ingresar un dígito, en este caso la clave consta de tres números los cuales al ingresarlos no se visualizaran por seguridad, solo se visualizará el conteo de los números ingresados.»

![Visualización](https://scontent.floh3-1.fna.fbcdn.net/v/t39.30808-6/277817462_513557207055257_8112643043527306654_n.jpg?_nc_cat=108&ccb=1-5&_nc_sid=730e14&_nc_eui2=AeH59p_AcEsKemHcQJWBU4hHfVyNCTXTKrt9XI0JNdMqu-8td83zXbmhie5UAwfIewCkNv_6JHxoP_1Igsc5jQ56&_nc_ohc=g8wzfTz5ZmgAX94Biuc&tn=ZY6xOTCubUHLZPh0&_nc_ht=scontent.floh3-1.fna&oh=00_AT-3-1mx47EY28oobNlU_x891JNrzF3Diw_lAnBTim3w8g&oe=624C10E7)

«En esta imagen se muestra que de haber ingresado el código de la clave correcto la puerta se abre.»

![Visualización](https://scontent.floh3-1.fna.fbcdn.net/v/t39.30808-6/277737324_513557347055243_9185056387977982653_n.jpg?_nc_cat=111&ccb=1-5&_nc_sid=730e14&_nc_eui2=AeEwY-Sp-jL2WbH_XWDuanGdlt3sGyZsPZiW3ewbJmw9mGajPB9-QXsSQ07gbrPr7Ugkhyc0e8v4JciFG5g-rwWC&_nc_ohc=LUkn6Xt3nycAX-DPzOT&_nc_ht=scontent.floh3-1.fna&oh=00_AT-OxZUVdHDIKrozPR2CknqOBO6K_H_boBGA7xJStXSbIg&oe=624BB550)

«En esta imagen se muestra que de haber ingresado el código de la clave incorrectamente la puerta se bloquea y la alarma comienza a sonar.»

Todo este circuito no tendría vida de no ser por las funciones que se les asigne a través del microcontrolador, dichas funciones no son más que el resultado de programar código que especifica las acciones a realizarse.

### Código C utilizado para la copilación

     #include <16f877A.h>                             //Incluye la librería del PIC16F877A
     #fuses XT,NOWDT,NOPROTECT,NOLVP                  //Configuración de fusibles.
     #use delay(clock= 4000000)                       //FOSC= 4MHz.
     #define use_portb_kbd TRUE                       //Define el uso del puerto B para el teclado.
     #include <TONES.c>                              //Incluye la librería TONES para generar sonido.
     #include <lcd.c>                                 //Incluye librería LCD.
     #include <kbd.c>                                 //Incluye librería que maneja el teclado.
     #rom 0x2100={'3','7','5'}                        //Graba en la ROM la clave 3 7 5.
     void alarma();                                   //Define la función alarma.
     void main()
     {                                                //Función principal main.
     char k;                                         //Variable K para almacenar los datos del teclado.
     int i;                                          //Variable para contar el número de veces  que se ingresa un dato.
     char data[3], clave[3];                         //Vectores para almacenar datos del teclado y de la clave.
     lcd_init();                                     //Inicializa el LCD.
     kbd_init();                                     //Inicializa el teclado.
     port_b_pullups(TRUE);                           //Activa las resistencias PULL UP del puerto B.
     while (TRUE) {                                  //Bucle infinito.
     i=0;                                            //Variable i, para almacenar cuantas teclas se ha pulsado.
     printf(lcd_putc,"\fingrese digito 1\n");        //Pide ingresar el primer digito.
     while(i<=2){                                    
     //Mientras i menor o igual a 2.
     k=kbd_getc();                                   //Asigna a la variable k la tecla pulsada.
     if (k!=0)                                       //Si k no es igual a 0.
     {data[i]=k;                                     //almacena en el vector data[i] el dato de la tecla ingresada.
     i++;                                            //incrementa i en 1
     printf(lcd_putc,"\fingrese digito %u\n",i+1);   //ingresa la tecla según indica i.
     }
     }

     for (i=0;i<=2;i++) {                             //Bucle para leer datos de la eeprom
     clave[i]=read_eeprom(i);          
     }                        //Lee y asigna en el vector clave[i] según indica i.
                                                  //clave igual a dato ingresado... abre la
     if ((data[0]==clave[0])&&(data[1]==clave[1])&&(data[2]==clave[2])){

      printf(lcd_putc,"\fPuerta Abierta");             //Puerta abierta
     output_high(PIN_A0);                             //Señal para manejar un relé para abrir la puerta.
     delay_ms(5000); //Retardo 5 s.
     output_low(PIN_A0);}                             //Apaga puerta
     else
     {                                                   //Si no son igual dato = clave. La puerta permanece cerrada.
     printf(lcd_putc,"\fPuerta Cerrada");
     for (i=1;i<=5;i++){ //Acciona alarma
     alarma(); //Función alarma.
     }
     }
     } //Fin del bucle.
     } //Fin del main.
     void alarma     (void)                                // Función alarma. Genera sonido que simula una alarma.
     {
      int fusa=62;
      int semicorchea=125;
      int corchea=250;
      generate_tone(C_NOTE[0],fusa);
      generate_tone(C_NOTE[1],fusa);
      generate_tone(C_NOTE[3],fusa);
      generate_tone(C_NOTE[0],fusa);
      generate_tone(Eb_NOTE[1],corchea);
      generate_tone(C_NOTE[2],fusa);
      generate_tone(Eb_NOTE[3],fusa);
      generate_tone(Ab_NOTE[0],semicorchea);
      generate_tone(G_NOTE[1],semicorchea);
      generate_tone(F_NOTE[2],semicorchea);
      generate_tone(F_NOTE[3],semicorchea);
      generate_tone(Eb_NOTE[0],semicorchea);
      delay_ms(100);
      return;
      }

Código para el funcionamiento del sistema de alarma.
