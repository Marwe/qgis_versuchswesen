# Requirements

## Seamless digital workflow for field trials

Goal: create and maintain globally unique identifiers for each parcel throughout any workflows

* digital interfaces within processes and between software are an issue
* create and maintain unique identifiers
* have a "master" component that is updated und from where setup and changes are delivered to the others (e.g. PIAF as central place, use PIAF IDs everywhere)
    * this needs to be automated, if updates or changes are necessary


## QR codes

* work with QR codes whereever possible
    * Use the unique plot ID
    * Label all samples

* read/analyse QR codes
    * read QR codes from labels, bags, displays, ...
    * Mobile App: QR + GPS Position


## Geodata

* create field trials with unique IDs
    * randomization? May be done externally (SAS, R domain)
        * see e.g. https://cran.r-project.org/web/views/ExperimentalDesign.html
    * create geometries
    * maintain geodata in a central (cloud? accessible) database/service
        * history of changes

* correct broken geometries
    * many datasets are invalid (mostly: invalid geometries)


### Log data import

* import geodata from agricultural terminals

### Export to terminals

* Export geometries for terminals (e.g. Trimble)
* shp-ISOBUS conversion thinkable/possible?
    * external tools (FMIS, converter)
    * free implementations of such 

## Sowing

* During sowing, each plot has prepared seed bags
    * prepare and
    * read QR code from bags
    * compare to field trial plan, check correctness
    * documentation of sowing: positions + IDs + plots

## Sampling

* sampling with handheld devices (Smartphone, Tablet)
* prepare sampling layers with predefined selection lists, attributes etc.
* sample images
    * image analysis methods, e.g. coverage, plant count, ...

## Harvest

* import harvest data
* correction of harvest data 
    * select valid measurements
    * correct for delayed measurement, if possible 
        * interpolate back along track, difficult, depends on machine etc.
        * interpolate between tracks (to account for alternating patterns)

## UAS

Goal: create and maintain a seemless UAS workflow

* flight planning according to plot map (waypoints, route)
* import analysis results in QGIS software
* georeferencing
* postprocessing
* image analysis
* intersect with trial data

## Mobile GPS-Sytems

* RTK GPS System support
* dead reckoning
    * approach a certain point in the field
* surveying in the field
    * mainly points? then full info of GPS metadata (HDOP, satellites, fix, ...) can be maintained for each measurment
    * sometimes lines, polygons can be necessary
    * WFS, WMS usage
    * ODK tools or tool chain?

## Track management

* generate tracks from logged positions
* generate tracks from field boundary
    * CTF controlled traffic farming
    * headland handling
* create application areas (e.g. management zones) from tracks and implement width


# General GIS operations

* field boundary as mask for many operations/results (wrap operation, append masking)
* points to area (Voronoi)
* area interpolation (transfer attributes)
* interpolate along tracks


