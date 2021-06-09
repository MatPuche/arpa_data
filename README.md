# arpa_data
QGIS Plugin enabling to extract weather and air quality data of ARPA Lombardia.


INSTALLATION 

The plugin is called "ARPA data” and needs to be installed manually. Download the folder as a ZIP and unzip it. Plugins in QGIS are stored in a special folder. The plugin directory must be copied to that folder before it can be used. In QGIS, locate your current profile folder by going to Settings ‣ User Profiles ‣ Open Active Profile Folder. Then, copy the plugin folder previsouly unziped to python ‣ plugins subfolder. 

Then, the “sodapy” library must be installed to make the plugin work. To do so, the following command has to be run:  pip install sodapy (pip must be installed).  

Finally, the plugin should appear in the Plugins management box of QGIS, in installed plugins and only needs to be activated as a usual plugin. 
