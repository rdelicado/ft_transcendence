# 🎮 ft_transcendence

[![Language](https://img.shields.io/badge/Language-Python-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Framework-Django-green.svg)](https://www.djangoproject.com/)
[![Database](https://img.shields.io/badge/Database-PostgreSQL-blue.svg)](https://www.postgresql.org/)
[![Web Server](https://img.shields.io/badge/Server-NGINX-red.svg)](https://nginx.org/)
[![Container](https://img.shields.io/badge/Container-Docker-blue.svg)](https://www.docker.com/)
[![42 School](https://img.shields.io/badge/42-School_Project-purple.svg)](https://42.fr/)

## 📋 Descripción

**ft_transcendence** es una aplicación web completa que recrea el clásico juego Pong con características modernas de una plataforma social. Este proyecto representa la culminación del currículo de 42 School, integrando desarrollo web full-stack, bases de datos, containerización, monitoreo y arquitectura de microservicios.

La aplicación está construida con Django como backend, PostgreSQL para la persistencia de datos, NGINX como servidor web, y está completamente dockerizada con servicios de monitoreo usando Prometheus y Grafana. Incluye funcionalidades como sistema de usuarios, chat en tiempo real, torneos, estadísticas y un juego Pong completamente funcional.

### Objetivos del Proyecto

- **Full-Stack Development**: Desarrollo completo frontend y backend
- **Web Technologies**: Dominio de tecnologías web modernas
- **Database Design**: Diseño e implementación de bases de datos relacionales
- **DevOps Practices**: Containerización y orquestación de servicios
- **Real-time Communication**: Implementación de WebSockets y chat en vivo
- **User Experience**: Interfaz de usuario moderna y responsive
- **Security**: Implementación de autenticación y autorización segura

## 🏗️ Arquitectura del Sistema

```
                    ┌─────────────────────────────────────┐
                    │          Load Balancer              │
                    │           (NGINX)                   │
                    │        Port 80/443                  │
                    └─────────────────┬───────────────────┘
                                      │
                    ┌─────────────────▼───────────────────┐
                    │        Django Application           │
                    │         (Gunicorn)                  │
                    │       Port 8000 (Internal)          │
                    └─────────────────┬───────────────────┘
                                      │
            ┌─────────────────────────┼─────────────────────────┐
            │                         │                         │
    ┌───────▼────────┐    ┌──────────▼──────────┐    ┌───────▼────────┐
    │   PostgreSQL   │    │     WebSocket       │    │     Redis      │
    │   Database     │    │      Server         │    │     Cache      │
    │   Port 5432    │    │   (Real-time Chat)  │    │   Port 6379    │
    └────────────────┘    └─────────────────────┘    └────────────────┘

                    ┌─────────────────────────────────────┐
                    │         Monitoring Stack            │
                    ├─────────────────┬───────────────────┤
                    │   Prometheus    │     Grafana       │
                    │   Port 9090     │    Port 3000      │
                    │  (Metrics)      │  (Dashboards)     │
                    └─────────────────┴───────────────────┘

                    ┌─────────────────────────────────────┐
                    │          Game Engine               │
                    │                                     │
                    │  Canvas  │  Physics │  Multiplayer │
                    │   2D     │  Engine  │   Support    │
                    │ Graphics │  (JS)    │ (WebSocket)  │
                    └─────────────────────────────────────┘
```

## 🚀 Características Principales

### 🌟 Funcionalidades Core
- **Juego Pong**: Implementación completa del clásico juego con gráficos modernos
- **Sistema de Usuarios**: Registro, autenticación y gestión de perfiles
- **Chat en Tiempo Real**: Sistema de mensajería instantánea con WebSockets
- **Sistema de Torneos**: Organización y gestión de competiciones
- **Estadísticas de Juego**: Tracking completo de partidas y rendimiento
- **Clasificaciones**: Leaderboards y rankings de jugadores
- **Responsive Design**: Interfaz adaptable a todos los dispositivos

### 🎮 Motor de Juego Pong
- **Gráficos 2D**: Renderizado suave con HTML5 Canvas
- **Physics Engine**: Motor de física realista para movimiento de pelota
- **Multiplayer Online**: Partidas en tiempo real entre jugadores
- **AI Opponent**: Oponente inteligente para modo single-player
- **Customización**: Personalización de paletas, velocidad y efectos
- **Power-ups**: Elementos especiales que modifican el gameplay
- **Replay System**: Sistema de reproducción de partidas

### 🔧 Gestión de Usuarios
- **Autenticación Segura**: Sistema de login/register con hash de contraseñas
- **Perfiles de Usuario**: Información detallada y personalizable
- **Avatar System**: Subida y gestión de imágenes de perfil
- **Friends System**: Sistema de amigos y conexiones sociales
- **Privacy Settings**: Configuración de privacidad y visibilidad
- **Account Management**: Gestión completa de cuenta de usuario
- **OAuth Integration**: Integración con proveedores externos (opcional)

### 💬 Sistema de Chat
- **Real-time Messaging**: Mensajería instantánea con WebSockets
- **Multiple Channels**: Canales públicos y privados
- **Direct Messages**: Mensajes privados entre usuarios
- **Chat Moderation**: Herramientas de moderación y administración
- **Message History**: Historial persistente de conversaciones
- **Emoji Support**: Soporte completo para emojis y emoticons
- **File Sharing**: Compartir archivos e imágenes en chat

### 🏆 Sistema de Torneos
- **Tournament Creation**: Creación y configuración de torneos
- **Bracket Management**: Gestión automática de eliminatorias
- **Scheduling**: Programación de partidas y horarios
- **Live Scoring**: Puntuación en tiempo real
- **Tournament History**: Historial completo de competiciones
- **Prize System**: Sistema de premios y reconocimientos
- **Spectator Mode**: Modo espectador para seguir partidas

### 📊 Analytics y Estadísticas
- **Game Statistics**: Estadísticas detalladas de partidas
- **Performance Metrics**: Métricas de rendimiento y progreso
- **Historical Data**: Datos históricos y tendencias
- **Custom Reports**: Reportes personalizables
- **Data Visualization**: Gráficos y visualizaciones interactivas
- **Export Functionality**: Exportación de datos en múltiples formatos

### 🛡️ Características de Seguridad
- **Secure Authentication**: Autenticación segura con tokens JWT
- **Password Hashing**: Hash seguro de contraseñas con bcrypt
- **Input Validation**: Validación estricta de todas las entradas
- **SQL Injection Protection**: Protección contra inyección SQL
- **XSS Prevention**: Prevención de Cross-Site Scripting
- **CSRF Protection**: Protección contra Cross-Site Request Forgery
- **Rate Limiting**: Limitación de velocidad para prevenir abuso

### 📈 Monitoreo y Observabilidad
- **Prometheus Metrics**: Recolección de métricas del sistema
- **Grafana Dashboards**: Dashboards visuales para monitoreo
- **Application Monitoring**: Monitoreo de rendimiento de aplicación
- **Error Tracking**: Seguimiento y análisis de errores
- **Performance Metrics**: Métricas de rendimiento en tiempo real
- **Custom Alerts**: Alertas personalizables para eventos críticos
- **Log Aggregation**: Agregación y análisis de logs

## 🛠️ Instalación y Despliegue

### Requisitos Previos

```bash
# Instalación de Docker y Docker Compose
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install docker.io docker-compose

# CentOS/RHEL
sudo yum install docker docker-compose

# macOS
brew install docker docker-compose

# Verificar instalación
docker --version
docker-compose --version
```

### Configuración del Entorno

```bash
# Clonar el repositorio
git clone https://github.com/rdelicado/ft_transcendence.git
cd ft_transcendence

# Configurar variables de entorno
cp .env.example .env
nano .env  # Editar con tus configuraciones
```

### Variables de Entorno Principales

```bash
# Database Configuration
POSTGRES_DB=transcendence_db
POSTGRES_USER=transcendence_user
POSTGRES_PASSWORD=secure_password
POSTGRES_HOST=postgre
POSTGRES_PORT=5432

# Django Configuration
DJANGO_SECRET_KEY=your_super_secret_key_here
DJANGO_DEBUG=False
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1,your-domain.com

# Redis Configuration
REDIS_HOST=redis
REDIS_PORT=6379
REDIS_PASSWORD=redis_password

# Email Configuration (opcional)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your_email@gmail.com
EMAIL_HOST_PASSWORD=your_app_password

# Monitoring Configuration
PROMETHEUS_PORT=9090
GRAFANA_PORT=3000
GRAFANA_ADMIN_PASSWORD=admin_password

# Storage Paths
HOST_STATIC_PATH=/home/user/transcendence/static
HOST_BACKEND_PATH=/home/user/transcendence/backend
HOST_DATABASE_PATH=/home/user/transcendence/database
HOST_PROMETHEUS_DATA_PATH=/home/user/transcendence/prometheus
HOST_GRAFANA_DATA_PATH=/home/user/transcendence/grafana
```

### Despliegue con Docker

```bash
# Despliegue completo
make all

# O manualmente
docker-compose up --build -d

# Verificar servicios
docker-compose ps

# Ver logs
docker-compose logs -f
```

### Configuración Inicial de la Base de Datos

```bash
# Acceder al contenedor Django
docker-compose exec gunicorn bash

# Ejecutar migraciones
python manage.py migrate

# Crear superusuario
python manage.py createsuperuser

# Cargar datos iniciales (opcional)
python manage.py loaddata initial_data.json

# Recopilar archivos estáticos
python manage.py collectstatic --noinput
```

## 🚀 Uso de la Aplicación

### Acceso a la Aplicación

```bash
# Aplicación principal
http://localhost:80

# Panel de administración Django
http://localhost:80/admin

# Monitoreo Prometheus
http://localhost:9090

# Dashboards Grafana
http://localhost:3000
```

### Creación de Usuario

1. **Registro**: Acceder a `/register` y crear una cuenta nueva
2. **Verificación**: Confirmar email si está configurado
3. **Perfil**: Completar información del perfil
4. **Avatar**: Subir imagen de perfil

### Jugar Pong

```javascript
// Controles del juego
// Jugador 1:
W - Mover paleta arriba
S - Mover paleta abajo

// Jugador 2:
↑ - Mover paleta arriba
↓ - Mover paleta abajo

// Controles adicionales:
SPACE - Pausar/Reanudar
ESC - Menú de pausa
R - Reiniciar partida
```

### Sistema de Chat

1. **Canales Públicos**: Unirse a canales de la comunidad
2. **Mensajes Privados**: Enviar mensajes directos a otros usuarios
3. **Crear Canales**: Crear canales temáticos personalizados
4. **Moderación**: Herramientas de moderación para administradores

### Torneos

1. **Crear Torneo**: Configurar nuevo torneo con parámetros
2. **Inscripción**: Los jugadores se inscriben en torneos activos
3. **Bracket**: Visualizar y seguir la estructura del torneo
4. **Partidas**: Jugar partidas programadas del torneo

## 📁 Estructura del Proyecto

```
ft_transcendence/
├── Makefile                              # Automatización de despliegue
├── docker-compose.yml                    # Orquestación de servicios
├── .env                                  # Variables de entorno
├── README.md                             # Documentación
├── srcs/                                 # Código fuente
│   └── requeriments/                     # Contenedores y servicios
│       ├── nginx/                        # Servidor web
│       │   ├── Dockerfile               # Imagen NGINX
│       │   ├── conf/                    # Configuraciones NGINX
│       │   └── ssl/                     # Certificados SSL
│       ├── gunicorn/                     # Servidor de aplicación
│       │   ├── Dockerfile               # Imagen Django/Gunicorn
│       │   ├── tools/                   # Scripts de inicialización
│       │   └── proyect/                 # Aplicación Django
│       │       ├── manage.py            # Django management
│       │       ├── trascendence/        # Configuración principal
│       │       │   ├── settings.py     # Configuración Django
│       │       │   ├── urls.py          # URL routing
│       │       │   ├── wsgi.py          # WSGI configuration
│       │       │   └── asgi.py          # ASGI configuration
│       │       ├── userManagement/      # Gestión de usuarios
│       │       │   ├── models.py        # Modelos de usuario
│       │       │   ├── views.py         # Vistas de usuario
│       │       │   ├── urls.py          # URLs de usuario
│       │       │   └── forms.py         # Formularios
│       │       ├── pong/                # Aplicación del juego
│       │       │   ├── models.py        # Modelos del juego
│       │       │   ├── views.py         # Lógica del juego
│       │       │   ├── consumers.py     # WebSocket consumers
│       │       │   ├── routing.py       # WebSocket routing
│       │       │   └── static/          # Assets del juego
│       │       │       ├── js/          # JavaScript del juego
│       │       │       ├── css/         # Estilos del juego
│       │       │       └── images/      # Recursos gráficos
│       │       ├── chat/                # Sistema de chat
│       │       │   ├── models.py        # Modelos de chat
│       │       │   ├── views.py         # Vistas de chat
│       │       │   ├── consumers.py     # WebSocket chat
│       │       │   └── routing.py       # Chat routing
│       │       ├── home/                # Página principal
│       │       │   ├── views.py         # Vistas principales
│       │       │   ├── urls.py          # URLs principales
│       │       │   └── templates/       # Templates HTML
│       │       └── templates/           # Templates globales
│       │           ├── base.html        # Template base
│       │           ├── login.html       # Página de login
│       │           ├── register.html    # Página de registro
│       │           ├── game.html        # Interfaz del juego
│       │           ├── chat.html        # Interfaz de chat
│       │           └── tournament.html  # Interfaz de torneos
│       ├── postgre/                      # Base de datos
│       │   ├── Dockerfile               # Imagen PostgreSQL
│       │   ├── init/                    # Scripts de inicialización
│       │   └── conf/                    # Configuración PostgreSQL
│       └── monitoring/                   # Stack de monitoreo
│           ├── prometheus/              # Configuración Prometheus
│           │   ├── Dockerfile           # Imagen Prometheus
│           │   └── prometheus.yml       # Configuración de métricas
│           └── grafana/                 # Configuración Grafana
│               ├── Dockerfile           # Imagen Grafana
│               ├── dashboards/          # Dashboards predefinidos
│               └── provisioning/        # Configuración automática
└── volumes/                             # Datos persistentes
    ├── database/                        # Datos PostgreSQL
    ├── static/                          # Archivos estáticos
    ├── media/                           # Archivos multimedia
    ├── prometheus/                      # Datos Prometheus
    └── grafana/                         # Datos Grafana
```

## 🔧 Desarrollo y Personalización

### Estructura de la Aplicación Django

**Models (Modelos)**:
```python
# userManagement/models.py
class CustomUser(AbstractUser):
    avatar = models.ImageField(upload_to='avatars/')
    wins = models.IntegerField(default=0)
    losses = models.IntegerField(default=0)
    total_points = models.IntegerField(default=0)
    created_at = models.DateTimeField(auto_now_add=True)

# pong/models.py
class Game(models.Model):
    player1 = models.ForeignKey(User, on_delete=CASCADE, related_name='games_as_p1')
    player2 = models.ForeignKey(User, on_delete=CASCADE, related_name='games_as_p2')
    score_p1 = models.IntegerField(default=0)
    score_p2 = models.IntegerField(default=0)
    winner = models.ForeignKey(User, on_delete=CASCADE, null=True)
    duration = models.DurationField()
    created_at = models.DateTimeField(auto_now_add=True)

class Tournament(models.Model):
    name = models.CharField(max_length=100)
    creator = models.ForeignKey(User, on_delete=CASCADE)
    participants = models.ManyToManyField(User, related_name='tournaments')
    max_participants = models.IntegerField(default=8)
    status = models.CharField(max_length=20, default='open')
    created_at = models.DateTimeField(auto_now_add=True)
```

**Views (Vistas)**:
```python
# pong/views.py
class GameView(View):
    def get(self, request):
        # Renderizar interfaz del juego
        return render(request, 'game.html')
    
    def post(self, request):
        # Procesar resultado del juego
        game_data = json.loads(request.body)
        game = Game.objects.create(
            player1=request.user,
            player2=User.objects.get(id=game_data['opponent_id']),
            score_p1=game_data['score_p1'],
            score_p2=game_data['score_p2']
        )
        return JsonResponse({'status': 'success'})

class TournamentView(View):
    def get(self, request):
        tournaments = Tournament.objects.filter(status='open')
        return render(request, 'tournament.html', {'tournaments': tournaments})
```

**WebSocket Consumers**:
```python
# pong/consumers.py
class GameConsumer(AsyncWebsocketConsumer):
    async def connect(self):
        self.room_name = self.scope['url_route']['kwargs']['room_name']
        self.room_group_name = f'game_{self.room_name}'
        
        await self.channel_layer.group_add(
            self.room_group_name,
            self.channel_name
        )
        await self.accept()
    
    async def receive(self, text_data):
        text_data_json = json.loads(text_data)
        message_type = text_data_json['type']
        
        if message_type == 'paddle_move':
            # Manejar movimiento de paleta
            await self.channel_layer.group_send(
                self.room_group_name,
                {
                    'type': 'paddle_update',
                    'player': text_data_json['player'],
                    'position': text_data_json['position']
                }
            )
```

### Motor de Juego JavaScript

```javascript
// static/js/pong.js
class PongGame {
    constructor(canvas) {
        this.canvas = canvas;
        this.ctx = canvas.getContext('2d');
        this.ball = new Ball(canvas.width/2, canvas.height/2);
        this.paddle1 = new Paddle(10, canvas.height/2);
        this.paddle2 = new Paddle(canvas.width-20, canvas.height/2);
        this.score = {p1: 0, p2: 0};
        this.websocket = null;
    }
    
    initWebSocket(roomName) {
        this.websocket = new WebSocket(
            `ws://${window.location.host}/ws/game/${roomName}/`
        );
        
        this.websocket.onmessage = (event) => {
            const data = JSON.parse(event.data);
            this.handleWebSocketMessage(data);
        };
    }
    
    update() {
        this.ball.update();
        this.checkCollisions();
        this.checkScore();
        this.render();
    }
    
    checkCollisions() {
        // Colisión con paletas
        if (this.ball.x <= this.paddle1.x + this.paddle1.width &&
            this.ball.y >= this.paddle1.y &&
            this.ball.y <= this.paddle1.y + this.paddle1.height) {
            this.ball.velocityX = -this.ball.velocityX;
        }
        
        // Colisión con paredes
        if (this.ball.y <= 0 || this.ball.y >= this.canvas.height) {
            this.ball.velocityY = -this.ball.velocityY;
        }
    }
    
    render() {
        // Limpiar canvas
        this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
        
        // Dibujar elementos
        this.ball.draw(this.ctx);
        this.paddle1.draw(this.ctx);
        this.paddle2.draw(this.ctx);
        this.drawScore();
    }
}

class Ball {
    constructor(x, y) {
        this.x = x;
        this.y = y;
        this.radius = 10;
        this.velocityX = 5;
        this.velocityY = 3;
    }
    
    update() {
        this.x += this.velocityX;
        this.y += this.velocityY;
    }
    
    draw(ctx) {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
        ctx.fillStyle = '#fff';
        ctx.fill();
        ctx.closePath();
    }
}
```

### Configuración de WebSockets

```python
# trascendence/routing.py
from django.urls import path
from channels.routing import ProtocolTypeRouter, URLRouter
from channels.auth import AuthMiddlewareStack
from pong.routing import websocket_urlpatterns as pong_ws
from chat.routing import websocket_urlpatterns as chat_ws

application = ProtocolTypeRouter({
    'websocket': AuthMiddlewareStack(
        URLRouter(
            pong_ws + chat_ws
        )
    ),
})

# pong/routing.py
from django.urls import path
from . import consumers

websocket_urlpatterns = [
    path('ws/game/<str:room_name>/', consumers.GameConsumer.as_asgi()),
]
```

## 🧪 Testing y Desarrollo

### Testing Local

```bash
# Ejecutar tests unitarios
docker-compose exec gunicorn python manage.py test

# Ejecutar tests específicos
docker-compose exec gunicorn python manage.py test pong.tests
docker-compose exec gunicorn python manage.py test userManagement.tests

# Coverage de tests
docker-compose exec gunicorn coverage run manage.py test
docker-compose exec gunicorn coverage report
```

### Debugging

```bash
# Acceder al shell de Django
docker-compose exec gunicorn python manage.py shell

# Ver logs en tiempo real
docker-compose logs -f gunicorn
docker-compose logs -f nginx
docker-compose logs -f postgre

# Debugging con breakpoints
docker-compose exec gunicorn python manage.py runserver 0.0.0.0:8000
```

### Development Mode

```bash
# Configurar para desarrollo
export DJANGO_DEBUG=True
export DJANGO_SETTINGS_MODULE=trascendence.settings.development

# Ejecutar servidor de desarrollo
docker-compose exec gunicorn python manage.py runserver 0.0.0.0:8000

# Hot reload para cambios en frontend
npm run watch  # Si tienes configurado webpack
```

## 📊 Monitoreo y Métricas

### Dashboards de Grafana

**Dashboard Principal**:
- Usuarios activos
- Partidas por hora
- Tiempo de respuesta promedio
- Uso de recursos del sistema

**Dashboard de Juego**:
- Partidas totales
- Duración promedio de partidas
- Jugadores más activos
- Estadísticas de torneos

**Dashboard de Sistema**:
- CPU y memoria usage
- Conexiones de base de datos
- Throughput de requests
- Errores por minuto

### Métricas de Prometheus

```yaml
# prometheus.yml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'django'
    static_configs:
      - targets: ['gunicorn:8000']
    metrics_path: '/metrics'
  
  - job_name: 'nginx'
    static_configs:
      - targets: ['nginx:80']
  
  - job_name: 'postgres'
    static_configs:
      - targets: ['postgre:5432']
```

## 🚨 Resolución de Problemas

### Problemas Comunes

**Error de conexión a base de datos**:
```bash
# Verificar estado de PostgreSQL
docker-compose logs postgre

# Reiniciar base de datos
docker-compose restart postgre

# Ejecutar migraciones manualmente
docker-compose exec gunicorn python manage.py migrate
```

**Problemas de WebSocket**:
```bash
# Verificar configuración de channels
docker-compose exec gunicorn python manage.py check

# Reiniciar Redis
docker-compose restart redis

# Verificar logs de WebSocket
docker-compose logs -f gunicorn | grep websocket
```

**Problemas de archivos estáticos**:
```bash
# Recolectar archivos estáticos
docker-compose exec gunicorn python manage.py collectstatic --clear

# Verificar configuración NGINX
docker-compose exec nginx nginx -t

# Reiniciar NGINX
docker-compose restart nginx
```

### Optimización de Rendimiento

```bash
# Optimizar base de datos
docker-compose exec postgre psql -U transcendence_user -d transcendence_db
VACUUM ANALYZE;

# Limpiar cache de Redis
docker-compose exec redis redis-cli FLUSHALL

# Optimizar imágenes
docker-compose exec gunicorn python manage.py optimize_images
```

## 📈 Características Avanzadas

### Integración con APIs Externas

**OAuth Authentication**:
```python
# settings.py
AUTHENTICATION_BACKENDS = [
    'social_core.backends.github.GithubOAuth2',
    'social_core.backends.google.GoogleOAuth2',
    'django.contrib.auth.backends.ModelBackend',
]

SOCIAL_AUTH_GITHUB_KEY = 'your_github_key'
SOCIAL_AUTH_GITHUB_SECRET = 'your_github_secret'
```

**Machine Learning Integration**:
```python
# AI opponent implementation
class AIPlayer:
    def __init__(self, difficulty='medium'):
        self.model = load_model(f'ai_models/{difficulty}_player.h5')
        
    def predict_move(self, game_state):
        prediction = self.model.predict(game_state)
        return prediction
```

### Escalabilidad

**Load Balancing**:
```nginx
# nginx.conf
upstream django_backend {
    server gunicorn1:8000;
    server gunicorn2:8000;
    server gunicorn3:8000;
}

server {
    location / {
        proxy_pass http://django_backend;
    }
}
```

**Database Sharding**:
```python
# settings.py
DATABASES = {
    'default': {},
    'users': {
        'NAME': 'transcendence_users',
    },
    'games': {
        'NAME': 'transcendence_games',
    }
}

DATABASE_ROUTERS = ['myapp.routers.DatabaseRouter']
```

## 👨‍💻 Autores

**Equipo de Desarrollo:**
- **Rubén Delicado** - [@rdelicado](https://github.com/rdelicado)
  - 📧 rdelicad@student.42malaga.com
  - 🏫 42 Málaga
  - 🎮 Arquitectura del sistema y motor del juego

**Áreas de Especialización:**
- **Backend Development**: Django, PostgreSQL, APIs REST
- **Frontend Development**: JavaScript, HTML5 Canvas, CSS3
- **DevOps**: Docker, NGINX, monitoreo y despliegue
- **Real-time Features**: WebSockets, chat en vivo, multiplayer

## 📜 Licencia

Este proyecto es parte del currículo de 42 School y sigue las pautas académicas. El código está disponible para fines educativos y demuestra habilidades avanzadas en desarrollo web full-stack, arquitectura de sistemas y tecnologías modernas.

## 🔗 Recursos y Referencias

### Desarrollo Web
- [Django Documentation](https://docs.djangoproject.com/)
- [Django Channels](https://channels.readthedocs.io/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [NGINX Configuration](https://nginx.org/en/docs/)

### Game Development
- [HTML5 Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [WebSocket API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
- [Game Programming Patterns](https://gameprogrammingpatterns.com/)
- [Real-time Multiplayer Games](https://gafferongames.com/)

### DevOps y Monitoreo
- [Docker Documentation](https://docs.docker.com/)
- [Prometheus Monitoring](https://prometheus.io/docs/)
- [Grafana Dashboards](https://grafana.com/docs/)
- [NGINX Load Balancing](https://docs.nginx.com/nginx/admin-guide/load-balancer/)

### 42 School Resources
- [42 School Curriculum](https://42.fr/en/the-program/software-engineer-degree/)
- [Web Development Track](https://github.com/42School)
- [Full-Stack Development](https://stackoverflow.com/questions/tagged/django+websocket)

## 🚀 Extensiones Futuras

### Características Planeadas
- [ ] **Mobile App**: Aplicación móvil nativa con React Native
- [ ] **AI Opponents**: Múltiples niveles de inteligencia artificial
- [ ] **VR Support**: Soporte para realidad virtual
- [ ] **Blockchain Integration**: NFTs y sistema de recompensas
- [ ] **Streaming**: Integración con plataformas de streaming
- [ ] **Machine Learning**: Análisis predictivo de partidas

### Mejoras Técnicas
- [ ] **Microservices**: Migración a arquitectura de microservicios
- [ ] **GraphQL API**: API GraphQL para mejor flexibilidad
- [ ] **Kubernetes**: Orquestación con Kubernetes
- [ ] **CDN Integration**: Red de distribución de contenido
- [ ] **Advanced Analytics**: Analytics avanzados con BigQuery
- [ ] **Multi-region**: Despliegue multi-región

### Características de Juego
- [ ] **New Game Modes**: Modos de juego adicionales
- [ ] **3D Graphics**: Upgrade a gráficos 3D
- [ ] **Power-ups System**: Sistema expandido de power-ups
- [ ] **Team Tournaments**: Torneos por equipos
- [ ] **Seasonal Events**: Eventos estacionales especiales
- [ ] **Custom Maps**: Editor de mapas personalizado

---

<div align="center">

*"En el mundo del desarrollo web, crear experiencias interactivas en tiempo real representa la convergencia perfecta entre tecnología, creatividad y experiencia de usuario."*

**ft_transcendence** demuestra que la integración de múltiples tecnologías modernas puede crear plataformas robustas y escalables que combinan entretenimiento, competición social y excelencia técnica en un ecosistema digital completo.

</div>