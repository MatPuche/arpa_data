# arpa_data
QGIS Plugin enabling to extract weather and air quality data of ARPA Lombardia.


# Installation 

The plugin is called "ARPA data” and needs to be installed manually. Plugins  in  QGIS  are stored in a special folder. We must copy the plugin directory to that folder before it can be used. 

#### 1) Download  the  entire  directory  from  GitHub and unzip it
#### 2) In QGIS, locate your current profile folder by going to Settings ‣ User Profiles ‣ Open Active Profile Folder.
#### 3) Copy the plugin folder previsouly unziped to python ‣ plugins subfolder. 
#### 4) Then, the “sodapy” Python library must be installed to make the plugin work. This can be done in two different ways: inside QGIS or from the command line.
##### Inside QGIS
Open  QGIS  Python  console  (under  Plugins  »  Python  Console)  and  typethe  following  lines:
```
>> import pip
>> pip.main(['install', 'sodapy'])
```
##### From the command line
On Linux systems, QGIS use the main Python installation, so the only thing to do is to run in the command line: (pip must be installed)
```
$ pip install sodapy
```
On  Windows,  QGIS  has  its  own  Python,  so  the  library must be  installed  in  the  right  one. Navigate to **C:\QGIS\apps\Python27\** or **C:\QGIS\apps\Python37**. Open command prompt or powershell here and type: 
On Linux systems, QGIS use the main Python installation, so the only thing to do is to run in the command line: (pip must be installed)
```
$ python -m pip install sodapy
```
More information can be found on the GitHub repository of sodapy: https://github.com/xmunoz/sodapy

#### 5) Finally, the plugin should appear in the Plugins management box of QGIS, in installed plugins and only needs to be activated as a usual plugin. 


# Plugin functionalities

## Available data:
The plugin enables to request the ARPA datasets regarding Weather or Air quality. 

### Types of sensor for Air quality: 
- Ammoniaca, 
- Arsenico, 
- Benzene, 
- Benzo(a)pirene, 
- Biossido di Azoto, 
- Biossido di Zolfo, 
- BlackCarbon, 
- Cadmio, 
- Monossido di Azoto, 
- Monossido di Carbonio, 
- Nikel, 
- Ossidi di Azoto, 
- Ozono, 
- Particelle sospese PM2.5, 
- Particolato Totale Sospeso, 
- Piombo, 
- PM10, 
- PM10 (SM2005). 

### Types of sensor for Weather : 
- Altezza Neve, 
- Direzione Vento, 
- Livello Idrometrico, 
- Precipitazione, 
- Radiazione Globale, 
- Temperatura, 
- Umidità Relativa, 
- Velocità Vento

### Limitations on data
Some limitations are imposed by the ARPA API:
- For weather, only the data of the current month are available, with a monitoring frequency of 10 min.
- For the air quality, the data of the current year are available, with a monitoring frequency of 1 hour.

Also, some of the air quality sensors may not be always working (for example: Arsenico, Benzo(a)pirene, Cadmio, Nikel, Particolato Totale Sospeso, Piombo and PM10)

## Available functionalities:
- Select the range of time (start and end date of monitoring)
- Distinction between weekends and weekdays 
- Having only stations locations, with the checkbox "No data"
- Include the visualization, when one sensor is selected, by means of histograms 
- Include raw data, when one sensor is selected. ***/!\ This could require more time than the usual process.***
- Include a shapefile with multipolygons to define the areas of interest ***/!\ The CRS of the inserted shapefile must be WSG84***
- Fisher test on statistics per area


## Results

- One map of polygons representing the areas of interest.
- One map of points representing the stations concerned by the filters and containing some metadata
- One map of points representing the sensors concerned by the filters and containing the computed statistics for each sensor
- One map of points representing the centroid of each of the areas of interest. Each point contains the statistics of the sensor types for the concerned area.
- (If the raw data have been asked:) One map of points containing all the measurements in the period selected. 

All these layers are temporary layers and need to be saved if the user wants to use them in future sessions. ***They must be saved as Geopackage*** in order to keep the attribute names as they are in the layers. 

For more details, see the pdf report called "Report - June 2021".
