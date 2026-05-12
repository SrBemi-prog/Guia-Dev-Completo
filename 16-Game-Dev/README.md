# 16 — Desarrollo de Videojuegos

> Una de las áreas más creativas de programar. Difícil, pero divertida.

## 🎮 Motores principales (engines)

| Engine | Lenguaje | Mejor para | Precio |
|--------|----------|-----------|--------|
| **Unity** ⭐ | C# | 2D/3D, móvil, indie | Gratis hasta $200k rev |
| **Unreal Engine 5** | C++ / Blueprints | AAA, gráficos hermosos | 5% royalty post $1M |
| **Godot** ⭐ | GDScript / C# | Indie, open source | 100% gratis |
| **GameMaker** | GML | 2D rápido | Gratis para hobby |
| **Bevy** | Rust | Indie técnico moderno | Open source |
| **PixiJS / Phaser** | JS/TS | Juegos web 2D | Gratis |
| **Three.js / R3F** | JS/TS | 3D web | Gratis |

> **Para empezar:** **Godot** (gratis, lenguaje fácil) o **Unity** (más recursos).

---

## 🟦 Unity (el más usado en la industria)

### Recursos
- 📺 [Unity desde cero - Spanish School of Coding](https://www.youtube.com/watch?v=fLi6tnsPDw0)
- 📺 [Brackeys (clásico, inglés)](https://www.youtube.com/@Brackeys)
- 📖 [Unity Learn](https://learn.unity.com/) — cursos gratis oficiales
- 📺 [Code Monkey](https://www.youtube.com/@CodeMonkeyUnity)

### Stack
- **C#** como lenguaje
- **Visual Scripting** si no querés código
- **DOTS** para juegos masivos

---

## 🟢 Godot 4 (open source, hot)

### Recursos
- 📺 [Godot Tutorial - HEARTBEAST](https://www.youtube.com/@uheartbeast)
- 📺 [GDQuest (gratis y excelente)](https://www.youtube.com/@Gdquest)
- 📖 [docs.godotengine.org](https://docs.godotengine.org/)

```gdscript
extends Sprite2D

func _process(delta):
    position.x += 100 * delta
```

---

## 🟣 Unreal Engine 5

### Recursos
- 📺 [Unreal Sensei (inglés)](https://www.youtube.com/@UnrealSensei)
- 📖 [docs.unrealengine.com](https://docs.unrealengine.com/5.0/en-US/)
- 📺 [Curso UE5 español - Crowders](https://www.youtube.com/@crowders)

**Pros:** gráficos brutales, Blueprints (visual), Lumen, Nanite.
**Contras:** pesado, curva alta.

---

## 🌐 Juegos web (sin engine pesado)

### Phaser.js
```javascript
const game = new Phaser.Game({
  width: 800, height: 600,
  scene: { create, update }
});
```

### Three.js + React Three Fiber
Para 3D en navegador.
- 📖 [threejs.org/manual](https://threejs.org/manual/)
- 📖 [docs.pmnd.rs](https://docs.pmnd.rs/react-three-fiber)

---

## 🧠 Lo que tenés que aprender (más allá del engine)

- **Game loop** — update + render cada frame
- **Física** — colisiones, gravedad
- **Animaciones** — sprites, esqueletales
- **Estados** — state machines (menú, jugando, pausa)
- **Audio** — música + efectos
- **AI** — pathfinding (A*), behavior trees
- **Networking** — multijugador (lo más difícil)
- **Optimización** — FPS, memoria

---

## 🎨 Assets gratis

- **OpenGameArt** — sprites, sonidos
- **Kenney.nl** — assets gratis premium
- **itch.io** — assets indies
- **Mixamo** — animaciones humanoides
- **Freesound** — sonidos CC0

---

## 🏪 Cómo publicar tu juego

| Plataforma | Para qué |
|------------|---------|
| **itch.io** | Indie, sin gatekeeping |
| **Steam** | PC, $100 USD por juego |
| **App Store / Play Store** | Móvil |
| **GameJolt** | Indie, gratis |
| **Newgrounds / Kongregate** | Juegos web |

---

## 🏆 Game Jams (la mejor forma de aprender)

Hacer un juego en 48-72 hs con un tema.

- **Ludum Dare** — el clásico
- **Global Game Jam** — presencial mundial
- **itch.io Jams** — siempre hay varias
- **GMTK Game Jam** — el de Mark Brown

---

## 🎯 Proyectos para empezar

1. **Pong** — el "hello world" del game dev
2. **Snake** — clásico, enseña grids
3. **Tetris** — enseña rotaciones, lógica
4. **Plataformero 2D** — Mario simplificado
5. **Top-down shooter** — estilo Asteroids
6. **Runner infinito** — generación procedural
7. **Tower defense** — IA básica
8. **Roguelike** — el meme del género

---

## 🧑‍🎓 Carrera en game dev

- **Indie:** hacés juego solo o equipo chico, vivís de Steam/itch
- **AAA:** programador en estudios grandes (Ubisoft, EA, etc.)
- **Mobile:** estudios de hipercasuales (Voodoo, Supercell)
- **Tech:** engine programmer, graphics programmer (los mejor pagos)

> **Realidad:** vivir de hacer juegos es difícil. Muchos lo hacen como hobby pagado + un trabajo "normal" en software.
