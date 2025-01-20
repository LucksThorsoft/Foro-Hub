# 🌐 ForoHub API

ForoHub es una API REST diseñada con Spring Boot para la gestión de un foro de discusión. Permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre tópicos, ofreciendo seguridad, validaciones y persistencia mediante bases de datos relacionales.

---

## 🚩 Funcionalidades

- Crear nuevos tópicos de discusión.
- Listar todos los tópicos disponibles.
- Consultar un tópico específico.
- Editar información de un tópico.
- Eliminar tópicos existentes.
- Autenticación y autorización de usuarios.
- Validación de reglas de negocio y datos.

---

## 🛠 Tecnologías Empleadas

- **Java 11**
- **Spring Boot**
- **Spring Data JPA**
- **Spring Security**
- **Hibernate**
- **H2 Database** (Desarrollo y pruebas)
- **MySQL** (Producción)
- **Maven**

---

## 🚀 Guía de Instalación

### Requisitos previos

- JDK 11 o superior.
- Maven instalado.
- MySQL configurado (para entorno de producción).

### Pasos

1. **Clonar el repositorio**:
   ```bash
   git clone https://github.com/tu-usuario/ForoHub.git
   cd ForoHub
   ```

2. **Configurar la base de datos**:

   - Para desarrollo y pruebas, H2 Database está habilitado por defecto.
   - Para producción, actualiza el archivo de configuración `src/main/resources/application.properties`:

     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/forohub
     spring.datasource.username=tu-usuario
     spring.datasource.password=tu-contraseña
     spring.jpa.hibernate.ddl-auto=update
     ```

3. **Construir y ejecutar la aplicación**:

   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

---

## 📖 Endpoints Principales

### Crear un nuevo tópico
```http
POST /api/topics
```
**Cuerpo de la petición (JSON)**:
```json
{
    "titulo": "Ejemplo de Título",
    "mensaje": "Contenido del tópico",
    "autorId": 1
}
```

### Consultar todos los tópicos
```http
GET /api/topics
```

### Consultar un tópico por ID
```http
GET /api/topics/{id}
```

### Actualizar un tópico
```http
PUT /api/topics/{id}
```
**Cuerpo de la petición (JSON)**:
```json
{
    "titulo": "Título Actualizado",
    "mensaje": "Mensaje Actualizado"
}
```

### Eliminar un tópico
```http
DELETE /api/topics/{id}
```

---

## 🔒 Seguridad

La API implementa autenticación y autorización utilizando **Spring Security**. Se requiere que los usuarios se autentiquen para acceder a los endpoints protegidos.

---

## ✅ Validaciones Incluidas

- Todos los campos son obligatorios al crear o actualizar tópicos.
- Se retornan mensajes claros en caso de errores o datos incorrectos.

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. Realiza tus cambios y haz un commit:
   ```bash
   git commit -m "Agregar nueva funcionalidad"
   ```
4. Sube los cambios a tu fork:
   ```bash
   git push origin feature/nueva-funcionalidad
   ```
5. Abre un Pull Request.

---

## 📝 Licencia

Este proyecto está bajo la **Licencia MIT**. Consulta el archivo `LICENSE` para más detalles.

