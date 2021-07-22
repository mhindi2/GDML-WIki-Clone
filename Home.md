# Welcome to the GDML Workbench Wiki !

!!!! ***** UNDER CONSTRUCTION ***** !!!!

Geometry Description Markup Language (GDML) is a specialized XML-based language used to specify
<br>Geometries for Monte Carlo Simulation software such as ROOT, Geant4, etc see [GDML Manual](https://gdml.web.cern.ch/GDML/doc/GDMLmanual.pdf).

It defines a rich set of Solid Computer Graphic Objects.

The **GDML Workbench** lets the user

* Import
* View
* Edit
* Create
* Export

Such Geometries.

**FreeCAD** has some Solid Graphic Objects in its Parts Workbench but they are a very limited set
<br> compared to GDML. The normal way to create CAD models with CAD software like FreeCAD is to 
<br> create sketches that one then

* Pockets
* Extrudes
* Rotates
* etc

The results of which are BREP (Boundary Representation) Shapes rather than Solid Graphic Objects.
<br> To translate the BREP Shapes to GDML one needs to create **GDML Tessellate shapes** from the BREP Shapes
<br> or use some software like [McCad](https://github.com/inr-kit/McCad-Salome-Binaries) to decompose the BREP Shapes into GDML Objects.

The **GDML Workbench** provides a number of facilities to

* Export FreeCAD(BREP) shapes as GDML Tessellated Objects.
* Allocate a GDML Material and directly Convert a FreeCAD(BREP) Shape to a GDML Tessellated Object
<br> using a number of different algorithms

    * Standard FreeCAD mesh facilties
    * [Gmsh](https://gmsh.info)
    * Tetrahedron (This does not directly translate to GDML, but to a GDML Assembly of GDML Tetra)
 
### Selecting/Activating the GDML workbench

From the FreeCAD command bar select **View | Workbench** then select **GDML**

![Workbenches](https://github.com/KeithSloan/GDML/wiki/wiki_images/Workbenches.gif)

### FreeCAD Setup for Workbench use.

It is recommended that when you have the GDML workbench active that the following Toolbars are viewable

* Workbench
* Structure
* GDMLTools
* GDML Part Tools

So Icons displayed should look similar to the following

![Icons](https://github.com/KeithSloan/GDML/wiki/wiki_images/Icons.jpeg)

To make a **Toolbar viewable**, from the FreeCAD command bar select **View | Toolbars**

### Importing Files

* [Import GDML file](https://github.com/KeithSloan/GDML/wiki/import.md)
* [Scan GDML file](https://github.com/KeithSloan/GDML/wiki/Scan_Facility) - Facility for dealing with large GDML files

### Importing a STEP file and creating GDML Tessellated Objects

* [Dealing with STEP files](https://github.com/KeithSloan/GDML/wiki/step2Tessellate)

### Viewing a GDML Model

### Modifying a GDML Model

### Creating a GDML model from scratch

[GDML Model Creation](https://github.com/KeithSloan/GDML/wiki/Model_Creation)

### Export/Import - Materials XML files

When creating a new file from the GDML workbench the file Defaults.gdml is read from the Resources directory,
this may or may not have material definitions, as supplied there are none.

A Materials Group called Geant4 is created by reading the file Geant4Materials.xml from the Resources directory
which define all the materials that GEANT4 implicitly defines by default.

When a file is exported the the materials in the geant4 group are ignored as GEANT4 implicitly defines these.

If you need the Geant4 materials for use in a none GEANT4 situation, for example ROOT, then one option is to 

   * Select the geant4 group.
   * export as an xml file
   * import the xml file

This should add the materials in the main materials definitions which should be exported in any subsequent
GDML exports

### Mesh Operations

### Exporting GDML files

To export a GDML file, select the root **Part** ( GDML World Volume ) then use the standard FreeCAD export
facility ( File | Export )

#### Single GDML file
If a filetype of lowercase **gdml** is selected a single GDML file is produced.

#### Multi GDML file
If a filetype of uppercase **GDML** is selected then the following files are created in a directory derived from the path name less the GDML file extension.
     
   * A [Name].gdml with imbeds for the following xml files
   * setup.xml
   * constants.xml
   * defines.xml
   * materials.xml
   * [Name]-solids.xml
   * [Name]-structure.xml

Note: Provided you have the lxml python library installed, you should be able to successfully open the [Name].gdml file 

### GDML - Multi Files

ROOT only supports GDML defined in a single file, as it does not support the required DOCTYPE !ENTITIES.

There are two options
 
1. Open the multi file with the workbench and then export with as a single GDML file.
2. Use the standalone python program supplied in **Utils** 

      **combineGDML.py [input file with imbeds] [output single file]** 

Such multi files are supported by **Geant4.**

### STEP files

When exporting STEP files that include GDML objects set the FreeCAD Preference for Export to
use legacy exporter

![Export STEP](https://github.com/KeithSloan/GDML/wiki/wiki_images/STEP-Export.png)

### Command line utilities

### Processing a Volume for subsequent Finite Element (FEM) Analysis 

### Installation
