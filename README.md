# 🚀 plugin_wifi_connect

**Flutter connector for Wi-Fi devices**  
Low-dependency plugin to simplify automatic connection to devices via SSID or SSID prefix. Compatible with **Android 10+ (API 29+)** and **iOS 11+**.

**Conector Flutter para dispositivos Wi‑Fi**  
Plugin com baixa dependência para facilitar a conexão automática a dispositivos via SSID ou prefixo de SSID. Compatível com **Android 10+ (API 29+)** e **iOS 11+**.

---

## 🎯 Features / Funcionalidades

- ✅ Connects to an exact SSID (iOS 11+, Android).
- 🔍 Connects to SSIDs that match a prefix (iOS 13+, Android).
- 📡 Compatible with IoT devices that use unique SSIDs.
- ⚙️ Efficient strategy: scans and connects by prefix on Android (requires `ACCESS_FINE_LOCATION`).
---
- ✅ Conecta-se a um SSID exato (iOS 11+, Android).
- 🔍 Conecta-se a SSIDs que combinam um prefixo (iOS 13+, Android).
- 📡 Compatível com dispositivos IoT que usam SSIDs únicos.
- ⚙️ Estratégia eficiente: escaneia e conecta no prefixo no Android (requer `ACCESS_FINE_LOCATION`).

---

## 📦 Installation / Instalação

Add to `pubspec.yaml`:

Adicione ao `pubspec.yaml`:

```yaml
dependencies:
  plugin_wifi_connect:
    git:
      url: https://github.com/chenrilima/plugin_wifi_connect.git
      ref: main
```

Then run / Depois execute:

```bash
flutter pub get
```

---

## 🔧 Usage / Uso

```dart
import 'package:plugin_wifi_connect/plugin_wifi_connect.dart';

void main() async {
  // Direct connection / Conexão direta
  bool ok = await PluginWifiConnect.connectToSsid(
    ssid: 'MeuDispositivoWiFi',
    password: 'senha123',
  );

  // Prefix connection / Conexão por prefixo
  bool okPrefix = await PluginWifiConnect.connectToSsidPrefix(
    prefix: 'IoTDevice_',
    password: 'senhaPadrao',
  );

  print('Direct SSID connection: 
