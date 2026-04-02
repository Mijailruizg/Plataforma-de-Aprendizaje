# 🚀 NEXUS Learning - Plataforma de Aprendizaje Futurista

Una plataforma moderna de e-learning con interfaz futurista, autenticación flexible y seguimiento de progreso.

![Status](https://img.shields.io/badge/Status-Activo-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)
![Version](https://img.shields.io/badge/Version-1.0.0-blue)

---

## ✨ Características

### 🔐 Autenticación Flexible
- **Login Manual**: Email y contraseña con validaciones
- **Crear Cuenta**: Registro completo y seguro
- **Google Sign-In**: Autenticación con Google OAuth 2.0

### 📚 Sistema de Aprendizaje
- 15 lecciones progresivas y desafiantes
- Sistema de bloqueo inteligente (desbloquea completando la anterior)
- Seguimiento de progreso en tiempo real
- Persistencia de datos con localStorage

### 🎨 Interfaz Moderna
- Diseño futurista con gradientes cian y magenta
- Animaciones suaves y efectos visuales
- Responsive design (móvil, tablet, desktop)
- Tema oscuro con elementos glassmorphism

---

## 🚀 Inicio Rápido

### Opción 1: Live Server (VS Code) - Recomendada ⭐
```bash
1. Haz clic derecho en index.html
2. Selecciona "Open with Live Server"
3. ¡La app se abre automáticamente en http://127.0.0.1:5500!
```

### Opción 2: Python
```bash
cd "app de pacheco"
python -m http.server 8000
# Accede a http://localhost:8000
```

### Opción 3: Node.js
```bash
npm install -g http-server
http-server
# Accede a http://localhost:8080
```

---

## 📖 Cómo Usar

### Registrarse (Crear Cuenta)
1. Haz clic en la pestaña **"Crear Cuenta"**
2. Completa tus datos:
   - Nombre completo
   - Email
   - Contraseña (mínimo 6 caracteres)
   - Confirmar contraseña
3. Haz clic en **"Crear Cuenta"**
4. ¡Automáticamente iniciarás sesión!

### Iniciar Sesión
1. Usa la pestaña **"Iniciar Sesión"**
2. Ingresa tu email y contraseña
3. O haz clic en **"Iniciar sesión con Google"** para acceso rápido

### Aprender y Progresar
- Haz clic en cualquier lección para abrirla
- Lee el contenido y aprende
- Haz clic en **"Marcar como Completada ✓"** para desbloquear la siguiente
- Ve tu progreso percentual en la barra superior
- Los datos se guardan automáticamente

---

## 🔧 Configuración de Google OAuth

Si obtienes el error **"no registered origin"**, sigue estos pasos:

### 1️⃣ Abre Google Cloud Console
```
https://console.cloud.google.com
```

### 2️⃣ Ve a Credenciales OAuth
- Menú lateral izquierdo → **Credenciales**
- Busca y haz clic en tu **OAuth 2.0 Client ID**

### 3️⃣ Agrega Orígenes Autorizados

En **"Orígenes autorizados de JavaScript"**, agrega:
```
http://localhost:5500
http://127.0.0.1:5500
http://localhost:8000
http://127.0.0.1:8000
```

En **"URI de redireccionamiento autorizados"**, agrega lo mismo:
```
http://localhost:5500
http://127.0.0.1:5500
http://localhost:8000
http://127.0.0.1:8000
```

### 4️⃣ Guarda y Espera
- Click en **"Guardar"**
- Espera 1-2 minutos para que se propague la configuración

**Tu Client ID:**
```
94848851465-nib239skv567avoccnei5r8mj2ju94qi.apps.googleusercontent.com
```

---

## 📁 Estructura del Proyecto

```
Plataforma-de-Aprendizaje/
├── index.html                      # 📱 Aplicación principal (TODO-EN-UNO)
├── README.md                       # 📖 Este archivo - Guía completa
├── INSTRUCCIONES_GOOGLE_OAUTH.txt  # 🔐 Configuración OAuth detallada
└── .gitignore                      # Git - Archivos ignorados
```

---

## 💾 Almacenamiento de Datos

Los datos se guardan en **localStorage** del navegador:

| Clave | Descripción |
|-------|-------------|
| `userData` | Información del usuario actualmente logueado |
| `completedLessons` | IDs de lecciones completadas por el usuario |
| `registeredUsers` | Base de datos local de usuarios registrados |

⚠️ **Nota Importante**: Para una aplicación en producción, necesitarías migrar a un backend con base de datos segura (MongoDB, PostgreSQL, etc.)

---

## 🎓 Lecciones Disponibles (15 Temas)

| # | Título | Duración | Estado |
|---|--------|----------|--------|
| 1 | 🚀 Fundamentos del Futuro | 45 min | ✅ Disponible |
| 2 | 🤖 Inteligencia Artificial | 60 min | ✅ Disponible |
| 3 | 🥽 Realidad Extendida | 50 min | ✅ Disponible |
| 4 | ⛓ Blockchain Descentralizado | 55 min | 🔒 Bloqueado* |
| 5 | ⚛ Computación Cuántica | 65 min | 🔒 Bloqueado* |
| 6 | 📡 IoT y Conectividad | 40 min | 🔒 Bloqueado* |
| 7 | 🔒 Ciberseguridad Avanzada | 70 min | 🔒 Bloqueado* |
| 8 | 🦾 Automatización Robótica | 45 min | 🔒 Bloqueado* |
| 9 | 📊 Big Data & Analytics | 60 min | 🔒 Bloqueado* |
| 10 | 📶 5G y Telecomunicaciones | 50 min | 🔒 Bloqueado* |
| 11 | ⚡ Energías Renovables | 55 min | 🔒 Bloqueado* |
| 12 | 🧬 Biotecnología | 65 min | 🔒 Bloqueado* |
| 13 | 🔬 Nanotecnología | 60 min | 🔒 Bloqueado* |
| 14 | 🚗 Transporte del Futuro | 45 min | 🔒 Bloqueado* |
| 15 | 🏆 Proyecto Final Integrador | 90 min | 🔒 Bloqueado* |

*Se desbloquean progresivamente al completar la lección anterior

---

## 🧪 Usuarios de Prueba

Crea tus propios usuarios usando **"Crear Cuenta"** o usa:

```
Email: test@example.com
Contraseña: password123
```

---

## 🛠️ Tecnologías Utilizadas

- **HTML5** - Estructura semántica
- **CSS3** - Estilos modernos
  - Glassmorphism
  - Gradientes CSS
  - Animaciones suaves
- **JavaScript Vanilla** - Interactividad sin frameworks
- **Google Identity Services** - OAuth 2.0 nativo
- **LocalStorage API** - Persistencia de datos

---

## 📱 Compatibilidad de Navegadores

| Navegador | Soporte |
|-----------|---------|
| Chrome/Chromium | ✅ Completo |
| Firefox | ✅ Completo |
| Safari | ✅ Completo |
| Edge | ✅ Completo |
| Móviles iOS/Android | ✅ Responsive |

---

## 🚀 Roadmap - Próximas Mejoras

- [ ] **Backend API** - Node.js/Express
- [ ] **Base de Datos** - MongoDB o PostgreSQL
- [ ] **Encriptación** - bcrypt para contraseñas
- [ ] **JWT** - Autenticación por tokens
- [ ] **Recuperación de Contraseña** - Email recovery
- [ ] **Confirmación de Email** - Verificación de cuenta
- [ ] **Multimedia** - Videos y PDFs embebidos
- [ ] **Certificados** - Diplomas descargables
- [ ] **Sistema de Puntos** - Gamificación
- [ ] **Comunidad** - Foros y comentarios
- [ ] **Analytics** - Estadísticas de aprendizaje
- [ ] **Mobile App** - React Native/Flutter

---

## ❓ Preguntas Frecuentes

**P: ¿Los datos se pierden al cerrar el navegador?**  
R: No. Se guardan indefinidamente en localStorage. Se pierden solo si limpias caché/cookies.

**P: ¿Puedo usar esto en producción?**  
R: Parcialmente. La autenticación necesita un backend seguro para proteger contraseñas.

**P: ¿Cómo modifico las lecciones?**  
R: Edita el objeto `lessonsData` en el script de index.html (alrededor de línea 1000).

**P: ¿Por qué hay 3 formas de login?**  
R: Para flexibilidad. Los usuarios pueden elegir: email, cuenta nueva, o Google.

**P: ¿Dónde está el backend?**  
R: Este es un prototipo frontend. El backend está en el roadmap.

**P: ¿Puedo compartir esto en redes?**  
R: Sí, es proyecto open-source con licencia MIT.

---

## 📞 Contacto y Soporte

- **Email**: mijailandresr@gmail.com
- **GitHub**: [@Mijailruizg](https://github.com/Mijailruizg)
- **Repositorio**: [Plataforma-de-Aprendizaje](https://github.com/Mijailruizg/Plataforma-de-Aprendizaje)

---

## 📄 Licencia

Este proyecto está bajo la **Licencia MIT**. Eres libre de:
- ✅ Usar comercialmente
- ✅ Modificar el código
- ✅ Distribuir
- ✅ Usar en privado

Solo requiere:
- ⚠️ Incluir la licencia original
- ⚠️ Indicar cambios significativos

---

## 🤝 Cómo Contribuir

¡Las contribuciones son bienvenidas! Para colaborar:

1. **Fork** el repositorio
2. **Crea rama** para tu feature:
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit** tus cambios:
   ```bash
   git commit -m 'Add: AmazingFeature'
   ```
4. **Push** a tu rama:
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Abre Pull Request** describiendo los cambios

---

## 📊 Estadísticas del Proyecto

- **Líneas de Código**: ~1600+
- **Lecciones**: 15 completas
- **Funciones**: 20+
- **Estilos CSS**: 100+ clases
- **Compatibilidad**: 5+ navegadores

---

## 🎉 Agradecimientos

Gracias por usar NEXUS Learning. ¡Esperamos que disfrutes tu experiencia de aprendizaje!

---

**Hecho con ❤️ para revolucionar el aprendizaje digital**

*Última actualización: 2 de abril de 2026*
