# ⚓ Batalla Naval · Guerra de Continentes

Batalla naval multijugador para hasta **4 equipos**, cada uno en su propio dispositivo, con una **pantalla principal** (proyector/TV) que muestra todos los ataques en vivo.

No necesita servidor ni cuentas: es un solo archivo `index.html`.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `batalla-naval`).
2. Sube `index.html` y este `README.md` a la rama `main`.
3. Ve a **Settings → Pages**.
4. En **Build and deployment** elige **Deploy from a branch**, rama `main`, carpeta `/ (root)` y guarda.
5. Espera 1–2 minutos. Tu juego quedará en `https://TU-USUARIO.github.io/batalla-naval/`.

## Cómo se juega

1. **Pantalla principal:** abre el enlace y toca **Pantalla principal**. Aparece un **código de 4 letras**, un enlace y un QR.
2. **Equipos:** en su dispositivo, abren el enlace del QR (o escriben el código) y eligen **continente** y nombre.
3. **Flota:** cada equipo reparte 14 puntos entre barcos, los coloca en el tablero 10×10 (o al azar) y pulsa **¡Listo!**.
4. **Sorteo:** cuando todos están listos, la pantalla principal pulsa **Sortear orden y empezar**.
5. **Batalla:** en su turno, cada equipo elige un rival, toca una casilla y pulsa **¡Fuego!**. Gana el último con barcos a flote.

Regla opcional en la preparación: *si aciertas, vuelves a disparar*.

## Cómo funciona

- Usa [PeerJS](https://peerjs.com/) (WebRTC): los navegadores se conectan entre sí. Solo se usa el servidor público gratuito de PeerJS para el primer contacto.
- La **pantalla principal es el servidor** de la partida: valida cada disparo y guarda la posición de los barcos. **Los equipos nunca reciben la flota de otros**, así que no se puede hacer trampa mirando el código.
- Si un equipo recarga o pierde conexión, al volver a abrir el enlace recupera su sitio automáticamente.
- Si recargas la pantalla principal, te ofrece **reanudar** la partida guardada con el mismo código.

## Limitaciones

- **La pantalla principal debe quedarse abierta** durante toda la partida.
- Algunas redes (colegios, empresas) bloquean WebRTC. Se incluyen servidores STUN y un TURN público gratuito como respaldo, pero este último puede ser lento o dejar de estar disponible. Si falla, prueba con datos móviles o usa un hotspot.
- Una partida por código: para varias partidas a la vez, abre varias pantallas principales.
- Requiere internet (carga PeerJS y las fuentes desde CDN).

## Probarlo en local

Abre `index.html` con un servidor local (`python3 -m http.server`) y entra desde varias pestañas o dispositivos de la misma red.
