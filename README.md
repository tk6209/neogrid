# NeoGrid NexaPay

> **Iniciação de pagamentos conta-a-conta por aproximação física (NFC) com prova criptográfica em módulo seguro e liquidação instantânea D+0 nos trilhos do SPI BACEN.**

---

## Visão Geral

No varejo físico atual, o Pix ainda enfrenta uma barreira de usabilidade: a dependência de desbloquear o smartphone, abrir o aplicativo bancário, escanear um QR Code e depender de sinal de dados móveis no checkout.

O **NeoGrid NexaPay** remove essa fricção através de uma arquitetura unificada:
- **Zero Fricção para o Consumidor**: Basta aproximar o cartão físico inteligente ou wearable no leitor NFC do terminal POS convencional.
- **Liquidação Instantânea D+0**: O lojista recebe os fundos imediatamente na conta via SPI (Sistema de Pagamentos Instantâneos).
- **Sem Intermediários de Bandeira**: Dispensa tabelas BIN proprietárias e taxas abusivas de arranjos legados.
- **Aproveitamento da Infraestrutura Existente**: Opera diretamente nos terminais POS já instalados no mercado nacional.

---

## Área Única NeoGrid: Os Dois Fluxos de Iniciação

A plataforma **NeoGrid** opera como uma camada única de iniciação e roteamento institucional, suportando duas modalidades complementares:

```
+-------------------------------------------------------------------+
|                        Área Única NeoGrid                         |
|            (Módulo de Iniciação & Roteamento Institucional)       |
+-------------------------------------------------------------------+
                     |                                   |
                     v                                   v
       [ Iniciação Direta SPI ]              [ Iniciação Open Finance ]
     - Iniciação Delegada (Novidade)        - Via Iniciador (ITP) habilitado
     - pacs.008 direta ao SPI               - APIs /payments/v4 padronizadas
     - Consumo durável de frescor           - Consentimento e credencial vinculada
     - Resolução Soberana por ISPB          - Detentor de conta liquida no SPI
```

### 1. Iniciação Delegada via SPI (pacs.008) — Novidade
O participante pagador habilitado recebe a prova criptográfica gerada pelo chip seguro no ato da aproximação física no terminal POS. 
Com a **autorização delegada previamente outorgada** pelo portador, o nó pagador valida a assinatura, realiza o **consumo atômico e durável do valor de frescor (contador monotônico)** em memória local para defesa anti-replay, e submete diretamente a ordem **pacs.008** ao SPI BACEN, obtendo confirmação D+0 (`pacs.002`).

### 2. Iniciação via Open Finance (ITP)
A requisição é estruturada pelo NeoGrid e submetida através de um **Iniciador de Transação de Pagamento (ITP)** regulado perante o Open Finance Brasil. A instituição detentora da conta valida o vínculo da credencial física, consome o frescor na máquina de estados e dispara a liquidação instantânea no SPI.

---

## Segurança Criptográfica & Resolução Soberana
- **Chave Não Exportável**: O material criptográfico secreto reside no módulo seguro (EAL5+) e nunca é exposto ao terminal ou à rede.
- **Resolução por ISPB**: A instituição pagadora é identificada pelo seu código de 8 dígitos (ISPB) resolvido em diretório soberano nacional, sem intermediários.
- **Defesa Anti-Replay**: Consumo prévio e durável de frescor antes da submissão da ordem financeira.
- **Idempotência**: Identificador único de transação garante que nenhuma operação duplicada ocorra mesmo com instabilidade de rede.

---

## Como Executar Localmente

Como o projeto é construído em padrões web modernos e leves, basta abrir o arquivo `index.html` em qualquer navegador ou rodar um servidor HTTP local:

```bash
# Com Python
python -m http.server 8080

# Ou com Node.js npx
npx serve .
```
Acesse `http://localhost:8080` para visualizar a página interativa e o simulador do terminal POS.
