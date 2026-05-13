# 13 — Desarrollo Móvil

> Hacer apps para iPhone y Android. 3 caminos: nativo, cross-platform, o web wrapper.

## 🚦 Qué camino elegir

| Camino | Ventaja | Desventaja | Ejemplo |
|--------|---------|-----------|---------|
| **Nativo iOS (Swift)** | Mejor performance, integración total | Solo Apple | Instagram (parte) |
| **Nativo Android (Kotlin)** | Mejor performance Android | Solo Google | Apps de Google |
| **React Native** | Una sola codebase, JS | Algunas limitaciones | Facebook, Discord |
| **Flutter** | UI hermosa, fluida | Dart (lenguaje nuevo) | Alibaba, Google Pay |
| **Expo + RN** | Setup fácil | Cuesta personalizar mucho | Apps indie |
| **Capacitor / Tauri Mobile** | Tu web → app | Limitado | Apps simples |

> **Recomendación 2026:** Empezá con **React Native + Expo** si ya sabés React.

---

## 📱 React Native + Expo (el más popular)

### Recursos
- 📺 [Curso React Native - midudev](https://www.youtube.com/results?search_query=Curso%20React%20Native%20-%20midudev)
- 📺 [Expo - React Native fácil](https://www.youtube.com/results?search_query=Expo%20-%20React%20Native%20f%C3%A1cil)
- 📖 [docs.expo.dev](https://docs.expo.dev/)
- 📖 [reactnative.dev](https://reactnative.dev/)

### Instalación
```bash
npx create-expo-app mi-app
cd mi-app
npx expo start
```

Te da un QR → lo escaneás con Expo Go en tu celu → corre tu app sin compilar.

### Stack moderno RN
- **Expo Router** — routing tipo Next.js
- **NativeWind** — Tailwind para RN
- **Zustand** — state simple
- **TanStack Query** — server state
- **Tamagui** — UI universal

---

## 🦋 Flutter (Google)

Lenguaje: **Dart**. Hot reload increíble.

### Recursos
- 📺 [Flutter desde cero - MoureDev](https://www.youtube.com/results?search_query=Flutter%20desde%20cero%20-%20MoureDev)
- 📖 [flutter.dev/learn](https://flutter.dev/learn)
- 📖 [dart.dev](https://dart.dev/)

```dart
void main() {
  runApp(MaterialApp(home: Scaffold(
    body: Center(child: Text('Hola Mundo')),
  )));
}
```

---

## 🍎 iOS nativo (Swift + SwiftUI)

Necesitás Mac.

- 📺 [Swift desde cero - MoureDev](https://www.youtube.com/playlist?list=PLLBpHvFs5_w_zVhCiP6yQENYxLCgkBwQt)
- 📖 [hackingwithswift.com](https://www.hackingwithswift.com/) ⭐
- 📖 [Apple Developer Tutorials](https://developer.apple.com/tutorials/swiftui)
- 📺 [Stanford CS193p (gratis)](https://cs193p.sites.stanford.edu/)

### Tools
- **Xcode** (gratis)
- **TestFlight** para distribución beta
- $99 USD/año para publicar en App Store

---

## 🤖 Android nativo (Kotlin + Jetpack Compose)

- 📺 [Kotlin desde cero - MoureDev](https://www.youtube.com/playlist?list=PLLBpHvFs5_w-RxYdcLuYIm9DEAr3wSfAQ)
- 📖 [Android Developers](https://developer.android.com/)
- 📖 [kotlinlang.org](https://kotlinlang.org/)

### Tools
- **Android Studio** (gratis)
- $25 USD una vez para Play Store

---

## 🎯 Proyectos para empezar

1. **Lista de tareas móvil** — CRUD básico con storage local
2. **Clima** — geolocalización + API
3. **App de hábitos** — notificaciones, streaks
4. **Linterna** — control de hardware (flash)
5. **Lector de QR** — cámara
6. **App social mini** — auth + feed
7. **Wallet de criptomonedas** — APIs financieras

---

## 📦 Cómo publicar

### App Store (iOS)
1. Cuenta de Apple Developer ($99/año)
2. Compilar con Xcode
3. Subir a App Store Connect
4. Esperar review (1-3 días)

### Play Store (Android)
1. Cuenta de Google Play Console ($25 una sola vez)
2. Generar APK/AAB firmado
3. Subir y completar ficha
4. Review (horas a días)

### Sin pagar
- **TestFlight** (iOS) — invitás hasta 10k testers
- **Expo Updates** — actualizaciones OTA sin store
- **APK directo** — Android permite instalar fuera de la store
