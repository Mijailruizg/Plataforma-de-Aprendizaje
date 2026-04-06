# 🔧 Configuración de Firebase para Nexus Learning

## 📋 Instrucciones de Setup

### 1. Crear Proyecto en Firebase

1. Ve a [Firebase Console](https://console.firebase.google.com/)
2. Click en "Crear Proyecto"
3. Nombre del proyecto: `nexus-learning-app`
4. Desactiva Google Analytics (opcional)
5. Haz clic en "Crear Proyecto"

### 2. Obtener Credenciales de Firebase

1. En el dashboard del proyecto, haz clic en "Agregar app"
2. Selecciona "Web" (icono `</>`)
3. Nombre de la app: `Nexus Learning`
4. Copia la configuración Firebase

### 3. Actualizar Credenciales en index.html

Reemplaza la `firebaseConfig` en `index.html` (línea ~1500) con tus credenciales:

```javascript
const firebaseConfig = {
    apiKey: "TU_API_KEY",
    authDomain: "tu-proyecto.firebaseapp.com",
    projectId: "tu-proyecto-id",
    storageBucket: "tu-proyecto.appspot.com",
    messagingSenderId: "tu-messaging-sender-id",
    appId: "tu-app-id"
};
```

### 4. Habilitar Firestore Database

1. En Firebase Console, ve a "Firestore Database"
2. Click en "Crear base de datos"
3. Ubicación: selecciona la más cercana a tu región
4. Modo: "Comenzar en modo prueba"
5. Click en "Crear"

### 5. Configurar Reglas de Seguridad (Opcional)

En la pestaña "Reglas" de Firestore:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{document=**} {
      allow read, write: if true; // Solo para desarrollo
    }
  }
}
```

⚠️ **Para producción**: Implementa autenticación y reglas de seguridad adecuadas.

---

## 📊 Estructura de Datos en Firestore

Los usuarios se guardan en la colección `users`:

```
users/
├── {documentId}
│   ├── name: "Juan Pérez"
│   ├── email: "juan@example.com"
│   ├── loginMethod: "google" | "manual"
│   ├── timestamp: 2026-04-06T10:30:00Z (fecha de registro)
│   ├── lastLogin: 2026-04-06T10:30:00Z (último acceso)
│   └── status: "active"
```

---

## 🖥️ Ver Registros de Usuarios

### Opción 1: Firebase Console
1. Ve a tu proyecto en Firebase Console
2. Abre "Firestore Database"
3. Verás la colección `users` con todos los registros

### Opción 2: Crear Dashboard Admin (Próximamente)
Podemos crear una página `/admin.html` con:
- ✅ Tabla de todos los usuarios
- ✅ Filtrar por método de login (Google/Manual)
- ✅ Ver fecha de registro y último acceso
- ✅ Estadísticas de uso

---

## 🚀 Verificar que Funciona

1. Abre la plataforma
2. Regístrate o inicia sesión
3. Abre Firebase Console → Firestore Database
4. Deberías ver un nuevo documento en la colección `users`

---

## 💡 Próximas Mejoras

- [ ] Dashboard admin con tablas y gráficos
- [ ] Exportar datos a CSV/Excel
- [ ] Autenticación de admin para ver reportes
- [ ] Analytics de engagement por lección
- [ ] SMS/Email de bienvenida automático

---

## 📞 Soporte

Si tienes problemas con Firebase:
- Revisa la consola del navegador (F12)
- Verifica que Firebase esté inicializado correctamente
- Asegúrate de que Firestore Database esté habilitada

