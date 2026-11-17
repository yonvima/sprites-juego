# Prompt COMPLETO — «DÚO SUPREMO» estilo survivor (para Gemini, conversación nueva)

Crea un juego web HTML completo (un solo archivo, listo para jugar en teléfono y computadora) llamado «DÚO SUPREMO», del género SURVIVOR (como Vampire Survivors / los survivor de móvil), protagonizado por MIS dos personajes con los sprites que te doy abajo. Devuélveme el archivo HTML completo.

## CÓMO SE JUEGA (esto es lo más importante)
- Pantalla VERTICAL pensada para móvil. Arena grande con suelo de baldosas que se desplaza; la cámara sigue al personaje, siempre centrado.
- Control: UN joystick virtual grande en la parte baja de la pantalla (se mueve con el dedo; en computadora también WASD/flechas y arrastrar el ratón). SOLO se controla el movimiento: todos los ataques son AUTOMÁTICOS.
- Los enemigos llegan en enjambre continuo, cada vez más y más fuertes con el tiempo. Al morir sueltan GEMAS de experiencia que quedan en el suelo; al caminar cerca, las gemas vuelan hacia el personaje y se recogen (radio imán). Un aviso «Acércate para recoger» aparece al inicio.
- Barra superior: NIVEL actual, barra de experiencia que se llena, TEMPORIZADOR de supervivencia y contador de bajas. Sobre el personaje, su barra de vida con el número.
- Al SUBIR DE NIVEL el juego se pausa y aparece la pantalla de ELECCIÓN: 3 cartas de habilidades; el jugador toca una para seguir. Hay habilidades ACTIVAS y PASIVAS, cada una con niveles (Nv. 1, 2, 3…) y ranuras visibles abajo (6 activas, 6 pasivas). Algunas cartas muestran «Para EVO» (evolución al combinar dos habilidades al máximo).
- De vez en cuando aparece un evento «REGALO»: ofrece subir una habilidad 2 niveles de golpe, con botones Aceptar / Rechazar.
- Botones de acción en pantalla: DASH, BLOQUEO y SÚPER (se llena con las bajas). Partida por OLEADAS (10 oleadas) con victoria al superar la última y pantalla de derrota si la vida llega a 0, con puntuación, bajas, nivel y récord guardado.

## LOS PERSONAJES (pareja, una sola unidad jugable)
Se controlan juntos como una unidad, hombro con hombro (30 px de separación por lado, sin encimarse), con orden por profundidad Y:
- EL DE BLANCO: hombre negro chibi, pelo muy corto, traje blanco, corbata amarilla, pin USA, botas negras. SIEMPRE se está riendo. Ataca con bolas de fuego y su GRITO aturde y empuja.
- EL LÍDER: hombre negro chibi CALVO, MUY SERIO siempre (nunca se ríe), traje beige, corbata roja vino, botas negras, libro negro en la mano, aura dorada y humo ligero. Golpea con el libro de cerca y también lanza fuego.
- NUNCA mezcles sus rasgos: El Líder nunca tiene pelo ni se ríe; el de blanco nunca es calvo ni lleva el libro.

## SPRITES (usa estas URL EXACTAS, letra por letra; prohibido inventar o acortar nombres)
BASE: https://raw.githubusercontent.com/yonvima/sprites-juego/main/

### HOJAS PRINCIPALES — FORMATO SURVIVOR NUEVO (PNG ya TRANSPARENTES, sin fondo: recorta solo por columnas, NO quites fondo)
Estas son las hojas que se ven en pantalla para los dos personajes; las de la lista siguiente son apoyo/reserva.
- Hoja survivor del de blanco (filas: 0 reposo riendo 6, 1 correr de perfil 6 — NO usar esta fila, 2 ataque de fuego 5, 3 caída 5): sprite-survivor-blanco.png
- Hoja survivor de El Líder (filas: 0 reposo gesticulando 6, 1 correr + golpe con libro 6, 2 caída 6): sprite-survivor-el-lider.png
- Correr DE FRENTE del de blanco (7 frames en bucle, es el correr que se usa al moverse): correr-frente-blanco.png
- Correr DE FRENTE de El Líder (7 frames en bucle): correr-frente-el-lider.png
- Tornado de El Líder — SÚPER (9 frames, libro siempre en la mano/pecho): tornado-survivor-el-lider.png
- Tornado del de blanco (8 frames): tornado-survivor-blanco.png
- Grito del de blanco (7 frames): grito-survivor-blanco.png
- Carga de aura de El Líder (8 frames, para subir de nivel y Juicio Final): carga-survivor-el-lider.png
- Dash + victoria del de blanco (6 poses + fantasmas de velocidad al inicio): dash-victoria-survivor-blanco.png
- Dash + victoria de El Líder (7 poses + 1 fantasma de velocidad): dash-victoria-survivor-el-lider.png
- Bloqueo del de blanco (6 frames, brazos cruzados): bloqueo-survivor-blanco.png
- Bloqueo de El Líder (10 frames, escudo con UN solo libro): bloqueo-survivor-el-lider.png
- Disparos por dirección del de blanco — cuadrícula 5 filas × 3 columnas (filas: derecha, diagonal arriba, arriba, diagonal abajo, abajo; columnas: prepara / lanza / recupera; lanzamiento a DOS MANOS y fuego PEQUEÑO; las direcciones a la izquierda se espejan → 360° en 8 sectores): disparo-direcciones-blanco.png

