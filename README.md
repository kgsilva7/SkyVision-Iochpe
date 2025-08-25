SkyVision - Mapeamento Inteligente com Drone e Visão Computacional

Este projeto é uma aplicação Fullstack (Front-end e API Back-end) que integra o controle de drones com visão computacional baseada em IA (YOLOv8) e geolocalização em tempo real, permitindo o mapeamento visual de objetos diretamente do vídeo capturado pelo drone.
A plataforma permite visualização ao vivo, detecção automática de objetos e monitoramento geográfico através de um mapa interativo com atualização dinâmica.

Funcionalidades

Conexão com drone real ou simulado via DroneKit

Captura de vídeo ao vivo da câmera acoplada ao drone

Detecção de objetos em tempo real usando YOLOv8

Mapeamento da posição atual do drone com Leaflet.js

Atualização automática da posição no mapa a cada 3 segundos

Interface web acessível localmente para monitoramento remoto

Tecnologias Utilizadas

Python → Linguagem base para o backend e controle do drone

Flask → Framework web para criação da API REST

DroneKit → Biblioteca para comunicação com drones via MAVLink

OpenCV → Processamento de vídeo e manipulação de imagens

YOLOv8 (Ultralytics) → IA para detecção de objetos em tempo real

HTML/CSS → Estrutura e estilo da interface

JavaScript (Vanilla) → Comunicação entre frontend e backend

Leaflet.js → Biblioteca para exibição de mapas interativos

Folium (opcional) → Geração de mapas em Python, se necessário

Estrutura dos Arquivos
Arquivo / Pasta	Função
backend/app.py	Inicializa o servidor Flask, define rotas da API e gera o stream de vídeo
backend/yolo_detector.py	Carrega o modelo YOLOv8 e executa a detecção de objetos
backend/drone_controller.py	Conecta ao drone e retorna localização GPS e status de voo
frontend/index.html	Página principal da interface com vídeo e mapa
frontend/static/style.css	Estilização visual da interface
frontend/static/script.js	Atualiza a posição do drone no mapa periodicamente via chamadas à API
requirements.txt	Lista de bibliotecas necessárias para rodar o backend
O que cada tecnologia faz

Flask → Gerencia as rotas da API e serve o frontend.

DroneKit → Conecta e controla o drone (modo de voo, localização, armamento).

YOLOv8 → Detecta objetos com base em modelos treinados, usando imagens capturadas ao vivo.

OpenCV → Captura e processa quadros da câmera, desenha bounding boxes.

Leaflet.js → Exibe a localização do drone sobre mapas do OpenStreetMap.

JavaScript → Atualiza dinamicamente a interface com dados do drone.

HTML/CSS → Estrutura e apresenta a interface para o usuário.

Como rodar o projeto

Clone o repositório

git clone https://github.com/seu-usuario/dronevisionai.git
cd dronevisionai


Crie e ative um ambiente virtual (opcional, mas recomendado)

python -m venv venv
source venv/bin/activate        # Linux/macOS
venv\Scripts\activate           # Windows


Instale as dependências

pip install -r backend/requirements.txt


Execute o servidor

cd backend
python app.py


Acesse o frontend
Abra seu navegador em:

http://localhost:5000

Endpoints principais

GET / → Interface web com mapa e vídeo ao vivo

GET /video_feed → Stream de vídeo processado com detecção de objetos

GET /api/location → Retorna a localização atual do drone (latitude, longitude, altitude)

GET /api/status → Retorna o status atual do drone (modo de voo, bateria, armado)

Licença

Este projeto está licenciado sob a licença MIT.
