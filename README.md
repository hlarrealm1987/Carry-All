# Carry All (NeoForge 26.3)

Mod para Minecraft Java 26.3 con NeoForge. Te deja levantar bloques (con todo lo que tienen adentro) y animales, y cargarlos a otro lugar.

## Cómo se juega

| Acción | Cómo |
|---|---|
| Levantar un bloque | **Agáchate (Shift) + clic derecho** en el bloque, con **las dos manos vacías** |
| Levantar un animal | **Agáchate (Shift) + clic derecho** en el animal, con **las dos manos vacías** |
| Soltarlo | **Clic derecho** en cualquier bloque |

- Los cofres, barriles, hornos, shulkers, letreros, spawners, etc. **guardan todo lo que tienen adentro**.
- Los animales guardan su nombre, su dueño (mascotas), su salud, su edad, etc.
- Mientras cargas algo vas más lento (Lentitud I), no puedes atacar y no puedes romper bloques.
- Si mueres cargando algo, se suelta donde moriste.
- Si te desconectas, lo sigues cargando cuando vuelves a entrar.
- Respeta la protección del spawn y los mods de protección de terrenos.

## Ajustes del servidor

Después de arrancar el servidor una vez, se crea el archivo:

```
world/serverconfig/carryall-server.toml
```

Ahí puedes cambiar:
- `carryBlocks`: permitir levantar bloques (true/false)
- `carryUnbreakableBlocks`: permitir levantar bedrock y bloques irrompibles
- `blockBlacklist`: bloques prohibidos (ej. `"minecraft:spawner"`, o todo un mod con `"otromod:*"`)
- `carryAnimals`, `carryVillagers`, `carryWaterMobs`, `carryHostileMobs`: qué mobs se pueden cargar
- `entityBlacklist`: mobs prohibidos
- `slownessLevel`: nivel de lentitud (0 = sin lentitud)

Los jefes (Wither, Ender Dragon, Warden, Elder Guardian) nunca se pueden levantar.

## Cómo compilar el mod (sacar el archivo .jar)

### Opción A: con GitHub, sin instalar nada
1. Crea un repositorio nuevo en GitHub y sube todos estos archivos.
2. GitHub compila el mod solo (pestaña **Actions**). Tarda unos 10–15 minutos la primera vez.
3. Cuando termine, entra al build y descarga **carryall-mod**. Adentro está `carryall-1.0.0.jar`.

### Opción B: en tu computadora
1. Instala **Java 25** (Temurin, de adoptium.net) y **IntelliJ IDEA Community**.
2. Abre esta carpeta en IntelliJ (File → Open). Espera a que Gradle descargue todo (la primera vez puede tardar bastante).
3. Para probar: en el panel de Gradle, corre `runClient` (abre Minecraft con el mod).
4. Para crear el .jar: corre `build`. El archivo sale en `build/libs/carryall-1.0.0.jar`.

## Instalar en el servidor

1. El servidor necesita **NeoForge 26.3** (versión 26.3.0.100 o más nueva).
2. Copia `carryall-1.0.0.jar` a la carpeta `mods/` del servidor.
3. **Cada jugador también** necesita NeoForge 26.3 y el mismo .jar en su carpeta `mods/`.

## Pendiente para la versión 2
- Que se vea el bloque o el animal en los brazos del jugador (ahora solo sale un mensaje arriba de la barra rápida: "Cargando: Cofre").
- Bloquear que otros jugadores levanten mascotas ajenas.
