📖 Índice

- [Sobre el proyecto](#-sobre-el-proyecto)
- [El eclipse](#-el-eclipse)
- [Objetivo](#-objetivo)
- [Características principales](#-características-principales)
- [Para usuarios](#-para-usuarios)
- [Cómo utilizar la aplicación](#-cómo-utilizar-la-aplicación)
- [Listado de concejos](#-listado-de-concejos)
- [Sistema de probabilidades](#-sistema-de-probabilidades)
- [Tiempos del eclipse](#-tiempos-del-eclipse)
- [Cronología de la observación](#-cronología-de-la-observación)
- [Alarmas](#-alarmas)
- [Posición del Sol](#-posición-del-sol)
- [Meteorología](#-meteorología)
- [Seguridad durante el eclipse](#-seguridad-durante-el-eclipse)
- [Persistencia de datos](#-persistencia-de-datos)
- [Arquitectura técnica](#-arquitectura-técnica)
- [Estructura del código](#-estructura-del-código)
- [Datos internos](#-datos-internos)
- [Cálculos astronómicos](#-cálculos-astronómicos)
- [Modelo de duración de la totalidad](#-modelo-de-duración-de-la-totalidad)
- [Metodología meteorológica](#-metodología-meteorológica)
- [Precisión y limitaciones](#-precisión-y-limitaciones)
- [Fuentes](#-fuentes)
- [Tecnologías](#-tecnologías)
- [Compatibilidad](#-compatibilidad)
- [Privacidad](#-privacidad)
- [Desarrollo](#-desarrollo)
- [Personalización](#-personalización)
- [Mantenimiento](#-mantenimiento)
- [Contribuir](#-contribuir)
- [Problemas conocidos](#-problemas-conocidos)
- [Créditos](#-créditos)
- [Estado del proyecto](#-estado-del-proyecto)
- [Licencia](#-licencia)

---

# 🌑 Sobre el proyecto

**OMEGA · Eclipse 12 agosto 2026 · Asturias** es una aplicación web desarrollada para facilitar la observación del eclipse total de Sol del **12 de agosto de 2026** desde el Principado de Asturias.

El proyecto está pensado para funcionar como una herramienta de observación de campo: el usuario puede seleccionar un concejo, consultar sus tiempos previstos, conocer la duración aproximada de la totalidad, consultar una estimación de las condiciones meteorológicas, comprobar hacia dónde debe mirar y utilizar una cuenta atrás sincronizada con las distintas fases del eclipse.

La aplicación está construida como un **único documento HTML autocontenido**, sin frameworks ni dependencias externas de JavaScript. La interfaz, los estilos, los datos, los cálculos y la lógica de funcionamiento están contenidos en el propio archivo.

Esto permite utilizarla de forma sencilla tanto desde un ordenador como desde un teléfono móvil.

El archivo principal del proyecto es:

```text
OMEGA-ECLIPSE-ASTURIAS-v7.html
````

El documento está configurado específicamente para el eclipse del 12 de agosto de 2026 y contiene los datos de los concejos asturianos utilizados por la aplicación. 

---

# 🌞 El eclipse

El proyecto está diseñado específicamente para el:

**Eclipse total de Sol — 12 de agosto de 2026**

La aplicación utiliza información para los concejos del Principado de Asturias y proporciona, para cada uno de ellos:

* coordenadas;
* duración estimada de la totalidad;
* probabilidad estimada de condiciones favorables;
* clasificación geográfica;
* cinco tiempos de contacto;
* posición del Sol;
* trayectoria aproximada del Sol sobre el horizonte;
* enlaces a fuentes meteorológicas y astronómicas oficiales.

Los datos precargados incluyen concejos como Gijón, Oviedo, Avilés, Llanes, Cangas de Onís, Cangas del Narcea, Allande, Aller, Somiedo, Tineo y el resto de concejos contemplados en la aplicación. 

---

# 🎯 Objetivo

El objetivo principal no es simplemente mostrar una cuenta atrás.

La aplicación intenta resolver un problema concreto:

> **¿Dónde puedo observar el eclipse desde Asturias y cómo puedo prepararme para observarlo correctamente?**

Para ello combina en una sola interfaz:

1. **Información astronómica**
2. **Información geográfica**
3. **Estimación meteorológica**
4. **Cuenta atrás**
5. **Tiempos de contacto**
6. **Posición del Sol**
7. **Alarmas**
8. **Información de seguridad**
9. **Enlaces a fuentes oficiales**
10. **Configuración específica para cada usuario**

La aplicación está pensada especialmente para utilizarse **el mismo día del eclipse**, cuando la información debe ser rápida de consultar y no depender de una conexión permanente con un servidor.

---

# ✨ Características principales

## 📍 Selección de concejo

La aplicación permite consultar individualmente los concejos disponibles.

Cada ubicación tiene asociada:

* nombre del concejo;
* población de referencia;
* latitud;
* longitud;
* probabilidad estimada;
* duración de la totalidad;
* indicador geográfico;
* cinco tiempos del eclipse.

Los datos se almacenan internamente en una estructura JavaScript y se transforman posteriormente en objetos utilizados por la interfaz. 

---

## 🔎 Buscador

La pantalla principal incorpora un buscador para localizar rápidamente un concejo.

La búsqueda:

* no distingue entre mayúsculas y minúsculas;
* normaliza caracteres Unicode;
* permite localizar nombres con o sin tildes;
* busca tanto por nombre del concejo como por población de referencia.

Por ejemplo:

```text
Gijón
```

y:

```text
gijon
```

pueden encontrar el mismo resultado.

El código elimina las marcas diacríticas antes de comparar las cadenas. 

---

## ↕️ Ordenación

Los resultados pueden ordenarse mediante tres criterios:

### Probabilidad

Ordena los concejos de mayor a menor probabilidad estimada.

### Alfabético

Ordena los concejos alfabéticamente.

### Duración

Ordena los concejos de mayor a menor duración de la totalidad.

En caso de empate se utilizan criterios secundarios para mantener una ordenación estable. 

---

# 👤 Para usuarios

La aplicación no requiere conocimientos astronómicos ni informáticos.

Un usuario puede utilizarla siguiendo este procedimiento:

### 1. Buscar su concejo

Introducir el nombre en el buscador o localizarlo en la lista.

### 2. Abrir la ubicación

Al pulsar sobre el concejo se muestra su ficha detallada.

### 3. Comprobar la probabilidad

La aplicación muestra una estimación de las posibilidades de disponer de condiciones meteorológicas favorables.

### 4. Comprobar el horizonte

La herramienta muestra hacia qué zona del cielo se encontrará el Sol durante el eclipse.

### 5. Consultar los tiempos

La ficha muestra:

* C1 — inicio del eclipse;
* C2 — comienzo de la totalidad;
* máximo;
* C3 — final de la totalidad;
* C4 — final del eclipse.

### 6. Consultar la meteorología

Desde la ficha se puede acceder directamente a las herramientas de AEMET y al visor del IGN.

### 7. Activar las alarmas

La aplicación puede emitir avisos acústicos y vibraciones.

### 8. Observar el eclipse

Durante la fase parcial deben utilizarse gafas adecuadas para la observación solar.

Durante la totalidad, las gafas pueden retirarse únicamente mientras el disco solar permanezca completamente cubierto.

Al comenzar C3 deben volver a utilizarse inmediatamente.

---

# 🗺️ Listado de concejos

La aplicación incorpora un conjunto de ubicaciones representativas de los concejos de Asturias.

Cada registro contiene conceptualmente:

```text
[
    concejo,
    población,
    latitud,
    longitud,
    probabilidad,
    duración,
    indicador geográfico,
    zona,
    tiempos
]
```

Por ejemplo, el registro de Gijón contiene:

```text
Gijón
43.5322 N
5.6611 O
31 %
109 s
```

junto con los cinco tiempos de contacto precargados. 

---

# ☁️ Sistema de probabilidades

## ⚠️ Importante

El porcentaje mostrado por la aplicación **no representa una probabilidad meteorológica oficial de AEMET**.

Es una **estimación propia del proyecto** destinada a facilitar la comparación entre ubicaciones.

La aplicación lo deja explícitamente indicado mediante etiquetas como:

```text
% estimado
```

y distingue estos valores de los tiempos oficiales del IGN. 

---

## Metodología

La estimación combina cinco factores:

### 1. Boletín especial de AEMET

Se tiene en cuenta la previsión meteorológica específica para la tarde del 12 de agosto.

La metodología considera especialmente la nubosidad baja y media. 

### 2. Geometría del horizonte

Debido a la baja altura del Sol durante el eclipse, no basta con comprobar únicamente la nubosidad situada exactamente sobre el observador.

El proyecto considera especialmente el sector occidental y ligeramente septentrional del horizonte.

Esto es importante porque las nubes situadas a cierta distancia pueden interferir con la observación del Sol. 

### 3. Climatología ERA5

Se utiliza como referencia la climatología de AEMET para los días 11–13 de agosto de 2010–2025.

La metodología documentada en la aplicación señala una frecuencia climatológica de cielos despejados del 30–50 % en la costa cantábrica. 

### 4. Ensemble ECMWF

Se incorpora el ensemble de 51 miembros como referencia probabilística para Oviedo. 

### 5. Geografía local

También se consideran:

* distancia al Cantábrico;
* altitud;
* exposición;
* nubosidad de evolución en zonas montañosas.



---

## Margen de incertidumbre

La propia aplicación establece un margen aproximado de:

```text
±10 puntos porcentuales
```

Por tanto:

```text
40 %
```

no debe interpretarse como una predicción meteorológica con una precisión del 40,00 %.

Es una herramienta comparativa.

La meteorología real puede diferir considerablemente de la estimación. 

---

# ⏱️ Tiempos del eclipse

Cada ubicación dispone de cinco momentos:

| Código  | Fase             | Significado                   |
| ------- | ---------------- | ----------------------------- |
| **C1**  | Primer contacto  | Comienza el eclipse parcial   |
| **C2**  | Segundo contacto | Comienza la totalidad         |
| **MAX** | Máximo           | Punto central de la totalidad |
| **C3**  | Tercer contacto  | Termina la totalidad          |
| **C4**  | Cuarto contacto  | Finaliza el eclipse           |

La aplicación utiliza estos cinco puntos para construir la cronología completa de observación. 

---

# 🕒 Tiempos oficiales frente a tiempos estimados

Este es uno de los aspectos más importantes del proyecto.

Los tiempos precargados **no deben considerarse automáticamente oficiales**.

La interfaz permite sustituirlos por los valores publicados por el Instituto Geográfico Nacional.

La aplicación distingue ambos estados:

```text
Tiempos estimados · confírmalos en el IGN
```

frente a:

```text
Tiempos oficiales IGN
```



---

## Introducción manual de tiempos

Desde la ficha de cada concejo puede abrirse el editor:

* Inicio del eclipse (C1)
* Inicio de la totalidad (C2)
* Máximo
* Fin de la totalidad (C3)
* Fin del eclipse (C4)

Los campos aceptan precisión de segundos. 

El programa valida que:

```text
C3 > C2
```

antes de guardar los datos. 

---

# 📅 Resolución temporal del IGN

La interfaz incorpora una explicación específica sobre la resolución de las fichas del IGN.

Si el IGN proporciona, por ejemplo:

```text
20:28,5
```

la aplicación considera compatible cualquier instante dentro del intervalo correspondiente a esos 0,5 minutos.

La propia interfaz documenta una resolución real de aproximadamente 6 segundos para ese formato. 

---

# 🧭 Cronología de la observación

La aplicación presenta una línea temporal dinámica.

Durante el eclipse cambia automáticamente entre:

### Antes del eclipse

```text
Antes del eclipse
Esperando
```

### Eclipse parcial creciente

```text
Parcial · creciente
Gafas puestas
```

### Totalidad

```text
TOTALIDAD
Gafas fuera
```

### Eclipse parcial menguante

```text
Parcial · menguante
Gafas puestas
```

### Final

```text
Terminado
Fin del eclipse
```



---

# 🔔 Alarmas

Una de las funciones principales del proyecto es ayudar al observador a no perder los momentos críticos.

La aplicación puede utilizar:

* sonido;
* vibración;
* avisos previos;
* alarmas específicas para C1;
* alarma para C2;
* alarma para el máximo;
* alarma para C3;
* alarma para C4.

---

## Avisos previos

Antes de la totalidad se generan avisos a:

```text
10 minutos
2 minutos
30 segundos
10 segundos
```

Además, existe un aviso de 10 segundos antes del final de la totalidad. 

---

## Diferentes sonidos

Las distintas fases utilizan patrones sonoros diferentes.

El sistema utiliza la Web Audio API mediante `AudioContext` y osciladores, y emplea vibración cuando el dispositivo lo permite. 

---

# 📱 Vibración

Cuando está disponible:

```javascript
navigator.vibrate()
```

se utiliza la vibración del dispositivo.

Esto permite que la aplicación pueda avisar incluso cuando el usuario no está mirando directamente la pantalla.

La disponibilidad depende del navegador y del dispositivo.

---

# 🌙 Modo noche

La aplicación incorpora un modo nocturno de color rojo.

Su objetivo es reducir el impacto de la pantalla sobre la adaptación visual del observador.

El modo se activa desde:

```text
Modo noche
```

y cambia las variables de color utilizadas por la interfaz. 

---

# 🔋 Pantalla encendida

La aplicación puede solicitar un **Screen Wake Lock** cuando el navegador lo permite.

Esto evita que la pantalla se apague durante la observación.

Se utiliza:

```javascript
navigator.wakeLock.request("screen")
```

y el estado se vuelve a solicitar cuando la página recupera visibilidad. 

---

# ⏰ Ajuste del reloj

Los móviles pueden tener pequeñas diferencias respecto a la hora de referencia.

La aplicación incorpora un ajuste manual:

```text
− 1 s
0 s
+ 1 s
```

Este desplazamiento se aplica al reloj utilizado por los contadores. 

Esto no corrige la hora del sistema operativo: únicamente modifica el tiempo utilizado internamente por la aplicación.

---

# 🧪 Modo de prueba

La aplicación incluye un modo para comprobar las alarmas antes del eclipse.

Al pulsar:

```text
Probar las alarmas ahora
```

la aplicación modifica temporalmente el reloj interno para situarlo poco antes de C2.

De esta forma pueden comprobarse:

* sonido;
* vibración;
* avisos;
* transiciones;
* comportamiento de la interfaz.

El modo puede desactivarse pulsando de nuevo el botón. 

---

# ☀️ Posición del Sol

La aplicación calcula la posición aproximada del Sol para la ubicación seleccionada.

Muestra:

* **acimut**
* **altura**

y representa gráficamente la posición del Sol respecto al horizonte.

También dibuja una trayectoria aproximada entre C1 y C4. 

---

## ¿Por qué es importante?

El eclipse se produce con el Sol relativamente bajo sobre el horizonte.

Por ello, no basta con tener un cielo despejado:

> también es necesario disponer de un horizonte suficientemente despejado en la dirección adecuada.

La herramienta intenta proporcionar una referencia visual para preparar previamente el lugar de observación.

---

# 🧭 Acimut y altura

El gráfico representa aproximadamente el sector:

```text
266° — 296°
```

correspondiente al horizonte occidental utilizado por la aplicación.

La posición se calcula dinámicamente a partir de:

* fecha;
* hora;
* latitud;
* longitud.

El cálculo astronómico está implementado directamente en JavaScript y no necesita una librería externa. 

---

# 🌦️ Meteorología

La aplicación no pretende sustituir a AEMET.

En su lugar, proporciona acceso directo a:

* visor de nubosidad;
* boletín especial del eclipse;
* predicción de AEMET;
* fichas del IGN;
* página específica del eclipse en Asturias;
* web oficial del proyecto gubernamental relacionado.

Los enlaces están integrados directamente en cada ficha. 

---

# 📋 Coordenadas

Cada ubicación dispone de sus coordenadas.

La aplicación muestra un campo como:

```text
43.5322, -5.6611
```

y permite copiarlo.

Esto está pensado especialmente para utilizar las coordenadas directamente en el visor meteorológico correspondiente. 

Si el navegador no permite el acceso al portapapeles, la aplicación ofrece un método alternativo basado en seleccionar manualmente el texto. 

---

# 👓 Seguridad durante el eclipse

La seguridad ocular es prioritaria.

Durante las fases parciales:

> **NO se debe mirar directamente al Sol sin protección solar adecuada.**

La aplicación muestra explícitamente:

```text
Gafas puestas
```

durante el eclipse parcial.

Al comenzar la totalidad muestra:

```text
GAFAS FUERA
```

y al terminar:

```text
GAFAS PUESTAS
```



---

## ⚠️ La aplicación no sustituye la observación visual

Las alarmas son una ayuda.

No deben utilizarse como único criterio de seguridad.

La aplicación advierte expresamente:

> Al primer destello de luz, gafas puestas sin esperar a la alarma.



Por tanto, durante la totalidad el observador debe permanecer atento al regreso de la luz solar.

---

# 💾 Persistencia de datos

La aplicación utiliza:

```javascript
localStorage
```

para guardar información en el dispositivo.

No existe una base de datos remota.

Se almacenan principalmente:

* concejo seleccionado;
* tiempos modificados;
* indicación de que esos tiempos han sido marcados como oficiales.

El almacenamiento utiliza la clave:

```text
omegaEclipse
```



---

## ¿Qué significa esto para el usuario?

Si introduces los tiempos oficiales del IGN y cierras la página, el navegador puede conservarlos.

Al volver a abrir la aplicación en el mismo dispositivo y navegador, los datos pueden recuperarse.

No obstante:

* borrar los datos del sitio puede eliminarlos;
* cambiar de navegador puede hacer que no aparezcan;
* utilizar otro dispositivo no comparte automáticamente la información.

---

# 🔐 Privacidad

El proyecto está diseñado para funcionar de forma local.

No requiere:

* registro;
* cuenta de usuario;
* contraseña;
* base de datos;
* servidor propio;
* envío de ubicación al desarrollador.

La ubicación seleccionada se utiliza internamente para mostrar los datos correspondientes.

Las coordenadas de cada concejo forman parte de los datos precargados.

---

# 🧑‍💻 Arquitectura técnica

El proyecto está deliberadamente construido sin frameworks.

## Stack

```text
HTML5
CSS3
JavaScript
SVG
Web Audio API
Vibration API
Clipboard API
Screen Wake Lock API
localStorage
```

No utiliza:

* React;
* Vue;
* Angular;
* jQuery;
* Bootstrap;
* Node.js;
* npm;
* Webpack;
* Vite;
* bases de datos.

Esto permite abrir el archivo directamente en un navegador.

---

# 📦 Estructura

El proyecto puede reducirse actualmente a:

```text
/
└── OMEGA-ECLIPSE-ASTURIAS-v7.html
```

El HTML contiene:

```text
HTML
├── estructura de la interfaz
├── CSS
│   ├── colores
│   ├── componentes
│   ├── responsive design
│   └── modo noche
└── JavaScript
    ├── datos astronómicos
    ├── datos geográficos
    ├── estado de la aplicación
    ├── buscador
    ├── ordenación
    ├── cuenta atrás
    ├── línea temporal
    ├── cálculo solar
    ├── alarmas
    ├── vibración
    ├── edición de tiempos
    ├── almacenamiento local
    └── enlaces externos
```

---

# 🧠 Datos internos

Los datos de cada concejo se almacenan en el array:

```javascript
var C = [...]
```

Cada registro utiliza la siguiente estructura:

```javascript
[
    nombre,
    población,
    latitud,
    longitud,
    probabilidad,
    duración,
    indicador_geográfico,
    zona,
    tiempos
]
```

Donde:

### `nombre`

Nombre del concejo.

### `población`

Localidad utilizada como referencia.

### `latitud`

Latitud geográfica en grados decimales.

### `longitud`

Longitud geográfica en grados decimales.

### `probabilidad`

Estimación porcentual propia del proyecto.

### `duración`

Duración estimada de la totalidad en segundos.

### `indicador_geográfico`

Indicador interno utilizado para señalar ubicaciones con determinadas condiciones de horizonte.

### `zona`

Clasificación interna de la ubicación.

### `tiempos`

Array con los cinco contactos:

```javascript
[
    C1,
    C2,
    MAX,
    C3,
    C4
]
```

---

# 🧮 Cálculos astronómicos

El proyecto no utiliza una librería astronómica externa para calcular la posición solar.

Implementa directamente un algoritmo aproximado basado en elementos orbitales del Sol.

El procedimiento calcula:

1. fecha juliana;
2. longitud solar;
3. anomalía solar;
4. longitud eclíptica;
5. oblicuidad de la eclíptica;
6. ascensión recta;
7. declinación;
8. tiempo sidéreo;
9. ángulo horario;
10. altura;
11. acimut.

La función principal es:

```javascript
sunPos(date, lat, lon)
```

y devuelve:

```javascript
{
    alt: ...,
    az: ...
}
```



---

# 📐 Modelo de duración de la totalidad

La duración de la totalidad no se obtiene simplemente interpolando los valores entre concejos.

El proyecto utiliza una relación geométrica basada en:

```text
D = Dmax · √(1 − (d/W)²)
```

donde:

* `D` = duración local;
* `Dmax` = duración máxima;
* `d` = distancia perpendicular al eje de la franja;
* `W` = semianchura de referencia.

La metodología documentada establece:

```text
rumbo del eje: 127°
semianchura: 164 km
duración máxima: 110,6 s
residuo medio: 1,9 s
```

según el modelo empleado en el proyecto. 

---

# ⏳ Precisión temporal

La metodología establece diferentes márgenes según la zona.

Como referencia:

```text
Centro de Asturias: ±10 s
Extremos oriental y occidental: ±30 s
```

Estos valores corresponden al modelo de estimación utilizado para generar los tiempos precargados. 

**Los tiempos oficiales del IGN tienen prioridad sobre los valores calculados por el proyecto.**

---

# 🧪 Limitaciones del modelo

Este proyecto no pretende ser un sustituto de:

* las predicciones oficiales;
* las efemérides del IGN;
* AEMET;
* las observaciones meteorológicas en tiempo real.

Su función es integrar información y hacerla operativa para un observador.

Especialmente:

### Meteorología

Las probabilidades son estimaciones y pueden fallar.

### Tiempos

Los tiempos precargados son aproximaciones y deben contrastarse con el IGN.

### Posición solar

La posición del Sol se calcula mediante un modelo implementado en JavaScript y no debe considerarse una efeméride de precisión profesional.

### Horizonte

La aplicación no conoce automáticamente los obstáculos reales del lugar:

* edificios;
* árboles;
* montañas;
* estructuras;
* humo;
* niebla;
* obstáculos locales.

Por ello, el gráfico de horizonte es una ayuda para la planificación, no un sustituto de visitar previamente el lugar.

---

# 🔗 Fuentes

El proyecto incorpora enlaces a las principales fuentes utilizadas para la preparación de la observación:

### Instituto Geográfico Nacional

```text
https://eclipses.ign.es/eclipse-total-sol-de-12-de-agosto-2026.html
```

### Visor de eclipses del IGN

```text
https://visualizadores.ign.es/eclipses/2026
```

### AEMET

```text
https://www.aemet.es
```

### Boletín especial de AEMET

```text
https://www.aemet.es/es/eltiempo/prediccion/destacados/p5_t?tipo=p51tesp1
```

### Eclipse Asturias 2026

```text
https://eclipseasturias2026.ficyt.es
```

### Trío Eclipses

```text
https://www.trioeclipses.es
```

Estos enlaces son los que la propia aplicación presenta al usuario desde la ficha de cada ubicación. 

---

# 🌐 Funcionamiento sin backend

Una de las características fundamentales del proyecto es que **no necesita un servidor propio para ejecutar la lógica principal**.

El navegador realiza localmente:

* búsqueda;
* ordenación;
* cálculos;
* cuenta atrás;
* representación gráfica;
* reproducción de sonidos;
* vibración;
* almacenamiento;
* edición de tiempos.

Por tanto, el archivo puede abrirse directamente:

```text
file:///...
```

aunque algunas APIs del navegador pueden requerir HTTPS o un contexto seguro.

---

# 📲 Diseño responsive

La interfaz está diseñada principalmente para dispositivos móviles.

El contenedor principal tiene una anchura máxima de:

```text
600 px
```

y utiliza un diseño adaptable.

Esto permite utilizar el mismo documento desde:

* smartphone;
* tablet;
* portátil;
* ordenador de sobremesa.

El diseño también contempla:

```css
env(safe-area-inset-bottom)
```

para dispositivos con áreas de seguridad del sistema operativo. 

---

# ♿ Accesibilidad

El proyecto incorpora varias medidas básicas:

* botones reales HTML;
* etiquetas `aria-label`;
* estados `aria-pressed`;
* elementos SVG con `role="img"`;
* título accesible para el gráfico;
* posibilidad de reducir las animaciones mediante `prefers-reduced-motion`.

Por ejemplo, la animación de alerta se desactiva cuando el sistema solicita reducir movimiento. 

---

# 🛠️ Desarrollo

## Requisitos

No es necesario instalar nada para modificar el proyecto.

Basta con:

* un editor de código;
* un navegador moderno;
* conocimientos básicos de HTML/CSS/JavaScript.

---

## Ejecutar localmente

La forma más sencilla es abrir:

```text
OMEGA-ECLIPSE-ASTURIAS-v7.html
```

en un navegador.

Para una experiencia más fiable, especialmente con APIs como:

* Clipboard;
* Wake Lock;
* Audio;

se recomienda servir el archivo mediante un servidor HTTP local.

Por ejemplo:

```bash
python3 -m http.server 8000
```

y abrir:

```text
http://localhost:8000
```

---

# 🧩 Modificar los datos

Los datos de los concejos se encuentran en:

```javascript
var C=[...]
```

Para añadir o modificar una ubicación debe respetarse exactamente la estructura de registros.

Ejemplo:

```javascript
[
    "Ejemplo",
    "Población",
    43.0000,
    -5.0000,
    40,
    100,
    1,
    "I",
    [
        "19:31:00",
        "20:27:00",
        "20:28:00",
        "20:29:00",
        "21:21:00"
    ]
]
```

Después de modificar datos se recomienda comprobar:

* orden cronológico;
* formato horario;
* latitud;
* longitud;
* duración;
* probabilidad;
* funcionamiento de la cuenta atrás.

---

# 🧱 Componentes principales del JavaScript

El código está organizado por bloques funcionales.

## Datos

```javascript
var C=[...]
```

Datos base de las ubicaciones.

## Estado

```javascript
var S={}
```

Objetos procesados utilizados por la interfaz.

## Persistencia

```javascript
cargar()
guardar()
```

Gestionan `localStorage`.

## Lista

```javascript
pintarLista()
```

Genera el listado de concejos.

## Posición solar

```javascript
sunPos()
dibujarHz()
pintarHz()
```

Calculan y representan la posición del Sol.

## Alarmas

```javascript
beep()
vib()
alarma()
```

Gestionan sonido y vibración.

## Detalle

```javascript
activar()
abrir()
volver()
```

Gestionan la navegación entre lista y ficha.

## Cronómetro

```javascript
tick()
```

Es el núcleo temporal de la aplicación y se ejecuta periódicamente.

---

# 🔄 Bucle principal

La función:

```javascript
tick()
```

se ejecuta cada:

```text
250 ms
```

Esto permite actualizar:

* reloj;
* cuenta atrás;
* fase actual;
* progreso;
* línea temporal;
* posición del Sol;
* alarmas.



---

# 🧭 Estados del eclipse

Internamente se distinguen cinco grandes estados:

```text
ANTES
  ↓
PARCIAL CRECIENTE
  ↓
TOTALIDAD
  ↓
PARCIAL MENGUANTE
  ↓
FINALIZADO
```

Cada estado modifica simultáneamente:

* texto;
* colores;
* cuenta atrás;
* instrucciones;
* barra de progreso;
* alarmas.

---

# 🗃️ Persistencia de tiempos oficiales

Cuando el usuario introduce tiempos oficiales, estos se guardan junto con una marca:

```javascript
of: true
```

Cuando se vuelven a utilizar, la interfaz los identifica como:

```text
Tiempos oficiales IGN
```

Si se restauran los valores originales, desaparece esa marca. 

---

# 🧹 Restaurar datos

La aplicación incorpora:

```text
Restaurar valores de partida
```

Esto elimina la modificación local de los tiempos del concejo seleccionado y devuelve los datos precargados.

No modifica el código fuente.

---

# 🌍 Dependencias externas

El proyecto **no depende de paquetes JavaScript externos**.

Sí depende conceptualmente de información externa para:

* datos oficiales;
* meteorología;
* comprobación de tiempos;
* información del eclipse.

Estos recursos se abren mediante enlaces externos.

La aplicación no realiza automáticamente peticiones AJAX a estos servicios.

---

# 🚀 Despliegue

Debido a su arquitectura estática, el proyecto puede desplegarse fácilmente en cualquier servicio capaz de servir archivos HTML.

Por ejemplo:

* GitHub Pages;
* servidor web convencional;
* alojamiento estático;
* intranet;
* almacenamiento local.

No necesita:

```text
Node.js
PHP
Python
MySQL
API propia
backend
base de datos
```

para funcionar.

---

# 🐛 Problemas conocidos

## El sonido no funciona

Algunos navegadores bloquean la reproducción de audio hasta que el usuario interactúa con la página.

**Solución:** pulsar un botón de la aplicación antes de esperar las alarmas.

---

## La vibración no funciona

No todos los navegadores o dispositivos implementan:

```javascript
navigator.vibrate()
```

La aplicación simplemente continúa funcionando sin vibración.

---

## La pantalla se apaga

El Screen Wake Lock depende del navegador, del dispositivo y del contexto de seguridad.

Si no está disponible, el usuario debe mantener la pantalla activa manualmente.

---

## El botón Copiar no funciona

La aplicación incluye un método alternativo que selecciona automáticamente las coordenadas para permitir copiarlas manualmente. 

---

## La meteorología no coincide

Es normal.

La probabilidad incluida en la aplicación es una estimación propia y no una predicción meteorológica oficial.

La información debe contrastarse con AEMET y el visor correspondiente. 

---

# ⚠️ Aviso importante sobre la seguridad

Esta aplicación es una herramienta de apoyo a la observación.

**No debe utilizarse como único sistema de seguridad.**

En particular:

* no se debe mirar al Sol durante las fases parciales sin protección adecuada;
* las alarmas pueden no sonar;
* el teléfono puede quedarse sin batería;
* el navegador puede suspender la página;
* el dispositivo puede perder precisión temporal;
* una estimación meteorológica puede resultar incorrecta.

Durante la totalidad, la observación a simple vista es segura **únicamente mientras el Sol esté completamente cubierto**.

Al primer destello de luz solar:

> **las gafas deben estar puestas.**

La propia aplicación incluye esta advertencia de forma explícita. 

---

# 🛰️ Filosofía del proyecto

El proyecto se ha diseñado siguiendo una idea sencilla:

> **La tecnología debe desaparecer durante el eclipse.**

La aplicación no pretende que el usuario pase el eclipse mirando una pantalla.

Su función es ayudar a preparar el lugar, comprobar los datos y avisar de los momentos importantes para que, cuando llegue la totalidad, el teléfono deje de ser protagonista y el cielo pase a ocupar toda la atención.

Por eso se priorizan:

* información clara;
* pocos controles;
* lectura rápida;
* funcionamiento local;
* alarmas;
* contraste con fuentes oficiales;
* ausencia de dependencias innecesarias.

---

# 🤝 Contribuir

Las contribuciones son bienvenidas.

Puedes contribuir mediante:

### Correcciones

* errores de interfaz;
* errores de cálculo;
* errores tipográficos;
* problemas de compatibilidad.

### Mejoras

* accesibilidad;
* compatibilidad móvil;
* rendimiento;
* representación astronómica;
* visualización de datos.

### Nuevas funciones

Por ejemplo:

* mapa interactivo;
* GPS;
* cálculo automático del horizonte;
* información de tráfico;
* meteorología en tiempo real;
* PWA;
* modo offline mejorado;
* exportación de horarios;
* sincronización con fuentes oficiales.

---

# 📋 Antes de modificar datos astronómicos

Cualquier modificación de:

* tiempos;
* duración;
* coordenadas;
* trayectoria;
* datos meteorológicos;
* probabilidades;

debería estar respaldada por una fuente identificable.

No se recomienda modificar los valores simplemente para que "parezcan" más coherentes.

Cuando existan datos oficiales del IGN, estos deben tener prioridad sobre cualquier estimación propia.

---

# 🔬 Principios científicos

El proyecto intenta mantener una separación clara entre:

### Datos oficiales

Procedentes de organismos como:

* Instituto Geográfico Nacional;
* Observatorio Astronómico Nacional;
* AEMET.

### Estimaciones del proyecto

Especialmente:

* probabilidades meteorológicas;
* modelos simplificados;
* determinados tiempos interpolados;
* visualizaciones.

La interfaz intenta hacer visible esta diferencia para evitar presentar una estimación como si fuese un dato oficial. 

---

# 📚 Referencias internas del proyecto

La aplicación identifica expresamente como referencias:

```text
Instituto Geográfico Nacional
Observatorio Astronómico Nacional
OMEGA · 12 · 08 · 2026
```



---

# 🏛️ Créditos

Proyecto desarrollado por:

## Sociedad Astronómica Asturiana OMEGA

El proyecto nace en el contexto de la preparación y divulgación del eclipse total de Sol del 12 de agosto de 2026 desde Asturias.

La aplicación combina trabajo de divulgación astronómica, tratamiento de datos, programación web y preparación de la observación de campo.

---

# 📅 Estado del proyecto

**Estado:** `FINAL / ECLIPSE DAY`

**Fecha del evento:**

```text
12 de agosto de 2026
```

**Estado temporal del proyecto:**

> 🔴 **Hoy es el día del eclipse.**

La versión actual está concebida principalmente como herramienta operativa para el día del evento.

Una vez finalizado el eclipse, el proyecto puede conservarse como:

* registro histórico;
* demostración técnica;
* archivo de datos;
* referencia para futuros proyectos;
* base para herramientas astronómicas posteriores.

---

# 🌑 Después del eclipse

Aunque la herramienta ha sido diseñada para el 12 de agosto de 2026, el código puede evolucionar hacia una aplicación más general.

Posibles líneas futuras:

```text
OMEGA Eclipse Engine
        │
        ├── Eclipse 2026 · Asturias
        ├── Eclipse 2027 · España
        ├── Eclipse 2028
        ├── Eclipses históricos
        └── Herramienta general de observación
```

La separación entre:

* datos;
* cálculo;
* interfaz;
* alarmas;
* persistencia;

facilitaría convertir la aplicación en una herramienta reutilizable para futuros eclipses.

---

# 📜 Licencia

Consultar el archivo `LICENSE` del repositorio para conocer las condiciones concretas de uso, modificación y redistribución.

Los datos procedentes de organismos oficiales y las fuentes externas utilizadas por el proyecto mantienen las condiciones de uso correspondientes a sus respectivos propietarios.

---

# ❤️ Una última cosa

Este proyecto no pretende competir con el IGN ni con AEMET.

Pretende hacer algo diferente:

**poner información científica compleja en manos de una persona que, probablemente, solo quiere saber tres cosas:**

> **¿Dónde me pongo?**
> **¿Cuándo ocurre?**
> **¿Cuándo tengo que quitarme las gafas?**

Y hacerlo sin que tenga que entender cómo funciona un modelo meteorológico, una efeméride solar o un algoritmo astronómico.

Hoy, **12 de agosto de 2026**, después de meses de preparación, el código deja de ser solamente un proyecto y se convierte en una herramienta de observación.

**Ahora toca mirar al cielo. 🌑**

---

## 🔗 Recursos oficiales

* Instituto Geográfico Nacional — Eclipse del 12 de agosto de 2026
* Visor de eclipses del IGN
* AEMET
* Eclipse Asturias 2026
* Trío Eclipses

Los enlaces anteriores están integrados también dentro de la aplicación para facilitar su consulta durante la preparación de la observación. 

---

**Raúl Pardo · OMEGA · Sociedad Astronómica Asturiana OMEGA**
**12 de agosto de 2026 · Asturias**
**Eclipse total de Sol**


NOTA: ESTE README HA SIDO PARCIALMENTE DESARROLLADO CON INTELIGENCIA ARTIFICIAL DADAS LAS LIMITACIONES DE TIEMPO.
