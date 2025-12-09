# Wallet Trainer

Wallet Trainer es una aplicación web desarrollada con Flask que permite gestionar usuarios, activar y desactivar un bot de trading conectado a Firebase, consultar historial de operaciones, visualizar estadísticas de rendimiento y generar reportes. El proyecto utiliza una arquitectura basada en ViewModels para mantener una separación clara entre lógica y presentación.

## Requisitos

* Python 3.10 o superior
* Firebase (Realtime Database y Storage) configurado
* Dependencias incluidas en `requirements.txt`

## Instalación

1. Instalar dependencias:

```bash
pip install -r requirements.txt
```

2. Verificar el archivo `firebase_config.json` con las credenciales correctas del proyecto Firebase.

3. Ejecutar la aplicación:

```bash
python app.py
```

4. Abrir en el navegador:

```
http://localhost:5000
```

## Arquitectura del Proyecto

```
PROYECTO-TRADING/
│
├── app.py                       # Aplicación principal Flask
├── firebase_config.json         # Configuración del proyecto Firebase
├── firebase_config.py           # Inicialización de Firebase
├── requirements.txt             # Dependencias
│
├── model/                       # Capa de datos y conexión con Firebase
│   └── user_model.py
│
├── viewmodels/                  # Lógica de presentación
│   ├── main_viewmodel.py
│   ├── login_viewmodel.py
│   ├── dashboard_viewmodel.py
│   ├── performance_viewmodel.py
│   ├── profile_viewmodel.py
│   ├── report_viewmodel.py
│   └── history_viewmodel.py
│
├── templates/                   # Plantillas HTML
│   ├── home.html
│   ├── login.html
│   ├── dashboard.html
│   ├── profile.html
│   ├── history.html
│   ├── performance.html
│   └── report.html
│
└── static/                      # Recursos estáticos
    ├── css/
    ├── js/
    └── img/
```

## Funcionalidades Principales

* Inicio de sesión autenticado mediante Firebase
* Dashboard con estado del bot y resumen del usuario
* Activación / desactivación del bot
* Historial de operaciones
* Visualización del rendimiento (performance)
* Generación de reportes en PDF
* Edición de perfil e imagen del usuario

## Rutas Principales

### Autenticación

* `GET /login`
* `POST /login`
* `GET /logout`

### Dashboard y Bot

* `GET /dashboard`
* `POST /bot/toggle`

### Historial y Rendimiento

* `GET /history`
* `GET /performance`

### Reportes

* `GET /report`

### Perfil

* `GET /profile`
* `POST /profile`

### Página inicial

* `GET /`

## Configuración

* La clave secreta de Flask se genera en `app.py`.
* Las credenciales y conexión con Firebase están en `firebase_config.py` y `firebase_config.json`.
* La lógica del proyecto está distribuida en ViewModels para mantener un orden limpio y escalable.
