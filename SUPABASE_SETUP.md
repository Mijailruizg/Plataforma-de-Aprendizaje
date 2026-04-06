# 🗄️ Configuración de Supabase (PostgreSQL Database)

## 📋 ¿Qué es Supabase?

Supabase es una base de datos **PostgreSQL** en la nube (como SQLite pero más potente). Puedes ver tus datos en una tabla SQL completa.

---

## 🚀 Pasos de Configuración

### 1️⃣ Crear Cuenta en Supabase

1. Ve a [https://supabase.com](https://supabase.com)
2. Click en "Start your project"
3. Regístrate con Google o email
4. Click en "New Project"

### 2️⃣ Crear Proyecto

- **Project Name:** `nexus-learning`
- **Database Password:** Crea una contraseña segura
- **Region:** La más cercana a ti
- Click "Create new project"

*Espera 2-3 minutos a que se cree*

### 3️⃣ Obtener Credenciales

1. Ve a Settings → API
2. Copia:
   - **Project URL** → `SUPABASE_URL`
   - **Anon Key** (public) → `SUPABASE_KEY`

### 4️⃣ Crear Tabla SQL

1. Ve a **SQL Editor** en Supabase
2. Click en "New Query"
3. Copia y pega este código:

```sql
CREATE TABLE usuarios (
  id BIGSERIAL PRIMARY KEY,
  nombre TEXT NOT NULL,
  email TEXT NOT NULL UNIQUE,
  metodo_login TEXT NOT NULL,
  foto_url TEXT,
  fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  ultimo_acceso TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  estado TEXT DEFAULT 'activo',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Crear índice para búsquedas rápidas
CREATE INDEX idx_email ON usuarios(email);
CREATE INDEX idx_metodo_login ON usuarios(metodo_login);
```

4. Click en "RUN"

### 5️⃣ Actualizar Credenciales en index.html

Abre `index.html` y busca la línea con `SUPABASE_URL`:

```javascript
const SUPABASE_URL = 'https://tu-proyecto.supabase.co';
const SUPABASE_KEY = 'tu-anon-key';
```

Reemplaza con tus credenciales reales.

### 6️⃣ Habilitar RLS (Seguridad - Opcional)

En Supabase → Authentication → Policies:

```sql
-- Permitir inserts públicos (para registro)
CREATE POLICY insert_usuarios ON usuarios
FOR INSERT
TO anon
WITH CHECK (true);

-- Permitir selects públicos (para admin)
CREATE POLICY select_usuarios ON usuarios
FOR SELECT
TO anon
USING (true);
```

---

## ✅ Verificar que Funciona

1. Abre tu app
2. Regístrate o inicia sesión
3. Ve a Supabase → Table Editor → `usuarios`
4. **¡Deberías ver tu usuario en la tabla!**

---

## 📊 Ver Datos SQL

### Opción 1: Interfaz Visual de Supabase ⭐

1. Ve a [tu proyecto Supabase](https://app.supabase.com)
2. Click en "Table Editor" (panel izquierdo)
3. Selecciona tabla `usuarios`
4. **¡Ves todos los usuarios en forma de tabla!**

### Opción 2: SQL Query

1. Ve a "SQL Editor"
2. Ejecuta consultas como:

```sql
-- Ver todos los usuarios
SELECT * FROM usuarios;

-- Contar por método de login
SELECT metodo_login, COUNT(*) as total FROM usuarios GROUP BY metodo_login;

-- Ver últimos 10 registros
SELECT * FROM usuarios ORDER BY fecha_registro DESC LIMIT 10;
```

---

## 🎯 Estructura de la Tabla

```
id             → Identificador único (auto-incremento)
nombre         → Nombre del usuario
email          → Email (único)
metodo_login   → 'google' o 'manual'
foto_url       → Link a la foto de perfil
fecha_registro → Cuándo se registró
ultimo_acceso  → Última conexión
estado         → 'activo', 'inactivo', etc.
created_at     → Timestamp automático
```

---

## 📥 Exportar Datos

### Exportar a CSV:

1. Supabase → Table Editor → `usuarios`
2. Click en ⋮ (tres puntos) → Download
3. Selecciona "CSV"

### Exportar a SQL:

```sql
-- Dump completo de la tabla
SELECT * FROM usuarios;
```

---

## 🔒 Seguridad

⚠️ **Para producción:**

1. Habilita Row Level Security (RLS)
2. Configura políticas de acceso
3. Usa variables de entorno para credenciales
4. No expongas la Anon Key en producción

---

## 💡 Consultas SQL Útiles

```sql
-- Usuarios registrados hoy
SELECT * FROM usuarios WHERE DATE(fecha_registro) = CURRENT_DATE;

-- Contar registros por método
SELECT metodo_login, COUNT(*) FROM usuarios GROUP BY metodo_login;

-- Buscar usuario por email
SELECT * FROM usuarios WHERE email = 'usuario@example.com';

-- Usuarios activos
SELECT * FROM usuarios WHERE estado = 'activo' ORDER BY ultimo_acceso DESC;
```

---

## 🆘 Troubleshooting

**Problema:** "Supabase conectado" pero no se guardan datos
- Solución: Verifica que las credenciales sean correctas
- Verifica que la tabla `usuarios` exista
- Abre la consola (F12) para ver errores

**Problema:** Error de CORS
- Solución: Ve a Supabase → Settings → API → Enable CORS para todo

**Problema:** "Email already exists"
- Solución: El email ya está registrado. Usa otro email para probar.

