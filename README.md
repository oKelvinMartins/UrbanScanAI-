# UrbanScan AI — Scanner Urbano Automático por Visão Computacional

Protótipo visual interativo que demonstra a evolução da zeladoria urbana: em vez de depender que o cidadão pare no trânsito para tirar fotos e preencher formulários manuais, o **UrbanScan AI** transforma câmeras de celulares, carros e motos em **scanners urbanos automáticos em tempo real**.

---

## Equipe

- **Kelvin Martins**
- **Jordan Henrique**
- **Moises**

---

## Onde está a Inovação

| Aspecto | Modelo Tradicional (Passivo / Manual) | UrbanScan AI (Automático / Zero Toque) |
| :--- | :--- | :--- |
| **Ação do cidadão** | Precisa parar, abrir o app, fotografar e digitar o endereço | Nenhuma interação manual (`0 cliques`) durante o trajeto |
| **Captação** | Foto isolada e pontual | Vídeo contínuo em tempo real (`60 FPS`) via celular no painel, carro ou moto |
| **Classificação** | Descrição subjetiva do usuário | IA de Visão Computacional detecta a anomalia, estima dimensões e calcula gravidade (`0–10`) |
| **Envio à Prefeitura** | Fila manual sem priorização padronizada | Envio automático imediato com coordenada **GPS**, gravidade e imagem com *bounding box* |

---

## Funcionalidades do Protótipo

### 1. Simulador Mobile (`App Celular`)
- **Modo `📸 Foto Cidadão`:** simula o cidadão apontando a câmera do celular diretamente para o problema na via, com grade de enquadramento, foco automático ao clicar na tela e **botão obturador** (dispara flash fotográfico, analisa a imagem com IA e envia imediatamente ao painel municipal).
- **Modo `⚡ Auto-Scan Vídeo`:** simula a captação contínua em movimento sem cliques, alternando entre os ângulos **`📸 Cidadão`**, **`🚘 Cabine`** (visão do painel automotivo) e **`🏍️ Moto`**.
- **Detecção das 4 anomalias urbanas:**
  - **Buraco na Via** (`CRÍTICO`)
  - **Rachadura no Asfalto** (`MODERADO`)
  - **Falta de Faixa de Pedestre** (`ALTO`)
  - **Lixo Acumulado** (`ALTO`)
- **Bento Grid Interativo no Smartphone:** medidor radial de **Gravidade**, seletor **Alvo na Via** (`‹` `›`), **Telemetria GPS** com slider de velocidade (`20` a `80 km/h`) e card **Última Captura**.

### 2. Painel de Controle da Prefeitura
- **4 KPIs em Tempo Real:** *Detecções Recebidas*, *Críticas Pendentes*, *Vias Escaneadas* (`km`) e *Precisão Média IA*.
- **Mapa de Zeladoria Georreferenciado:** exibe o deslocamento ao vivo do dispositivo scanner e os pins GPS coloridos por gravidade/status.
- **Evidência & Despacho de Ordens de Serviço (OS):** exibe a foto capturada pela IA, score de gravidade, validação cruzada (`+1 Veículo`) e botão **Gerar OS / Acionar Equipe**.
- **Fila de Ocorrências:** listagem sincronizada em tempo real com filtros por categoria e gravidade.

---

## Como Abrir e Apresentar o Projeto

### Opção 1 — Direto no Navegador (Mais Rápida)
Por ser um protótipo autocontido em HTML, basta dar um **duplo clique** no arquivo no Finder ou executar no terminal (dentro da pasta do projeto):

```bash
open prototipo_scanner_urbano.html
```
*(Ou `open index.html`, que possui o mesmo conteúdo.)*

### Opção 2 — Servidor HTTP Local (Recomendado para Apresentação em Tela Cheia)
No terminal, dentro da pasta do projeto:

```bash
python3 -m http.server 8080
```

Depois, abra no navegador:
- `http://localhost:8080` (carrega `index.html`), ou
- `http://localhost:8080/prototipo_scanner_urbano.html`

> **Dica:** Para alternar entre tema claro e escuro quando aberto no navegador, use o botão `☀️` / `🌙` no cabeçalho superior direito.

### Opção 3 — Dentro do Antigravity IDE
- **No Chat:** quando embutido pelo assistente via `<agent-embed>`, o protótipo roda diretamente dentro da conversa.
- **No Painel Lateral (Preview Visual):** clique no link do artefato gerado no histórico do chat (arquivos abertos diretamente da árvore do workspace mostram o código-fonte HTML no editor).

---

## Roteiro Sugerido para Apresentação (1–2 minutos)

1. Comece no modo padrão **`📸 Foto Cidadão`** e clique no botão obturador amarelo (ou diretamente sobre o buraco na tela do celular) para mostrar como funciona a captura manual tradicional — observe a foto aparecer instantaneamente no **Mapa** e na **Fila da Prefeitura** ao lado.
2. Em seguida, alterne no topo do simulador para **`⚡ Auto-Scan Vídeo`** e selecione **`🚘 Cabine`** ou **`🏍️ Moto`**.
3. Mostre que, com **zero cliques**, o veículo percorre a avenida no mapa e envia automaticamente buracos, rachaduras, falta de faixa de pedestre e lixo acumulado com GPS e gravidade.
4. Clique em uma ocorrência crítica no **Painel da Prefeitura** e clique em **`Gerar OS / Acionar Equipe`** para demonstrar o fechamento do ciclo operacional.

---

## Estrutura de Arquivos

```text
projeto-design-profissional/
├── index.html                      # Versão principal do protótipo para navegador
├── prototipo_scanner_urbano.html   # Cópia nomeada do protótipo interativo
└── README.md                       # Documentação e instruções de uso
```
