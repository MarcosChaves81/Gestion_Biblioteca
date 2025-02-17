# Sistema de Biblioteca

Este es un sistema básico de gestión de una biblioteca, implementado en Python. Permite registrar usuarios, agregar libros, gestionar préstamos y devoluciones de libros.

## Estructura del Código

El sistema está compuesto por las siguientes clases:

1. **Usuario**:
    - Atributos:
        - `ID_usuario`: Identificación del usuario.
        - `nombre`: Nombre del usuario.
        - `email`: Correo electrónico del usuario.
        - `libros_prestados`: Lista de libros prestados por el usuario.
    - Métodos:
        - `prestar_libros(libro)`: Permite al usuario prestar un libro si está disponible.
        - `devolver_libro(libro)`: Permite al usuario devolver un libro prestado.

2. **Bibliotecario**:
    - Atributos:
        - `id_bibliotecario`: Identificación del bibliotecario.
        - `nombre`: Nombre del bibliotecario.
    - Métodos:
        - `agregar_libro(biblioteca, libro)`: Agrega un libro a la biblioteca.
        - `eliminar_libro(biblioteca, libro)`: Elimina un libro de la biblioteca.

3. **Biblioteca**:
    - Atributos:
        - `libros`: Lista de libros en la biblioteca.
        - `usuarios`: Lista de usuarios registrados en la biblioteca.
    - Métodos:
        - `registrar_usuario(usuario)`: Registra un usuario en la biblioteca.
        - `eliminar_usuario(usuario)`: Elimina un usuario de la biblioteca.
        - `listar_libros()`: Lista todos los libros disponibles en la biblioteca.
        - `listar_usuarios()`: Lista todos los usuarios registrados en la biblioteca.

4. **Libro**:
    - Atributos:
        - `titulo`: Título del libro.
        - `autor`: Autor del libro.
        - `isbn`: ISBN del libro.
        - `editorial`: Editorial del libro.
        - `anio_publicacion`: Año de publicación del libro.
        - `disponible`: Estado de disponibilidad del libro.
    - Métodos:
        - `mostrar_info()`: Muestra la información del libro.
        - `actualizar_disponibilidad(estado)`: Actualiza la disponibilidad del libro.

5. **Prestamo**:
    - Atributos:
        - `id_prestamo`: Identificación del préstamo.
        - `libro`: Libro prestado.
        - `usuario`: Usuario que realiza el préstamo.
        - `fecha_prestamo`: Fecha del préstamo.
        - `fecha_devolucion`: Fecha límite de devolución.
    - Métodos:
        - `finalizar_prestamo()`: Finaliza el préstamo y actualiza la disponibilidad del libro.

## Ejemplo de Uso

```python
# Creación de la biblioteca
mi_biblioteca = Biblioteca()

# Creación de libros
libro1 = Libro("El Aleph", "Jorge Luis Borges", "72423498423", "Editorial Mundo", 1949)
libro2 = Libro("Rayuela", "Julio Cortázar", "92384328745", "Editorial Sudamericana", 1962)

# Creación de usuarios
usuario1 = Usuario(1, "Juan Ignacio Zimmerman", "Juanii@gmail.com")
usuario2 = Usuario(2, "Jazmin Helena Zimmerman", "Jazz@gmail.com")

# Registro de usuarios en la biblioteca
mi_biblioteca.registrar_usuario(usuario1)
mi_biblioteca.registrar_usuario(usuario2)

# Creación del bibliotecario
bibliotecario = Bibliotecario(1, "Marcos Chaves")

# Agregar libros a la biblioteca
bibliotecario.agregar_libro(mi_biblioteca, libro1)
bibliotecario.agregar_libro(mi_biblioteca, libro2)

# Listar libros en la biblioteca
mi_biblioteca.listar_libros()

# Préstamo de libros
usuario1.prestar_libros(libro1)
usuario2.prestar_libros(libro2)

# Listar libros prestados por un usuario
for libro in usuario1.libros_prestados:
    print(libro.mostrar_info())

# Devolución de libros
usuario1.devolver_libro(libro1)

# Listar libros nuevamente para confirmar la devolución
mi_biblioteca.listar_libros()
