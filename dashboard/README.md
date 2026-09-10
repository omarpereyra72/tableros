# Alldashboards

Portal de gestión de dashboards para COFARSUR S.A.

## Estructura del proyecto

```
alldashboard/
├── index.html          ← Página principal con login y directorio
└── dashboard/
    ├── calidad.html    ← Dashboard de Calidad (Omar Pereyra)
    ├── stock.html      ← Dashboard de Stock (Germán García)
    └── [nuevos].html   ← Agregar aquí nuevos dashboards
```

## Acceso por defecto

- **Usuario:** `admin`
- **Contraseña:** `123456`

Las credenciales pueden cambiarse desde la misma página principal una vez iniciada la sesión. Se guardan en el `localStorage` del navegador.

## Cómo agregar un nuevo dashboard

1. Copiar un dashboard existente (ej: `calidad.html`) y personalizarlo.
2. Guardarlo en la carpeta `dashboard/`.
3. Abrir `index.html` y editar el array `DASHBOARDS` en el bloque `<script>`:

```javascript
const DASHBOARDS = [
  // ...dashboards existentes...
  {
    id: "ventas",
    title: "Dashboard de Ventas",
    dept: "Comercial",
    icon: "📈",
    iconBg: "#FEF9C3",
    owner: "Nombre Apellido",
    initials: "NA",
    avatarColor: "#A16207",
    badge: "Ventas",
    badgeClass: "badge-amber",
    file: "dashboard/ventas.html",
  },
];
```

### Clases de badge disponibles
- `badge-blue` → Azul
- `badge-green` → Verde
- `badge-amber` → Ámbar/Naranja
- `badge-purple` → Violeta

## Cómo linkear un archivo Excel

En el array `DASHBOARDS`, usar la URL de OneDrive/Google Sheets como `file`:

```javascript
{
  id: "presupuesto",
  title: "Presupuesto Anual",
  dept: "Administración",
  file: "https://onedrive.live.com/view/...",
  // ...resto de propiedades
}
```

## Deploy en Vercel

1. Subir este repositorio a GitHub.
2. En [vercel.com](https://vercel.com), importar el repositorio.
3. Framework preset: **Other** (sitio estático).
4. No se necesita ninguna configuración adicional.

## Notas

- El proyecto es completamente estático (HTML/CSS/JS puro), sin dependencias externas de backend.
- Los meses y años en las tarjetas se actualizan automáticamente con la fecha del sistema.
- El tema claro/oscuro se guarda por usuario en `localStorage`.
