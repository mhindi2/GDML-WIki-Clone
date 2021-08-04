# Converting a STEP file to GDML Tessellated Objects.

The following is a suggested workflow for dealing with a STEP file
1. Activate the GDML workbench
2. Create a new file ( FreeCAD | File | New )
This should create a file with the following structure

![NewFile](https://github.com/KeithSloan/GDML/wiki/wiki_images/NewFile.jpg)

3. Create a New Part under the World Volume.
4. Having selected the Part import the STEP file
You can set the FreeCAD general import Options for STEP to import as one compound object or separate objects.
5. You then need to Tessellate the Objects via following Icons/Commands
> * Tessellate. 
![Tessellate](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Tessellate.svg)
> * Tessellate via Gmsh. 
![TessellateGmsh](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Tessellate_Gmsh.svg)

> * [Using the Mesh Workbench](https://github.com/KeithSloan/GDML/wiki/UsingMeshWorkBench) to mesh an Object, then to convert the Mesh to a GDML Tessellated Object using. 
![Mesh2Tess](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Mesh2Tess.svg)  
6. There is also the option of simplifying the Mesh with FreeCAD's mesh decimate facility
'Decimate Selected Object' Command/Icon. 
![Decimate](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Decimate.svg) 
7. You can set the objects material either via the properties window or selecting the material before the Tessellation operation.
8. When you are happy with the Tessellation you can delete the original STEP object.

You need to end up with the following structure 
>> World Volume
>> * A number of Parts under the World Volume.
>> * Each Part containing a GDML Tessellated Object.

If your structure is not as advised you can always drag FreeCAD objects around in the Tree View i.e Parts to World Volume,
Tessellated Objects to Parts etc.

If necessary you can alter the position of GDML Tessellated Objects by changing its parent Parts, Position & Rotation.

9. You can now export the GDML file by selecting the World Volume and using File | Export and selecting GDML as the file type.  