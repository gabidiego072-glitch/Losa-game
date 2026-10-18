# Plaza Llanera — shooter en Xirivella

Shooter en primera persona hecho con Three.js que recrea la **Plaza Marqués Llanera** (Xirivella, Valencia):
la pista de fútbol sala "La Losa" (con valla solo en el lado de Carrer les Oliveres y canastas), el parque de pinos
con la zona infantil y la mesa de ping-pong, la explanada de cemento y la fachada con bares (Bar Las Morenas),
los coches aparcados y las naves industriales de **Carrer les Oliveres**, **Carrer les Moreres** y **Carrer els Garrofers**.

## Cómo jugar

Abre `index.html` en un navegador de escritorio (Chrome, Edge o Firefox). Necesita internet para cargar Three.js.

Para servirlo en local:

```bash
python3 -m http.server 8000
# y abre http://localhost:8000
```

| Tecla | Acción |
|---|---|
| W A S D | Moverse |
| Ratón | Apuntar · clic izq. disparar · clic der. mirilla |
| Shift | Correr |
| Espacio | Saltar (puedes subirte a los coches) |
| C / Ctrl | Agacharse |
| R | Recargar |
| Esc | Pausa |

Sobrevive a oleadas de enemigos cada vez más numerosos y precisos. Usa los coches, los troncos y
los edificios como cobertura. Los enemigos dejan botiquines y munición al caer.

## Detalles técnicos

- Un único archivo `index.html`, sin dependencias que instalar (Three.js 0.160 desde unpkg).
- Texturas generadas por código (asfalto, baldosas rojas y beige, tierra, fachadas con persianas verdes, nave industrial).
- Enemigos con búsqueda de caminos (A* sobre una rejilla), línea de visión, ráfagas y precisión que depende de la distancia, de si te mueves y de si estás agachado.
- Los disparos del jugador tienen dispersión, retroceso, daño extra a la cabeza y marcas de impacto.
