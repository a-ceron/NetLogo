NetLogo es una tecnología que puede ser usada para modelar sistemas complejos con autómatas celulares o para cualquier actividad discreta. 
#
----

# Preparación del entorno
NetLogo es una herramienta que permite diseñar y programar modelos de forma dinámica, para el lado gráfico se cuentan con elementos que pueden ser posicionados y ajustados con la interfaz gráfica. 

Primero realice un boceto en mi cuaderno de cómo esperaba que se viera el entorno y acto seguido comence a generar la interfaz, lo cual se traduce en el arrastre de los diferentes elementos gráficos de netlogo a la posición de mi gusto, ajustar las dimensiones y establecerle los parámetros que cada elemento necesita.

:::image type="content" source="img/interfaz_v.png" alt-text="diseño":::

# Setup
Como primer paso agregue el código necesario para generar a mis humanos y a mis moscos.

```netlogo
    ;;Generamos algunas razas
breed [mosquitos mosco]
breed [humanos humano]

;; Generamos algunas variables para nuestros agentes
mosquitos-own[
  n_dias ;;Establece el tiempo de vida del mosquito
  infectado ;;Establece si esta, o no, infectado
]
humanos-own[
  n_inmunidad  ;; Establece el tiempo de inmunidad
  infectado
]


to setup    
  ;;Configuración inicial del programa
  clear-all
  preparar-humanos
  preparar-mosquitos
  reset-ticks
end

```

En las primeras lineas del código mostrado se generan dos razas humanos y mosquitos. Después de ello se establecieron variables para cada una de las razas y al último se configuro la función setup que inicializa el entorno.

El setup a su vez tiene dos funciones, la primera genera los humanos iniciales y la segunda genera los moquitos iniciales. 
En cada una de las funciones se les asigno los parámetros necesarios que definen a un humano y a un mosquito

:::image type="content" source="img/interfaz.png" alt-text="steup":::

# Play
El segmento play tenemos la lógica del programa, que se define con cuatro funciones, las primeras funciones realizan infecciones y las últimas modifican las variables de los agentes.

```
to play
  ;;add.Condición de paro
  infectar-humanos
  infectar-mosquitos
  
  generar_mosquitos
  tick  ;;Avanzamos en el tiempo
  
  actualizar-mosquitos
  actualizar-humanos
 
end
```

# Resultados
En la figura de abajo podemos observar una corrida del modelo generado.

En la figura se exiben diferentes comportamientos que nos hacen pensar si el modelo se desarrolla de forma exitosa pues, en el tiempo no hay una *epidemia* grande. Aspecto que me deja a pensar si hay algo mal en mi código. 

:::image type="content" source="img/resutados.png" alt-text="resultados":::