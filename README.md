# Dolores Hoy

Tablero Flutter que consume 5 APIs gratuitas (Open-Meteo, Frankfurter, Nager.Date,
Wikipedia, NASA APOD) con buenas prácticas de seguridad, desarrollado con TDD.

## Puesta en marcha

```bash
# 1. Genera las carpetas de plataforma (android/, ios/, etc.) sin tocar lib/ ni test/
flutter create . --project-name dolores_hoy --org mx.edu.utng

# 2. Dependencias
flutter pub get

# 3. Pruebas (sin internet, con MockClient)
flutter test

# 4. Ejecutar con tu clave (edita secrets.json; NUNCA lo subas a git)
flutter run --dart-define-from-file=secrets.json
```

## Android
Verifica que `android/app/src/main/AndroidManifest.xml` tenga:
`<uses-permission android:name="android.permission.INTERNET"/>`
y **no** actives `usesCleartextTraffic`.

## Versión final ofuscada
```bash
flutter build apk --obfuscate --split-debug-info=build/simbolos --dart-define-from-file=secrets.json
```

## Estructura
- `lib/dominio/`: excepciones con mensajes seguros y modelos.
- `lib/datos/`: `ClienteSeguro` (única puerta a internet), `ConfigClaves`, un servicio por API.
- `lib/presentacion/`: `TableroViewModel` (estado independiente por API) y pantalla.
- `test/`: cliente, servicios, seguridad y viewmodel.
