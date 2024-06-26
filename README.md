<h1>DOSu! -- Manual de instrucciones</h1>

Controles: Mouse y Teclado.

<div>=====  Preparacion del Juego:  =====</div>

Se recomienda jugar DOSu! en un procesador de: 
- MINIMO: 10kHz (10000 ciclos por segundo).
- RECOMENDADO: 50kHz (50000 ciclos por segundo) o mas.

Si esta jugando en DOSBOX: Vaya al archivo de configuracion y en la seccion [cpu] debe haber
una propiedad "cycles". Debe ser o "max" o un valor mayor o igual a 50000.

El juego requiere que la interrupcion INT81RNG este instalada en memoria. El juego lo usa para
generar numeros aleatorios. El jugador primero debe ejecutar INT81RNG.COM para instalar la
interrupcion, y luego podra ejecutar el juego (MAIN.EXE).

<div>=====  Juego:  =====</div>
El juego se trata de clickear cuadrados que van apareciendo en la pantalla de forma aleatoria.
Los cuadrados pueden moverse o quedarse quietos. Los que se mueven rebotan en los bordes de
la pantalla. Los cuadrados aparecen cada vez mas rapido, para aumentar la dificultad.

El jugador empieza con 5 vidas. Los cuadrados tienen un limite de tiempo para ser clickeados, 
una vez agotado el tiempo explotan y sacan 1 vida. El juego acaba cuando el jugador pierde las
5 vidas. 
Clickear cuadrados suma puntaje. Mientras mas rapido clickee el cuadrado, mas puntaje otorga.

Tipos de cuadrados:
- Cuadrado azul: Se clickea con el boton izquierdo del mouse y da puntaje.
- Cuadrado verde: Se clickea con el boton derecho del mouse y da puntaje.
- Cuadrado violeta: NO SE CLICKEA. Si el jugador lo clickea pierde una vida.

Dificultades:
El juego tiene 3 dificultades (facil / normal / dificil). Lo que hacen es variar la velocidad de 
aparicion de los cuadrados y el limite de tiempo que tiene cada uno.

Highscores:
El juego puede guardar highscore (puntajes altos). Cuando un jugador obtiene un puntaje mas alto 
que el highscore, este puntaje reemplaza al highscore y se guarda. Para resetear el highscore 
se debe borrar el archivo "savefile.dat". El juego generara uno nuevo con 0 como highscore.

Gameover:
La pantalla de Game Over ocurre cuando el jugador pierde (se le acaban todas las vidas).
Muestra el puntaje final y el highscore. El jugador puede presionar "Q" para volver al menu,
o presionar "Espacio" para volver a intentar.

Durante el juego, el jugador puede presionar Q para volver al menu principal en cualquier momento.

<div>=====  Codigo:  =====</div>
PROGRAMAS NECESARIOS:
- Turbo Assembler (TASM.EXE)
- Turbo Linker (TLINK.EXE)
- Turbo Debugger (TD.EXE)

El codigo fuente del juego esta compuesto de varios archivos .asm: main.asm, random.asm, savefile.asm,
graphics.asm, sound.asm, strings.asm, y INT81RNG.asm. El usuario debe compilar main, random,
savefile, graphics, sound y strings con TASM y linkearlos en un solo archivo con TLINK, y compilar
y linkear INT81RNG como un ejecutable .com (tambien con TASM y TLINK).

Dentro tambien hay dos archivos por lotes llamados "make.bat" y "maked.bat". Make.bat compila 
y linkea el juego y la interrupcion, y de paso instala la interrupcion en memoria, luego el usuario
debe ejecutar MAIN.EXE.
Maked.bat compila y linkea el juego para debug, instala la interrupcion y luego debugea el juego
usando TD.

<div>===========================================</div>
Proyecto realizado por el Grupo 2 para la materia Sistema de Procesamiento de Datos en la
Universidad Nacional de San Martin.

Integrantes del grupo 2:
- Carolina Villalba
- Nelyer Narvaez
- Paulo Gaston Meira Strazzolini
- Ulises Zagare

Profesores:
- Fabio Sergio Bruschetti
- Pedro Facundo Iriso
