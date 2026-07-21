# Liquidaciones SPEI (Transfer In) — Prototipo UX

Prototipo de la pantalla **Liquidaciones › Por liquidar** del Backoffice de Velpay, base para el requerimiento **26028-VEL-BO — Integración de Liquidaciones SPEI (Transfer In) con STP**.

- **PRD:** 26028-VEL-BO (v1.2) — *Integración de Liquidaciones SPEI (Transfer In) con STP*
- **Product Owner:** Alma Elizabeth Aldana Alipio
- **Ruta UX:** Nueva integración (el módulo de Liquidaciones ya opera para Adquirente; SPEI se **suma** como un filtro más, sin rehacer el flujo existente)
- **Diseño de referencia:** Figma — Q3 Jul–Sept '26, frame "Por liquidar"

## Cómo verlo

Abre `index.html` en cualquier navegador. No requiere build ni dependencias.

## Qué incluye este prototipo (v0)

- Pantalla **Por liquidar** replicando el diseño de Figma: header, tabs, tarjeta de resumen, buscador, filtro de fechas, toggle **Adquirente / SPEI**, tabla y paginación.
- Interacciones básicas: búsqueda por comercio, cambio de tab, cambio de página y toggle de origen.
- El toggle **SPEI** cambia el botón principal a **Dispersar** y muestra un placeholder de la vista pendiente.

## Qué falta construir (siguiente iteración, según el PRD)

Vista **SPEI** completa:

1. Agrupamiento de operaciones por **Comercio + Sucursal** (# ops, monto conciliado, comisiones, monto neto, CLABE destino).
2. Obtención automática de **CLABE** desde Assistant (solo lectura, enmascarada `****XXXX`).
3. Botón **Dispersar** por grupo, habilitado solo con CLABE válida.
4. Manejo de **fallo + reintento** (las ops permanecen "Pendiente de Liquidar", botón "Reintentar").
5. Actualización de estatus a **Liquidada** al dispersar con éxito.
6. **Log de auditoría** de cada dispersión (usuario, timestamp, comercio, sucursal, monto, CLABE enmascarada, resultado).

> Nota: el PRD 26028-VEL-BO está **pendiente de aprobación** al momento de crear este prototipo. Los datos mostrados (Foliatti, montos) son de ejemplo.
