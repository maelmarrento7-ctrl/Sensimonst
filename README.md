# 🎯 SensiMaster — Painel Flutuante de Sensibilidade

App Android nativo (Kotlin) com painel flutuante (overlay) que **gera sensibilidades únicas na hora** para Free Fire e jogos FPS, baseando-se nas características reais do dispositivo do usuário.

## ✨ Funcionalidades

- 🫧 **Bolha flutuante arrastável** sobre qualquer app (incluindo durante o jogo)
- 🎨 **Painel colorido e vibrante** com 4 modos: Precisão / Equilibrada / Agressiva / Headshot
- 📱 **Detecção automática do dispositivo** (modelo, RAM, DPI, taxa de atualização, Android)
- 🤖 **Gerador inteligente** que combina heurísticas + randomização (sensi diferente a cada toque)
- 💾 **Histórico** das sensibilidades salvas (até 50)
- 📤 **Compartilhamento** em texto formatado pronto para colar
- ⚙️ **Ajustes recomendados de DPI / FPS / Gráficos** baseados no tier do processador

## 📂 Estrutura

```
SensiMaster/
├── app/
│   ├── build.gradle
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/sensimaster/app/
│       │   ├── activities/  (Splash, Main, History, Settings, Permission)
│       │   ├── adapters/    (SensitivityAdapter)
│       │   ├── models/      (Sensitivity, DeviceProfile)
│       │   ├── services/    (FloatingBubbleService — overlay window)
│       │   └── utils/       (DeviceDetector, SensitivityGenerator, HistoryRepository)
│       └── res/
│           ├── drawable/    (gradientes, ícones, fundos coloridos)
│           ├── layout/      (todas as telas + painel flutuante)
│           ├── mipmap-*/    (ícone do app)
│           └── values/      (cores vibrantes, strings, tema)
├── build.gradle
├── settings.gradle
└── gradle.properties
```

## 🚀 Como compilar

1. Abra a pasta `SensiMaster` no **Android Studio (Hedgehog ou superior)**
2. Aguarde o Gradle sincronizar (ele baixa as dependências sozinho)
3. Conecte um celular ou inicie um emulador (Android 6.0+)
4. Clique em ▶ Run

## 🔐 Permissões

- `SYSTEM_ALERT_WINDOW` — necessária para o painel flutuante (o app pede ao usuário na primeira execução)
- `FOREGROUND_SERVICE` — para manter a bolha viva enquanto o jogo roda
- `POST_NOTIFICATIONS` — Android 13+ exige para mostrar a notificação persistente

## 🎮 Como usar

1. Abra o app → toque em **🚀 Ativar Painel Flutuante**
2. Conceda a permissão de sobreposição quando solicitado
3. Abra Free Fire (ou qualquer FPS) — a bolha colorida aparece
4. Toque na bolha → painel abre com sensibilidades geradas na hora
5. Use os 4 modos coloridos para gerar variações
6. Salve as melhores no histórico ou compartilhe com amigos

## 🛠 Tecnologias

- **Kotlin** + AndroidX
- **WindowManager** com `TYPE_APPLICATION_OVERLAY` para a bolha
- **Material Components 1.11**
- **Gson** para persistência do histórico
- **ConstraintLayout / CardView / RecyclerView**

## ⚠ Aviso

Este é um app **independente, inspirado** no conceito de painéis de sensibilidade — não é afiliado a Garena (Free Fire) nem ao app Faile Sensitivity. Os valores gerados são **sugestões iniciais** que cada jogador deve ajustar conforme seu estilo.
