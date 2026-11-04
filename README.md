# Lurxork's-Garden
Repositorio del juego "Lurxork's Garden", un juego arcade, 2D Pixel Art con sesiones de juego cortas y repetitivas para alcanzar el puntaje mas alto

## 1. Información General del Proyecto

- **Título del Proyecto:** Lurxork's Garden
- **Versión actual:** v1.0.2
- **Desarrollador:** Francisco Aumada
- **Plataforma Objetivo:** Android
- **Resumen del Alcance:** Juego arcade 2D desarrollado integramente en **Godot Engine 4.6** Utilizando **GDScript (100%)**. El proyecto abarca la lógica del personaje principal (**Player**), comportamiento de distintos tipos de enemigos (**Mob**, **FlyMob**), la interfaz táctil de usuario (**HUD**), la gestión de recursos multimedia (**Assets**), y la persistencia local de puntuaciones máximas, aunque (todavia) no se muestre esa puntuación en el juego final.

---

## 2. Documentación Técnica y Arquitectura

### 2.1 Descripción de Arquitectura
- **Motor y Lenguaje:** Godot Engine 4.6 (GDScript 100%)
- **Estructura Modular de Escenas y Directorios:**
    - `Main/`: Escena principal. Administra el ciclo de vida del juego, los temporizadores de creacion (instancias) de enemigos y el flujo general de la partida.
    - `Player/`: Controlador del jugador, procesamiento de entradas táctiles y detección de colisiones (`Area2D`).
    - `Mob/` y `FlyMob/`: Escenas de distintos enemigos con mismo comportamiento, cambiando solo la velocidad, y con temporizadores de liberación de memoria (`VisibleOnScreenNotifier2D`).
    - `HUD/`: Capa de interfaz gráfica (Display de puntaje actual, pantalla de inicio, botón de inicio y Game Over adaptado a pantallas móviles).
    - `Assets/`: Recursos gráficos (sprites, texturas) y fuentes (.ttf).
- **Persistencia de Datos Local:** Guardado de la mejor puntuación de forma offline en el almacenamiento interno del dispositivo (`user://highscore.save`).

### 2.2 Especificación de APIs / Endpoints 
- **Estado:** No Aplica (Juego 100% Offline).
- **Explicación:** La aplicación opera de manera autónoma en el dispositivo móvil sin requerir servidores externos, APIs REST ni bases de datos en la nube.

### 2.3 Modelo de Datos Local
- **Esquema de Almacenamiento Local (`user_//highscore.save`):**
  ```json
  {
  "player_name": "Jugador",
  "High_score": 2450,
  "last_updated: "2026-11-04T13:00:00"
  }
