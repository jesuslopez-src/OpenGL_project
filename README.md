1) Clonar el repositorio.

La estructura de carpetas será la siguiente:

    |OpenGL_project
    |   |libs
    |   |include
    |   |
    |   |src
    |   |   |main.cpp
    |   |   |res
    |   |   |   |shaders
    |   |   |   |   Basic.shader

2) Descargar y compilar las librerias de GLFW y de GLEW.

En la carpeta "libs" (OpenGL_project/libs) se colocaran las librerias estáticas previamente compiladas
de GLFW y de GLEW o cualquier otra que sea necesaria colocar.

En la carpeta "include" (OpenGL_project/include) se colocaran los headers files de las librerias
que se necesiten usar así como cualquier otro header creado para el programa (si esta carpeta no existe debe crearla).
además recuerde colocar los include de GL y GLFW en subcarpetas con dichos nombres.

La carpeta "res" (OpenGL_project/src/res) guarda recursos usados por el programa como shaders
u otros.

3) Para compilar "main.cpp" hay que indicar el path tanto de los headers como de las librerias
a utilizar.

NOTA: en linux - Manjaro las librerías mínimas requeridas suelen ser:

    glfw3;OpenGL;pthread;dl;X11;GLEW;GLX
    
4) Se utilizara c-make a fin de que el proyecto sea lo más multiplataforma posible.

5) Para generar el proyecto, cree una carpeta "build" y ejecute desde alli: cmake -DCMAKE_BUILD_TYPE=Release  -S .. -B .
puede escoger el generador que desee por ejemplo : cmake -DCMAKE_BUILD_TYPE=Release  -G "CodeLite - Unix Makefiles" -S .. -B .
ejecutando: cmake --help podra ver los diferentes generadores soportados por su plataforma

6) Luego de generado los archivos de construcción puede ejecutar: cmake --build .

7) El ejecutable generado al seguir estos pasos tiene como nombre openglexe.
