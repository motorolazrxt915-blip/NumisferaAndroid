# Numisfera Android — versión 0.4.0

Proyecto fuente Android Studio en Kotlin, Jetpack Compose y Room, con enfoque offline-first.

## Qué contiene
- Colección local persistente con Room.
- Catálogo offline ampliado a más de 70 tipos y series, con mayor cobertura de emisiones argentinas de circulación y conmemorativas y ejemplos internacionales.
- Fichas técnicas exactas cuando se dispone de fuente oficial; las entradas históricas sin ficha verificada se marcan como referencias generales para no inventar medidas o composiciones.
- Fichas técnicas profesionales: sistema monetario, fecha de emisión, diámetro, peso, grosor, canto, forma, ceca, tirada, diseñador/grabador, técnica, orientación, variante, rareza, conservación, autenticidad, adquisición, procedencia, valoración y fuente.
- Fotografías de anverso y reverso en almacenamiento privado.
- Ficha A4 imprimible con fotografías y datos técnicos.
- Copias JSON con registros y fotografías en Base64.
- Estado de emisiones conmemorativas del BCRA consultado el 27/10/2026, con fichas ampliadas para las emisiones de Belgrano 2020, Mundiales Brasil 2014, Rusia 2018, Catar 2022 y FIFA 2026, Independencia 2016, Series Iberoamericanas y otras emisiones conmemorativas históricas listadas por el BCRA.
- Enlaces desde el catálogo hacia las páginas oficiales del BCRA.
- Flujo de GitHub Actions para compilar y descargar el APK de depuración como artefacto.

## Actualización del BCRA
El estado integrado es una **fotografía estática** de las páginas oficiales consultadas el 27/10/2026. La app no consulta el servidor en segundo plano ni actualiza su base de datos automáticamente. Revisá `docs/ESTADO_BCRA_2026-10-27.md`; el stock puede cambiar y debe verificarse en el BCRA antes de comprar.

Fuentes principales:
- https://www.bcra.gob.ar/emisiones-conmemorativas/
- https://www.bcra.gob.ar/stand-de-emisiones-numismaticas/
- https://www.bcra.gob.ar/copa-mundial-de-la-fifa-2026/
- https://www.bcra.gob.ar/40-aniversario-de-la-restauracion-de-la-democracia/
- https://www.bcra.gob.ar/series-iberoamericanas/

## Cómo compilar el APK
### En Android Studio
1. Descomprimí el ZIP.
2. Abrí la carpeta `NumisferaAndroid` en Android Studio.
3. Usá JDK 17 e instalá Android SDK Platform 35 y Build Tools.
4. Sincronizá Gradle con internet.
5. Elegí **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. El APK de depuración debería quedar en `app/build/outputs/apk/debug/app-debug.apk`.

### Con GitHub Actions
1. Subí el contenido de esta carpeta a un repositorio de GitHub.
2. Abrí la pestaña **Actions** y ejecutá **Build Numisfera Android APK** (o hacé push a `main`/`master`).
3. Descargá el artefacto `numisfera-debug-apk` cuando termine el trabajo.

## Estado de verificación
- Versión de proyecto: 0.4.0 (catálogo ampliado).
- Se verificó por compilador Kotlin aislado la sintaxis del módulo `CoinCatalog.kt` y sus mapeos contra un modelo de datos equivalente. Esto no equivale a compilar la aplicación Android completa.
- Esta entrega es código fuente, **no contiene un APK compilado**.
- En el entorno donde se preparó este ZIP no están instalados Gradle ni Android SDK y no hay acceso de red para descargarlos; por eso no fue posible compilar aquí ni probar en un teléfono. El flujo de GitHub Actions está incluido para intentar la compilación en un runner con SDK.
- El catálogo es una base de referencia inicial, no un inventario exhaustivo de cada año, variante, ceca o tirada.
- Los campos técnicos se completan solo cuando hay fuente para el tipo indicado; verificar siempre que la pieza física corresponda a esa variante.
- No hay todavía precios de mercado en vivo, tasación automática, identificación real por IA ni sincronización en nube.
- La importación de copia agrega registros; importar repetidamente el mismo archivo puede duplicar entradas.
- Exportá una copia de seguridad antes de instalar futuras versiones.
