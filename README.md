# 🧩 Offer Experience Builder Lite
Aplicación React (client-side) optimizada para crear, editar y validar estructuras JSON complejas usadas en espacios comerciales y mensajes dinámicos.  

Permite generar tipos como:

- `CommercialBanner`
- `PromotedProduct`
- `Alert` (icon, illustration, image, conversational)
- `Interstitial` (Work in progress)
- Acciones (`featureAction`, `browserAction`, `webviewAction`)
- Previews en tiempo real  
- Variables personalizadas dinámicas (perfil y eventos)

Este proyecto está diseñado para ser **escalable y modular**, permitiendo añadir nuevos renderizados o acciones sin romper compatibilidad.

---

## 🚀 Características principales

### **🧱 Arquitectura modular**
El proyecto está dividido por dominios:
- `components/`
- `forms/`
- `schemas/`
- `previews/`
- `utils/`
- `hooks/`
- `data/initial/`

Cada tipo de renderizado tiene:
- Formulario asociado  
- Datos iniciales  
- Esquema JSON con validación AJV  
- Vista previa en tiempo real  
- Traducciones por defecto  

---

### **🔍 Validación de JSON con AJV**
El JSON generado se valida con:
- `discriminator` para seleccionar el tipo de acción/renderizado
- Validaciones estrictas
- Tipos seguros
- Mensajes de error precisos

---

### **⚡ Preview en tiempo real**
Cada vez que el usuario edita un campo:
- Se valida el JSON
- Se actualiza la vista previa (componentes comerciales visuales)

---

### **🧮 Variables personalizadas dinámicas**
Los usuarios pueden pegar dos JSON:
- **Perfil**
- **Eventos**

Y usar variables como:
{{data.profile.firstName}}
{{data.event.purchase.amount}}

Con modal para insertarlas fácilmente.

---

## 📁 Estructura del proyecto
src/
│
├── components/
├── forms/
├── previews/
├── schemas/
├── utils/
├── hooks/
├── data/
│ └── initial/
└── index.jsx

### Descripción rápida
- **components/** — Elementos UI reutilizables (inputs, buttons, modals, textarea avanzado…)
- **forms/** — Formularios dinámicos para cada renderizado o acción
- **previews/** — Renderizado visual de los componentes (CommercialBannerPreview, AlertPreview…)
- **schemas/** — Validaciones AJV con `discriminator` y estructura modular
- **data/initial/** — Estructuras por defecto para cada tipo
- **utils/** — Normalización, helpers, gestión de variables, validación…
- **hooks/** — Lógica compartida (estado, validación, almacenamiento…)

---

## 🛠️ Requisitos

- Node.js ≥ 18  
- npm ≥ 9  
- Proyecto construido con **Vite**

---

## ▶️ Instalación

```sh
npm install
```

## ▶️ Exportar a un fichero HTML
```sh
npm run build
```

### **🎯 Objetivo del proyecto**
1. Generar JSON válidos para espacios comerciales
2. Permitir a equipos de marketing crear assets visuales sin programar
3. Mantener consistencia y validación

### **🛡️ Seguridad**
Este proyecto:
* No tiene backend
* No envía datos fuera del navegador
* Usa localStorage para perfil/eventos
* Solo genera JSON escapado
* No procesa código ejecutable
