<h1 style="text-align: center;">CASOS DE USO</h1>

### Caso de Uso: Registro de Usuario 

```mermaid
graph TB
    A[Visitante] --> B[Registrarse en Loopify]
    B --> C[Acceder a funcionalidades según rol]
```

### Diagrama de Secuencia: Acceso al Formulario de Registro

```mermaid
sequenceDiagram
    participant Visitante
    participant Sistema

    Visitante->>Sistema: Acceder al formulario de registro
    Sistema-->>Visitante: Mostrar formulario de registro
    Visitante->>Sistema: Completar los campos (nombre, correo y contraseña)
    Sistema-->>Visitante: Validar campos obligatorios
    Sistema-->>Visitante: Permitir continuar si los campos son válidos
```

### Diagrama de Secuencia: Asignación de Rol de Cliente

```mermaid
sequenceDiagram
    participant Cliente
    participant Sistema

    Cliente->>Sistema: Completar registro
    Sistema-->>Cliente: Asignar rol de cliente automáticamente
    Sistema-->>Cliente: Confirmar registro exitoso
```

### Diagrama de Secuencia: Creación de Cuenta por Administrador

```mermaid
sequenceDiagram
    participant Vendedor
    participant Sistema
    participant Administrador

    Vendedor->>Sistema: Completar registro
    Sistema-->>Administrador: Notificar creación de cuenta pendiente
    Administrador->>Sistema: Aprobar o rechazar la cuenta
    Sistema-->>Vendedor: Notificar estado de la cuenta
```

### Diagrama de Secuencia: Validación de Correo Único

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Completar registro con correo
    Sistema-->>Sistema: Validar si el correo ya está registrado
    alt Correo no único
        Sistema-->>Usuario: Mostrar mensaje de error
    else Correo único
        Sistema-->>Usuario: Continuar con el registro
    end
```

### Diagrama de Secuencia: Mensaje de Confirmación de Registro

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Completar registro exitosamente
    Sistema-->>Usuario: Mostrar mensaje de confirmación
```

### Diagrama de Secuencia: Tiempo de Carga del Formulario

```mermaid
sequenceDiagram
    participant Visitante
    participant Sistema

    Visitante->>Sistema: Acceder al formulario de registro
    Sistema-->>Visitante: Mostrar formulario en menos de 2 segundos
```

### Diagrama de Secuencia: Cifrado de Contraseña

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Completar registro con contraseña
    Sistema-->>Sistema: Cifrar contraseña
    Sistema-->>Usuario: Confirmar registro exitoso
```


### Caso de Uso: Inicio de Sesion 

```mermaid
graph TB
    A[Usuario registrado] --> B[Acceder al formulario de inicio de sesión]
    B --> C[Ingresar credenciales]
    C --> D[Validar credenciales]
    D --> E{¿Credenciales válidas?}
    E -- No --> F[Mostrar mensaje de error]
    E -- Sí --> G[Acceder a la cuenta según el rol] 
```

### Diagrama de Secuencia: Campos de Inicio de Sesión

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Acceder al formulario de inicio de sesión
    Sistema-->>Usuario: Mostrar campos para correo y contraseña
```

### Diagrama de Secuencia: Mensaje de Error por Credenciales Incorrectas

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Intentar iniciar sesión con credenciales incorrectas
    Sistema-->>Sistema: Validar credenciales
    Sistema-->>Usuario: Mostrar mensaje de error claro
```

### Diagrama de Secuencia: Redirección según Rol

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Iniciar sesión con credenciales correctas
    Sistema-->>Sistema: Verificar rol del usuario
    Sistema-->>Usuario: Redirigir según rol (ej. cliente, vendedor, administrador)
```

### Diagrama de Secuencia: Redirección para Administrador

```mermaid
sequenceDiagram
    participant Administrador
    participant Sistema

    Administrador->>Sistema: Iniciar sesión
    Sistema-->>Sistema: Verificar rol de administrador
    Sistema-->>Administrador: Redirigir a la vista de gestión de vendedores y negocios
```

### Diagrama de Secuencia: Recuperación de Contraseña

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Solicitar recuperación de contraseña
    Sistema-->>Usuario: Enviar correo con enlace para restablecer contraseña
```

### Diagrama de Secuencia: Inicio de Sesión en Menos de 3 Segundos

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Intentar iniciar sesión
    Sistema-->>Sistema: Validar credenciales
    Sistema-->>Usuario: Completar el inicio de sesión en menos de 3 segundos
```

### Diagrama de Secuencia: Expiración de Sesión por Inactividad

```mermaid
sequenceDiagram
    participant Usuario
    participant Sistema

    Usuario->>Sistema: Estar inactivo durante 30 minutos
    Sistema-->>Sistema: Detectar inactividad
    Sistema-->>Usuario: Expirar sesión automáticamente
```

### Caso de Uso: Gestion de Vendedores 

```mermaid
graph TB
    A[Administrador] --> B[Crear cuenta de vendedor]
    A --> C[Editar cuenta de vendedor]
    A --> D[Eliminar cuenta de vendedor]
    B --> E[Cuenta creada correctamente]
    C --> F[Cambios guardados correctamente]
    D --> G[Cuenta eliminada correctamente]
```

### Caso de Uso: Gestión de negocios

```mermaid
graph TB
    A[Vendedor] --> B[Crear negocio]
    A --> C[Editar negocio]
    A --> D[Eliminar negocio]
    B --> E[Negocio creado correctamente]
    C --> F[Cambios guardados correctamente]
    D --> G[Negocio eliminado correctamente]
```

### Caso de Uso: Publicación de productos

```mermaid
graph TB
    A[Vendedor] --> B[Agregar producto con descuento]
    B --> C[Producto agregado al negocio]
    C --> D[Producto visible para clientes]
```

### Caso de Uso: Recuperacion de contraseña 

```mermaid
graph TB
    A[Usuario registrado] --> B[Solicitar recuperación de contraseña]
    B --> C[Ingresar correo asociado a la cuenta]
    C --> D[Validar correo]
    D --> E{¿Correo válido?}
    E -- No --> F[Mostrar mensaje de error]
    E -- Sí --> G[Enviar enlace de recuperación]
    G --> H[Acceder a la página para restablecer contraseña]
    H --> I[Restablecer contraseña]
    I --> J[Contraseña restablecida correctamente]
```

### Caso de Uso: Visualizacion de Negocios

```mermaid
graph TB
    A[Cliente] --> B[Ver lista de negocios disponibles]
    B --> C[Explorar los productos del negocio]
```

### Caso de Uso: Compra de Productos 

```mermaid
graph TB
    A[Cliente] --> B[Seleccionar producto]
    B --> C[Agregar producto al carrito de compras]
    C --> D[Producto agregado correctamente]
    D --> E[Visualizar carrito de compras]
```

### Caso de Uso: Reportes 

```mermaid
graph TB
    A[Administrador] --> B[Generar reporte de ventas]
    A --> C[Generar reporte de productos]
    B --> D[Reporte de ventas generado]
    C --> E[Reporte de productos generado]
    D --> F[Evaluar rendimiento de la plataforma]
    E --> F
```

### Caso de Uso: Notificaciones 

```mermaid
graph TB
    A[Cliente] --> B[Suscribirse a notificaciones]
    B --> C[Recibir notificación de nuevos productos]
    C --> D[Ver detalles del producto]
    D --> E[Aprovechar ofertas antes de que se agoten]
```


