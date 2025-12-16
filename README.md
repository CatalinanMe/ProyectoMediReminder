=====================================
IacSharp - SISTEMA DE CONTROL DE MEDICAMENTOS (MediReminder)
=====================================

Este proyecto es un sistema web completo de registro e inicio de sesión
con gestión de medicamentos diarios. Incluye:

1. Módulo de Autenticación: Registro e inicio de sesión de usuarios
2. Módulo de Calendario: Seguimiento de toma de medicamentos
3. Módulo de Medicamentos: Agregar y gestionar medicamentos

CARACTERÍSTICAS PRINCIPALES:
✓ Autenticación segura con contraseñas
✓ Calendario interactivo para visualizar medicamentos
✓ Seguimiento de toma diaria de medicamentos
✓ Estadísticas de cumplimiento
✓ Persistencia de datos con localStorage
✓ Interfaz moderna y responsive
✓ Validación completa de formularios

=====================================
REQUISITOS FUNCIONALES
=====================================

RF1: REGISTRO DE USUARIO CON VALIDACIÓN
Descripción: El sistema debe permitir a nuevos usuarios crear una cuenta
con validación completa de datos.

Criterios de Aceptación:

- Solicitar nombre completo, email, contraseña y RUT
- Validar nombre: solo letras y espacios
- Validar email: formato correcto único en el sistema
- Validar contraseña: mínimo 8 caracteres con mayúscula y número
- Validar RUT chileno con algoritmo módulo 11
- Mostrar indicadores visuales de validez
- Guardar usuario en localStorage
- Prevenir duplicados de email
- Modal de confirmación de registro exitoso
- Redirigir a login después del registro

RF2: INICIO DE SESIÓN CON AUTENTICACIÓN
Descripción: El sistema debe permitir a usuarios registrados iniciar
sesión de forma segura.

Criterios de Aceptación:

- Solicitar email y contraseña
- Validar credenciales contra datos almacenados
- Crear sesión activa (usuarioActual)
- Redirigir a calendario tras login exitoso
- Mostrar error si credenciales son incorrectas
- Mantener sesión durante navegación
- Permitir cerrar sesión desde cualquier página
- Validación de email formato

RF3: CALENDARIO INTERACTIVO DE MEDICAMENTOS
Descripción: El sistema debe mostrar un calendario visual que permita
tracking de medicamentos por día.

Criterios de Aceptación:

- Mostrar calendario del mes actual
- Navegar entre meses (anterior/siguiente)
- Indicar día actual con borde especial
- Mostrar estado de medicamentos en cada día:
  ✓ Verde si medicamento fue tomado
  ● Amarillo si medicamento está pendiente
  ✗ Rojo si medicamento no fue tomado (faltada)
- Responder a clicks en días (seleccionar día)
- Actualizar calendario al marcar medicamentos
- Compatible con vista responsive

RF4: GESTIÓN DE MEDICAMENTOS
Descripción: El sistema debe permitir agregar, editar, ver y eliminar
medicamentos.

Criterios de Aceptación:

- Agregar nuevo medicamento con nombre y dosis
- Mostrar lista de medicamentos actuales
- Mostrar estado del medicamento de hoy (tomada/pendiente/faltada)
- Marcar medicamento como "tomado hoy"
- Marcar medicamento como "faltado"
- Eliminar medicamento del sistema
- Guardar cambios en localStorage
- Validar que nombre no esté vacío
- Mostrar información de cada medicamento (nombre, dosis, fecha creación)
- Actualizar interfaz en tiempo real

RF5: ESTADÍSTICAS Y SEGUIMIENTO
Descripción: El sistema debe mostrar estadísticas diarias del cumplimiento
de medicamentos.

Criterios de Aceptación:

- Mostrar número de medicamentos tomados hoy
- Mostrar número de medicamentos pendientes
- Mostrar número de medicamentos faltados
- Mostrar total de medicamentos registrados
- Actualizar estadísticas en tiempo real
- Mostrar en tarjetas visuales con colores
- Tarjetas responsive en grid
- Datos basados en información de hoy

RF6: PERSISTENCIA Y SINCRONIZACIÓN DE DATOS
Descripción: El sistema debe guardar y sincronizar todos los datos del
usuario en localStorage.

Criterios de Aceptación:

- Guardar registro de usuarios
- Mantener sesión activa entre recargas
- Sincronizar cambios en medicamentos
- Guardar historial de fechas de toma
- Guardar historial de fechas faltadas
- Prevenir pérdida de datos al cerrar navegador
- Actualizar datos al cambiar medicamentos
- Mantener datos por usuario (email como identificador)

