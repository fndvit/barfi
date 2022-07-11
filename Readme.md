# Barfi: a tool to create tile grid maps and cartograms for UNEP's climate crisis communications
Xaquín Veira-González[^a] [^b] (xaquin@fundaciovit.org), Anton Bardera[^a] [^b] (anton.bardera@imae.udg.edu), Matt Osborn[^a] (mattjosborn@gmail.com), Aleix Alvarez-Calafell[^a] (u1956244@campus.udg.edu), Miguel Villalobos-Jiménez[^a] (miguel7vj@gmail.com), Karma Peiró[^a] (karma@fundaciovit.org)

[^a]: Fundació Visualització per a la Transparència (ViT)
[^b]: Graphics and Imaging Laboratory, Universitat de Girona

**Barfi** is an interactive tool to create square (Demers) cartograms using a force-directed layout. It spun off a collaboration with the United Nations Environment Programme and a good bunch of design restrictions when visualizing data about the climate crisis.

**Why Barfi?**

```
Because the tool uses *d3-force* (a force-directed graph drawing algorithm) →
→ Matt called the original repo *cartogram fdg* →
→ *fdg* reads as *fudge* →
→ we love an Indian fudge-like dessert called **Barfi**, that happens to be cut in **squares**.
```

## 

We presented the tool in the 2022 Open GIS Conference organized by Universitat de Girona's SIGTE.
* [Watch the presentation](http://diobma.udg.edu/handle/10256.1/6776)
* You can follow along with the slides (the slides in the video are too bright)
* Read the summary in [English](#tiles-demers-and-climate-data), [Spanish](#teselas-demers-y-los-datos-geoclimáticos-de-la-onu
), [Catalan](#rajoles-demers-i-les-dades-geoclimàtiques-de-lonu
)

[GIF OF TOOL FLOW]

Here're some examples with the results of our tool
* [Climate Action Note](https://www.unep.org/explore-topics/climate-action/what-we-do/climate-action-note/state-of-climate.html)
* [Air Pollution Action Note](https://www.unep.org/interactive/air-pollution-note/)

![Poster image of UNEP's Climate Action Note](https://cdn.unenvironment.org/s3fs-public/2021-11/ClimateAction-Banner.jpg)

We're currently working on a paper looking at the task-based effectiveness of these visualizations.

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

## Tiles, Demers and Climate Data
The Visualization for Transparency Foundation (ViT) collaborates since 2020 with the United Nations Environment Program (UNEP) in the design and development of data dashboards about climate change and pollution in the context of the program's digital communication plan. These projects required multiple country-by-country data visualizations.

The UN, being an intergovernmental institution, adopts a neutral position in territorial disputes between different countries, which somewhat complicated the use of standard choropleth maps. The project also had some constraints intrinsic to the display. There were countries with a small geographical area, but with significant data to highlight, and vice versa. For example, Qatar's per capita emissions are very high, even though the area of ​​the country is not. Additionally, we had data in many shapes and format: simple numerical data, but also timeseries, distributions, categorical data or text lists.

Taking these restrictions into account, we decided to opt for two types of grammatically related visualizations: tile grid maps and Demers cartograms (Bortins et al., 2002).

In tile grid maps, admin divisions become cells arranged on a grid that fits their geographic layout. Each cell allows multiple possibilities: a class can be displayed by color, a line plot to show a time trend, a histogram to show a statistical distribution, or a broken bar to show parts of a total.

In Demers cartograms, admin units are visually coded as squares and geography is approximated. The visual mark, the square in this case, allows you to encode a numerical variable through area and a categorical variable through color.

Another advantage of this design solution is the use of the same visual mark, in this case squares, which allows us to create transitions between maps that facilitate a fluid sequential narrative.

To automate this type of cartogram, the team developed a tool that uses force-directed graph drawing to find the spatial distribution of cartograms. Force-based design is a method of generating aesthetically pleasing graphs when the simulation finds equilibrium. Specifically, the program uses d3-force, an algorithm that simulates, in a simplified way, the physical forces between “particles” —in this case squares that represent the countries. As a starting point for the simulation, the tool allows us to change the projection used and the minimum and maximum area for ​​the visual marks. Once the simulation is finished, the user can refine the spatial distribution manually. The program exports a JSON object with the coordinates and dimensions of the map for later use within a web component.