# Challenge-Literalura
# 📚 LiterAlura - Catálogo de Libros

Un catálogo de libros interactivo que permite buscar, registrar y consultar información sobre libros utilizando la API de Gutendex (Project Gutenberg). Desarrollado como parte del challenge de Oracle Next Education.

## 🌟 Características

- ✅ Búsqueda de libros por título en tiempo real
- 📖 Registro automático en base de datos PostgreSQL
- 👥 Gestión de autores y sus obras
- 🌍 Filtrado de libros por idioma
- 📊 Consultas avanzadas a la base de datos
- 🎯 Interfaz de consola intuitiva

## 🛠️ Tecnologías Utilizadas

- **Java 17** - Lenguaje de programación
- **Spring Boot 3.2.4** - Framework principal
- **Spring Data JPA** - Para el manejo de datos
- **PostgreSQL** - Base de datos
- **Jackson** - Manipulación de JSON
- **Maven** - Gestión de dependencias
- **Gutendex API** - Fuente de datos de libros

## 📋 Funcionalidades Principales

### 1. 🔍 Buscar Libro por Título
- Busca libros en la API de Gutendex por título
- Registra automáticamente el libro en la base de datos
- Evita duplicados en el catálogo

### 2. 📚 Listar Libros Registrados
- Muestra todos los libros guardados en la base de datos
- Incluye información detallada de cada libro

### 3. 👤 Listar Autores Registrados
- Presenta todos los autores con sus respectivos libros
- Muestra fechas de nacimiento y muerte

### 4. 🕰️ Listar Autores Vivos en un Año Determinado
- Permite consultar qué autores estaban vivos en un año específico
- Útil para contexto histórico

### 5. 🌐 Listar Libros por Idioma
- Filtra libros por idioma (ES, EN, FR, PT)
- Facilita la búsqueda por preferencia de idioma

## 🚀 Instalación y Configuración

### Prerrequisitos

- Java 17 o superior
- Maven 3.8+
- PostgreSQL 12+

### Configuración del Proyecto

1. **Clonar el repositorio**
```bash
git clone https://github.com/JRMYLLA/literalura.git
cd literalura
```

2. **Configurar PostgreSQL**
```sql
CREATE DATABASE literalura;
CREATE USER literalura_user WITH PASSWORD 'tu_password';
GRANT ALL PRIVILEGES ON DATABASE literalura TO literalura_user;
```

3. **Configurar application.properties**
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/literalura
spring.datasource.username=literalura_user
spring.datasource.password=tu_password
spring.datasource.driver-class-name=org.postgresql.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

4. **Ejecutar la aplicación**
```bash
mvn spring-boot:run
```

## 🎮 Ejemplo de Uso

```
========================================
    BIENVENIDO A LITERALURA
========================================

1 - Buscar libro por título
2 - Listar libros registrados
3 - Listar autores registrados
4 - Listar autores vivos en un determinado año
5 - Listar libros por idioma
0 - Salir

Elija una opción válida: 1
Ingrese el nombre del libro que desea buscar:
> Pride and Prejudice

----- LIBRO ENCONTRADO -----
Título: Pride and Prejudice
Autor: Austen, Jane
Idioma: EN
Número de descargas: 6493

¡Libro registrado exitosamente en la base de datos!
```

## 🏗️ Estructura del Proyecto

```
literalura/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/alura/literalura/
│       │       ├── LiteraluraApplication.java
│       │       ├── model/
│       │       │   ├── Libro.java
│       │       │   ├── Autor.java
│       │       │   └── DatosLibro.java
│       │       ├── repository/
│       │       │   ├── LibroRepository.java
│       │       │   └── AutorRepository.java
│       │       ├── service/
│       │       │   ├── ConsumoAPI.java
│       │       │   └── ConvierteDatos.java
│       │       └── principal/
│       │           └── Principal.java
│       └── resources/
│           └── application.properties
├── pom.xml
└── README.md
```

## 📊 Modelo de Datos

### Entidad Libro
- ID (generado automáticamente)
- Título
- Idioma
- Número de descargas
- Autor (relación Many-to-One)

### Entidad Autor
- ID (generado automáticamente)
- Nombre
- Fecha de nacimiento
- Fecha de muerte
- Libros (relación One-to-Many)

## 🔗 API Utilizada

**Gutendex API**: Una API REST que proporciona metadatos del Proyecto Gutenberg
- Base URL: `https://gutendex.com/books/`
- Documentación: [gutendx.com](https://gutendx.com/)
- Más de 70,000 libros disponibles
- Acceso gratuito sin necesidad de API key

## ✨ Características Adicionales Implementadas

- 🔒 **Validación de duplicados** - Previene el registro del mismo libro múltiples veces
- 🚫 **Manejo de errores** - Mensajes informativos cuando no se encuentran libros
- 🎨 **Interfaz mejorada** - Menú intuitivo con separadores visuales
- 📈 **Optimización de consultas** - Uso eficiente de JPA queries

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Para contribuir:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/NuevaFuncionalidad`)
3. Commit tus cambios (`git commit -m 'Añadir nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/NuevaFuncionalidad`)
5. Abre un Pull Request

## 📝 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👨‍💻 Autor

**JRMYLLA**
- GitHub: JRMYLLA
- Proyecto desarrollado como parte del programa Oracle Next Education

## 🎯 Challenge Oracle Next Education

Este proyecto fue desarrollado como parte del Challenge Backend de Oracle Next Education en colaboración con Alura Latam, enfocado en:
- Consumo de APIs REST
- Manipulación de datos JSON
- Persistencia con JPA/Hibernate
- Desarrollo con Spring Boot
- Manejo de bases de datos PostgreSQL

## 🙏 Agradecimientos

- **Oracle Next Education** por la oportunidad de aprendizaje
- **Alura Latam** por el contenido educativo de calidad

---



📚 *"Un lector vive mil vidas antes de morir... El que nunca lee vive sólo una."* - George R.R. Martin
