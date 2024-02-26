# Weather data in France

This project is part of my PhD thesis. 

_(still work in progress)_

## Objectives

I present how to:

- download weather data in ``nc_data`` format from Copernicus
- extract relevant information
- create a panel data at the municipal level with precipitations and temperature


## Software used

The project is written in R, and mainly uses ``terra`` and ``sf`` packages.

## Sources

Data are mainly from the Copernicus project. They can be downloaded [here](https://surfobs.climate.copernicus.eu/dataaccess/access_eobs_chunks.php). Data are in version 28, for 2011-2023 and were accessed in February 2024. 

I use the 0.1°x0.1° resolution, and the more specific information on rainfall (RR) and temperature (TG). 

## Author

Matéo Moglia, PhD student at CREST/IP-Paris.
[Website](https://mateomoglia.github.io)
[Twitter](https://twitter.com/MateoMogliaEcon)

