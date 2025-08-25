SkyVsion – Mapeamento Inteligente com Drone e YOLO

Este projeto é uma aplicação fullstack (Front-end + API Back-end) para o controle e monitoramento de drones equipados com câmera e geolocalizador, integrando visão computacional com IA (YOLOv8) para mapeamento de objetos em tempo real. A plataforma oferece um painel com visualização ao vivo do vídeo do drone, detecção automática de objetos e atualização dinâmica do local no mapa.

🚀 Funcionalidades

Conexão com drone físico ou simulado via DroneKit

Captura de vídeo ao vivo diretamente da câmera do drone

Detecção de objetos em tempo real com YOLOv8

Exibição da posição do drone no mapa (OpenStreetMap)

Atualização automática da posição no frontend via API

Visualização dos objetos detectados com bounding boxes

Interface web simples para visualização em tempo real

🧰 Tecnologias Utilizadas
Backend (API e controle do drone)

Python → Linguagem principal do projeto

Flask → Micro framework web para criar a API e servidor

DroneKit → Comunicação com o drone via MAVLink

OpenCV → Processamento de imagem da câmera

YOLOv8 (Ultralytics) → Detecção de objetos via IA

Gunicorn → Servidor WSGI de produção (opcional)

Frontend (Interface de controle)

HTML + CSS → Estrutura e estilo básico da interface

JavaScript (Vanilla) → Atualização do mapa e comunicação com a API

Leaflet.js → Biblioteca para mapas interativos com OpenStreetMap

📁 Estrutura dos Arquivos
Arquivo / Pasta	Função
backend/app.py	Inicializa o servidor Flask, rotas da API e feed de vídeo
backend/yolo_detector.py	Classe responsável por carregar e executar o modelo YOLOv8
backend/drone_controller.py	Conecta ao drone, recupera status e geolocalização
frontend/index.html	Página principal com feed de vídeo e mapa em tempo real
frontend/static/script.js	Atualiza o mapa com base na localização do drone via API
frontend/static/style.css	Estilo visual da interface
requirements.txt	Lista todas as dependências do projeto
🔧 O que cada tecnologia faz

Flask → Cria a API, serve a interface HTML e gerencia o fluxo de dados.

DroneKit → Controla o drone (armar, status, localização) e interage com PX4/ArduPilot.

YOLOv8 (Ultralytics) → Detecta objetos em tempo real com IA diretamente do vídeo da câmera.

OpenCV → Lê e processa quadros de vídeo para aplicar a detecção e visualização.

Leaflet.js → Exibe a localização do drone em um mapa interativo no frontend.

JavaScript → Consulta a API periodicamente para atualizar a interface com dados do drone.

▶️ Como Rodar o Projeto
1. Clone o repositório
git clone https://github.com/seu-usuario/dronevisionai.git
cd dronevisionai

2. Crie e ative um ambiente virtual (opcional, mas recomendado)
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows

3. Instale as dependências
pip install -r backend/requirements.txt

4. Execute o servidor Flask
cd backend
python app.py

5. Acesse o Frontend no navegador
http://localhost:5000

📡 Endpoints principais
Método	Rota	Função
GET	/	Página HTML com feed de vídeo e mapa
GET	/video_feed	Stream de vídeo ao vivo do drone
GET	/api/location	Retorna geolocalização atual do drone
GET	/api/status	Retorna status atual (modo, bateria, armado)
💡 Observações

O drone pode ser real ou simulado com SITL + MAVProxy.

A câmera pode ser substituída por uma URL de vídeo ao vivo ou RTSP.

O modelo YOLOv8 usado é o yolov8n.pt por padrão (leve e rápido).

Você pode treinar seu próprio modelo com classes específicas se necessário.

🧪 Requisitos para Testes Locais

Python 3.8+

OpenCV

DroneKit

YOLOv8 (instalado com pip install ultralytics)

Drone simulado (opcional): SITL ou PX4 + QGroundControl

🛡️ Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.****
