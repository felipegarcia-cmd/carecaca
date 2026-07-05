# Carecaca 🃏

El clásico juego de cartas chileno, jugable en el navegador — pensado para el celular.
**Tú contra 3 rivales con IA**, cada uno con su propia personalidad y nivel de dificultad.

**▶ Jugar:** abre `index.html` en cualquier navegador, o visita la versión publicada en GitHub Pages.

## Cómo se juega

- Objetivo: ser el primero en quedarse sin cartas. El último con cartas es el **Carecaca** 💩.
- Juegas primero desde tu **mano** (se repone a 3 mientras haya mazo), luego tu **mesa abierta** (3 cartas boca arriba) y al final tu **mesa ciega** (3 boca abajo, a la suerte).
- En tu turno juega una carta **igual o mayor** a la del pozo. Si no puedes, te llevas todo el pozo.

### Cartas especiales

| Carta | Efecto |
|-------|--------|
| **2** | Pozo libre: el siguiente juega lo que quiera |
| **7** | El siguiente debe jugar menor a 7 (o un 7) |
| **8** | Salta al siguiente jugador (varios 8 saltan a varios) |
| **10** | Quema el pozo y vuelves a jugar |
| **J** | Invierte el sentido del juego |
| **Joker** | El siguiente se lleva el pozo (se puede encadenar con otro Joker) |

Además: **quema automática** con 4 cartas iguales seguidas, **elástico** (si tienes la carta idéntica a la recién jugada, puedes tirarla fuera de turno) y **enganche** (si robas una carta del mismo valor que acabas de jugar, puedes encadenarla).

## Tecnología

El juego vive en `index.html`: sin dependencias, sin build, sin backend.
Arte de cartas en SVG dibujado a mano, sonidos generados con Web Audio API.

- **Guardado automático**: la partida se guarda sola en tu navegador; si cierras o recargas, al volver aparece "Continuar partida".
- **Instalable (PWA)**: desde el menú del navegador puedes "Agregar a pantalla de inicio" y jugar sin conexión (`manifest.json` + `sw.js` + `icon.svg`).
- Menú "⋮" dentro de la partida para reiniciar o terminar en cualquier momento.
- **Música de fondo generativa**: un pad de acordes cálido compuesto en vivo con Web Audio (sin archivos de audio externos), con su propio botón de silencio independiente del de efectos.

## Publicar en GitHub Pages

1. Crea un repositorio y sube este proyecto (incluyendo `manifest.json`, `sw.js` e `icon.svg`).
2. En el repo: **Settings → Pages → Source: Deploy from a branch → `main` / root**.
3. En un minuto queda disponible en `https://<tu-usuario>.github.io/<repo>/`.
4. Si actualizas `index.html` más adelante, sube también la versión del caché en `sw.js` (`CACHE = 'carecaca-v2'`, etc.) para que los usuarios reciban los cambios.
