# Weather data in France

This project is part of my PhD thesis. 

_(still work in progress)_

I present how to:

- download weather data in ``nc_data`` format from Copernicus
- extract relevant information
- create a panel data at the municipal level with precipitations and temperature

The project is written in R, and mainly uses ``terra`` and ``sf`` packages. This readme guides you through the codes, which can also be download or forked from this repo. 

_there are obviously faster/cleaner solutions, but this is the one I came up with, hoping it my be useful to anyone. comments are more than welcomed_

### Sources

Data are mainly from the Copernicus project. They can be downloaded [here](https://surfobs.climate.copernicus.eu/dataaccess/access_eobs_chunks.php). Data are in version 28, for 2011-2023 and were accessed in February 2024. I use the 0.1°x0.1° resolution, and the more specific information on rainfall (RR) and temperature (TG). 

We use the OSM shapefile of French municipality in their *2020 geography* (downloaded [here](https://www.data.gouv.fr/fr/datasets/decoupage-administratif-communal-francais-issu-d-openstreetmap/)). 

<div align="center">
  
| Data               | Source             | Format    | Link                                                                                              |
|--------------------|--------------------|-----------|---------------------------------------------------------------------------------------------------|
| Weather data       | Copernicus (2011-2023) | `nc_data` | [Link](https://surfobs.climate.copernicus.eu/dataaccess/access_eobs_chunks.php)                   |
| Municipalities (2020) | OSM              | `shp`     | [Link](https://www.data.gouv.fr/fr/datasets/decoupage-administratif-communal-francais-issu-d-openstreetmap/) |

**Table: Summary of sources**

</div>

### Roadmap

The project is separated in three parts:

1. Open and clean the raster data 
2. Open and clean the shapefile of cities
3. Create a panel of weather data at the municipal level in France

### Author

Matéo Moglia, PhD student at CREST/IP-Paris.
[Website](https://mateomoglia.github.io)
[Twitter](https://twitter.com/MateoMogliaEcon)

## Setting up the libraries and data

We load the relevant libraries and the two key datasets:



## Create a crosswalk between city map and raster

The key issue of this project is to match each city (stored as polygons in `city.shp`) and the corresponding cell(s) in the weather data. 

### Open the shapefile of cities

We open the shapefile, remove the non-continental cities (with `INSEE_COM` not starting with 97) and get the extent of the shapefile.

```r
  # Open the shp
city.shp = read_sf(paste0(path,"/../shp/shp_co2020.shp")) %>% 
  arrange(INSEE_COM) %>%
  mutate(num = row_number()) %>%
  dplyr::select(num,INSEE_COM,geometry)

  # Select only cities in continental France (+ Corsica)
  # -> cities with INSEE_COM < 97000
city.shp = city.shp %>%
  filter(substr(INSEE_COM,1,2)!="97")

  # Extract the extent of city
city.ext = extent(city.shp)
```

### Open the raster of precipitation




