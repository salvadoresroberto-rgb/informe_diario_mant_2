# 📊 Sistema de Informes de Mantenimiento

Sistema completo de gestión de informes y reportes de mantenimiento con **sincronización en tiempo real** entre múltiples dispositivos y usuarios.

[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue)](https://pages.github.com/)
[![Firebase](https://img.shields.io/badge/Firebase-Realtime-orange)](https://firebase.google.com/)
[![PWA](https://img.shields.io/badge/PWA-Ready-green)](https://web.dev/progressive-web-apps/)

---

## 🚀 DEMO EN VIVO

**URL:** https://TU-USUARIO.github.io/informes-mantenimiento/

*(Reemplazar con tu URL después del despliegue)*

---

## ✨ CARACTERÍSTICAS

### 🌐 Sincronización Multidispositivo en Tiempo Real
- ✅ **Sincronización instantánea** - Cambios visibles en < 2 segundos
- ✅ **Multi-usuario** - Múltiples usuarios trabajando simultáneamente
- ✅ **Multi-dispositivo** - PC, móvil, tablet con datos sincronizados
- ✅ **Persistencia offline** - Funciona sin conexión

### 📊 Gestión de Informes
- ✅ **Crear informes** de mantenimiento detallados
- ✅ **Gestión de equipos** - Registro completo de maquinaria
- ✅ **Solicitudes de piezas** - Control de repuestos y materiales
- ✅ **Tipos de mantenimiento** - Correctivo, preventivo, predictivo
- ✅ **Historial completo** - Todos los informes por equipo
- ✅ **Búsqueda y filtros** - Encuentra información rápidamente

### 📈 Estadísticas y Reportes
- ✅ **Dashboard con gráficas** - Chart.js para visualización
- ✅ **Exportación a Excel** - Todos los datos exportables
- ✅ **Informes por período** - Diario, semanal, mensual, anual
- ✅ **Análisis por equipo** - Estadísticas individuales
- ✅ **KPIs de mantenimiento** - Métricas clave

### 👥 Sistema de Usuarios
- ✅ **Login seguro** - Autenticación Firebase
- ✅ **Roles diferenciados** - Admin, Técnico, Usuario
- ✅ **Permisos configurables** - Control de acceso
- ✅ **Gestión de usuarios** - Alta, baja, modificación

### 📱 PWA (Progressive Web App)
- ✅ **Instalable** como app nativa
- ✅ **Funciona offline** - Caché local
- ✅ **Notificaciones** (opcional)
- ✅ **Experiencia nativa** - Sin barra del navegador

---

## 🎯 INICIO RÁPIDO

### Opción 1: Usar en Línea (Inmediato)

1. Abrir: **https://TU-USUARIO.github.io/informes-mantenimiento/**
2. Crear cuenta o iniciar sesión
3. ¡Empezar a crear informes!

### Opción 2: Desplegar Tu Propia Versión

#### Paso 1: Fork o Descarga
```bash
# Descargar Informes-GitHub-Package.zip
# O hacer fork del repositorio
```

#### Paso 2: Subir a GitHub
1. Crear repositorio: `informes-mantenimiento`
2. Subir todos los archivos
3. Configuración: Público

#### Paso 3: Activar GitHub Pages
1. Settings > Pages
2. Source: main / (root)
3. Save
4. Esperar 2 minutos

#### Paso 4: Acceder
```
https://TU-USUARIO.github.io/informes-mantenimiento/
```

---

## 🔧 CONFIGURACIÓN

### Firebase (Ya Configurado)

El sistema viene con Firebase pre-configurado. Si quieres usar tu propia base de datos:

1. Crear proyecto en [Firebase Console](https://console.firebase.google.com)
2. Activar:
   - **Realtime Database**
   - **Authentication** (Email/Password)
3. Copiar credenciales
4. Editar `index.html` líneas 1922-1930:

```javascript
const firebaseConfig = {
    apiKey: "TU_API_KEY",
    authDomain: "tu-proyecto.firebaseapp.com",
    databaseURL: "https://tu-proyecto.firebaseio.com",
    projectId: "tu-proyecto",
    storageBucket: "tu-proyecto.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:abcdef"
};
```

5. Configurar reglas de seguridad en Firebase

---

## 📱 INSTALAR COMO APP

### Android / Chrome
1. Abrir URL en Chrome
2. Menú (⋮) > **"Instalar app"**
3. Confirmar

### iOS / Safari
1. Abrir URL en Safari
2. Compartir > **"Añadir a inicio"**
3. Confirmar

### Desktop
1. Ícono de instalación en barra de direcciones
2. Click > **"Instalar"**

---

## 👥 USUARIOS Y ROLES

### Tipos de Usuario

| Rol | Permisos |
|-----|----------|
| **Admin** | Acceso total, gestión de usuarios, configuración |
| **Técnico** | Crear/editar informes, solicitar piezas, ver historial |
| **Usuario** | Solo visualización de informes |

### Primer Acceso

**Usuario por defecto:**
- **Email:** admin@mantenimiento.com
- **Password:** admin123

⚠️ **Cambiar credenciales después del primer login**

---

## 🏗️ ARQUITECTURA

```
┌─────────────────┐
│  Usuario Admin  │──────┐
└─────────────────┘      │
                         │
┌─────────────────┐      │     ┌──────────────────┐
│ Técnico 1 (PC)  │──────┼────►│    Firebase      │
└─────────────────┘      │     │  Realtime DB +   │
                         │     │  Authentication  │
┌─────────────────┐      │     └──────────────────┘
│Técnico 2 (Móvil)│──────┘              │
└─────────────────┘                     │
                                        ▼
                              ┌──────────────────┐
                              │ Sincronización   │
                              │   Automática     │
                              └──────────────────┘
```

**Stack Técnico:**
- Frontend: JavaScript Vanilla + HTML5 + CSS3
- Base de datos: Firebase Realtime Database
- Autenticación: Firebase Authentication
- Gráficas: Chart.js
- Exportación: SheetJS (xlsx)
- Hosting: GitHub Pages

---

## 📂 ESTRUCTURA DEL PROYECTO

```
informes-mantenimiento/
├── index.html              # Aplicación principal
├── manifest.json           # Configuración PWA
├── README.md              # Esta documentación
├── LICENSE                # Licencia MIT
├── CHANGELOG.md           # Historial de versiones
├── CONTRIBUTING.md        # Guía para contribuir
└── GUIA_DESPLIEGUE.md    # Instrucciones detalladas
```

---

## 📊 FUNCIONALIDADES PRINCIPALES

### 1. Gestión de Equipos
```javascript
- Registrar nuevos equipos
- Editar información técnica
- Asignar ubicación y responsable
- Ver historial de mantenimiento
- Estadísticas por equipo
```

### 2. Informes de Mantenimiento
```javascript
- Crear informes detallados
- Adjuntar observaciones
- Registrar tiempo de intervención
- Clasificar tipo de mantenimiento
- Marcar prioridad
- Estado de cierre
```

### 3. Solicitudes de Piezas
```javascript
- Solicitar repuestos
- Aprobar/rechazar solicitudes
- Historial de solicitudes
- Control de stock (próximamente)
```

### 4. Estadísticas y Reportes
```javascript
- Dashboard con KPIs
- Gráficas por tipo de mantenimiento
- Gráficas por equipo
- Tendencias temporales
- Exportación a Excel
```

---

## 🔒 SEGURIDAD

### Autenticación
- Sistema de login con Firebase Auth
- Contraseñas encriptadas
- Sesiones seguras
- Tokens JWT

### Reglas de Firebase

**Producción (Recomendado):**
```json
{
  "rules": {
    "users": {
      ".read": "auth != null",
      ".write": "auth != null && root.child('users').child(auth.uid).child('role').val() === 'admin'"
    },
    "reports": {
      ".read": "auth != null",
      ".write": "auth != null"
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

### Mejores Prácticas
1. Cambiar password de admin por defecto
2. Activar autenticación de dos factores
3. Revisar logs de acceso regularmente
4. Mantener Firebase actualizado
5. Hacer backups periódicos

---

## 📈 MONITOREO

### Firebase Console
Ver datos en tiempo real:
1. [Firebase Console](https://console.firebase.google.com)
2. Proyecto: `mantenimiento-ccc15`
3. Realtime Database - Ver estructura
4. Authentication - Usuarios activos

### Estadísticas GitHub
1. Repositorio > Insights
2. Traffic - Visitas
3. Visitors - Usuarios únicos

---

## 🐛 SOLUCIÓN DE PROBLEMAS

### No puedo hacer login

**Verificar:**
1. Credenciales correctas
2. Firebase Auth activado
3. Usuario existe en la base de datos

**Solución:**
```javascript
// En Console (F12)
firebase.auth().signInWithEmailAndPassword(email, password)
  .then(user => console.log('Login OK:', user))
  .catch(error => console.log('Error:', error));
```

### No sincroniza datos

**Verificar:**
1. F12 > Console - Buscar errores
2. Conexión a internet activa
3. Firebase configurado correctamente

**Solución:**
```javascript
// Verificar conexión Firebase
firebase.database().ref('.info/connected').on('value', (snap) => {
  console.log('Conectado a Firebase:', snap.val());
});
```

### Error al exportar Excel

**Causa:** Librería xlsx no cargada

**Solución:**
- Verificar que CDN de xlsx esté cargando
- Revisar conexión a internet
- Probar en navegador diferente

---

## 📱 COMPATIBILIDAD

| Navegador | PC | Móvil | PWA | Login |
|-----------|-------|--------|-----|-------|
| Chrome | ✅ | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ⚠️ | ✅ |
| Safari | ✅ | ✅ | ✅ | ✅ |
| Edge | ✅ | ✅ | ✅ | ✅ |

**Recomendado:** Chrome o Edge para mejor experiencia

---

## 🤝 CONTRIBUIR

¿Quieres mejorar el sistema?

1. Fork el proyecto
2. Crear rama: `git checkout -b feature/nueva-funcionalidad`
3. Commit: `git commit -m 'Agregar nueva funcionalidad'`
4. Push: `git push origin feature/nueva-funcionalidad`
5. Pull Request

Ver [CONTRIBUTING.md](CONTRIBUTING.md) para más detalles.

---

## 📄 LICENCIA

Este proyecto está bajo la Licencia MIT - ver [LICENSE](LICENSE) para detalles.

---

## 🎯 ROADMAP

### v1.1 (Próximo)
- [ ] Control de stock de piezas
- [ ] Notificaciones push
- [ ] Adjuntar fotos a informes
- [ ] Firma digital

### v1.2
- [ ] Escaneo QR para equipos
- [ ] Modo oscuro
- [ ] App móvil nativa
- [ ] Integración con email

### v2.0
- [ ] IA para mantenimiento predictivo
- [ ] Integración IoT
- [ ] API REST
- [ ] Multi-idioma

---

## 📞 SOPORTE

### Documentación
- [Firebase Docs](https://firebase.google.com/docs)
- [Chart.js Docs](https://www.chartjs.org/docs)
- [GitHub Pages](https://docs.github.com/pages)

### Issues
¿Encontraste un bug? [Reportar Issue](../../issues)

### Comunidad
- Discusiones en GitHub
- Stack Overflow: `firebase` + `maintenance-management`

---

## 📊 ESTADÍSTICAS

![GitHub stars](https://img.shields.io/github/stars/TU-USUARIO/informes-mantenimiento?style=social)
![GitHub forks](https://img.shields.io/github/forks/TU-USUARIO/informes-mantenimiento?style=social)

---

**Desarrollado para equipos de mantenimiento profesionales** 🔧

**Versión:** 1.0.0  
**Última actualización:** Diciembre 2024  
**Estado:** ✅ Producción
