# Cómo generar el APK de Numisfera 0.4.0

Este ZIP es el código fuente, no un APK. En el entorno donde se preparó no hay Android SDK/Gradle y no se puede acceder a internet para instalar esas herramientas, por lo que no es posible compilar ni validar un APK aquí.

## Con una computadora y Android Studio
1. Instalar Android Studio y Android SDK Platform 35.
2. Descomprimir el proyecto y abrir la carpeta `NumisferaAndroid`.
3. Usar JDK 17; permitir la sincronización de Gradle.
4. Ejecutar **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Si la compilación termina sin errores, obtener `app/build/outputs/apk/debug/app-debug.apk`.
6. Transferir el archivo al teléfono Android, abrirlo y autorizar la instalación desde esa fuente si Android lo solicita. Instalar solo el APK generado desde este código fuente.

## Compilación en la nube con GitHub Actions
1. Crear un repositorio GitHub propio y subir el contenido de esta carpeta (no solo el ZIP como archivo adjunto).
2. Confirmar que `.github/workflows/android-debug-apk.yml` esté en la rama `main` o `master`.
3. En GitHub, abrir **Actions > Build Numisfera Android APK > Run workflow**.
4. Esperar a que el trabajo termine correctamente y descargar el artefacto `numisfera-debug-apk`.
5. Dentro del artefacto estará `app-debug.apk`.

El flujo no se ha ejecutado todavía. La compilación y las pruebas en un teléfono siguen pendientes; si aparecen errores de compilación, deben corregirse antes de considerar el APK listo.
