# 🎮 Pokémon & Cat Gallery App

<div align="center">

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=apple&logoColor=white)

**Una aplicación multiplataforma que integra múltiples APIs públicas**

[Características](#-características) • [Instalación](#-instalación) • [APIs Utilizadas](#-apis-utilizadas) • [Capturas](#-capturas-de-pantalla) • [Licencia](#-licencia)

</div>

---

## 📋 Descripción

Aplicación móvil desarrollada en Flutter que consume dos APIs públicas diferentes:

1. **Pokémon API** - Búsqueda detallada de Pokémon con toda su información
2. **CATAAS (Cat as a Service)** - Galería de imágenes de gatos con filtros

La app demuestra el consumo de APIs REST, manejo de estado, navegación por tabs, y patrones de diseño modernos como skeleton loaders.

---

## ✨ Características

### 🔴 Actividad 1: Buscador de Pokémon

- ✅ Búsqueda por nombre de Pokémon
- ✅ Información completa:
  - Imagen del Pokémon
  - ID y nombre
  - Altura y peso
  - Tipos (fuego, agua, planta, etc.)
  - Habilidades
  - Estadísticas con barras de progreso visual
- ✅ Manejo de errores (Pokémon no encontrado)
- ✅ Interfaz intuitiva con Material Design

### 🐱 Actividad 2: Galería de Gatos

- ✅ Grid de imágenes de gatos en formato 2 columnas
- ✅ Filtros por categoría:
  - Cute (Tiernos)
  - Kitten (Gatitos)
  - Funny (Graciosos)
  - Sleep (Durmiendo)
  - Play (Jugando)
- ✅ Skeleton loader animado durante la carga
- ✅ Modal con detalles al tocar cada imagen
- ✅ Sin necesidad de API Key
- ✅ Sin problemas de CORS

### 🎨 Características técnicas

- 📱 Navegación por tabs (Bottom Navigation Bar)
- 🔄 Manejo de estados de carga, error y éxito
- 💾 HTTP requests con el paquete `http`
- 🎭 Skeleton loaders animados
- 🎨 Diseño Material Design 3
- ⚡ Optimizado para rendimiento
- 📦 Sin dependencias innecesarias

---

## 🚀 Instalación

### Prerrequisitos

- Flutter SDK (>=3.5.4)
- Dart SDK (>=3.5.4)
- Android Studio / VS Code
- Android SDK / Xcode (para iOS)

### Pasos de instalación

1. **Clona el repositorio**

```bash
git clone https://github.com/tu-usuario/pokemonapi_flutter.git
cd pokemonapi_flutter
```

2. **Instala las dependencias**

```bash
flutter pub get
```

3. **Ejecuta la aplicación**

```bash
# En modo debug
flutter run

# Para web
flutter run -d chrome

# Para Android
flutter run -d android

# Para iOS
flutter run -d ios
```

4. **Genera el APK (Android)**

```bash
# APK de debug
flutter build apk --debug

# APK de release
flutter build apk --release

# APK dividido por arquitectura (más pequeño)
flutter build apk --split-per-abi
```

El APK generado estará en: `build/app/outputs/flutter-apk/`

---

## 🌐 APIs Utilizadas

### 1. PokéAPI

- **URL Base**: `https://pokeapi.co/api/v2/`
- **Endpoint**: `/pokemon/{nombre}`
- **Documentación**: [https://pokeapi.co/](https://pokeapi.co/)
- **Características**:
  - API REST pública y gratuita
  - No requiere autenticación
  - Información completa de todos los Pokémon

**Ejemplo de uso:**
```dart
GET https://pokeapi.co/api/v2/pokemon/pikachu
```

### 2. CATAAS (Cat as a Service)

- **URL Base**: `https://cataas.com/`
- **Endpoint API**: `/api/cats?tags={tag}&limit={limit}`
- **Endpoint Imágenes**: `/cat/{id}`
- **Documentación**: [https://cataas.com/](https://cataas.com/)
- **Características**:
  - API REST pública y gratuita
  - No requiere API Key
  - Sin problemas de CORS
  - Miles de imágenes de gatos

**Ejemplo de uso:**
```dart
GET https://cataas.com/api/cats?tags=cute&limit=20
GET https://cataas.com/cat/{id}
```

---

## Dependencias

```yaml
dependencies:
  flutter:
    sdk: flutter
  http: ^1.2.2
  cupertino_icons: ^1.0.8
```

---

## 📱 Capturas de Pantalla

### Tab 1: Buscador de Pokémon
```
┌─────────────────────┐
│  🔴 Pokémon Search  │
├─────────────────────┤
│ [Search: pikachu] 🔍│
│    [Buscar Button]  │
├─────────────────────┤
│       🖼️            │
│     PIKACHU         │
│       #25           │
├─────────────────────┤
│ Altura: 0.4m        │
│ Peso: 6.0kg         │
├─────────────────────┤
│ Tipos: ⚡electric   │
│ Habilidades: static │
├─────────────────────┤
│ Estadísticas:       │
│ HP      ████░░ 35   │
│ ATTACK  ████░░ 55   │
│ DEFENSE ███░░░ 40   │
└─────────────────────┘
```

### Tab 2: Galería de Gatos
```
┌─────────────────────┐
│  🐱 Cat Gallery     │
├─────────────────────┤
│ [cute][kitten][funny]│
│    [Recargar 🔄]    │
├─────────────────────┤
│  🖼️      🖼️         │
│ Cat #1   Cat #2     │
│                     │
│  🖼️      🖼️         │
│ Cat #3   Cat #4     │
└─────────────────────┘
```

---

## Estructura del Proyecto

```
pokemonapi_flutter/
├── lib/
│   └── main.dart              # Código principal de la app
├── android/                   # Configuración Android
│   ├── app/
│   │   ├── build.gradle      # Configuración de la app
│   │   └── src/
│   │       └── main/
│   │           └── AndroidManifest.xml
│   ├── build.gradle          # Configuración del proyecto
│   └── settings.gradle       # Plugins de Gradle
├── ios/                       # Configuración iOS
├── test/                      # Tests unitarios
│   └── widget_test.dart
├── pubspec.yaml              # Dependencias del proyecto
└── README.md                 # Este archivo
```

---

## Tests

Ejecuta los tests con:

```bash
flutter test
```

Los tests incluyen:
- ✅ Verificación de carga inicial de la app
- ✅ Navegación entre tabs
- ✅ Búsqueda de Pokémon
- ✅ Manejo de campos de texto

---

## Desarrollo

### Agregar nuevas características

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/NuevaCaracteristica`)
3. Commit tus cambios (`git commit -am 'Agrega nueva característica'`)
4. Push a la rama (`git push origin feature/NuevaCaracteristica`)
5. Abre un Pull Request

### Código limpio

El proyecto sigue las convenciones de Dart y Flutter:

```bash
# Analiza el código
flutter analyze

# Formatea el código
flutter format .
```

---

## Solución de Problemas

### Problema: Error de CORS en web

**Solución**: Ejecuta con proxy
```bash
flutter run -d chrome --web-browser-flag "--disable-web-security"
```

### Problema: Gradle build falla

**Solución**: Limpia y reconstruye
```bash
flutter clean
cd android
./gradlew clean
cd ..
flutter pub get
flutter build apk
```

### Problema: Imágenes no cargan

**Solución**: Verifica permisos de internet en `AndroidManifest.xml`:
```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

---

## Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

---

## Autor

**Tu Nombre**
- GitHub: Mateo Paredes

---

## Agradecimientos

- [PokéAPI](https://pokeapi.co/) - Por proporcionar una API pública gratuita de Pokémon
- [CATAAS](https://cataas.com/) - Por la API de imágenes de gatos
- [Flutter Team](https://flutter.dev/) - Por el increíble framework

---

## Versiones

### v1.0.0 (2024-12-01)
- rimera versión estable
- Actividad 1: Buscador de Pokémon completo
- Actividad 2: Galería de gatos con filtros
- Skeleton loaders animados
- Navegación por tabs
- Correcciones de bugs iniciales

---
