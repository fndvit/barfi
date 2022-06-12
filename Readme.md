# Barfi: a tool to create tile grid maps and cartograms for UNEP's climate crisis communications
Xaquín Veira-González[^a] [^b] (xaquin@fundaciovit.org), Anton Bardera[^a] [^b] (anton.bardera@imae.udg.edu), Matt Osborn[^a] (mattjosborn@gmail.com), Aleix Alvarez-Calafell[^a] (u1956244@campus.udg.edu), Miguel Villalobos-Jiménez[^a] (miguel7vj@gmail.com), Karma Peiró[^a] (karma@fundaciovit.org)

[^a]: Fundació Visualització per a la Transparència (ViT)
[^b]: Graphics and Imaging Laboratory, Universitat de Girona

Summary TK TK

```
**Why Barfi?**
Because the tool uses *d3-force* (a force-directed graph drawing algorithm) →
→ Matt called the original repo *cartogram fdg* →
→ *fdg* reads as *fudge* →
→ we love an Indian fudge-like dessert called **Barfi**, that happens to be cut in **squares**.
```

## 

We presented the tool in the 2022 Open GIS Conference organized by Universitat de Girona's SIGTE.
* Watch the presentation
* You can follow along with the slides
* Read the summary in [English](#this), [Spanish](#teselas-demers-y-los-datos-geoclimáticos-de-la-onu
), [Catalan](#rajoles-demers-i-les-dades-geoclimàtiques-de-lonu
)

[GIF OF TOOL FLOW]