### HOJAS 360° — DIRECCIÓN COMPLETA (PNG TRANSPARENTES, celdas uniformes de 256×256: recorta por rejilla exacta, sin detectar columnas)
Material nuevo para que cada personaje MIRE y se MUEVA en la dirección real del joystick y DISPARE con animación de 3 frames en esa dirección. En todas las hojas 4×4 el orden es el mismo, de izquierda a derecha y de arriba abajo: fila 0 = 0°, 22,5°, 45°, 67,5°; fila 1 = 90°, 112,5°, 135°, 157,5°; fila 2 = 180°, 202,5°, 225°, 247,5°; fila 3 = 270°, 292,5°, 315°, 337,5° (0° = frente, 90° = perfil derecho, 180° = espalda, 270° = perfil izquierdo). Elige la celda según el sector de 22,5° más cercano al ángulo de movimiento/apunte.
- Rotación del de blanco (16 vistas en reposo, tira 8960×1120; también como hoja por grupos y sprites sueltos rotacion-000.png … rotacion-337.png): rotacion-360-blanco/rotacion-360-COMPLETA-16-blanco.png
- Rotación de El Líder (16 vistas, serio, libro en la mano; sueltos rotacion-lider-000.png … rotacion-lider-337.png): rotacion-360-lider/rotacion-360-COMPLETA-16-lider.png
- Caminar 360° del de blanco (hoja 2048×2048, rejilla 8×8: cada fila trae 2 direcciones seguidas con sus 4 fases A/B/C/D — fila 0 = 0° y 22,5°, fila 1 = 45° y 67,5°, y así hasta 337,5°; sueltos en caminar-360-blanco/frames/caminar-<ángulo>-<fase>.png): caminar-360-blanco/hoja-caminar-360-COMPLETA-64.png
- Caminar 360° de El Líder (mismo formato; sueltos en caminar-360-lider/frames/caminar-lider-<ángulo>-<fase>.png): caminar-360-lider/hoja-caminar-360-COMPLETA-64-lider.png
- DISPARO 360° del de blanco — TRES hojas 4×4 que forman la animación completa del tiro en cada dirección (reproduce anterior → central → posterior a 12 fps al disparar): disparo-360-blanco/hoja-disparo-360-anterior-4x4-blanco.png (carga: chispa pequeña), disparo-360-blanco/hoja-disparo-360-4x4-blanco.png (bola de fuego formada), disparo-360-blanco/hoja-disparo-360-posterior-4x4-blanco.png (soltar: manos vacías y estela). Sueltos: disparo-360-blanco/disparo-anterior-<ángulo>.png, disparo-360-blanco/disparo-<ángulo>.png, disparo-360-blanco/disparo-posterior-<ángulo>.png
- DISPARO 360° de El Líder — las mismas tres hojas con su esfera dorada y su libro (suelto central: disparo-lider-<ángulo>.png): disparo-360-lider/hoja-disparo-360-anterior-4x4-lider.png, disparo-360-lider/hoja-disparo-360-4x4-lider.png, disparo-360-lider/hoja-disparo-360-posterior-4x4-lider.png
- Apunte omnidireccional del de blanco (alternativa tipo twin-stick: el cuerpo NO rota, apunta con los brazos en 16 direcciones de pantalla — orden por filas: arriba, arriba-arriba-derecha, arriba-derecha, derecha-arriba / derecha, derecha-abajo, abajo-derecha, abajo-abajo-derecha / abajo, abajo-abajo-izquierda, abajo-izquierda, izquierda-abajo / izquierda, izquierda-arriba, arriba-izquierda, arriba-arriba-izquierda; sueltos apunte-<dirección>.png): disparo-omnidireccional-blanco/hoja-disparo-omnidireccional-4x4-blanco.png
- USO EN EL JUEGO: al moverse, anima el caminar de la dirección del joystick (4 fases en bucle); al estar quieto, usa la vista de rotación de la última dirección; al disparar (automático, al enemigo más cercano), superpone la secuencia de disparo de 3 frames de la dirección del objetivo SIN detener el caminar. Cada personaje usa SU set: el de blanco nunca usa sprites de El Líder ni al revés.

