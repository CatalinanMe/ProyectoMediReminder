*** Begin MediReminder README ***

# MediReminder

Aplicación web cliente para registro de usuarios y seguimiento diario de
toma de medicamentos. Esta versión está centrada únicamente en la
aplicación web (frontend) y no contiene proyectos .NET ni referencias a
archivos históricos.

**Principal:** `index.html` (registro/login)
**Dashboard:** `calendario.html` (calendario y gestión de medicamentos)

Características resumidas:
- Registro e inicio de sesión (validaciones básicas)
- Calendario mensual con estado por día (tomada / pendiente / faltada)
- CRUD de medicamentos (agregar, eliminar, marcar tomada)
- Estadísticas diarias (tomadas / pendientes / faltadas)
- Persistencia en `localStorage`

Tecnologías usadas:
- HTML5, CSS3
- JavaScript (ES6+)
- Bootstrap 5 (vía CDN)
- Bootstrap Icons (vía CDN)

Cómo ejecutar localmente:
1. Abre `index.html` en un navegador moderno (o sirve la carpeta con un
    servidor estático):

```powershell
cd "C:\Users\Makem\Desktop\Iacsharp"
python -m http.server 8000
# Abrir http://localhost:8000/index.html
```

Datos de prueba:
- Nombre: Juan Pérez García
- Email: juan@example.com
- Contraseña: Password123
- RUT: 12.345.678-9

Estructura del repositorio (actual):
- `index.html`
- `calendario.html`
- `README.md`
- archivos estáticos (CSS/JS en línea o CDN)

Notas de seguridad:
- Los datos se guardan en `localStorage` sin cifrar; no usar en
   producción para datos sensibles.

*** End MediReminder README ***

- Guía clara de instalación y uso
- Ejemplos de datos de prueba
- Estructura de proyecto organizada
- Separación clara HTML/CSS/JavaScript
- Funciones con responsabilidad única
- API clara y consistente

RNF6: ESCALABILIDAD Y CRECIMIENTO FUTURO
Descripción: La arquitectura debe permitir agregar nuevas funcionalidades
sin comprometer el funcionamiento actual.

Criterios:

- Código modular para agregar nuevos medicamentos
- Fácil agregar recordatorios/notificaciones
- Estructura preparada para migrar a backend (API)
- Posibilidad de agregar base de datos
- Preparado para sistema de backup/exportación
- Facilidad para agregar temas/estilos
- Soporte para múltiples idiomas (i18n ready)
- Logging preparado para debugging
- Sistema de versionado implementado
- Changelog documentado

RNF7: ALMACENAMIENTO Y DATOS
Descripción: El sistema debe manejar correctamente el almacenamiento y
sincronización de datos del usuario.

Criterios:

- LocalStorage como persistencia (demo)
- Máximo 5-10MB de datos permitidos
- Sincronización automática entre tabs
- Recuperación de datos tras recargar página
- Histórico de cambios por medicamento
- Datos organizados por usuario (email)
- Integridad de datos verificada
- Validación de estructura de datos

RNF8: ACCESIBILIDAD
Descripción: La aplicación debe ser accesible para usuarios con diferentes
capacidades, incluyendo personas con discapacidades.

Criterios:

- WCAG 2.1 Level AA compliance
- Compatible con lectores de pantalla
- Navegación por teclado funcional
- Atributos aria-\* implementados
- Etiquetas semánticas HTML5
- Alt text en iconos descriptivos
- Color no es el único medio de información
- Suficiente contraste de colores
- Tamaño de fuente ajustable
- Sin captchas sin alternativa

=====================================
CÓMO EJECUTAR LA APLICACIÓN
=====================================

OPCIÓN 1: Abrir directamente (más rápido)

1. Navega a la ruta principal de tu archivo
2. Haz doble clic en: index.html
3. Se abrirá automáticamente en tu navegador

OPCIÓN 2: Desde PowerShell

1. Abre PowerShell
2. Ejecuta:
   start C:\Users\xxxx(tu ruta)

OPCIÓN 3: Servir localmente (recomendado)

1. Abre PowerShell en la carpeta del proyecto
2. Ejecuta: python -m http.server 8000
3. Abre: http://localhost:8000/index.html

FLUJO DE LA APLICACIÓN:

1. index.html → Página de Registro/Login
2. calendario.html → Gestión de Medicamentos (después de login)
3. # Cerrar Sesión → Vuelve a index.html

VERSIÓN C# (Consola):

- .NET 8 instalado (o al menos .NET Runtime 8)
- Sistema Operativo: Windows, Linux o macOS

VERSIÓN HTML (Web):

- Navegador web moderno (Chrome, Firefox, Edge, Safari)
- No requiere instalación adicional

# MediReminder

Aplicación cliente para registro de usuarios y seguimiento diario de toma de medicamentos (p. ej. anticonceptivos, vitaminas). Interfaz en `index.html` (registro/login) y `calendario.html` (panel principal con calendario y gestión de medicamentos). Este repositorio NO incluye ya el proyecto `IacSharp/` — la versión .NET previa fue eliminada y el repositorio está centrado en la app web.

