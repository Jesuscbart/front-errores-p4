# Correcciones Realizadas

## 1. Correcciones en `types.ts`

### 1.1. Cambio en los nombres de campos
- Se modificaron los nombres de los campos `created_at` y `updated_at` a `createdAt` y `updatedAt` en las interfaces `User` y `Task`, según la información de la documentación de la API.

### 1.2. Modificación de los valores de enum TaskStatus
- Se cambiaron los valores del enum `TaskStatus`:
  - De `TODO` a `PENDING`
  - De `DONE` a `COMPLETED`
  - Se mantuvo `IN_PROGRESS`

## 2. Correcciones en `utils.ts`

### 2.1. Corrección de la función `fetchUsers()`
- Se modificó para manejar correctamente la respuesta de la API que devuelve un objeto con una propiedad `data` que contiene el array de usuarios.

### 2.2. Corrección en la función `fetchTasks()`
- Se modificó para manejar correctamente la respuesta de la API que devuelve un objeto con una propiedad `data` que contiene el array de tareas.

### 2.3. Corrección de los métodos HTTP en las peticiones
- `updateUser()`: Se cambió el método de `DELETE` a `PUT` (correcto para actualizar)
- `deleteUser()`: Se cambió el método de `PUT` a `DELETE` (correcto para eliminar)
- `updateTask()`: Se cambió el método de `DELETE` a `PUT` (correcto para actualizar)

## 3. Correcciones en `components/TaskCard.tsx`

### 3.1. Se eliminaron dos `<div>`

- Se eliminaron dos `<div>` que estaban en las líneas 56 y 57 y que causaban que no se mostrara bien.

## 4. Correcciones en `islands/TaskBoard.tsx`

### 4.1. Importación de funcionalidad
- Se añadió la importación de `moveTask` para implementar la funcionalidad de mover tareas entre estados.

### 4.2. Actualización de la función `handleMoveTask()`
- Se modificó para usar la función `moveTask()` en lugar de `updateTaskStatus()`, permitiendo así el movimiento correcto de tareas entre estados.
- Se agregó un valor temporal "USER_ID" como parámetro userId.

### 4.3. Actualización de las referencias a TaskStatus
- Se actualizaron todas las referencias a los estados de tareas para usar los nuevos valores del enum:
  - `TaskStatus.TODO` -> `TaskStatus.PENDING`
  - `TaskStatus.DONE` -> `TaskStatus.COMPLETED`

## 5. Correcciones en `islands/TaskForm.tsx`

### 5.1. Actualización de las referencias a TaskStatus
- Se han actualizado las referencias de .TODO a `.PENDING` y de .DONE a `.COMPLETED`