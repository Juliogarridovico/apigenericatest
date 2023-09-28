# API de Gastos de Viaje

API RESTful para gestionar los gastos de un grupo durante un viaje, desarrollado en Node.js y Express, y utiliza un archivo JSON como almacenamiento de datos.

## Índice

- [Instalación](#instalación)
- [Uso](#uso)
- [API Endpoints](#api-endpoints)
- [Mejoras Futuras](#mejoras-futuras)
- [Licencia](#licencia)

## Instalación

** Clona este repositorio a tu máquina local:
   git clone https://github.com/<tu-usuario>/proyecto-viaje.git
   cd proyecto-viaje

**Instala las dependencias necesarias:
   npm install
**Ejecuta el servidor:
  node src/index.js

  ## API Endpoints

A continuación, se describen los endpoints disponibles en la API:

### 1. Crear Viaje
   - **URL:** `/viajes`
   - **Método:** `POST`
   - **Descripción:** Permite agregar un nuevo viaje.
   - **Cuerpo de la Solicitud:**
     ```json
     {
       "nombre": "Nombre del Viaje",
       "grupo": {
         "nombre": "Nombre del Grupo",
         "personas": [
           {
             "nombre": "Nombre de la Persona",
             "gastos": [
               {
                 "descripcion": "Descripción del Gasto",
                 "monto": 100.00
               }
             ]
           }
         ]
       }
     }
     ```

### 2. Obtener Viajes
   - **URL:** `/viajes`
   - **Método:** `GET`
   - **Descripción:** Retorna una lista con todos los viajes registrados.

### 3. Obtener Viaje por ID
   - **URL:** `/viajes/:id`
   - **Método:** `GET`
   - **Descripción:** Retorna la información de un viaje específico.
   - **Parámetros de Ruta:**
     - `id`: ID del viaje a obtener.

### 4. Actualizar Viaje
   - **URL:** `/viajes/:id`
   - **Método:** `PUT`
   - **Descripción:** Permite modificar la información de un viaje existente.
   - **Parámetros de Ruta:**
     - `id`: ID del viaje a actualizar.
   - **Cuerpo de la Solicitud:**
     ```json
     {
       "nombre": "Nuevo Nombre del Viaje",
       "grupo": { /*...*/ }
     }
     ```

### 5. Eliminar Viaje
   - **URL:** `/viajes/:id`
   - **Método:** `DELETE`
   - **Descripción:** Elimina un viaje especificado por su ID.
   - **Parámetros de Ruta:**
     - `id`: ID del viaje a eliminar.

Cada uno de estos endpoints debe ser usado conforme a su método HTTP correspondiente, y en caso de enviar o recibir información, ésta será en formato JSON.