**Estado:** Listo para pruebas locales (cliente-side, sin servidor).

**Estructura principal**
- `index.html`  : Registro e inicio de sesión.
- `calendario.html` : Calendario, CRUD de medicamentos y estadísticas.
- `README.md` : Documentación (este archivo).

**Características principales**
- Registro y login en el navegador.
- Validación de RUT (formato chileno), email y permisos mínimos de contraseña.
- Calendario mensual con marcadores: tomada (verde), pendiente (amarillo), faltada (rojo).
- Añadir/eliminar medicamentos y marcar toma diaria.
- Estadísticas diarias (tomadas / pendientes / faltadas).
- Persistencia en `localStorage` (sin backend).

**Tecnologías usadas**
- **HTML5** y **CSS3**
- **JavaScript (ES6+)** — lógica del frontend
- **Bootstrap 5.3.0** — estilos y componentes UI
- **Bootstrap Icons** — iconografía
- **localStorage** — persistencia de datos en navegador
- **(Opcional)** .NET 8 / C# en `IacSharp/` (código original de validación)

**Limitaciones y notas de seguridad**
- Todos los datos (incluidas contraseñas) se almacenan en `localStorage` sin cifrar. Esto está bien para pruebas locales o demos, pero **no es seguro** para producción.
- Para producción: mover autenticación y datos a servidor seguro, usar hashing (bcrypt), HTTPS, y una base de datos.

**Cómo ejecutar localmente (rápido)**
Puedes abrir `index.html` directamente en el navegador (archivo local) o usar un servidor estático para evitar limitaciones CORS cuando pruebes desde múltiples archivos.

Ejemplo usando Python (recomendado si tienes Python instalado):

```powershell
cd "ruta de tu archivo"
python -m http.server 8000
# Luego abre: http://localhost:8000/index.html
```

O usando `npx serve` (Node.js):

```powershell
cd "ruta de tu archivo"
npx serve -s . -l 8000
# Luego abre: http://localhost:8000/index.html
```

También puedes abrir directamente `file:///C:/Users/Makem/Desktop/Iacsharp/index.html` en el navegador para pruebas básicas.

**Datos de prueba**
- Registro (ejemplo):
  - Nombre: `Juan Pérez García`
  - Email: `juan@example.com`
  - Contraseña: `Password123`
  - RUT: `12.345.678-9`

**Estructura de datos en `localStorage`**
- `usuarios` : array de objetos usuario
- `usuarioActual` : objeto con sesión activa (email, nombre, `pastillas`)
- Cada `pastilla` contiene: `id`, `nombre`, `dosis`, `fechaCreacion`, `fechasTomadas` (array YYYY-MM-DD), `fechasFaltadas` (array YYYY-MM-DD)



CORREO ELECTRÓNICO:
✓ Formato: usuario@dominio.extension
✓ Máximo 255 caracteres
✓ Validación con expresión regular

Ejemplos válidos:

- juan.perez@example.com
- maria@empresa.cl
- usuario+tag@dominio.co.uk

RUT CHILENO:
✓ Máximo 9 dígitos
✓ Formatos aceptados: - 123456789 (solo dígitos) - 12345678-9 (con guión) - 12.345.678-9 (formato completo)
✓ Validación de dígito verificador (algoritmo módulo 11)
✓ Autoformatea mientras escribes

Ejemplos válidos:

- 12345678-9 → 12.345.678-9
- 19876543-K → 19.876.543-K
- 15234567-8 → 15.234.567-8

=====================================
DATOS DE PRUEBA
=====================================

RUTs VÁLIDOS PARA PROBAR:

1. 12345678-9 (Formato: 12.345.678-9)
2. 19876543-K (Formato: 19.876.543-K)
3. 15234567-8 (Formato: 15.234.567-8)
4. 24830440-9 (Formato: 24.830.440-9)
5. 16500000-0 (Formato: 16.500.000-0)

EJEMPLO DE FORMULARIO COMPLETO:
Nombre: Juan Pérez García
Email: juan.perez@example.com
RUT: 12.345.678-9

=====================================
ESTRUCTURA DEL PROYECTO
=====================================

c:\xxxx(Tu ruta)
├── index.html ← Sistema de autenticación (Registro/Login)
├── calendario.html ← Gestión de medicamentos
├── README.md ← Este archivo
└── (archivos auxiliares y recursos estáticos)

=====================================
SOLUCIÓN DE PROBLEMAS
=====================================

PROBLEMA: El HTML no se abre
SOLUCIÓN:

1. Verifica la ruta: c:\Users(TU RUTA)
2. Intenta abrir con PowerShell: start c:\Users(TU RUTA)
3. O arrastra el archivo al navegador

PROBLEMA: El .NET no se encuentra
SOLUCIÓN:

1. Verifica que .NET 8 esté instalado: dotnet --version
2. Si no está instalado, descargalo desde: https://dotnet.microsoft.com/download

