# Plaza Llanera — shooter en Xirivella

Shooter en primera persona hecho con Three.js que recrea la **Plaza Marqués Llanera** (Xirivella, Valencia) con las medidas reales sacadas de OpenStreetMap y de la ortofoto del IGN:
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
| G | Lanzar granada de fragmentación |
| V | Lanzar granada cegadora (flash) |
| O | Invencibilidad (activar / desactivar) |
| F | Mostrar FPS y calidad |
| Esc | Pausa |

Empiezas con 2 granadas y 2 flashes; las cajas de munición y cada oleada superada dan una más de cada (máximo 4). A partir de la oleada 2 los enemigos también lanzan granadas si te escondes.

Sobrevive a oleadas de enemigos cada vez más numerosos y precisos. Usa los coches, los troncos y
los edificios como cobertura. Los enemigos dejan botiquines y munición al caer.

## Mapas

En el menú hay un selector de mapa:

- **Plaza Llanera**: la pista de fútbol La Losa, el parque y los bares de la fachada.
- **Parque del Avión** (Av. de la Constitució 22 / Pl. de la Comare Rosario Soler): los dos bloques de ladrillo, el parque infantil, los plátanos y la jacaranda, los aparcamientos de la avenida y el muro de las vías. Los dos bares de la planta baja se pueden visitar por dentro:
  - **Villa & Nueva** (grill y bar): barra de madera, botellero, grifos, parrilla de carbón con campana, tele con el fútbol y terraza con parasol grande.
  - **Tot per l'aire** (cervecería artesana): barra, seis grifos, depósitos de fermentación, pizarra con las cervezas, hélice en la pared y una avioneta colgada del techo, y terraza con cinco sombrillas.

  El trazado sale de OpenStreetMap y de la ortofoto PNOA. El interior y los letreros de los bares son una recreación: no había fotos de dentro.

## Dos jugadores (1 contra 1, táctico o cooperativo)

En la pantalla de inicio, en **DOS JUGADORES**:

1. Uno elige el modo (**Cooperativo**: los dos contra las oleadas · **1 contra 1**: gana el primero en llegar a 10 bajas) y pulsa **CREAR PARTIDA**. Sale un código de 4 letras y un enlace.
2. El otro escribe el código y pulsa **UNIRSE** (o abre el enlace directamente).
3. Cuando aparezca «¡Tu amigo se ha unido!», el anfitrión pulsa **EMPEZAR**.

**Táctico 1 contra 1**: rondas y una sola vida por ronda. Gana la partida el primero en llegar a 5 rondas. Al empezar cada ronda tienes 6 segundos quieto para elegir arma. No te curas, solo tienes un cargador de repuesto por arma y 1 granada y 1 flash. Al rival no se le ve nunca en el minimapa, pero se oyen sus pasos si anda o corre (agachado o apuntando no hace ruido). Una ronda se gana de tres maneras: eliminando al rival, quedándote solo 8 segundos dentro de la zona marcada (el parque infantil o la mesa de ping-pong), o, si se acaban los 100 segundos, teniendo más salud. Los lados se cambian cada ronda.

Si tu amigo tiene abierto otro mapa, al unirse cambia solo al mapa del anfitrión.

Funciona navegador a navegador (WebRTC con PeerJS): no hace falta servidor propio. El ordenador del anfitrión controla a los enemigos. En cooperativo, si caes reapareces al empezar la siguiente oleada; si caéis los dos, se acaba. En 1 contra 1 reapareces a los 3 segundos lejos del rival y la invencibilidad está desactivada.

Algunas redes muy restrictivas (colegios, empresas) bloquean la conexión directa entre navegadores; en casa normalmente funciona.

### Publicarlo gratis con GitHub Pages

1. En GitHub, abre el repositorio → **Settings** → **Pages**.
2. En *Build and deployment* elige **Deploy from a branch**, la rama del juego y la carpeta **/ (root)**, y guarda.
3. En un par de minutos tendrás el enlace para compartir con tus amigos: **https://gabidiego072-glitch.github.io/Losa-game/**

## Armas

| Tecla | Arma | Notas |
|---|---|---|
| 1 | Pistola 9 mm | Semiautomática, rápida de recargar |
| 2 | Subfusil P90 | Mucha cadencia, poco daño por bala |
| 3 | Fusil de asalto (AK-47) | Equilibrado |
| 4 | Escopeta | 9 perdigones, devastadora de cerca, recarga cartucho a cartucho |
| 5 | Francotirador | Mira telescópica (clic derecho), mata de un tiro a la cabeza |

## Recursos usados (todos libres)

- Trazado real de calles, edificio de 6 plantas, pista, parque y bares: datos © colaboradores de [OpenStreetMap](https://www.openstreetmap.org/copyright) (ODbL).
- Ortofoto aérea (tejados reales, minimapa y medidas): PNOA cedido por © [Instituto Geográfico Nacional](https://www.ign.es) (CC BY 4.0).

- Cielo HDRI y texturas PBR (asfalto, hormigón, tierra, corteza, enlucido, caucho): [Poly Haven](https://polyhaven.com), licencia CC0.
- Soldado animado: modelo `Soldier.glb` de los ejemplos de [three.js](https://github.com/mrdoob/three.js).
- Pistola, fusil de cerrojo (francotirador), mesas y sillas de terraza, banco urbano, botiquín y caja de munición: [Poly Haven](https://polyhaven.com) (CC0).
- AK-47 texturizado: «AK trio pack» de mightydinosaurcol en [OpenGameArt](https://opengameart.org/content/ak-trio-pack) (CC-BY 3.0).
- P90 y escopeta: «Low poly animated guns» de Quaternius en [OpenGameArt](https://opengameart.org/content/low-poly-animated-guns) (CC0).

## Detalles técnicos

- Rendimiento: los objetos estáticos se fusionan en pocas llamadas de dibujo, las sombras siguen al jugador, los disparos usan un BVH (three-mesh-bvh) y la resolución se ajusta sola para mantener unos 60 FPS. En el menú se puede elegir calidad Automática, Alta, Media o Baja.

- Un único archivo `index.html`, sin dependencias que instalar (Three.js 0.160 desde unpkg).
- Texturas fotográficas PBR con relieve (normal maps) y rugosidad; iluminación con un cielo HDRI real; los cristales y coches reflejan el cielo.
- Pinos piñoneros hechos con tarjetas de agujas, sombras suaves, bloom, viñeta y grano de película.
- Fachadas, rótulos y baldosas rojas y beige dibujados por código.
- Enemigos con búsqueda de caminos (A* sobre una rejilla), línea de visión, ráfagas y precisión que depende de la distancia, de si te mueves y de si estás agachado.
- Los disparos del jugador tienen dispersión, retroceso, daño extra a la cabeza y marcas de impacto.
