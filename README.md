# A UK local authority Shapefile with area insets (2020 and 2021 local authority boundaries)
This repository contains a UK local authority layer that includes larger insets for 7 parts of the UK. I haven't included everywhere (sorry), just some of the main urban areas with small areas that are difficult to see on a zoomed out map. I have also (as of January 2022) added in a new file that takes into account the 2021 local government boundary changes in Northamptonshire. If you join some spreadsheet data to the Shapefile then the data will also be joined to the areas in the insets as well, with no fuss.

Feel free to use as you see fit. There's also a video showing how to use the files - scroll down to the bottom of the page to see this.

**There are FOUR zipped folders. One is just the boxes that the insets fit within. The other two are the UK local authority files - one version has just the basic fields (area names, codes, country, etc) but I also added another one with population data, using the latest ONS mid-year estimates (2019). The 'scale' field tells you how much bigger I made the inset areas - everywhere is 3x bigger, apart from London (5x) and Orkney and Shetland (same size, just moved south). I have also added QGIS style files for the inset boxes and one for the layer with the population data (this style shows the % aged 80+ in each area). As of January 2022 there is another local authority file that uses the 2021 boundaries.**

I have also included bounding boxes with a 10km buffer so that you can add these in to make clear which areas are insets and which are not.

The idea behind this is to make maps that are easier to see and understand, but also more quickly, and from one layer. 

There are lots of possibilities, but if you wanted to just put Orkney and Shetland into a little inset, you could run a flter on the layer, something like this:

* *"inset_area" = 'None' and NOT "lad20nm" IN ('Orkney Islands','Shetland Islands') OR "inset_area" = 'Orkney and Shetland'*

If you just wanted an inset for London, you could try something like this:

* *"inset_area"  IN ('Greater London','None')*

If you wanted to show all insets, but not Shetland and Orkney in their actual location, then you could do this:

* *NOT "areaname" IN( 'Orkney Islands','Shetland Islands') OR "inset" = 'Yes'*

And in all cases you just do a similar filter on the box layer to show a box round these areas.

I used data from the ONS geography portal to create this. It's all open, licenced under the Open Government Licence v3.0. 

Source: Office for National Statistics licensed under the Open Government Licence v.3.0. Contains OS data © Crown copyright and database right [2020].

**Alasdair Rae**
26 Nov 2020
Updated 25 Jan 2022 to include new file with 2021 boundary changes taken into account (i.e. Northamptonshire councils)

(work in progress)


![Example map](insets_example.png)

[Video showing how it all works in QGIS](https://twitter.com/undertheraedar/status/1332034822697611270)


