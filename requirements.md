# Requirements

## Seamless digital workflow for field trials

Goal: create and maintain globally unique identifiers for each parcel throughout any workflows

* digital interfaces within processes and between software are currently an issue
    * complex and diverse workflows with many participants
* create unique identifiers (e.g. UUIDs)
* have a "master" component that is updated und from where setup and changes are delivered to the others (e.g. PIAF as a central component, then use PIAF IDs everywhere)
    * automated, if updates or changes are necessary
* provide possibilities to convert IDs (e.g. locally-unique ones to globally unique ones) - "lookup table"



## QR codes

* work with QR codes whereever possible
    * Use the unique plot ID
    * Label all samples

* read/analyse QR codes
    * read QR codes from labels, bags, displays and other media
    * Mobile App: log QR + GPS Position
        * QGIS Extension to monitor camera input for QR codes and add points?
* generate QR-codes, e.g from position, attributes,  ...



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

## Visualisation

* have a better/adaptable way for visualizing plot information in the field
    * e.g. tablet + geodata + QGIS project + QField
    * prepare standard views and standard styling

## Add info to plots

* add information from csv to regular grids (plot layout)
    * e.g. plot layouts are often xls/csv, base

## Sowing

* During sowing, each plot has prepared seed bags
    * prepare and
    * read QR code from bags
    * compare to field trial plan, check correctness
    * documentation of sowing: positions + IDs + plots

## Sampling

* sampling with handheld devices (Smartphone, Tablet)
* use QField outdoors
    * prepare field data + project
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
    * bluetooth, serial
* dead reckoning
    * approach a certain point in the field
    * show RTK status
    * show distance + direction
* surveying in the field
    * mainly points? then full info of GPS metadata (HDOP, satellites, fix, ...) can be maintained for each measurment
    * sometimes lines, polygons can be necessary
    * WFS, WMS usage
    * ODK tools or tool chain?
    * flexible attribute definitions
    * take images at position
    * integrate further sensor measurements (external devices, internal sensors of a smartphone etc)
* use IoT-technology?

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
* point smpling tool to sample through any number and type of layers
    * polygons
    * points (nearest neighbor, maybe constraint max. distance)
    * raster data
    * attribute handling (large no. of attributes)
        * naming schema
        * type checks
        * aggregation
* buffer operations (Multi-Buffer extensions)
* statistics
* image processing (UAS surveys, aerial, manual photos) and analysis
* develop modeler processes for repeating processing chains
    * often with multiple inputs
* merge operations
    * merge layers based on filenames, paths, attributes
* add/relate field information to any vector dataset (intersect, join attributes) oon the fly
* convert GPS measurements between ETRS89 and WGS84
    * currently no tranformation defined in epsg
    * changing parameters/offsets



## Attribute handling

* randomize
* generate and use UUIDs




