

## 📦 Requisitos de instalación

Antes de compilar el juego, asegúrate de tener instalado lo siguiente:

### Dependencias principales
- Compilador C++  
  - En Linux: g++ (instalar con sudo apt install g++)  
  - En Windows: MinGW-w64 o MSVC  
  - En macOS: instalar con xcode-select --install  

- raylib (librería gráfica usada para el juego)  
  - En Linux (Ubuntu/Debian):  
    sudo apt install libraylib-dev
  - En Windows: descarga los binarios precompilados desde  
    https://github.com/raysan5/raylib/releases  
  - En macOS:  
    brew install raylib

- pkg-config (para simplificar compilación en Linux/macOS):  
  sudo apt install pkg-config

### Librerías del sistema (Linux)
raylib depende de estas (normalmente ya vienen instaladas):
- OpenGL (-lGL)
- Math library (-lm)
- POSIX threads (-lpthread)
- Dynamic loading (-ldl)
- Real-time extension (-lrt)
- X11 (-lX11)

---

## ⚙ Compilación

### Método 1: usando pkg-config (recomendado en Linux/macOS)
g++ *.cpp -o tetris $(pkg-config --libs --cflags raylib)

### Método 2: manual (ejemplo Linux si pkg-config no funciona)
g++ *.cpp -o tetris -I/usr/local/include -L/usr/local/lib \
-lraylib -lGL -lm -lpthread -ldl -lrt -lX11

---

## ▶ Ejecución

En Linux/macOS:
./tetris

En Windows (PowerShell):
.\tetris.exe
