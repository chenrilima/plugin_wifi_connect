
  # 🚀 plugin_wifi_connect

**Conector Flutter para dispositivos Wi‑Fi**  
Plugin com baixa dependência para facilitar a conexão automática a dispositivos via SSID ou prefixo de SSID. Compatível com Android 10+ (API 29+) e iOS 11+.

---

## 🎯 Funcionalidades

- Conecta-se a um SSID exato (iOS 11+, Android).
- Conecta-se a SSIDs que combinam um prefixo (iOS 13+, Android).
- Compatível com dispositivos IoT que usam SSIDs únicos.
- Estratégia eficiente: escaneia e conecta no prefixo no Android (requer `ACCESS_FINE_LOCATION`).

---

## 📦 Instalação

No `pubspec.yaml`, adicione:

```yaml
dependencies:
  plugin_wifi_connect:
    git:
      url: https://github.com/chenrilima/plugin_wifi_connect.git
      ref: main


Depois, execute:
flutter pub get
🔧 Uso

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

  print('Conexão SSID direta: $ok');
  print('Conexão com prefixo: $okPrefix');
}
📱 Permissões Necessárias

iOS
  •	Access WiFi Information Entitlement (obter SSID)
  • Hotspot Configuration Entitlement (conectar redes)

Android

Android 10+ (API 29+):
ACCESS_FINE_LOCATION (para prefixo ou obter SSID)

Android <29:
ACCESS_WIFI_STATE
CHANGE_WIFI_STATE
CHANGE_NETWORK_STATE
ACCESS_FINE_LOCATION (ao usar prefixo)

Use permission_handler para solicitar permissões em tempo de execução.

⸻

🧪 Exemplo

Veja a pasta example/ com uma aplicação minimalista que:
	•	Solicita permissões no startup;
	•	Conecta-se a uma rede específica ou via prefixo;
	•	Exibe o estado da conexão.

⚙️ Desenvolvimento
1.	Clone o repo:
  git clone https://github.com/chenrilima/plugin_wifi_connect.git
  cd plugin_wifi_connect

2.	Teste o plugin:
  cd example
  flutter run

	3.	Faça melhorias, testes e abra PRs! 😉

📚 Suporte & Contribuições
  • Bugs e features: issues
  • Star e Fork bem-vindos!
  •	Documentação expandida no futuro.

⸻

📜 Licença

Licenciado sob BSD‑3 Clause — consulte o arquivo LICENSE.

⸻

🧠 Por que usar este plugin?
 •	🌐 Desenvolvido para facilitar integrações Wi‑Fi em Flutter.
 •	🔄 Base contínua do plugin flutter_wifi_connect (criado por weplenish).
 •	✅ Simples, eficiente e com foco em conectividades IoT.

⸻

✔️ Próximos passos
  •	Suporte a Android & iOS mais antigos?
  •	Conexão segura com WPA/WPA2 Enterprise?
  •	Integração com notificações de mudança de rede?
