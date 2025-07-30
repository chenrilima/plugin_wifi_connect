# 🚀 plugin_wifi_connect

**Conector Flutter para dispositivos Wi‑Fi**  
Plugin com baixa dependência para facilitar a conexão automática a dispositivos via SSID ou prefixo de SSID. Compatível com **Android 10+ (API 29+)** e **iOS 11+**.

---

## 🎯 Funcionalidades

- ✅ Conecta-se a um SSID exato (iOS 11+, Android).
- 🔍 Conecta-se a SSIDs que combinam um prefixo (iOS 13+, Android).
- 📡 Compatível com dispositivos IoT que usam SSIDs únicos.
- ⚙️ Estratégia eficiente: escaneia e conecta no prefixo no Android (requer `ACCESS_FINE_LOCATION`).

---

## 📦 Instalação

No `pubspec.yaml`, adicione:

```yaml
dependencies:
  plugin_wifi_connect:
    git:
      url: https://github.com/chenrilima/plugin_wifi_connect.git
      ref: main
```

Depois, execute:

```bash
flutter pub get
```

---

## 🔧 Uso

```dart
import 'package:plugin_wifi_connect/plugin_wifi_connect.dart';

void main() async {
  // Conexão direta
  bool ok = await PluginWifiConnect.connectToSsid(
    ssid: 'MeuDispositivoWiFi',
    password: 'senha123',
  );

  // Conexão por prefixo
  bool okPrefix = await PluginWifiConnect.connectToSsidPrefix(
    prefix: 'IoTDevice_',
    password: 'senhaPadrao',
  );

  print('Conexão SSID direta: 
