# Plaza Llanera — shooter en Xirivella

Shooter en primera persona hecho con Three.js que recrea la **Plaza Marqués Llanera** (Xirivella, Valencia):
la pista de fútbol sala "La Losa" (con valla solo en el lado de Carrer les Oliveres y canastas), el parque de pinos
con la zona infantil y la mesa de ping-pong, la explanada de cemento y la fachada con sus dos bares (Bar Restaurante Las Morenas y Bar Hermanas Penella),
los coches aparcados y las naves industriales de **Carrer les Oliveres**, **Carrer les Moreres** y **Carrer els Garrofers**.

## Cómo jugar

Sírvelo con un servidor web y ábrelo en un navegador de escritorio (Chrome, Edge o Firefox). Las texturas y el modelo 3D están en `assets/`, por eso abrir el archivo con doble clic no basta. Necesita internet para cargar Three.js.

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
| 1 – 5 / rueda | Cambiar arma |
| O | Invencibilidad (activar / desactivar) |
| F | Mostrar FPS y calidad |
| Esc | Pausa |

Sobrevive a oleadas de enemigos cada vez más numerosos y precisos. Usa los coches, los troncos y
los edificios como cobertura. Los enemigos dejan botiquines y munición al caer.

## Armas

| Tecla | Arma | Notas |
|---|---|---|
| 1 | Pistola 9 mm | Semiautomática, rápida de recargar |
| 2 | Subfusil MP5 | Mucha cadencia, poco daño por bala |
| 3 | Fusil de asalto | Equilibrado, mira holográfica |
| 4 | Escopeta | 9 perdigones, devastadora de cerca, recarga cartucho a cartucho |
| 5 | Francotirador | Mira telescópica (clic derecho), mata de un tiro a la cabeza |

## Recursos usados (todos libres)

- Cielo HDRI y texturas PBR (asfalto, hormigón, tierra, corteza, enlucido, caucho): [Poly Haven](https://polyhaven.com), licencia CC0.
- Soldado animado: modelo `Soldier.glb` de los ejemplos de [three.js](https://github.com/mrdoob/three.js).

## Detalles técnicos

- Rendimiento: los objetos estáticos se fusionan en pocas llamadas de dibujo, las sombras siguen al jugador, los disparos usan un BVH (three-mesh-bvh) y la resolución se ajusta sola para mantener unos 60 FPS. En el menú se puede elegir calidad Automática, Alta, Media o Baja.

- Un único archivo `index.html`, sin dependencias que instalar (Three.js 0.160 desde unpkg).
- Texturas fotográficas PBR con relieve (normal maps) y rugosidad; iluminación con un cielo HDRI real; los cristales y coches reflejan el cielo.
- Pinos piñoneros hechos con tarjetas de agujas, sombras suaves, bloom, viñeta y grano de película.
- Fachadas, rótulos y baldosas rojas y beige dibujados por código.
- Enemigos con búsqueda de caminos (A* sobre una rejilla), línea de visión, ráfagas y precisión que depende de la distancia, de si te mueves y de si estás agachado.
- Los disparos del jugador tienen dispersión, retroceso, daño extra a la cabeza y marcas de impacto.