### HOJAS DE APOYO (fondo gris, recorte con flood-fill como se explica abajo)
- Hoja completa del de blanco (6 filas): media-generation-desde-cero-blanco-formato-nuev-0-debf5941-78ae-4526-8720-2a571ea49f40.png
- Hoja completa de El Líder (6 filas): media-generation-desde-cero-el-lider-formato-nu-0-da3edfce-b049-44dd-bca7-531eba778885.png
- Pasos del de blanco (fila 0 caminar, fila 1 correr): media-generation-pasos-mejorados-blanco-0-b0c2ff7c-5c4f-40e9-bc25-820c842b680d.png
- Pasos de El Líder (fila 0 caminar, fila 1 correr): media-generation-pasos-mejorados-el-lider-0-c5d30f20-156a-4a3b-8ad1-41a842b84e97.png
- Reposo del de blanco (8 frames): media-generation-reposo-blanco-0-57bc9a71-1c93-4787-9e39-a4f8e62cea39.png
- Reposo de El Líder (8 frames): media-generation-reposo-el-lider-0-eb25fcaa-4b84-43c1-97fb-36b5930e1886.png
- Bola de fuego del de blanco: media-generation-bola-fuego-blanco-0-80a5d245-5df2-4dc7-94d0-2db95649af4d.png
- Bola de fuego de El Líder: media-generation-bola-fuego-el-lider-0-d5029cc9-bd90-48c8-8fc0-4bf685eb9d61.png
- Grito del de blanco: media-generation-grito-blanco-0-42c34de5-0fa8-480c-b9a9-7281478ae112.png
- Golpe con libro de El Líder (descarta el último frame): media-generation-golpe-libro-el-lider-nuevo-0-c4c4a94d-f6cd-45df-8ffd-d1a2d40f6636.png
- Tornado del de blanco: media-generation-tornado-blanco-0-54070a3e-3dc3-458c-b50b-e7fa8608dae2.png
- Tornado de El Líder: media-generation-tornado-el-lider-0-be8ff3b4-ca17-4eec-a8cb-cea001ea5acd.png
- Daño/muerte del de blanco: media-generation-dano-muerte-blanco-0-51e97a8d-5ded-42e1-94b9-24da8a8bd4b9.png
- Daño/muerte de El Líder: media-generation-dano-muerte-el-lider-0-e4aad2df-6995-4815-a236-0e60edbdc521.png
- Dash/victoria del de blanco: media-generation-dash-victoria-blanco-0-26dd5c69-1f40-4be1-8733-8e3d0bd80689.png
- Dash/victoria de El Líder: media-generation-dash-victoria-el-lider-0-01c0acd6-2683-4320-8882-621f146b2d23.png
- Carga de aura de El Líder: media-generation-carga-aura-el-lider-0-a3c2d963-3b89-470b-a3cd-26f1b25c9c8d.png
- Carga de poder del de blanco: media-generation-carga-poder-blanco-0-124662be-e617-43ad-8e72-d10f42c98a8a.png
- Bloqueo del de blanco: media-generation-bloqueo-blanco-0-800d3640-a896-424b-b053-a65f725de14f.png
- Bloqueo de El Líder: media-generation-bloqueo-el-lider-0-ddd28305-d8d6-4cfb-8c80-ed4006f2893f.png
- Direcciones del de blanco (fila 0 frente, fila 1 espaldas): media-generation-direcciones-blanco-0-4d9c914c-01f1-4a62-bcfe-c17d70e911ec.png
- Direcciones de El Líder (fila 0 frente, fila 1 espaldas): media-generation-direcciones-el-lider-0-ca1efb31-8a1f-443c-a93b-b8eec672101f.png
- Enemigos (fila 0 baboso verde, fila 1 murciélago, fila 2 gólem de piedra): media-generation-enemigos-juego-0-5cd5127d-6e4a-40d7-8f9e-fc09620e8690.png

