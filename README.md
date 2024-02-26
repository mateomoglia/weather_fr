# Weather data in France

This project is part of my PhD thesis. 

_(still work in progress)_

I present how to:

- download weather data in ``nc_data`` format from Copernicus
- extract relevant information
- create a panel data at the municipal level with precipitations and temperature

The project is written in R, and mainly uses ``terra`` and ``sf`` packages.

_there are obviously faster/cleaner solutions, but this is the one I came up with, hoping it my be useful to anyone. comments are more than welcomed_

### Sources

Data are mainly from the Copernicus project. They can be downloaded [here](https://surfobs.climate.copernicus.eu/dataaccess/access_eobs_chunks.php). Data are in version 28, for 2011-2023 and were accessed in February 2024. 

I use the 0.1°x0.1° resolution, and the more specific information on rainfall (RR) and temperature (TG). 

Two shapefiles are used: one for France's extent (downloaded [here](https://ec.europa.eu/eurostat/fr/web/gisco/geodata/reference-data/administrative-units-statistical-units/nuts)) and one for French municipality in their *2020 geography* (downloaded [here](https://www.data.gouv.fr/fr/datasets/decoupage-administratif-communal-francais-issu-d-openstreetmap/)). 

| Data               | Source             | Format    | Link                                                                                              |
|--------------------|--------------------|-----------|---------------------------------------------------------------------------------------------------|
| Weather data       | Copernicus (2011-2023) | `nc_data` | [Link](https://surfobs.climate.copernicus.eu/dataaccess/access_eobs_chunks.php)                   |
| France             | Eurostat           | `shp`     | [Link](https://ec.europa.eu/eurostat/fr/web/gisco/geodata/reference-data/administrative-units-statistical-units/nuts) |
| Municipalities (2020) | OSM              | `shp`     | [Link](https://www.data.gouv.fr/fr/datasets/decoupage-administratif-communal-francais-issu-d-openstreetmap/) |

## Roadmap

The project is separated in three parts:

1. Open and clean the raster data 
2. Open and clean the shapefile of cities
3. Create a panel of weather data at the municipal level in France



## Author

Matéo Moglia, PhD student at CREST/IP-Paris.
[Website](https://mateomoglia.github.io)
[Twitter](https://twitter.com/MateoMogliaEcon)

