# 🚀 GUÍA DE DESPLIEGUE - Sistema de Informes de Mantenimiento

## 📋 PASOS RÁPIDOS (5 MINUTOS)

### PASO 1: Crear Repositorio en GitHub (2 min)

1. Ir a: **https://github.com/new**
2. Configurar:
   ```
   Repository name: informes-mantenimiento
   Description: Sistema de informes de mantenimiento
   ✅ Public
   ✅ Add a README file
   ```
3. Click **"Create repository"**

### PASO 2: Subir Archivos (2 min)

1. Descomprimir **Informes-GitHub-Package.zip**
2. En repositorio: **"Add file"** > **"Upload files"**
3. Arrastrar TODOS los archivos:
   - index.html
   - manifest.json
   - README.md
   - LICENSE
   - CHANGELOG.md
   - GUIA_DESPLIEGUE.md
4. Commit message: `Sistema de informes v1.0.0`
5. Click **"Commit changes"**

### PASO 3: Activar GitHub Pages (1 min)

1. **Settings** > **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / **(root)**
4. Click **"Save"**
5. Esperar 2 minutos
6. Refrescar (F5)

### PASO 4: Configurar Firebase (Opcional)

Si quieres usar tu propia base de datos:

1. Ir a: https://console.firebase.google.com
2. Crear nuevo proyecto: `mi-informes-mantenimiento`
3. Activar **Realtime Database**
4. Activar **Authentication** > **Email/Password**
5. Copiar credenciales
6. Editar `index.html` líneas 1922-1930
7. Commit cambios

### PASO 5: ✅ Acceder

URL generada:
```
https://TU-USUARIO.github.io/informes-mantenimiento/
```

---

## 🔐 CONFIGURACIÓN DE FIREBASE

### Reglas de Realtime Database

**Para desarrollo (permisivo):**
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

**Para producción (seguro):**
```json
{
  "rules": {
    "users": {
      ".read": "auth != null",
      "$uid": {
        ".write": "auth.uid === $uid || root.child('users').child(auth.uid).child('role').val() === 'admin'"
      }
    },
    "reports": {
      ".read": "auth != null",
      ".write": "auth != null",
      "$reportId": {
        ".validate": "newData.hasChildren(['equipmentId', 'maintenanceType', 'date'])"
      }
    },
    "equipment": {
      ".read": "auth != null",
      ".write": "auth != null"
    },
    "partsRequests": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

### Autenticación

1. Firebase Console > **Authentication**
2. **Sign-in method** > **Email/Password**
3. **Enable** > Save
4. Crear primer usuario admin manualmente si es necesario

---

## 👥 CREAR USUARIOS

### Método 1: Desde la aplicación

1. Login con credenciales admin
2. Ir a **Gestión de Usuarios**
3. **Agregar Usuario**
4. Completar datos
5. Asignar rol

### Método 2: Firebase Console

1. Authentication > Users
2. **Add user**
3. Email y password
4. Luego agregar role en Realtime Database:
   ```
   users/{uid}/role = "admin" | "tecnico" | "usuario"
   ```

---

## 🔄 ACTUALIZAR SISTEMA

### Opción A: Editar en GitHub

1. Repositorio > `index.html`
2. Click ícono lápiz
3. Hacer cambios
4. Commit changes
5. Esperar 2 min

### Opción B: Subir Nuevo Archivo

1. Eliminar `index.html` actual
2. Upload nuevo `index.html`
3. Commit

---

## 📱 COMPARTIR CON EQUIPO

```
URL: https://TU-USUARIO.github.io/informes-mantenimiento/

Credenciales iniciales:
Email: admin@mantenimiento.com
Password: admin123

⚠️ Cambiar después del primer login
```

---

## 🐛 TROUBLESHOOTING

### Error: No puedo hacer login

**Verificar:**
- Firebase Authentication activado
- Email/Password habilitado
- Usuario existe en Firebase

**Solución:**
```javascript
// Console (F12)
firebase.auth().currentUser
// Si es null, no hay sesión activa
```

### Error: No guarda datos

**Verificar:**
- Reglas de Firebase permiten escritura
- Usuario autenticado
- Internet activo

### Error 404

**Verificar:**
- Archivo se llama `index.html`
- GitHub Pages activado
- Esperar 2-3 minutos

---

## ✅ CHECKLIST

- [ ] Repositorio creado
- [ ] Archivos subidos (7 archivos)
- [ ] GitHub Pages activado
- [ ] Firebase configurado (opcional)
- [ ] URL funciona
- [ ] Login funciona
- [ ] Puede crear informes
- [ ] Sincronización funciona
- [ ] Credenciales cambiadas

---

**Sistema listo para producción** ✅
