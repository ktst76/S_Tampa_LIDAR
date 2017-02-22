# Introduction
South Tampa also known as the Interbay peninsula, is a long (14 km / 8.6 miles) narrow (4 km / 2.5 miles), highly urbanized area with Tampa Bay shoreline on three sides (E,S,W).  

![Tampa Bay Watershed](inset_map.jpg)

Tampa and the surrounding area lie in a zone of often heavy summer (June-September) precipitation, that combined with limited vertical relief can rapidly overwhelm natural drainage and municipal services (sewer, stormwater, etc).  In addition to the heavy summer precipitation, Atlantic hurricanes are a potential threat for both heavy precipitation and storm surge.  Finally, sea levels will rise as a result of anthropogenic climate change, reducing the already limited vertical relief; or an even flatter South Tampa.

# Driving Factor
During the summer of 2015 the Tampa area received heavy rainfall compared to seasonal averages; the author's calibrated backyard rain-gauge recorded 46.61 inches (118.4 cm) of rain from June 1st until August 31st, an amount equal to 211% of average during the period.  In addition to the well above average volume of precipitation, rain often fell in heavy spells lasting two to three days, June and August saw events with greater than 6 inches (15 cm) of precipitation in 48 hours.  This heavy rainfall, saturated soils and limited vertical relief resulted in large areas of South Tampa flooding.  Streets that were passable, rapidly became unpassable, with little visible indication why street X is flooded, but street Y is merely wet.  The images below highlight surface flooding on August 1st, the first image looks east (the Tampa Bay shoreline is 0.6 mile / 1 km down the street) while the second image looks west.  

 ![Ballast Point Looking East](IMG_2607.JPG)
  
 ![Ballast Point Looking West](IMG_2610.JPG)
 
The transportation issues that resulted from the flooding, which occurred during the middle of a workday - led to a normal commute of 15 minutes turning into a commute of 45 minutes in search of a route that wasn't flooded.  That event provided the impetus to either locate data or maps that may show routes that would be less likely to be flooded, or create maps to fill the gap in information.
 
# Objective
Using publicly available LIDAR data, build a terrain model that provides high fidelity ground elevation data.  Fidelity should enable modeling of water depth in inches or cm.  

## *This study does not account for the effects of: stormwater infrastructure, culverts, wave action. At the most basic, it models the ability of water to move horizontality and/or down a gradient*

## LIDAR, what's LIDAR? 
**LI**ght **D**etection **A**nd **R**anging is a survey method that utilizes a laser sensor to build a 3-D model of the terrain or object based on the returned laser energy.  LIDAR is not without its faults, vegetation can greatly hinder the ability of laser energy to strike the ground and return to the sensor.  The data used in this study was collected by an airborne sensor flying over the survey area during the peak of summer, when trees have full leaf cover. The data used in this study was collected by an airborne sensor flying over the survey area during the peak of summer, when trees have full leaf cover.  The image below is a LIDAR image color-coded to the height of the return.

![Live Oak](bp_lidar-pts.jpg)

Warm colors reflect returns that are at or near ground level, a darker cool color represents a higher return.  The large blue-ish green blob in the center of the image is a large Live Oak (a ground based photo of the oak is below).  Note the limited number of red or orange marks within the blue-green blob, the lack of those red or orange marks indicate that foliage interfered with laser energy.

![Live Oak Ground View](IMG_4233.JPG)

The ground based photograph was taken in February when the Oak was missing a majority of leaf cover, which would be an ideal time to collect LIDAR data with limited vegetation impacts. 

# Procedure

Eleven publicly available LIDAR datasets were downloaded from the USGS National Map Viewer (1).  This data was collected in July and August of 2007.  The LIDAR files were processed using the LAStools (2) software suite in order to create a terrain model of the ground and buildings in the Ballast Point area. Following creation of the terrain model, the dataset was imported into the SAGA-GIS (3) program.  Within SAGA the model was 'flooded' at six inch (15 cm) steps from 3 feet to 12 feet (1-4 m) above current sea level. The resulting images from each flood step were then exported into Adobe Creative Suite to facilitate display in Google Earth. 

# Results

The figure below examines sea level ranges from four feet to seven feet six inches (above current).  Within each frame the water depth is color coded to a fixed range.
![Ballast Point](looped.gif)

A visualization covering the entire study area (3.5 to 7.5 feet above current) can be found in the following YouTube video:
https://www.youtube.com/watch?v=W1C75yHVH7A

Google Earth files with full resolution overlays are listed below (note color code errors exist in overlays 8 feet or greater):

[Water depth from base sea level change, under 6 feet (2m)](S_Tampa_LIDAR/S Tampa Sea Level Base Levels Sub 6 Feet.kmz)
 
[Water depth from base sea level change, 6-9 feet (2-3m)](S_Tampa_LIDAR/SE Tampa Sea Level Rise 6-9 Feet.kmz)
 
[Water depth from base sea level change, 9-12 feet (3-4m)](S_Tampa_LIDAR/SE Tampa Sea Level Rise 9-12 Feet.kmz)
 
[Areas with 'new' water per step - the deepest blue represents 6+ inches](S_Tampa_LIDAR/Sea Level Rise - Water Build Up.kmz)

# Discussion

The resulting Google Earth files (Google Maps does not display graphics) allow a user to zoom into an area of interest that is not possible to display in a large study area.  Draft results of this work have resulted in a list of areas to focus on in order to provide interested parties the ability to find their way home from work, or to a school to pick up children.  Additional work will examine ponding from a constant amount of precipitation (without the effects of stormwater systems), which will present differing results than those presented at this time.

This project will continue to map both the sea level flooding risk, and the precipitation ponding potential - to provide tools to make life in South Tampa less stressful.

# Sources and Tools:
USGS National Map: https://viewer.nationalmap.gov/basic/

Specific LIDAR files: USGS Lidar Point Cloud (LPC) FL_HillsboroughCo_2007_000258-260,280-283,302-305

LAStools: http://www.cs.unc.edu/~isenburg/lastools/

SAGA-GIS: http://www.saga-gis.org/en/index.html
