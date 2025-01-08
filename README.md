### Caso de Uso: Registro de Usuario 

```mermaid
graph TB
    A[Visitante] --> B[Registrarse en Loopify]
    B --> C[Acceder a funcionalidades según rol]
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


