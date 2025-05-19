
## Exploring the Distribution of Traffic Accidents in the Antofagasta Region, Chile

### Administrative Context of the Antofagasta Region

The Antofagasta region covers an area of 126,049.1 km² and has a population of 444,276 inhabitants, according to the 2024 Census. Administratively, it is composed of three provinces (Antofagasta, El Loa, and Tocopilla), which are divided into nine communes: Antofagasta, Calama, Tocopilla, Mejillones, María Elena, Taltal, Sierra Gorda, San Pedro de Atacama, and Ollagüe. The regional capital is the city of Antofagasta.

### Traffic Accidents in Chile

In Chile, traffic accidents result in an average of around 1,500 deaths annually, a figure that has remained relatively stable, although with a slight decrease of 12% during 2023 (CONASET, 2023). The main cause of these accidents is human error, with driver and pedestrian negligence being the most frequent reasons for fatal accidents. In the Antofagasta region, while the number of accidents has been increasing, the number of fatalities and injuries remains below the national average. Most accidents occur in urban areas.

### Research Questions and Repository Content

This project addresses the final assignment for the GEOG5990M module and aims to answer the following questions:

- Is the distribution of traffic accidents in the Antofagasta commune random, or does it follow a spatial pattern? Is there spatial autocorrelation to support this?
- Are fatal accidents in the Antofagasta commune located in areas with a higher overall concentration of accidents?

The `Data` folder includes five GeoJSON files: four contain traffic accident records from 2019 to 2022, and one contains the political-administrative boundaries of the region. It is important to note that the accident files vary in structure and column names. The following common variables were selected and renamed in English for consistency:

- `'Año'`: Year when the accident occurred  
- `'Fecha'`: Date and time of the accident  
- `'Región'`: Name of the region  
- `'Comuna'`: Name of the commune  
- `'Tipo__CONA'`: Accident subtype (CONASET classification)  
- `'Causa__CON'`: Secondary cause (CONASET classification)  
- `'Fallecidos'`: Number of fatalities  
- `'Graves'`: Number of people with serious injuries  
- `'Menos_Grav'`: Number of people with moderate injuries  
- `'Leves'`: Number of people with minor injuries  
- `'geometry'`: Geometry type (POINT)

### Code Overview

The code follows the data science process. After cleaning the data, a regional-level exploration is conducted to analyze accident patterns by commune and type. The analysis then focuses on the communes of Antofagasta and Calama, including a detailed look at fatal accidents and their causes.

An initial attempt was made to apply K-Means clustering using the elbow method to identify accident clusters. However, due to unsatisfactory results, the methodology was switched to Uber’s H3, which divides space into hexagonal cells. This approach allows for a clearer visualization of accident concentration and spatial distribution.

To assess spatial autocorrelation, the Global Moran’s Index was calculated. To identify the specific locations of spatial clusters, the Local Moran’s Index (LISA) was applied.

### Final Visualisations

The non-spatial visualisations include four horizontal bar charts showing the total number of accidents in Antofagasta and Calama, categorized by accident type and associated fatalities.

![Image](https://github.com/user-attachments/assets/af5f5c74-fce6-4fbb-9fdd-b07723a2ab93)

The spatial visualisation displays accident concentration using H3 hexagons and includes the precise locations of fatal accidents.

![Image](https://github.com/user-attachments/assets/ae152803-a1d6-4a83-846a-f1bdb9a7cac9)
