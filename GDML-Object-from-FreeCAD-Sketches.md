### Export of FreeCAD sketches as GDML objects.
The GDML workbench now supports creating a GDML object from a FreeCAD Sketch currently
* Extrusion
* Revolution (In development )
* Sketches with Bezier curves In development
### Restrictions
* Sketch should be made in the X-Y Plane ( Created Objects can be rotated )
### Document structure
* Extrusion should be in a single GDML volume (FreeCAD Part)
### Allocated Material
Suggestion is to use toolbar 'Set Material' facility.
### On GDML Export
* The extruded sketch is processed to create a series of booleans of GDML solids.
* Import of the exported file will show the booleans and structure in the FreeCAD Treeview
### Display in GEANT4
* Some objects will only display as point clouds, this is due to limitations in Geant4 ablity to display certain forms, it does not affect any simulation
* "solution" is to display everything as a cloud by issuing

/vis/viewer/set/style cloud


### Examples of simulation of extruded sketches versus same objects Tessellated
Examples and [Timing comparisons - Booleans versus Tessellated](https://github.com/KeithSloan/GDML/wiki/Extruded-sketches-timing-comparisons)


