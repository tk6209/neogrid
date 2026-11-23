# NeoGrid NexaPay 💳⚡

> **A união da fluidez da aproximação (NFC/EMV) dos cartões físicos com a liquidação instantânea e baixo custo dos trilhos do Pix (Banco Central do Brasil).**

---

## 🌟 Visão Geral

No varejo físico atual, o Pix ainda enfrenta uma barreira de usabilidade: a dependência de desbloquear o smartphone, abrir o aplicativo bancário, escanear um QR Code e depender de sinal de dados móveis no checkout.

O **NeoGrid NexaPay** remove essa fricção:
- **Zero Fricção para o Consumidor**: Basta aproximar o cartão físico ou smartphone no leitor NFC do terminal POS convencional.
- **Liquidação Instantânea D+0**: O lojista recebe os fundos imediatamente na conta via SPI (Sistema de Pagamentos Instantâneos).
- **Redução Drástica em Taxas (MDR)**: Economia de até 70% comparado às taxas convencionais de débito e crédito das bandeiras tradicionais.
- **Aproveitamento da Infraestrutura Existente**: Opera diretamente nos terminais POS já instalados no mercado nacional.

---

## 🏛️ Os Três Pilares da Arquitetura

```
+-------------------------------------------------------------+
|                     NeoGrid NexaPay                      |
+-------------------------------------------------------------+
           |                         |                       |
           v                         v                       v
     [ NeoCore™ ]            [ NeoGrid Mesh™ ]         [ NeoGraph™ ]
  Motor Transacional        Roteamento Distribuído   Confiança Invisível
  - Tokenização EMV/NFC     - Sharding Dinâmico L5   - FIDO2 / Passkeys
  - De-tokenização & SPI    - Multi-tenant Edge      - Telemetria de Risco
  - Liquidação BACEN D+0    - Controle de Latência   - Antifraude Contínuo
```

### 1. NeoCore™
Motor transacional responsável pela ponte de protocolos entre a norma EMV Contactless (ISO 8583) e as mensagens XML/JSON do SPI BACEN (ISO 20022). Realiza o cofre de tokenização seguro, mapeamento dinâmico de chaves Pix e orquestração de liquidação financeira.

### 2. NeoGrid Mesh™
Camada de Control Plane e roteamento distribuído de alta disponibilidade. Utiliza Dynamic Database Sharding para isolar inquilinos de alto volume transacional (adquirentes e grandes emissores) com failover automático e latência de borda de sub-milissegundos.

### 3. NeoGraph™
Motor de Inteligência de Risco e Confiança Invisível (*Invisible Trust*). Aplica biometria comportamental, telemetria de POS e cerimônias silenciosas FIDO2/WebAuthn para garantir risco zero de fraude e mitigar engenharia social sem introduzir etapas de atrito ao portador.

---

## 🚀 Como Executar Localmente

Como o projeto é construído em padrões web modernos e leves, basta abrir o arquivo `index.html` em qualquer navegador ou rodar um servidor HTTP local:

```bash
# Com Python
python -m http.server 8080

# Ou com Node / npx
npx serve .
```

Acesse em: `http://localhost:8080`

---

## 🌐 Publicação no GitHub Pages

O site é automaticamente compilado e publicado no GitHub Pages:
🔗 **[https://tk6209.github.io/neogrid/](https://tk6209.github.io/neogrid/)**

---

## 📄 Licença e Autoria
Desenvolvido por **Vinicius Teixeira**.  
Todos os direitos reservados / Open Architecture Protocol 2026.
