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