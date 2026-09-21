# Getsemaní Kids · Sistema de asistencia

Sitio web con HTML, CSS y un poco de JavaScript. Se conecta a **Supabase**.

## Estructura

```
getsemani-asistencia/
├── index.html        ← las 3 pantallas (inicio, salones, lista). Aquí editas el texto de la iglesia y la dirección.
├── css/styles.css    ← todos los colores y estilos
├── js/config.js      ← aquí pegas la URL y la clave de Supabase
├── js/app.js         ← la lógica (asistencia, administrador, Excel, Supabase)
├── img/              ← logo, fondo, salones e íconos de niña y niño
└── supabase.sql      ← crea las tablas en Supabase
```

## 1. Probarlo en Visual Studio Code (modo demostración)

1. Abre la carpeta `getsemani-asistencia` en VS Code (**Archivo → Abrir carpeta**).
2. Instala la extensión **Live Server** (de Ritwick Dey).
3. Clic derecho sobre `index.html` → **Open with Live Server**.

Sin configurar Supabase funciona en **modo demostración** (los datos quedan solo en tu navegador).
Administrador de prueba: `admin@getsemani.pe` / `admin123`.

## 2. Conectar Supabase

1. Crea un proyecto en https://supabase.com.
2. **SQL Editor → New query**, pega el contenido de `supabase.sql` y pulsa **Run**.
3. **Authentication → Users → Add user → Create new user**: escribe el correo y la contraseña del administrador (marca *Auto Confirm User*).
4. **Authentication → Sign In / Providers**: desactiva *Allow new users to sign up*, para que nadie más pueda crear cuentas.
5. **Project Settings → API**: copia **Project URL** y la clave **anon / publishable**, y pégalas en `js/config.js`.
6. Recarga la página. El aviso amarillo de "modo demostración" desaparece.

> No pegues nunca la clave `service_role` en `config.js`.

## 3. Publicarlo (opcional)

Sube la carpeta completa a Netlify, Vercel o GitHub Pages (son sitios estáticos, no necesitan servidor).

## Cómo se usa

- **Salones:** cada icono abre la lista del salón. Primero aparecen las niñas y luego los niños.
- **Tomar asistencia:** elige la fecha, toca *Presente* o *Falta* en cada estudiante y pulsa **Guardar asistencia**.
- **Excel:** **Descargar Excel** genera un archivo con la asistencia de la fecha elegida y otra hoja con el historial del salón.
- **Administrador:** botón *Administrador* → inicia sesión → aparecen *Agregar estudiante* y los botones de editar y quitar. Quitar oculta al estudiante de la lista pero conserva su historial.
