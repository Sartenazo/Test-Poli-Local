# Test Policía Local – App Android

Proyecto Capacitor 7 que empaqueta la app web (`www/index.html`) como APK.

## Opción A: que GitHub compile el APK (sin instalar nada)
1. Crea un repositorio en GitHub y sube el contenido de esta carpeta (rama `main`).
2. Ve a la pestaña **Actions**: el flujo "Compilar APK" arranca solo (o pulsa *Run workflow*).
3. Cuando termine (unos 5 min), entra en la ejecución y descarga el artefacto
   **test-policia-local-apk** (un .zip con `app-debug.apk`).
4. Pásalo al móvil, ábrelo y permite "instalar apps de origen desconocido".

## Opción B: Android Studio
1. `npm install`
2. `npx cap sync android`
3. `npx cap open android` (o abre la carpeta `android` en Android Studio)
4. Build > Build Bundle(s) / APK(s) > Build APK(s).

## Actualizar las preguntas
Sustituye `www/index.html` por la nueva versión y vuelve a ejecutar
`npx cap sync android` (o simplemente haz push: GitHub recompila).

## Notas
- Funciona sin conexión: todas las preguntas van dentro del APK.
- El progreso se guarda en el propio móvil.
- El APK de depuración vale para uso personal. Para Google Play hay que
  generar un APK/AAB firmado (Build > Generate Signed Bundle).
- Requisitos locales: Node 20+, JDK 21 y Android SDK.

## Versión web (iPhone, ordenador y Android)
Cada push a `main` publica la carpeta `www` en GitHub Pages:
https://sartenazo.github.io/test-poli-local/
- iPhone: abrir en Safari → Compartir → "Añadir a pantalla de inicio".
- Ordenador: abrir en Chrome o Edge → icono "Instalar" de la barra de direcciones.
- Funciona sin conexión una vez abierta. El progreso se guarda en cada dispositivo.
