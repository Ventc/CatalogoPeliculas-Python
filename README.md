# CatalogoPeliculas-Python

### **Dominio/Pelicula**

**1)** **_Constructor_ (__init__):**
La función __init__ es el constructor de la clase. Se llama automáticamente cuando se crea una nueva instancia de la clase.
Toma como parámetros self (una referencia a la instancia recién creada) y nombre.
Inicializa el atributo de instancia _nombre con el valor proporcionado como argumento.

```
    def __init__(self, nombre):
        self._nombre = nombre
```
 **2)** **_Método_ __str__:**
Este método se llama cuando se utiliza la función str() para convertir un objeto a una cadena de caracteres.
Devuelve una cadena formateada que representa el objeto Pelicula en forma legible.

```
    def __str__(self):
        return f"Pelicula: {self._nombre}"
```
**3)** **Propiedad nombre con su Setter:**
Se define una propiedad llamada nombre utilizando el decorador @property.
Permite acceder al valor de _nombre como si fuera un atributo, sin necesidad de llamar a un método.
Se define un setter para la propiedad nombre con el decorador @nombre.setter. Esto permite modificar el valor de _nombre.

```
    @property
    def nombre(self):
        return self._nombre

    @nombre.setter
    def nombre(self, nombre):
        self._nombre = nombre
```
**En resumen, esta clase Pelicula tiene un atributo privado _nombre, un constructor para inicializar ese atributo, un método para representar la instancia como una cadena y una propiedad nombre con su setter para acceder y modificar el valor de _nombre. Esto sigue el principio de encapsulación al utilizar propiedades para el acceso controlado a los atributos.**

============================================================================================
### **Servicio/Catalogo-Peliculas**

**1)** **_Atributo de Clase ruta_archivo:_**
Se define un atributo de clase llamado ruta_archivo, que almacena la ruta del archivo de texto donde se guardarán las películas.
La ruta por defecto es "peliculas.txt".

```
    ruta_archivo = "peliculas.txt"
```
**2)** **_Método de Clase agregar_peliculas:_**
Este es un método de clase (@classmethod) llamado agregar_peliculas.
Toma como parámetros cls (referencia a la clase) y pelicula.
Abre el archivo en modo "a" (append) y escribe el nombre de la película seguido de un salto de línea.

```
    @classmethod
    def agregar_peliculas(cls, pelicula):
        with open(cls.ruta_archivo, "a", encoding="utf8") as archivo:
            archivo.write(f"{pelicula.nombre}\n")
```
**3)** **_Método de Clase listar_peliculas:_**
Este es otro método de clase llamado listar_peliculas.
Toma como parámetro cls.
Abre el archivo en modo "r" (lectura) y muestra el contenido del archivo en la consola.

```
    @classmethod
    def listar_peliculas(cls):
        with open(cls.ruta_archivo, "r", encoding="utf8") as archivo:
            print(f"Catalogo de peliculas".center(50, "-"))
            print(archivo.read())
```
**4)** **_Método de Clase eliminar_peliculas:_**
Este es otro método de clase llamado eliminar_peliculas.
Toma como parámetro cls.
Utiliza la función os.remove para eliminar el archivo de películas.

```
    @classmethod
    def eliminar_peliculas(cls):
        os.remove(cls.ruta_archivo)
        print(f"Archivo eliminado: {cls.ruta_archivo}")
```
**En resumen, esta clase CatalogoPeliculas proporciona métodos para agregar películas al archivo, listar las películas almacenadas y eliminar el archivo de películas. Los métodos de clase utilizan la variable de clase ruta_archivo para determinar la ubicación del archivo.**



