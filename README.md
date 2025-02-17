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
        - `nombre`: Nombre del bibli