Here're some examples with the results of our tool
* [Climate Action Note](https://www.unep.org/explore-topics/climate-action/what-we-do/climate-action-note/state-of-climate.html)
* [Air Pollution Action Note](https://www.unep.org/interactive/air-pollution-note/)

[IMAGE OF CLIMATE ACTION NOTE]

We've also submitted it for TK TK and 

## To do before open sourcing:
- [ ] Add your own geography
- [ ] Auto ‘snap to grid’ on tile grid maps
- [ ] Facelift to the interface
- [ ] Research opportunity: crowdtesting projections

## Rajoles, Demers i les dades geoclimàtiques de l'ONU
La Fundació Visualització per a la Transparència (ViT) col·labora des de l’any 2020 amb el Programa de les Nacions Unides per al Medi Ambient (PNUMA) en el disseny i desenvolupament de panells de dades sobre canvi climàtic i contaminació en el context del pla de comunicació digital del programa de l’ONU. Dins el context d’aquests projectes, hi apareixen nombroses visualitzacions de dades geogràfiques.

L’ONU, en ser una institució intergovernamental, adopta una posició neutral en les disputes territorials entre els diversos països, fet que limita l’establiment d’unes línies concretes que defineixin amb detall les fronteres entre països. Això restringia l’ús de mapes de coropletes estàndards en la visualització de les dades. En el projecte també hi havia nombroses restriccions intrínseques de la visualització. En primer lloc, ens vam trobar que hi havia països amb una àrea geogràfica petita, però amb dades significatives que calia destacar, i viceversa. Per exemple, les emissions per càpita de Qatar mostren un valor molt elevat, per bé que l’àrea del país no ho és. Una altra problemàtica va ser la disparitat del format de les dades, ja que teníem simples dades numèriques, però també dades temporals, distribucions, dades categòriques o llistats en format text.

Tenint en compte aquestes restriccions, vam decidir optar per dos tipus de visualitzacions gramaticalment relacionades: els diagrames de rajoles (tile grid maps, en anglès) i els cartogrames Demers (Bortins et al., 2002).

En els diagrames de rajoles, les divisions administratives es converteixen en cel·les que es distribueixen en una retícula que s’ajusta a la seva distribució geogràfica. Cada cel·la permet múltiples possibilitats: pot visualitzar una classe mitjançant el color, una gràfica de línia per a mostrar una tendència temporal, un histograma per a mostrar una distribució estadística, o una barra trencada per a mostrar parts d’un total.

En els cartogrames Demers, les unitats administratives es codifiquen com a quadrats i la geografia s’aproxima. La marca visual, el quadrat en aquest cas, permet codificar una variable numèrica mitjançant l’àrea i una variable categòrica mitjançant el color.
Un altre dels avantatges d’aquesta solució de disseny és l’ús de la mateixa marca visual, en aquest cas quadrats, fet que ens permet crear transicions entre mapes que faciliten una narrativa seqüencial fluïda.

Per automatitzar aquest tipus de cartogrames, l’equip va desenvolupar una eina que utilitza el disseny basat en forces (force-directed drawing/layout, en anglès) per trobar la distribució espacial dels cartogrames. El disseny basat en forces és un mètode per generar grafs estèticament grats quan la simulació troba equilibri. El programa utilitza concretament d3-force, un algorisme que simula de manera simplificada les forces físiques entre “partícules”, en aquest cas quadrats, que representen els països. Com a punt de partida per a la simulació, l’eina permet canviar la projecció utilitzada i l’àrea mínima i màxima de les marques visuals. Un cop acabada la simulació, l’usuari pot refinar la distribució espacial de manera manual. El programa exporta un objecte JSON amb les coordenades i les dimensions del mapa per al seu ús posterior dins d’un component web.

## Teselas, Demers y los datos geoclimáticos de la ONU
La Fundación Visualización para la Transparencia (ViT) colabora desde el 2020 con el Programa de Naciones Unidas para el Medio Ambiente (PNUMA) en el diseño y desarrollo de paneles de datos sobre cambio climático y contaminación en el contexto del plan de comunicación digital del programa de la ONU. Dentro del contexto de estos proyectos, aparecen numerosas visualizaciones de datos geográficos.

La ONU, al ser una institución intergubernamental, adopta una posición neutral en las disputas territoriales entre los distintos países, lo que limita el establecimiento de unas líneas concretas que definan con detalle las fronteras entre países. Esto restringía el uso de mapas de coropletas estándar en la visualización de los datos. El proyecto también presentaba numerosas restricciones intrínsecas de la visualización. En primer lugar, nos encontramos con que había países con un área geográfica pequeña, pero con datos significativos a destacar, y viceversa. Por ejemplo, las emisiones per cápita de Qatar muestran un valor muy elevado, si bien el área del país no lo es. Otra problemática fue la disparidad del formato de los datos, puesto que teníamos simples datos numéricos, pero también datos temporales, distribuciones, datos categóricos o listados en formato texto.

Teniendo en cuenta estas restricciones, decidimos optar por dos tipos de visualizaciones gramaticalmente relacionadas: los diagramas de azulejos (tile grid maps, en inglés) y los cartogramas Demers (Bortins et al., 2002).

En los diagramas de azulejos, las divisiones administrativas se convierten en celdas que se distribuyen en una retícula que se ajusta a su distribución geográfica. Cada celda permite múltiples posibilidades: puede visualizarse una clase mediante el color, una gráfica de línea para mostrar una tendencia temporal, un histograma para mostrar una distribución estadística o una barra rota para mostrar partes de un total.

En los cartogramas Demers, las unidades administrativas se codifican como cuadrados y se aproxima la geografía. La marca visual, el cuadrado en este caso, permite codificar una variable numérica mediante el área y una variable categórica mediante el color.
Otra de las ventajas de esta solución de diseño es el uso de la misma marca visual, en este caso cuadrados, lo que nos permite crear transiciones entre mapas que facilitan una narrativa secuencial fluida.

Para automatizar este tipo de cartogramas, el equipo desarrolló una herramienta que utiliza el diseño basado en fuerzas (force-directed drawing/layout, en inglés) para hallar la distribución espacial de los cartogramas. El diseño basado en fuerzas es un método para generar grafos estéticamente agradables cuando la simulación encuentra equilibrio. El programa utiliza concretamente d3-force, un algoritmo que simula de manera simplificada las fuerzas físicas entre “partículas”, en este caso cuadrados, que representan a los países. Como punto de partida para la simulación, la herramienta permite cambiar la proyección utilizada y el área mínima y máxima de las marcas visuales. Una vez terminada la simulación, el usuario puede refinar la distribución espacial de forma manual. El programa exporta un objeto JSON con las coordenadas y dimensiones del mapa para su uso posterior dentro de un componente web.