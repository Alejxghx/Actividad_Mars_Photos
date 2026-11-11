# Actividad Mars Photos

Implementación del codelab [Cómo obtener datos de Internet](https://developer.android.com/codelabs/basic-android-kotlin-compose-getting-data-internet?hl=es-419).

## Resultado

La aplicación consulta `https://android-kotlin-fun-mars-server.appspot.com/photos` con Retrofit y una función `suspend`. Kotlin Serialization convierte el JSON en `List<MarsPhoto>` usando `@Serializable` y `@SerialName("img_src")`.

El ViewModel ejecuta la consulta en `viewModelScope` y expone los estados de carga, éxito y error. La pantalla muestra `Success: N Mars photos retrieved`, donde N es el tamaño real de la respuesta. Si falla la conexión, el servidor o el formato de los datos, muestra un error y permite reintentar. El manifiesto declara el permiso `INTERNET`.

Este codelab termina con el conteo de registros; la cuadrícula de imágenes corresponde a una actividad posterior. Se conserva el repositorio y la inyección manual de dependencias que ya contenía el proyecto base para permitir pruebas aisladas.

## Ejecución

1. Abrir esta carpeta en Android Studio y sincronizar Gradle.
2. Usar JDK 17 o superior, Android SDK 35 y un dispositivo con API 24 o superior.
3. Ejecutar `app` con conexión a Internet.
4. Para comprobar el error, desactivar la conexión y pulsar Retry después de reiniciar la aplicación; restaurar la conexión y reintentar.

## Verificación local

```sh
./gradlew :app:testDebugUnitTest :app:assembleDebug :app:lintDebug
```

Código base de Google, conservando su licencia Apache 2.0.
