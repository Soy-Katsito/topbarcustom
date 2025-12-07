# TopbarAssets – Tutorial de Configuración
Guía oficial para estructurar correctamente los assets utilizados por el sistema del Topbar.

El sistema lee automáticamente cada carpeta y genera:
- Menú de Accesorios  
- Menú de Emotes  
- Menú de Objetos  
- Menú de Vehículos  

Si algún elemento no cumple los requisitos indicados, el sistema puede generar errores, ignorar assets o no mostrarlos.

---

## Estructura General Requerida
```
ReplicatedStorage
└─ TopbarAssets
├─ Accessories
├─ Emotes
├─ Items
└─ Vehicles
```
---

# 1. Accessories
Carpeta donde se almacenan los accesorios que los jugadores pueden equipar.

### Tipos aceptados
- `Accessory`
- `Model`

### Requisitos
- Deben tener **nombres únicos y descriptivos** (ej: `Sombrero1`, `GafasAzules`).
- Si es un **Accessory**, debe incluir:
  - Un `Handle`
  - Meshes o partes necesarias
- Si es un **Model**:
  - Debe estar correctamente orientado.
  - Sus partes deben ser compatibles para soldarse al personaje.

---

# 2. Emotes
Carpeta donde se almacenan animaciones que el jugador podrá reproducir desde el menú.

### Tipo aceptado
- `Animation`

### Requisitos
- Cada animación debe tener:
  - Un **nombre claro** (ej: `Wave`, `Dance1`, `Saludo`).
  - Un **AnimationId válido**, con el formato:
    ```
    rbxassetid://NUMERO
    ```
- El ID debe pertenecer a una animación existente en Roblox.

---

# 3. Items
Carpeta destinada a herramientas u objetos seleccionables por el jugador.

### Tipos aceptados
- `Tool`
- `Model`

### Requisitos
- Si es un **Tool**:
  - Debe tener un `Handle`.
  - Puede incluir scripts de funcionalidad.
- Si es un **Model**:
  - Debe estar correctamente orientado.
  - Debe ser compatible con clonación y equipamiento.

---

# 4. Vehicles
Carpeta donde se guardan los vehículos que el jugador podrá generar mediante el menú.

### Tipo aceptado
- `Model`

### Requisitos
- Cada modelo debe tener:
  - **PrimaryPart configurado** (OBLIGATORIO).
  - Todas las partes correctamente unidas.
  - Scripts internos si el vehículo es funcional.
- Nombres recomendados:
  - `Sedan`
  - `Moto`
  - `Camioneta`
  - `Deportivo`

---

# ✔ Resumen Final
| Carpeta       | Tipo de objetos | Requisitos principales |
|---------------|-----------------|-------------------------|
| Accessories   | Accessory, Model | Handle (si es Accessory), orientación correcta |
| Emotes        | Animation        | AnimationId válido y nombre claro |
| Items         | Tool, Model      | Handle (si es Tool), clonable y funcional |
| Vehicles      | Model            | PrimaryPart definido, listo para spawn |

---

# ✔ Notas importantes
- No agregues objetos de otros tipos, el sistema los ignorará.  
- Si algo no aparece en el menú, revisa:
  - PrimaryPart faltante  
  - AnimationId incorrecto  
  - Nombre duplicado  
  - Objetos sin Handle  
- Mantén los nombres limpios y sin caracteres extraños.