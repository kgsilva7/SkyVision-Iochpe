# SkyVision - Mapeamento Inteligente com Drone

Este projeto é uma aplicação de mapeamento inteligente com drones que integra visão computacional com YOLOv8, geolocalização em tempo real e exibição interativa em mapa.
O sistema foi desenvolvido para monitoramento e demonstração tecnológica no Porto de Santos, em parceria com a empresa Iochpe, possibilitando identificar objetos em tempo real a partir do vídeo do drone e exibir os resultados em uma plataforma web interativa.
---
## Funcionalidades:
- Conexão com drone e captura de vídeo em tempo real.
- Detecção automática de objetos usando YOLOv8.
- Exibição do vídeo com caixas delimitadoras dos objetos detectados.
- Integração com mapa interativo mostrando a posição do drone e pontos de detecção.
- Atualização em tempo real via WebSocket.
- Painel web responsivo para monitoramento.
---
## Tecnologias Utilizadas:
- **Python** (FastAPI) → API backend para processar o vídeo e fornecer dados em tempo real.
- **YOLOv8** (Ultralytics) → Modelo de visão computacional para detecção de objetos.
- **8OpenCV** → Processamento de vídeo e integração com YOLO.
- **WebSocket** → Comunicação em tempo real entre backend e frontend.
- **Leaflet.js** → Biblioteca de mapas interativos para exibição da posição do drone.
- **React.js** → Frontend moderno e responsivo para interface de monitoramento.
- **Tailwind CSS3** → Estilização rápida e responsiva no frontend.
- **Docker** → Containerização da aplicação para fácil implantação.
---
##O que cada tecnologia faz:
- **FastAPI** → Cria rotas e gerencia o backend de forma rápida e performática.
- **React.js** → Interface web para visualização do vídeo e mapa.
- **Tailwind CSS3** → Fornece um design limpo e responsivo.
- **Docker** → Facilita a implantação em diferentes ambientes.
- **YOLOv8** → Detecta objetos em tempo real a partir do vídeo do drone.
- **OpenCV** → Manipula o vídeo para desenhar caixas delimitadoras.
- **WebSocket** → Envia dados de detecção e localização para o frontend em tempo real.
- **Leaflet** → Exibe mapa interativo com rota do drone e pontos de interesse.
---
## Como rodar o projeto:

**Clone o repositório**
git clone https://github.com/seu-usuario/skyvision.git
cd skyvision

**Configure o arquivo `.env`**
DRONE_STREAM_URL=rtsp://seu-drone-url
YOLO_MODEL=yolov8n.pt

**Suba os containers com Docker**
docker-compose up --build

**Acesse o sistema**
Backend API: http://localhost:8000
Frontend Web: http://localhost:3000
---
**Endpoints principais**
GET /video → Stream de vídeo processado com detecção de objetos
WS /ws/detections → Canal WebSocket para enviar detecções e localização em tempo real
GET /status → Verifica se o backend está ativo
---
**Licença**
Este projeto está licenciado sob a licença MIT.
