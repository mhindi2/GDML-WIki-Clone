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
 
### FreeCAD Setup

**Selecting the GDML workbench**

From the FreeCAD command bar select **View | Workbench** then select **GDML**

![Workbenches](https://github.com/KeithSloan/GDML/wiki/wiki_images/Workbenches.gif)

It is recommended that when you have the GDML workbench active that the following Toolbars are viewable

* Workbench
* Structure
* GDMLTools
* GDML Part Tools

So Icons displayed should look similar to the following

![Icons](https://github.com/KeithSloan/GDML/wiki/wiki_images/Icons.jpeg)

To make a **Toolbar viewable**, from the FreeCAD command bar select **View | Toolbars**

### Importing Files

* [Import GDML file](https//github.com/KeithSloan/GDML/wiki/import.md)
* [Scan GDML file](https//github.com/KeithSloan/GDML/wiki/Scan_Facility.md)
* [Importing a STEP file](https//github.com/KeithSloan/GDML/wiki/importSTEP.md)

### Viewing a GDML Model

### Modifying a GDML Model

### Creating a GDML model from scratch

[GDML Model Creation](https://github.com/KeithSloan/GDML/wiki/Model_Creation)

### Export/Import - Materials XML files

### Mesh Operations

### Exporting

### Processing a Volume for subsequent Finite Element (FEM) Analysis 

### Installation
