# 🛒 Práctica Supabase - Reparadora de Calzados

## Propósito
Esta práctica demuestra cómo conectar un frontend HTML/JavaScript con una base de datos **Supabase (PostgreSQL)** para cargar productos dinámicamente, reemplazando el array fijo de productos.

---

## 📁 Archivos Incluidos

| Archivo | Descripción |
|---------|-------------|
| `Tienda-Profesional-Supabase.html` | Archivo principal - Tienda con conexión a Supabase |
| `stylesTPWP.css` | Hoja de estilos para la tienda |
| `README-CAMBIOS.md` | Documentación detallada de los cambios realizados |
| `README.md` | Este archivo (instrucciones de uso) |

---

## 🚀 Cómo Probar

### Opción 1: Abrir localmente (Recomendado)
1. Abre el archivo `Tienda-Profesional-Supabase.html` en tu navegador
2. Debería cargar automáticamente los 5 productos desde Supabase

### Opción 2: GitHub Pages
Si configuras GitHub Pages en este repositorio:
1. Ve a Settings → Pages
2. Activa GitHub Pages (rama: main, carpeta: /root)
3. Accede a `https://tu-usuario.github.io/practica-supabase/`

---

## 📊 ¿Qué hace este código?

### Flujo de la aplicación:
1. **Carga inicial:** Al abrir la página, se ejecuta `cargarProductos()`
2. **Conexión a Supabase:** El cliente de Supabase se conecta a tu proyecto
3. **Consulta SQL:** Ejecuta `SELECT * FROM productos ORDER BY nombre`
4. **Renderizado:** Muestra los productos en el grid
5. **Interacción:** Usuario agrega productos al carrito
6. **Persistencia:** Carrito se guarda en localStorage
7. **Pedido:** Envío del pedido por WhatsApp

### Estructura de la tabla `productos` en Supabase:
```sql
CREATE TABLE productos (
  id SERIAL PRIMARY KEY,
  nombre VARCHAR(255) NOT NULL,
  descripcion TEXT,
  precio DECIMAL(10,2) NOT NULL,
  stock INTEGER DEFAULT 0,
  imagen_url TEXT,
  categoria VARCHAR(100),
  created_at TIMESTAMP DEFAULT NOW()
);
```

---

## 🔧 Configuración

El archivo ya incluye las credenciales de tu proyecto:
- **URL:** `https://vwhuksxaczasugmyswdj.supabase.co`
- **API Key:** La clave pública (anon) configurada

Si necesitas cambiar la configuración, busca en `Tienda-Profesional-Supabase.html`:
```javascript
const SUPABASE_URL = 'https://vwhuksxaczasugmyswdj.supabase.co';
const SUPABASE_ANON_KEY = 'tu-api-key';
```

---

## 📝 Productos Actuales en la BD

Según lo cargado en tu sesión:
1. **Reparación de Zapatos** - $15.000
2. **Limpieza Profunda** - $8.000
3. **Cambio de Suela** - $25.000
4. **Ortopedia Personalizada** - $45.000
5. **Impermeabilización** - $12.000

---

## 🎯 Aprendizaje Clave

### Conceptos aplicados:
- ✅ Importar librerías externas desde CDN
- ✅ Configurar cliente de Supabase
- ✅ Consultas asíncronas con `async/await`
- ✅ Manejo de promesas y errores
- ✅ Renderizado dinámico con JavaScript
- ✅ Manipulación del DOM
- ✅ LocalStorage para persistencia

### Diferencia con la versión anterior:
| Versión Antigua | Versión Nueva |
|-----------------|---------------|
| Array fijo en código | Datos desde BD real |
| 5 productos hardcoded | Productos ilimitados |
| Actualización manual | Actualización automática |
| Sin descripción ni stock | Información completa |

---

## 🔗 Próximos Pasos Sugeridos

1. **Validar funcionamiento:**
   - Abrir la página y verificar carga de productos
   - Probar agregar al carrito
   - Probar envío por WhatsApp

2. **Mejoras posibles:**
   - Agregar filtro por categoría
   - Implementar buscador
   - Agregar imágenes reales
   - Crear panel de administración

3. **Aprender más:**
   - Documentación de Supabase: https://supabase.com/docs
   - MDN Web Docs: https://developer.mozilla.org

---

## 📞 Soporte

Si algo no funciona:
1. Revisa la consola del navegador (F12) para ver errores
2. Verifica que la tabla `productos` exista en Supabase
3. Confirma que haya datos en la tabla
4. Revisa que la API key sea correcta

---

**Creado:** 2026-05-23  
**Propósito:** Práctica de conexión frontend-backend con Supabase  
**Nivel:** Intermedio (Día 5 - Transición a base de datos real)
