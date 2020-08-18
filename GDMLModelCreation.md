## Creation of a basic GDML Model.

**Select/Activate** the GDML Workbench

With an empty FreeCAD document - From FreeCAD Command bar select **File | New**

You should then see a display like 

<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/Create_1.gif" width="650" height="500">
</p>

This will have imported the initial GDML default file from the workbench resources directory and will have defined initial values for

* Constants
* Isotopes
* Elements
* Materials

Clicking on any of these in the **Tree view** will expand their contents to reveal more details.

A **World Volume - worldVol** containing a GDML Box

You can change the size of the box by first selecting **worldVol** in the **Tree view** which should expand its contents
Then selecting **GDMLBox_WorldBox** and changing its parameters in the **Property view**

GDML Volumes are implemented as FreeCAD Parts so to add a **Volume** click on the Part Icon to create a new Part and then
drag it to the Work Volume **WorldVol**

Your display should now look like

<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/Create_2.gif" width="650" height="500">
</p>
