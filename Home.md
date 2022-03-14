# Welcome to the GDML Workbench Wiki !

!!!! ***** UNDER CONSTRUCTION ***** !!!!

Geometry Description Markup Language (GDML) is a specialized XML-based language used to specify
<br>Geometries for Monte Carlo Simulation software such as ROOT, Geant4, etc see [GDML Manual](https://gdml.web.cern.ch/GDML/doc/GDMLmanual.pdf).

It defines a rich set of Solid Computer Graphic Objects for details of
[GDML Solids](http://geant4-userdoc.web.cern.ch/geant4-userdoc/UsersGuides/ForApplicationDeveloper/html/Detector/Geometry/geomSolids.html)

The **GDML Workbench** lets the user

* Import
* View
* Edit
* Create
* Export

Such Geometries.


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

## GDML Objects / Solids

### GDML Solids

GDML Solids are implemented as FreeCAD Python Objects and have the same properties as defined by GDML. By selecting an Object the properties can be changed via the FreeCAD properties windows and the resulting changes displayed.

### GDML Objects Currently Supported for creation via the GUI are

#### GDMLBox 
![GDML_Box-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Box_mauve_blackline.svg)
_Short decription_

#### GDMLCone
![GDML_Clone-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Polycone_Mauve_blackline.svg)
_Short decription_

#### GDMLElTube
![GDML_EllipticalTube-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_EllipticalTube_Mauve_blackline.svg)
_Short decription_

#### GDMLEllipsoid
![GDML_Ellipsoid-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Ellipsoid_Mauve_blackline.svg)
_Short decription_

#### GDMLSphere
![GDML_Sphere-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Sphere_mauve.svg)
_Short decription_

#### GDMLTrap
![GDML_Trapezoid-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Trapezoid_Mauve_blackline.svg)
_Short decription_

#### GDMLTube
![GDML_Tube-Icon](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Tube_mauve_blackline.svg)
_Short decription_

Given a lot more solids are supported for import, it is not too difficult to add more,
so if you feel you need a particular solid to be added please contact me.

### Boolean Operations

Select two Parts/Logical Volumes and then click on the appropriate boolean icon


### Importing Files

* [Import GDML file](https://github.com/KeithSloan/GDML/wiki/import.md)
* [Scan GDML file](https://github.com/KeithSloan/GDML/wiki/Scan_Facility) - Facility for dealing with large GDML files

### Importing a STEP file and creating GDML Tessellated Objects

* [Dealing with STEP files](https://github.com/KeithSloan/GDML/wiki/Step2Tessellate)

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

## FreeCAD Objects (Non-GDML)
In addition to the GDML solids, the **GDML Workbench** supports the
export of a subset of the solids one can create in the **FreeCAD**
Parts Workbench. These are documented below. For those shapes not
directly supported for export, the recommended way to proceed is to
take the resulting BREP (Boundary Representation) Shape and then
translate it to a **GDML Tessellate**, or use some software like
[McCad](https://github.com/inr-kit/McCad-Salome-Binaries) to decompose
the BREP Shapes into GDML Objects.

The **GDML Workbench** provides a number of facilities to

* Export FreeCAD(BREP) shapes as GDML Tessellated Objects.
* Allocate a GDML Material and directly Convert a FreeCAD(BREP) Shape to a GDML Tessellated Object
<br> using a number of different algorithms

    * Standard FreeCAD mesh facilities
    * [Gmsh](https://gmsh.info)
    * Tetrahedron (This does not directly translate to GDML, but to a GDML Assembly of GDML Tetra)

### Part Objects directly exportable to GDML
(_Note some of these are currently only supported in the Beta2 branch_)

#### Extruded Sketches

Shapes created by the **Sketch Workbench** and extruded via the
**Part** Extrude command can be exported to GDML. The extrusion must
be added to a Part under the worldVol tree. Currently extrusion
exports have the following limitations: (1) only extrusions along the
z-axis are supported (i.e., the sketches must be in the x-y
plane). Note that this does not pose a real limitation, since the
extrusion object itself can be rotated or translated to any desired
orientation or location. (2) Arcs/elliptical whose chords are crossed
by lines (or other arcs) cannot currently be processed. Arcs/lines
that are completely inside or outside other arcs, are supported,
though. Examples of Extruded sketches are in [Extruded sketches
examples](https://github.com/KeithSloan/GDML/wiki/Extrude--:-Examples-of-Extruded-sketches)

Technical Notes: extrusions are exported as a sequence of booleans of
intrinsic GDML objects. BSplines are discretized as a sequence lines
and exported as an <xtru solid. The exported xtru can be made smoother
(more points) as follows: select the extrusion object, then select its
View property Panel. Right click on the Display Options header and
check the 'Show All' check box. This will reveal additional properties
that can be set. One of them is 'deviation', which defaults to 0.5
(%). Decrease that number to get smoother curves. You may increase it
to get coarser curves. **FreeCAD** does not support Deviation values
larger than 0.5, but the GDML extruder can use larger values.

Tests comparing the performance of geant simulations with extruded
sketches vs their tessellated versions have shown the extrusions to be
2-5 times faster than their tessellations.

#### Revolved Sketches

Shapes created by the **Sketch Workbench** and revolved via the
**Part** Revolve command can be exported to GDML. The revolution must
be added to a Part under the worldVol tree. Currently revolution
exports have the following limitations: (1) only revolutions around
the z-axis are supported and (2) the sketches **must** be in the x-z
plane. Further, if the sketch is revolved by less than 360 degrees,
then it must be on the positive side of the x-axis.
Note that this does not pose a real limitation, since the
revolved object itself can be rotated or translated to any desired
orientation or location. Examples of revolved sketches are in
[Revolved sketches
examples](https://github.com/KeithSloan/GDML/wiki/Revolved-:-Examples-of-Revolved-sketches)

Technical Note: All curves in a revolved sketch, except circles, are
discretized and exported as <polycone's. Circles are exported as a
torus. Booleans of these are used to fully construct the revolved
sketch. The smoothness of the discretization can be changed as
described above, under **Extruded Sketches**.

#### Arrays of Objects

Arrays of objects, constructed under the Draft Array command, or the
GDML Array command can be exported as GDML objects. The arrays must be
of currently supported objects (GDML, or Part objects, such as
extrusions, or revolutions). Arrays of arrays can also be
exported. Currently the following types of arrays are supported:
* Ortho(gonal) arrays
* Polar arrays
In the future other types of arrays will be supported.

The Array object must be added to a Part under the WorldVolume tree.
Note that the array object is exported as a **single** multiUnion gdml
solid. Thus the objects in the array are considered as part of **one**
solid, and hence have **one** material. It is best practice to assign
the material to the Array object. If a material is not assigned to the
Array object itself, its (sub)objects are scanned recursively and the
material of the first object that does have a material property is
selected.

#### Mirrored Objects

A mirror of a GDML exportable object (including extrusions,
revolutions, arrays) can be created and exported; either using the
Draft mirror command, or or the provided GDML short cut. At present
the mirrored objects (both the original object and its mirror image
are exported in a gdml <assembly. They both share the original volume
and hence will have the same material. Examples are in [Mirror
examples](https://github.com/KeithSloan/GDML/wiki/Mirror-:-Examples-of-use-of-Mirror). Note
that in FreeCAD when a mirrored object is itself mirrored, one only
get an additional mirror of the mirrored object, not additionally a
mirror of the original object.

#### Scaled Objects

A scaled copy of an exportable object can be exported. The scaling of
GDML solids (as opposed to Part shapes, that are **not** GDML Solids),
can be scaled using the Scale Command icon provided with in the **GDML
Workbench**. This command adds a scale property to each of the
selected solids; no additional objects are created. In contrast, the
Draft scaling operation creates a separate object (must be a clone)
that carries the scaling information, while the original object
remains in the tree. To export the scaled object, the clone must be
added to a Part that is under the WorldVolume tree, while the original
object must be **outside** that tree (but not deleted, as the clone
refers to it). If multiple objects are selected and scaled using the
Draft scale operation, all those objects become part of the clone and
are exported as GDML multiUnion, and hence will have one and the same
material. That material is best assigned to the clone object, but, as
in the case of other composite objects, if a material is not provided,
the sub-objects will be searched recursively until one is found with a
material property, then that material is assigned to the
multiUnion. Otherwise a default material (currently
G4_STAINLESS-STEEL) will be assigned. A peculiarity of the Draft scale
operation is that its placement (rotation and position) are copied
from the scaled object, in the case of scaling a single object, and
set to the identity placement in the case of scaling several
objects. In either case, the placement property of the clone is its
own and separate from the of the scaled object. Subsequent changes to
the placement of the scaled object **do not** affect the placement of
the clone. However, because the GDML Workbench makes use of the
original object's placement, changes to those **after** a scaling
operation is performed **will** affect the exported model, but not the
FreeCAD one. **Therefore, changing the placement of the original
object should not be done after scaling**. If it is desired the change
the location of the scaled object (the clone), change **that**
placement (not the original), or else delete the clone, move the
original and scale again.

 
### Exporting GDML files

To export a GDML file, select the root **Part** ( GDML World Volume ) then use the standard FreeCAD export
facility ( File | Export )

#### Single GDML file
If a filetype of lowercase **gdml** is selected a single GDML file is produced.

#### Multi GDML file
If a filetype of uppercase **GDML** is selected then the following files are created in a directory derived from the path name less the GDML file extension.
     
   * A [Name].gdml with embeds for the following xml files
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

### Installation - For Installation see the [README](https://github.com/KeithSloan/GDML#readme) 
