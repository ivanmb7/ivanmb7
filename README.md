# Ivan Martinez Bastida – Desarrollador Junior / Estudiante DAW

## 👤 Sobre mí
¡Hola! Bienvenido a mi perfil de GitHub. Soy estudiante de **Desarrollo de Aplicaciones Web (DAW)** con un fuerte enfoque en el desarrollo Backend. Actualmente estoy centrado en dominar la programación orientada a objetos con **Java** y el diseño y gestión de **Bases de Datos relacionales y no relacionales**.

Me apasiona resolver problemas lógicos, estructurar código limpio y entender qué ocurre "detrás de escena" en una aplicación web. Busco constantemente mejorar mis habilidades y aprender nuevas tecnologías del ecosistema web.

* **Mis intereses principales:** Desarrollo Backend (Java/Spring Boot), Diseño de Bases de Datos (SQL), APIs REST y metodologías ágiles.

---

## 🛠️ Habilidades Técnicas

### Lenguajes de Programación
* **Java:** Programación Orientada a Objetos (POO), manejo de excepciones, colecciones (`List`, `Map`), y persistencia de datos.
* **HTML5 & CSS3 / JavaScript:** Conocimientos esenciales para el desarrollo frontend y conexión con el backend.

### Sistemas y Virtualización
* **Linux (Debian/Ubuntu Server):** Gestión de usuarios, permisos, y manejo de la terminal de comandos para configurar entornos de desarrollo.
* **Máquinas Virtuales:** Creación, configuración y mantenimiento de entornos aislados utilizando herramientas como **VirtualBox** o **VMware**.

### Bases de Datos
* **Relacionales (SQL):** Diseño de diagramas Entidad-Relación, normalización, y dominio de consultas complejas (JOINs, subconsultas, funciones de agregación) en **MySQL**, **PostgreSQL** o **MariaDB**.
* **Herramientas de gestión:** Conexión y persistencia mediante `JDBC` y primeros pasos con Hibernate/JPA.

### Herramientas de Desarrollo
* Control de versiones con **Git** y **GitHub**.
* Entornos de desarrollo: **IntelliJ IDEA**, **Eclipse** y VS Code.

---

## 🚀 Proyectos y Prácticas Realizadas

Durante mi formación en DAW, he desarrollado proyectos prácticos para aplicar los conceptos de programación y bases de datos:

1. **Despliegue de Entornos de Desarrollo en Linux:**
   * Configuración de máquinas virtuales con Linux para simular servidores de producción locales.
   * Instalación y configuración de servidores web y entornos de ejecución para aplicaciones Java utilizando la terminal de comandos.

2. **Sistema de Gestión de Biblioteca (Java + SQL):**
   * Aplicación de escritorio desarrollada en Java que permite realizar el CRUD completo (Crear, Leer, Actualizar, Borrar) de libros, usuarios y préstamos.
   * Conexión directa a una base de datos MySQL utilizando el conector `JDBC`.

3. **Diseño de Base de Datos para un E-commerce:**
   * Creación del modelo conceptual y lógico para una tienda online (usuarios, productos, pedidos y carrito).
   * Implementación del script SQL con restricciones de clave primaria (`PRIMARY KEY`) y foránea (`FOREIGN KEY`) para asegurar la integridad de los datos.

4. **Calculadora Orientada a Objetos (Java):**
   * Proyecto inicial para consolidar conceptos de clases, herencia y polimorfismo en Java, implementando un control estricto de errores (como la división por cero).

---

## 🎯 Objetivo Profesional
**Mi meta actual es finalizar con éxito mis estudios de DAW y realizar mis prácticas en empresa (FCT). De cara al futuro, mi objetivo profesional es incorporarme al mercado laboral como Desarrollador Web Full-Stack o Backend, en un equipo de desarrollo donde pueda seguir perfeccionando mi nivel de Java, optimizando bases de datos y aprovechando mis conocimientos en entornos Linux y virtualización para desplegar aplicaciones eficientes y seguras.


---
## 📨 Contacto
**¡Estoy abierto a colaborar en proyectos, resolver dudas o simplemente conectar con otros desarrolladores del sector! Puedes contactar conmigo a través de:

*📧 Correo electrónico: im191841@gmail.com

*💼 LinkedIn: https://www.linkedin.com/in/ivan-martinez-538006372/

---
## 💻 Código de Ejemplo (Java & SQL)

A continuación, muestro un método en Java que simula la inserción de un nuevo usuario en la base de datos utilizando `PreparedStatement` para evitar la inyección SQL:

```java
public void registrarUsuario(String nombre, String email) {
    String sql = "INSERT INTO usuarios (nombre, email) VALUES (?, ?)";
    
    // Conexión y ejecución segura utilizando Try-with-resources
    try (Connection conn = Conexiones.obtenerConexion();
         PreparedStatement pstmt = conn.prepareStatement(sql)) {
         
        pstmt.setString(1, nombre);
        pstmt.setString(2, email);
        
        int filasAfectadas = pstmt.executeUpdate();
        if (filasAfectadas > 0) {
            System.out.println("¡Usuario registrado correctamente!");
        }
    } catch (SQLException e) {
        System.err.println("Error al registrar el usuario: " + e.getMessage());
    }
}