=====================================
REQUISITOS NO FUNCIONALES
=====================================

RNF1: RENDIMIENTO Y VELOCIDAD
Descripción: La aplicación debe responder de manera rápida a las acciones
del usuario, proporcionando una experiencia fluida sin demoras.

Criterios:

- Tiempo de carga < 2 segundos
- Validación de formularios < 100ms
- Generación de calendario < 200ms
- Transiciones y animaciones 60 FPS
- Tamaño total de archivos < 200KB
- Sin lag perceptible en escritura de texto
- Marcar medicamento como tomado < 500ms
- Navegación entre meses sin delay

RNF2: COMPATIBILIDAD Y RESPONSIVE
Descripción: La aplicación debe ser compatible con múltiples navegadores
y dispositivos, funcionando correctamente en móviles, tablets y desktops.

Criterios:

- Compatible con Chrome 90+
- Compatible con Firefox 88+
- Compatible con Edge 90+
- Compatible con Safari 14+
- Responsive en móviles (< 768px)
- Responsive en tablets (768px - 1024px)
- Responsive en desktops (> 1024px)
- Funciona en pantallas de 320px a 2560px
- Grid calendario adaptable
- Menús responsive

RNF3: SEGURIDAD DE DATOS
Descripción: La aplicación debe proteger los datos del usuario y mantener
privacidad de información sensible.

Criterios:

- Validación de entrada en todos los formularios
- Prevención de XSS mediante sanitización
- Contraseñas almacenadas (sin encriptación en demo - sugerencia: usar bcrypt)
- Sesión únicamente en memoria durante la sesión
- Datos persistentes solo en localStorage (cliente)
- Sin envío de datos a servidores externos
- Logout limpia sesión completamente
- Validación de RUT actual no es fácilmente falsificable

RNF4: USABILIDAD Y UX
Descripción: La interfaz debe ser intuitiva, clara y agradable, minimizando
la necesidad de capacitación del usuario.

Criterios:

- Interfaz auto-explicativa sin manual necesario
- Mensajes de error claros y específicos
- Feedback visual inmediato en acciones
- Indicadores visuales de estado (colores intuitivos)
- Animaciones suaves y no intrusivas
- Paleta de colores profesional y consistente
- Tipografía legible en todos los tamaños
- Contraste WCAG AA mínimo
- Espaciado consistente y lógico
- Botones con estados claros (hover, active, disabled)
- Placeholder descriptivos en campos
- Labels claros y descriptivos

RNF5: MANTENIBILIDAD Y DOCUMENTACIÓN
Descripción: El código debe ser limpio, bien documentado y fácil de
mantener por desarrolladores futuros.

Criterios:

- Código JavaScript modular y reutilizable
- Nombres de variables descriptivos en inglés/español
- Comentarios en funciones complejas
- Documentación completa en README
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

Aplicación cliente para registro de usuarios y seguimiento diario de toma de medicamentos (p. ej. anticonceptivos, vitaminas). Interfaz en `index.html` (registro/login) y `calendario.html` (panel principal con calendario y gestión de medicamentos). El proyecto contiene además una carpeta `IacSharp/` con código .NET 8 original opcional.

**Estado:** Listo para pruebas locales (cliente-side, sin servidor).

**Estructura principal**
- `index.html`  : Registro e inicio de sesión.
- `calendario.html` : Calendario, CRUD de medicamentos y estadísticas.
- `README.md` : Documentación (este archivo).
- `IacSharp/` : Proyecto .NET 8 (código auxiliar / histórico).

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
├── formulario.html ← Formulario web (abrir en navegador)
├── ReadMe.txt ← Este archivo
├── datos_prueba.txt ← Ejemplos y datos de prueba
├── ruts_prueba.txt ← RUTs chilenos válidos para prueba
└── IacSharp/ ← Proyecto .NET 8
├── Program.cs ← Código fuente C#
├── IacSharp.csproj ← Archivo de proyecto
└── bin/
└── Debug/
└── net8.0/
└── IacSharp.exe ← Ejecutable compilado

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

c:\Users(TU RUTA)
├── index.html ← Sistema de autenticación (Registro/Login)
├── calendario.html ← Gestión de medicamentos
├── README.md ← Este archivo
└── IacSharp/ ← Proyecto .NET 8 (opcional)
├── Program.cs
├── IacSharp.csproj
└── bin/...

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
