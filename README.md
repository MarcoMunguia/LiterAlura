# LiterAlura

¡Bienvenido a LiterAlura! Este es un proyecto diseñado para construir un catálogo interactivo de libros que permite a los usuarios buscar libros a través de la API [Gutendex](https://gutendex.com/), almacenar información en una base de datos, y realizar consultas sobre los libros guardados.

## **Descripción del Proyecto**

LiterAlura es una aplicación de consola desarrollada en Java que permite:

1. Buscar libros por título en la API de Gutendex.
2. Guardar libros y sus autores en una base de datos.
3. Listar los libros guardados.
4. Filtrar y mostrar libros según diversos criterios.
5. Interactuar con el catálogo de manera textual desde la consola.

Este proyecto está diseñado para enseñar habilidades prácticas de programación, como el consumo de APIs, manejo de JSON, bases de datos y la construcción de una aplicación interactiva.

---

## **Requisitos Previos**

Antes de comenzar, asegúrate de tener instalado lo siguiente:

- **Java Development Kit (JDK)** versión 11 o superior.
- Un IDE de Java (como IntelliJ IDEA, Eclipse o Visual Studio Code).
- **Apache Maven** para la gestión de dependencias.
- **MySQL** o cualquier otra base de datos relacional.
- Conexión a Internet para consumir la API de Gutendex.

---

## **Tecnologías Utilizadas**

- **Lenguaje de programación**: Java
- **Gestión de dependencias**: Maven
- **Consumo de API**: `HttpClient`
- **Procesamiento de JSON**: `Gson`
- **Base de datos**: MySQL
- **ORM**: Hibernate para la interacción con la base de datos

---

## **Configuración del Proyecto**

### **1. Clona el repositorio**
```bash
git clone https://github.com/tu-usuario/literalura.git
cd literalura
```

### **2. Configura la base de datos**

1. Crea una base de datos llamada `literalura` en tu sistema de MySQL:
```sql
CREATE DATABASE literalura;
```

2. Configura el archivo `hibernate.cfg.xml` en el proyecto con tus credenciales de MySQL:
```xml
<hibernate-configuration>
    <session-factory>
        <property name="hibernate.connection.driver_class">com.mysql.cj.jdbc.Driver</property>
        <property name="hibernate.connection.url">jdbc:mysql://localhost:3306/literalura</property>
        <property name="hibernate.connection.username">tu_usuario</property>
        <property name="hibernate.connection.password">tu_contraseña</property>
        <property name="hibernate.dialect">org.hibernate.dialect.MySQLDialect</property>
        <property name="hibernate.hbm2ddl.auto">update</property>
    </session-factory>
</hibernate-configuration>
```

3. Hibernate creará automáticamente las tablas necesarias (`books` y `authors`) en la base de datos al ejecutar el programa.

---

### **3. Instala las dependencias**

Ejecuta el siguiente comando para instalar todas las dependencias del proyecto:
```bash
mvn clean install
```

---

### **4. Ejecuta el proyecto**

Compila y ejecuta el proyecto desde tu IDE o usando el siguiente comando:
```bash
mvn exec:java -Dexec.mainClass="com.example.literalura.Main"
```

---

## **Opciones de Interacción**

Cuando ejecutes el programa, tendrás acceso a las siguientes opciones:

1. **Buscar libros por título**: Ingresa el nombre de un libro y el programa buscará en la API los libros relacionados, almacenándolos en la base de datos.
2. **Listar libros guardados**: Muestra todos los libros almacenados en la base de datos.
3. **Salir**: Cierra la aplicación.

---

## **Estructura del Proyecto**

El proyecto está organizado en los siguientes paquetes y clases:

```
com.example.literalura
    ├── Main.java          // Clase principal para interactuar con el usuario
    ├── ApiService.java    // Clase para consumir la API de Gutendex
    ├── Book.java          // Entidad Book (libro)
    ├── Author.java        // Entidad Author (autor)
    ├── HibernateUtil.java // Configuración de Hibernate
    ├── BookDAO.java       // DAO para manejar libros en la base de datos
    ├── AuthorDAO.java     // DAO para manejar autores en la base de datos
```

---

## **API Utilizada**

Este proyecto utiliza la API pública [Gutendex](https://gutendex.com/) para buscar libros y obtener información como título, autores e idioma. Ejemplo de endpoint para buscar libros:

```
https://gutendex.com/books?search={titulo}
```

---

## **Contribuciones**

¡Las contribuciones son bienvenidas! Si deseas agregar nuevas funcionalidades o mejorar el proyecto, sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una rama nueva:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. Realiza los cambios y haz commit:
   ```bash
   git commit -m "Agregada nueva funcionalidad"
   ```
4. Envía tus cambios:
   ```bash
   git push origin feature/nueva-funcionalidad
   ```
5. Abre un pull request en el repositorio principal.

---

## **Licencia**

Este proyecto está licenciado bajo la [MIT License](https://opensource.org/licenses/MIT).

---

## **Autor**

Desarrollado por Marco Antonio Munguia Hernandez.  
Si tienes dudas o sugerencias, ¡contáctame!
