# Proyecto de Formulario de Registro con Pruebas Cypress

Este proyecto implementa un formulario de registro de usuario completamente funcional con validaciones del lado del cliente y pruebas automatizadas utilizando Cypress. El sistema ofrece una experiencia de usuario intuitiva con validación en tiempo real y una página de confirmación que muestra los datos ingresados.

![Formulario de Registro](PruebaZhetian.mp4)

## Características

### Formulario de Registro
- **Campos obligatorios**:
  - Nombre completo
  - Correo electrónico (con validación de formato)
  - Contraseña (con requisitos de seguridad)
  - Confirmación de contraseña
  - Aceptación de términos y condiciones
- **Campos opcionales**:
  - Fecha de nacimiento
- **Validaciones en tiempo real**:
  - Errores específicos para cada tipo de validación
  - Habilitación/deshabilitación del botón de envío según el estado de validación
  - Verificación de coincidencia de contraseñas

### Página de Confirmación
- Mensaje de bienvenida personalizado
- Resumen de la información registrada (sin mostrar la contraseña)
- Opciones para navegar al inicio o continuar al área de usuario

### Tests Automatizados con Cypress
- Verificación de carga correcta del formulario
- Validación de campos obligatorios
- Pruebas de formato y validación de correo electrónico
- Verificación de requisitos de contraseña
- Pruebas de flujo completo de registro
- Manejo de caracteres especiales
- Pruebas básicas de seguridad contra inyección de scripts

## Estructura del Proyecto

```
├── formulario.html      # Página principal con el formulario de registro
├── confirm.html         # Página de confirmación tras registro exitoso
├── style.css            # Estilos CSS para ambas páginas
├── script.js            # Lógica JavaScript para validaciones
├── cypress/             # Directorio de pruebas Cypress
│   └── e2e/             # Tests end-to-end
│       └── form.cy.js   # Tests del formulario de registro
├── cypress.config.js    # Configuración de Cypress
└── package.json         # Dependencias del proyecto
```

## Requisitos Técnicos

### Validaciones Implementadas
1. **Campos obligatorios**: No pueden estar vacíos
2. **Correo electrónico**: Debe tener un formato válido (validado con expresión regular)
3. **Contraseña**: Mínimo 8 caracteres, al menos una letra mayúscula, una minúscula y un número
4. **Confirmación de contraseña**: Debe coincidir con la contraseña
5. **Términos y condiciones**: Debe estar marcado para poder enviar el formulario

### Mensajes de Error
- Implementación de mensajes de error específicos para cada tipo de validación
- Visualización dinámica de errores después de que el usuario interactúa con un campo
- Desactivación del botón de envío cuando hay errores de validación

## Instalación y Ejecución

1. **Clonar el repositorio**:
   ```bash
   git clone <url-del-repositorio>
   cd <nombre-del-directorio>
   ```

2. **Instalar dependencias**:
   ```bash
   npm install
   ```

3. **Ejecutar con servidor local**:
   ```bash
   # Si utilizas XAMPP:
   # Coloca los archivos en la carpeta htdocs
   # Accede a http://localhost/nombre-del-directorio/formulario.html
   
   # Alternativa: usar servidor de desarrollo
   npx http-server
   ```

4. **Ejecutar pruebas de Cypress**:
   ```bash
   # Abrir la interfaz de Cypress
   npm run cy:open
   
   # O ejecutar tests en modo headless
   npx cypress run
   ```

## Pruebas Implementadas

Las pruebas de Cypress incluyen:

1. **Validación de carga del formulario**:
   - Verificación de que todos los elementos estén presentes

2. **Validación de campos**:
   - Pruebas de campos obligatorios vacíos
   - Validación de formato de correo electrónico
   - Requerimientos de seguridad de contraseña
   - Coincidencia de contraseñas

3. **Habilitación/deshabilitación del botón**:
   - Comprobación de que el botón se habilita solo cuando todos los campos son válidos

4. **Flujo completo de registro**:
   - Completar y enviar el formulario
   - Verificar que la página de confirmación muestra los datos correctamente

5. **Pruebas de casos especiales**:
   - Manejo de caracteres especiales y no ASCII
   - Pruebas básicas de prevención de inyección de scripts

## Mejoras Futuras

- Implementación de validación del lado del servidor
- Integración con un sistema de autenticación
- Almacenamiento de datos en una base de datos
- Implementación de opciones de recuperación de contraseña
- Mejora de accesibilidad para cumplir con WCAG

## Tecnologías Utilizadas

- HTML5
- CSS3
- JavaScript (ES6+)
- Cypress 14.1.0 para pruebas automatizadas

## Licencia

ISC

---
