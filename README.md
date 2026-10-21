# hello-world

Programa "Hello, World!" escrito en Java.

## Estructura del proyecto

```
hello-world/
├── src/
│   └── HelloWorld.java   # Código fuente
├── .gitignore
└── README.md
```

## Requisitos

- **JDK (Java Development Kit) 8 o superior.** Se recomienda una versión LTS (17 o 21).
- Git (opcional, para clonar el repositorio).

> Nota: se necesita el **JDK**, no solo el JRE, porque incluye el compilador `javac`.

## Instalación

### 1. Instalar el JDK

**Linux (Debian/Ubuntu)**

```bash
sudo apt update
sudo apt install openjdk-21-jdk
```

**Linux (Fedora/RHEL)**

```bash
sudo dnf install java-21-openjdk-devel
```

**macOS (con [Homebrew](https://brew.sh))**

```bash
brew install openjdk@21
```

Si `java` no aparece en el `PATH`, sigue las instrucciones que muestra `brew info openjdk@21`.

**Windows**

1. Descarga el instalador de [Eclipse Temurin](https://adoptium.net/) (JDK 21, `.msi`).
2. Ejecútalo y marca las opciones **"Set JAVA_HOME"** y **"Add to PATH"**.
3. Abre una nueva terminal (PowerShell o CMD).

Alternativamente, con `winget`:

```powershell
winget install EclipseAdoptium.Temurin.21.JDK
```

### 2. Verificar la instalación

```bash
java -version
javac -version
```

Ambos comandos deben mostrar la versión instalada (por ejemplo, `21.x.x`).

### 3. Obtener el código

```bash
git clone https://github.com/rodgergutierrezx/hello-world.git
cd hello-world
```

## Compilar y ejecutar

### Opción A: compilar y luego ejecutar

```bash
# Compila el código fuente; los .class se generan en el directorio out/
javac -d out src/HelloWorld.java

# Ejecuta el programa
java -cp out HelloWorld
```

### Opción B: ejecutar directamente (Java 11+)

Desde Java 11 se puede ejecutar un archivo fuente sin compilarlo explícitamente:

```bash
java src/HelloWorld.java
```

### Salida esperada

```
Hello, World!
```

## Solución de problemas

| Problema | Causa probable | Solución |
|---|---|---|
| `javac: command not found` / `'javac' no se reconoce...` | El JDK no está instalado o no está en el `PATH`. | Instala el JDK y agrega su carpeta `bin` al `PATH`. Abre una terminal nueva. |
| `Error: Could not find or load main class HelloWorld` | El classpath no apunta a la carpeta con `HelloWorld.class`. | Ejecuta desde la raíz del proyecto con `java -cp out HelloWorld`. |
| `UnsupportedClassVersionError` | Se compiló con un JDK más nuevo que el `java` usado para ejecutar. | Usa la misma versión para compilar y ejecutar (`java -version` y `javac -version` deben coincidir). |

## Limpieza

Para eliminar los archivos compilados:

```bash
rm -rf out        # Linux / macOS
rmdir /s /q out   # Windows (CMD)
```