## CÓMO RECORTAR LOS SPRITES (obligatorio)
Las HOJAS PRINCIPALES (formato survivor) ya vienen con fondo TRANSPARENTE: recorta cada frame detectando las columnas de píxeles no transparentes de cada fila. Las HOJAS 360° también son transparentes pero con celdas UNIFORMES de 256×256: recórtalas dividiendo la hoja en su rejilla exacta (4×4 en las de 1024×1024, 8×8 en las de caminar de 2048×2048, y la tira de rotación en 16 columnas de 560×1120). Las hojas de apoyo tienen fondo GRIS plano: para ellas elimina el gris con flood-fill desde los bordes. En todas, los frames NO forman una rejilla uniforme y hay que alinear los pies de todos los frames en la misma línea base. Anima con tiempo delta y fps fijos por estado (reposo 6, caminar 9, correr 14, ataques 12). Movimiento continuo en píxeles por segundo. Precarga TODAS las hojas (con 3 reintentos) antes de dejar jugar. PROHIBIDO dibujar personajes o enemigos por código como respaldo: si una hoja falla, muestra el error con su nombre y no inicies la partida. Los sprites deben ser los mismos en TODAS las pantallas y estados.

## HABILIDADES PARA LAS CARTAS DE ELECCIÓN (temáticas del dúo)
Activas: Bola de Fuego (más bolas / más daño por nivel), Grito Dorado (radio y aturdimiento mayores), Libro Sagrado (golpes más fuertes y rápidos), Tornado Gemelo (el súper se carga antes), Dash Relámpago (más rápido, menos espera), Aura del Líder (daño continuo alrededor).
Pasivas: Botas de Combate (+velocidad), Corazón Doble (+vida máxima y cura), Imán de Gemas (+radio de recogida), Pin Dorado (+experiencia ganada), Corbata de Poder (+daño de todo), Humo Ligero (probabilidad de esquivar).
Evoluciones «Para EVO»: Bola de Fuego Nv. máx + Corbata de Poder = LLAMARADA SUPREMA; Grito Nv. máx + Imán = GRITO SÍSMICO; Libro Nv. máx + Aura = JUICIO FINAL.

## SONIDOS (MP3 en el mismo GitHub; precargar y reproducir en su momento)
VOLÚMENES (obligatorio: el usuario se quejó de que el fuego y otros sonidos suenan MUY FUERTES): volumen maestro 0.6 y estos volúmenes por sonido al reproducir; ningún efecto puede sonar más fuerte que la voz del Súper ni saturar.
- Súper Tornado → voz real de El Líder: https://raw.githubusercontent.com/yonvima/sprites-juego/main/voz-lider-poder.mp3 (volumen 0.85, desde el segundo 0, junto al efecto de tornado)
- Grito del de blanco → https://raw.githubusercontent.com/yonvima/sprites-juego/main/faaa.mp3 (volumen 0.5)
- Impacto del libro → https://raw.githubusercontent.com/yonvima/sprites-juego/main/golpe-punch.mp3 (volumen 0.55)
- Dash → https://raw.githubusercontent.com/yonvima/sprites-juego/main/espada-slash.mp3 (volumen 0.45)
- Impacto de bola de fuego → https://raw.githubusercontent.com/yonvima/sprites-juego/main/explosion.mp3 (volumen 0.35; es el sonido más fuerte, déjalo bajo)
- Muerte del gólem → https://raw.githubusercontent.com/yonvima/sprites-juego/main/tubo-metal.mp3 (volumen 0.45)
- Subida de nivel → https://raw.githubusercontent.com/yonvima/sprites-juego/main/vine-boom.mp3 (volumen 0.5)
- Disparo de fuego (sintético, por código): ruido blanco con bandpass 400→1800 Hz, efecto «whoosh» de llamarada, a volumen BAJO (0.2); NUNCA un tono láser.
El archivo disparo-gunshot.mp3 existe en el repo pero NO se usa en este juego.

Devuelve el archivo HTML completo, listo para pegar y jugar.
