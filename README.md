# XPE Detector v 1.0 
![Made with Python](https://img.shields.io/badge/Made%20with-Python-1f425f.svg?logo=python&logoColor=white)<br>
XPE Detector es una herramienta de análisis estático de ejecutables (PE) ligera y potente, diseñada para identificar compiladores, protectores (packers) y extraer información relevante de archivos binarios de Windows, ver el codigo en ensamblador y en codigo hexadecimal, detecta tambien  mas de 1832 compiladores. (windows exe)


<img width="300" height="300" alt="...." src="https://github.com/user-attachments/assets/79f1b095-c86d-481f-ae02-0b654f1f5d1a" />


<b><h1>🚀 Características Principales</h1></b>

<b><h2>Detección de Firmas Avanzada:</b></h2>

      * Detección de Firmas Avanzada:
      * Base de datos interna con +1800 firmas de compiladores y packers.
      * Soporte para base de datos externa (UserDB.TXT) para añadir firmas personalizadas.
      * Detección de: Borland Delphi, Visual Basic, Visual C++, MinGW, UPX, VMProtect, Themida, ASPack, y muchos más.
      
 <b><h2>Análisis PE Profundo:</b></h2>
 
      * Visualización de Cabeceras (File Header, Optional Header).
      * Listado de Secciones con direcciones y tamaños.
      * Análisis de Importaciones y Exportaciones (con ventanas emergentes detalladas).
   <b><h2> Extracción Inteligente de Strings:</b></h2>
   
        * Filtrado automático por categorías: URLs, Correos, Claves de Registro, Rutas de archivo, IPs y Dominios.
        * Soporte para strings ASCII y Unicode.
        * Función de búsqueda integrada.
        
  <b><h2>Desensamblador Integrado:</h2></b>
     
        * Desensamblaje del Entry Point (Punto de Entrada) utilizando Capstone.
        * Soporte para arquitecturas x86 y x64.
   <b><h2>Herramientas de Utilería:</h2></b>
  - **Vista HExadecimal:** Inspección rápida de los primeros bytes del archivo.
  - **Comparacaión de Archivos:** Compara dos ejecutables por tamaño y hash MD5 para determinar si son idénticos.
  - **Calculadora de Hashes:** Genera MD5, SHA-1, SHA-256, SHA-512 y CRC32.

<br>
<b><h2>🛠️ Requisitos e Instalación</h2></b><br>
<br><b></b>Dependencias</b>
<br>
<br>
Para ejecutar el código fuente, necesitas:
<br><br>
-- Python 3.x 
<bR><br>
y las siguientes librerías:
<br><br>

**pip install pefile capstone**
<br>
 <br>

Nota: tkinter suele venir instalado por defecto con Python. 
<br>
<br><b>Ejecución </b>
<br>
- Simplemente ejecuta el script principal:
<br><br>
python xpe_detector.py
<br>
<h2>⚙️ Compilación (Generar .EXE)</h2> 

Para distribuir la herramienta como un ejecutable independiente, se recomienda PyInstaller. 
1. Instalar PyInstaller
<b>Pip install pyinstaller</b>
<br>
<h2>2. Comando de Compilación </h2>

Debido al uso de la librería capstone (que requiere binarios externos) y pefile, se recomienda el siguiente comando para asegurar que todo funcione correctamente: 
<br><br>

<b>pyinstaller --onefile --noconsole --collect-all capstone --hidden-import pefile xpe_detector.py</b>
<br>
<b>Explicación de los parámetros: </b>

  - **onefile:** Genera un único archivo .exe en lugar de una carpeta con dependencias.
  - **noconsole** Oculta la terminal negra de comandos al abrir la aplicación (ideal para GUIs).
  - **hidden-import pefile:** Incluye todas las DLLs y archivos necesarios de Capstone dentro del ejecutable.
  - **collect-all capstone.**
  - **collect-all capstone:** Asegura que el módulo pefile sea incluido en el paquete.
<bR>
<h1>📖 Manual de Uso </h1>
<b>Barra de Menú</b> 

     Archivo > Abrir: Carga un archivo .exe o .dll para analizar.
     Ayuda > About: Muestra información del autor y lista las firmas cargadas en la base de datos.
     

<b>Pestañas Principales</b> 
**Detección:**
         Muestra los resultados de las firmas coincidentes (Packers/Compiladores).
         Muestra el tamaño del archivo.
          

   <b>Cabeceras: </b>
         Información técnica del PE (Machine, Timestamp, EntryPoint, ImageBase).
         Listado de secciones (.text, .data, etc.).
          

   <b> Importaciones / Exportaciones: </b>
         Lista las DLLs importadas. Doble clic en una DLL para ver las funciones importadas en una ventana emergente.
          

<b>    Strings: </b>
         Extrae texto legible del binario.
         Usa el cuadro de búsqueda superior para filtrar resultados.
         Clasifica automáticamente URLs, IPs y correos electrónicos.
          

<b>    Entrypoint: </b>
         Muestra el código desensamblado (Assembler) al inicio del programa. Requiere capstone.
          

<b>    Comparación: </b>
         Carga dos archivos y determina si son idénticos comparando sus hashes MD5.
          

<b>    Hash/CRC: </b>
         Calcula los hashes criptográficos del archivo cargado para verificar su integridad.
          

<h2>📁 Base de Datos de Firmas (UserDB.TXT) </h2>

La aplicación soporta la carga de firmas externas para expandir su capacidad de detección. Si el archivo UserDB.TXT existe en la misma carpeta que el ejecutable, se cargará automáticamente. 

Formato del archivo UserDB.TXT:<br> <img width="288" height="199" alt="Captura" src="https://github.com/user-attachments/assets/d0928d3f-9528-4d73-98da-b58fa6463c6e" />

<bR>

<h1>👨‍💻 Autor </h1>

<b>Rodolfo Hernandez Baz
Proyecto: Rhino Toolkit 2026 </b>

<h3>Si encuentdas esta herramienta útil, siéntete libre de dejar una estrella ⭐ en el repositorio. </h3>
<br>
<b></b>📜 Licencia </b>

Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles. 




    
