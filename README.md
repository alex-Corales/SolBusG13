# Aplicación Java de Escritorio - Administración de Venta de Pasajes SOL BUS

## Descripción del Proyecto

Esta aplicación de escritorio en Java permite administrar la venta de pasajes de colectivos para la empresa **SOL BUS Línea La Punta**. La aplicación gestiona rutas, horarios, pasajeros y ventas de pasajes, interactuando con una base de datos MySQL para el almacenamiento eficiente de la información.

## Objetivo

Desarrollar una aplicación que facilite la administración de pasajes de colectivos mediante una interfaz intuitiva y robusta, permitiendo a los usuarios realizar gestiones de forma eficiente y confiable.

## Características Principales

### 1. **Gestión de Rutas**
- Agregar nuevas rutas con origen y destino.
- Visualizar la lista de rutas disponibles.
- Buscar rutas por origen o destino.

### 2. **Gestión de Horarios**
- Agregar horarios a las rutas con hora de salida y llegada.
- Visualizar horarios disponibles para una ruta.
- Buscar horarios por ruta u horario de salida.

### 3. **Gestión de Pasajeros**
- Registrar nuevos pasajeros.
- Visualizar la lista de pasajeros.
- Buscar pasajeros por nombre, apellido o documento de identidad.

### 4. **Gestión de Ventas de Pasajes**
- Registrar la venta de pasajes, asociando ruta, horario y pasajero.
- Visualizar el historial de ventas con filtros por ruta, horario o pasajero.
- Emitir recibos de venta y anular ventas.

## Requisitos Técnicos

### **Interfaz de Usuario**
- La aplicación contará con una interfaz gráfica desarrollada con **Swing**.

### **Persistencia de Datos**
- Base de datos **MySQL**.
- Interacción con la base de datos a través de **JDBC**.

### **Esquema de Base de Datos**

#### 1. **Tabla: Pasajeros**
- `ID_Pasajero` (INT, PK)
- `Nombre` (VARCHAR)
- `Apellido` (VARCHAR)
- `DNI` (VARCHAR, Único)
- `Correo` (VARCHAR, Único)
- `Teléfono` (VARCHAR)
- `Estado` (BOOLEAN)

#### 2. **Tabla: Pasajes**
- `ID_Pasaje` (INT, PK)
- `ID_Pasajero` (INT, FK)
- `ID_Colectivo` (INT, FK)
- `ID_Ruta` (INT, FK)
- `Fecha_Viaje` (DATE)
- `Hora_Viaje` (TIME)
- `Asiento` (INT)
- `Precio` (DECIMAL)

#### 3. **Tabla: Colectivos**
- `ID_Colectivo` (INT, PK)
- `Matrícula` (VARCHAR)
- `Marca` (VARCHAR)
- `Modelo` (VARCHAR)
- `Capacidad` (INT)
- `Estado` (BOOLEAN)

#### 4. **Tabla: Rutas**
- `ID_Ruta` (INT, PK)
- `Origen` (VARCHAR)
- `Destino` (VARCHAR)
- `Duración_Estimada` (TIME)
- `Estado` (BOOLEAN)

#### 5. **Tabla: Horarios**
- `ID_Horario` (INT, PK)
- `ID_Ruta` (INT, FK)
- `Hora_Salida` (TIME)
- `Hora_Llegada` (TIME)
- `Estado` (BOOLEAN)

### **Relaciones entre Tablas**
- Un **pasajero** puede tener múltiples pasajes, pero un pasaje está asociado a un solo pasajero.
- Un **pasaje** está asociado a un colectivo y una ruta específica.
- Una **ruta** puede tener múltiples horarios.

## Funcionalidades Clave

### **Operaciones CRUD**
- Implementadas para todas las entidades (Rutas, Horarios, Pasajeros, Ventas).

### **Validación de Datos**
- Validación de formato, longitud y campos requeridos.
- Control de capacidad de colectivos para evitar sobreventa de pasajes.

### **Manejo de Errores**
- Mensajes de error informativos para el usuario.
- Prevención de datos duplicados y manejo de campos vacíos.

## Tecnologías Utilizadas
- **Java** (Swing, JDBC)
- **MySQL** (Persistencia de datos)
- **Patrón MVC** (Separación de lógica y UI)

## Instalación y Configuración
1. **Clonar el repositorio**
   ```sh
   git clone https://github.com/tu-repo/sol-bus.git
   ```
2. **Configurar la Base de Datos**
   - Crear una base de datos MySQL con el esquema mencionado.
   - Actualizar la configuración de conexión en el archivo de configuración.
3. **Ejecutar la Aplicación**
   - Compilar y ejecutar la aplicación desde un IDE compatible con Java.

## Contribución
Las contribuciones son bienvenidas. Para colaborar:
1. Realizar un fork del repositorio.
2. Crear una rama nueva para la funcionalidad.
3. Enviar un pull request para revisión.

## Contacto
Para dudas o soporte, contactar a: **correo@solbus.com**
