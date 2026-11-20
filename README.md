# OpenKeyTest

**OpenKeyTest** (`v1.0.0`) es una herramienta web gratuita y de código abierto diseñada para realizar diagnósticos interactivos en tiempo real de teclados, *switches* mecánicos, teclas de función y controles multimedia directamente desde el navegador, sin necesidad de instalar software adicional.

---

## Características Principales

- **Detección visual de 4 estados:**
  - **Gris (Sin probar):** Tecla aún no pulsada.
  - **Verde (Detectada OK):** Tecla detectada correctamente (verde brillante mientras se mantiene pulsada, verde suave al soltarla).
  - **Azul (Función de Sistema / Multimedia):** Identifica teclas especiales de brillo, volumen, reproducción multimedia, bloqueo, captura de pantalla y tecla `Fn`.
  - **Rojo (Averiada):** Permite marcar manualmente teclas defectuosas o que no responden haciendo **clic derecho** sobre ellas o activando el **Modo Marcar Avería**.
- **Soporte Multi-Distribución e Idioma:**
  - `QWERTY` — English (USA)
  - `QWERTY` — Español (LATAM)
  - `AZERTY` — Français (France)
  - `QWERTZ` — Deutsch (Deutschland)
  - `Dvorak` — Simplified
- **Compatibilidad de Sistema Operativo:** Alterna dinámicamente las etiquetas y asignaciones de teclas modificadoras entre **Windows** (`Win`, `Ctrl`, `Alt`) y **macOS** (`Command ⌘`, `Control ⌃`, `Option ⌥`).
- **Formatos de Teclado:**
  - **Laptop (75%):** Compacto con fila de funciones integradas y flechas.
  - **Con Numérico (100%):** Teclado estándar completo con bloque de navegación y *NumPad*.
  - **Completo Extendido:** Añade controles dedicados de brillo y volumen sobre el teclado numérico.
- **Probador de Funciones de Sistema / Multimedia:** Barra dedicada para validar teclas físicas o virtuales de brillo (`Br-`/`Br+`), volumen, multimedia (`Anterior`, `Play/Pause`, `Siguiente`), bloqueo, hibernación, proyección, silencio de micrófono, modo avión, lupa y nueva pestaña.
- **Feedback Sonoro Sintetizado (Web Audio API):** Genera efectos de sonido en tiempo real sin archivos de audio externos, con control de volumen y perfiles seleccionables:
  - *Mecánico Clicky (Azul)*
  - *Mecánico Táctil (Marrón)*
  - *Membrana Suave*
  - *Silencio*
- **Inspector de Eventos y Telemetría:** Muestra en tiempo real los valores de `event.key`, `event.code`, `keyCode`, barra de porcentaje de progreso, contadores de teclas (probadas, funciones, averiadas y total) e historial de las últimas 24 pulsaciones.
- **Exportación a PNG:** Genera y descarga una captura limpia en alta resolución (`OpenKeyTest_Teclado_YYYY-MM-DD.png`) mostrando únicamente la leyenda de estados y el mapa del teclado mediante `html2canvas`.

---

## Tecnologías Utilizadas

- **HTML5 & JavaScript (Vanilla ES6+):** Arquitectura autocontenida en un único archivo sin dependencias de compilación (*zero-build*).
- **Tailwind CSS (CDN):** Interfaz moderna con diseño *glassmorphism* en modo oscuro.
- **Web Audio API:** Síntesis procedural de sonido de pulsación (*noise bursts* y osciladores) en el navegador.
- **html2canvas:** Exportación directa del diagnóstico visual a imagen PNG.
- **Google Fonts:** Tipografías *Inter* y *JetBrains Mono*.

---

## Instalación y Uso

Al tratarse de una aplicación web estática autocontenida en un solo archivo (`OpenKeyTest.html`), no requiere servidores complejos ni gestores de paquetes:

### 1. Clonar el repositorio

```bash
git clone [https://github.com/edwarly999plus/Open-Key-Test.git](https://github.com/edwarly999plus/Open-Key-Test.git)
cd Open-Key-Test

```

### 2. Ejecutar la aplicación

* **Opción A (Directa):** Haz doble clic sobre `OpenKeyTest.html` para abrirlo directamente en cualquier navegador moderno (Chrome, Firefox, Edge, Safari, Brave).
* **Opción B (Servidor local):** Si prefieres servirlo mediante HTTP local:

```bash
# Usando Python 3
python -m http.server 8080

```

Luego accede a `http://localhost:8080/OpenKeyTest.html` en tu navegador.

---

## Guía Rápida de Diagnóstico

| Acción | Resultado |
| --- | --- |
| **Pulsar cualquier tecla física** | La tecla se ilumina en **verde** (o **azul** si es multimedia/sistema) y registra su telemetría. |
| **Clic derecho sobre una tecla** | Marca o desmarca la tecla en **rojo** como averiada. |
| **Botón `Modo Marcar Avería**` | Permite marcar teclas averiadas usando **clic izquierdo** (ideal para pantallas táctiles o *trackpads*). |
| **Botón `Teclas de Función**` | Muestra u oculta la fila superior `F1–F12` y la barra multimedia. |
| **Botón `Reiniciar Prueba**` | Restablece a gris todas las teclas probadas manteniendo las marcas de teclas averiadas. |
| **Botón `Guardar PNG**` | Descarga una imagen del estado actual del teclado para reportes técnicos o garantías. |

---

## Contribuir

Las contribuciones son bienvenidas. Si deseas agregar nuevas distribuciones de teclado (como ISO Español, ABNT2 Portugués o JIS Japonés), mejorar la detección de eventos o reportar un error:

1. Haz un **Fork** del proyecto.
2. Crea una rama para tu mejora (`git checkout -b feature/nueva-distribucion`).
3. Realiza tus cambios y haz *commit* (`git commit -m "Agrega distribución ISO-ES"`).
4. Sube los cambios a tu rama (`git push origin feature/nueva-distribucion`).
5. Abre un **Pull Request**.

---

## Licencia

Este proyecto se distribuye bajo la licencia `[especificar licencia, ej. MIT]` — consulta el archivo `LICENSE` en el repositorio para más detalles.
