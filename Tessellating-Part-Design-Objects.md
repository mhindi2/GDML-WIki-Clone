If you are using Part Design to create objects which you are then going to Tessellate the suggested workflow is

* Activate GDML workbench
* Open New File - Should setup the basic GDML structure
* Under the World Volume - create your Part Designs i.e The World Volume contains one or more Part Designs
* When you are ready to Tessellate your Part Designs
    - select the Part Design and then use Button - Tessellate Selected Object

      This should then create a new part LV-[part design name] and under it a GDML Tessellated Object
* Select the Tessellated Objects material via Properties window if a material was not selected at the time of Tessellation.
* To adjust the position use the Placement in LV-[part design name]
*  You need to do this before exporting, by selecting the world volume then export file type gdml
* You can also mix in GDMLsolid objects
* Remember there must only be one GDML object in a Part(GDML Volume)
* a Part(GDML Volume) may contain a number of other Part(GDML Volume) objects