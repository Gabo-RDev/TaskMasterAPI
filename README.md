```markdown
# 📌 TaskMasterAPI

API REST sencilla construida con **ASP.NET Core** que permite la gestión de tareas (CRUD).  
Se utiliza un `TaskDataStore` en memoria como base de datos simulada.

---

## 🚀 Características

- Obtener todas las tareas
- Obtener una tarea por su **ID**
- Crear nuevas tareas
- Actualizar tareas existentes
- Eliminar tareas

---

## 📂 Estructura del proyecto

```markdown

TaskMasterAPI/
│── Controllers/
│   └── TaskController.cs   # Controlador principal con los endpoints
│── Models/
│   └── Task.cs             # Modelo de datos de una tarea
│   └── TaskInsert.cs       # Modelo para insertar/actualizar tareas
│── Services/
│   └── TaskDataStore.cs    # Data store en memoria con datos iniciales
│── Program.cs              # Configuración de la app

````

---

## 📡 Endpoints

### 🔹 Obtener todas las tareas
```http
GET /api/task
````

### 🔹 Obtener una tarea por ID

```http
GET /api/task/{id}
```

Ejemplo:

```http
GET /api/task/1
```

### 🔹 Crear una nueva tarea

```http
POST /api/task
```

Body (JSON):

```json
{
  "title": "Nueva tarea",
  "description": "Descripción de la tarea"
}
```

### 🔹 Actualizar una tarea

```http
PUT /api/task/{id}
```

Body (JSON):

```json
{
  "title": "Tarea actualizada",
  "description": "Nueva descripción"
}
```

### 🔹 Eliminar una tarea

```http
DELETE /api/task/{id}
```

---

## 🛠️ Instalación y ejecución

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/tu-usuario/TaskMasterAPI.git
   cd TaskMasterAPI
   ```

2. Restaurar dependencias:

   ```bash
   dotnet restore
   ```

3. Ejecutar la aplicación:

   ```bash
   dotnet run
   ```

4. Abrir en el navegador:

   ```
   https://localhost:5001/swagger
   ```

---

## 📖 Tecnologías utilizadas

* [C#](https://learn.microsoft.com/es-es/dotnet/csharp/)
* [ASP.NET Core Web API](https://learn.microsoft.com/es-es/aspnet/core/web-api/)
* [Swagger / Swashbuckle](https://swagger.io/tools/swagger-ui/)

---

## ✨ Ejemplo de datos iniciales

La API arranca con las siguientes tareas precargadas en memoria:

```json
[
  {
    "id": 1,
    "title": "Aprender C#",
    "description": "Aprender los fundamentos C#",
    "isCompleted": false
  },
  {
    "id": 2,
    "title": "Aprender ASP.NET Core",
    "description": "Aprender los fundamentos ASP.NET Core",
    "isCompleted": false
  },
  {
    "id": 3,
    "title": "Aprender Entity Framework Core",
    "description": "Aprender los fundamentos Entity Framework Core",
    "isCompleted": false
  }
]
```

---

## 📌 Notas

* Actualmente, la API no usa base de datos real, solo un **almacenamiento en memoria** (`TaskDataStore`).
* Los datos se reinician cada vez que se reinicia la aplicación.
* Ideal para practicar CRUD básico con ASP.NET Core.

---

## 📜 Modelo `Task`

```csharp
public class Task
{
    public int Id { get; set; }
    public string? Title { get; set; }
    public string? Description { get; set; }
    public bool IsCompleted { get; set; }
    public DateTime CreatedAt { get; set; }
    public DateTime UpdatedAt { get; set; }
}
```

---

## 📜 Modelo `TaskInsert`

Este modelo se utiliza para crear y actualizar tareas.

```csharp
public class TaskInsert
{
    public string? Title { get; set; }
    public string? Description { get; set; }
}
```