PROBLEMA: El RUT no se valida
SOLUCIÓN:

1. Verifica que sea un RUT chileno válido (usa los ejemplos de prueba)
2. Asegúrate de incluir el dígito verificador con guión (ej: 12345678-9)
3. Recarga la página si hay dudas

PROBLEMA: Los caracteres especiales se aceptan en el nombre
SOLUCIÓN:

1. Recarga la página: Ctrl + F5 (limpia caché)
2. Asegúrate de que solo uses letras y espacios

PROBLEMA: La barra de progreso no avanza
SOLUCIÓN:

1. Recarga la página: F5 o Ctrl + R
2. Intenta nuevamente ingresando datos en los campos

=====================================
INFORMACIÓN TÉCNICA
=====================================

VERSIÓN .NET: 8.0
FRAMEWORKS: .NET
LENGUAJES: C#, HTML5, CSS3, JavaScript (ES6+)

LIBRERÍAS UTILIZADAS:

- Bootstrap 5.3.0 (vía CDN)
- Bootstrap Icons 1.11.0 (vía CDN)

FUNCIONALIDADES:

- Validación de email con regex
- Validación de RUT con algoritmo módulo 11
- Formateo automático de RUT
- Contador de caracteres en tiempo real
- Barra de progreso interactiva
- Modal de confirmación
- Almacenamiento temporal de datos en variables

NAVEGADORES SOPORTADOS:

=====================================
ESTRUCTURA DEL PROYECTO
=====================================

c:\Users\Makem\Desktop\Iacsharp\
├── index.html                 ← Sistema de autenticación (Registro/Login)
├── calendario.html            ← Gestión de medicamentos
├── README.md                  ← Este archivo
└── (proyecto .NET histórico eliminado; repositorio centrado en la app web)

=====================================
GUÍA DE USO
=====================================

PASO 1: CREAR CUENTA

1. Abre index.html
2. Completa el formulario de registro:
   - Nombre: solo letras y espacios
   - Email: formato válido
   - Contraseña: 8+ caracteres, 1 mayúscula, 1 número
   - RUT: formato chileno (12.345.678-9)
3. Verifica que todos los campos sean válidos (✓)
4. Haz clic en "Crear Cuenta"
5. Se abrirá automáticamente el login

PASO 2: INICIAR SESIÓN

1. Ingresa tu email y contraseña
2. Haz clic en "Inicia Sesión"
3. Serás redirigido al calendario

PASO 3: GESTIONAR MEDICAMENTOS

1. En la página de calendario:
   - Ver estadísticas diarias
   - Navegar entre meses
   - Ver estado de medicamentos por día
2. Agregar medicamento:
   - Ingresa nombre y dosis
   - Haz clic en "Agregar"
3. Marcar como tomado:
   - Haz clic en "Marcar Tomada" en la tarjeta del medicamento
4. Eliminar medicamento:
   - Haz clic en "Eliminar"

PASO 4: CERRAR SESIÓN

- Haz clic en "Cerrar Sesión" en la esquina superior derecha
- Volverás a la página de login

=====================================
DATOS DE PRUEBA
=====================================

Puedes usar estos datos para probar la aplicación:

REGISTRO (Crear nueva cuenta):
Nombre: Juan Pérez García
Email: juan@example.com
Contraseña: Password123
RUT: 12.345.678-9

MEDICAMENTOS DE PRUEBA:

1. Anticonceptivo - 1 pastilla
2. Vitamina D - 1 cápsula
3. Omega 3 - 1 cápsula
4. Magnesio - 1 comprimido

=====================================
CARACTERÍSTICAS ADICIONALES
=====================================

1. RESPONSIVE DESIGN

   - Funciona en móviles, tablets y desktops
   - Adaptación automática de layouts
   - Interfaz optimizada por dispositivo

2. ANIMACIONES SUAVES

   - Transiciones en formularios
   - Cambios entre tabs
   - Actualizaciones de calendario

3. ALMACENAMIENTO LOCAL

   - Los datos se guardan en tu navegador (localStorage)
   - Persisten entre sesiones
   - Sin necesidad de servidor

4. SEGURIDAD
   - Validación de entrada completa
   - Prevención de duplicados
   - Contraseñas en localStorage (NOTA: en producción usar bcrypt)
   - Sesión local únicamente
   - Prevención de caracteres inválidos

=====================================
NOTAS FINALES
=====================================

- El formulario HTML es completamente autónomo (no requiere servidor)
- Los datos se almacenan solo en la memoria del navegador (sesión actual)
- Al recargar la página, se limpian los datos
- La validación del RUT sigue el estándar chileno vigente
- Compatible con navegadores modernos

RECOMENDACIÓN:
Para una experiencia óptima, usa el formulario HTML (formulario.html).
Es más rápido, más amigable y no requiere instalaciones adicionales.

=====================================
VERSIÓN: 1.0
FECHA: Noviembre 2025
Trabajo realizado en Conjunto a tecnologias de IA: COPILOT en VSC
=====================================
