## Scan Facility : Dealing with large GDML files

Currently importing of large GDML files is problematic, it is uncertain if this is because of

* Bugs in the Workbench
* Bugs in FreeCAD

There is an intention to profile the Workbench as a means of investigating but to-date this has not happened due to lack of time.

To mitigate the problems of loading large GDML files a **Scan facility** has been implemented.
<br> The following is an attempt to illustrate the the **modus operandi** of using the Scan Facility.

With the GDML workbench installed opening a GDML file will cause the following the following dialog prompt
<br>
<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/Import_Dialog.png" width="650" height="500">
</p>

Opening a large file such as **Alice.gdml**  which is supplied in the **SampleFiles / CERN** directory
<br> and then clicking on **Scan Vol** will cause a scan of the high level GDML Volumes in the file. 

<br>

<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/Scan_1.png" width="650" height="500">
</p>

Expanding the **ALIC** Part

<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/Scan_2.png" width="650" height="500">
</p>

Selecting an unexpanded volume as indicated by the name starting with **NOT_Expanded**
<br> and using the **Expand Volume** function, **'Capital E'** icon will expand the selected Volume.

The Following two screen captures show the result of performing expansion of the
<br> Volume L3MO_ in the Alice.gdml file 
<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/L3MO_.png" width="650" height="500">
</p>
<p align="left">
  <img src="https://github.com/KeithSloan/GDML/wiki/wiki_images/L3MO_2.png" width="650" height="500">
</p>