# Converting a STEP file to GDML Tessellated Objects.

The following is a suggested workflow for dealing with a STEP file
1. Activate the GDML workbench
2. Create a new file ( FreeCAD | File | New )
This should create a file with the following structure

![NewFile](https://github.com/KeithSloan/GDML/wiki/wiki_images/NewFile.jpg)

3. Create a New Part under the World Volume.
4. Having selected the Part import the STEP file
You can set the FreeCAD general import Options for STEP to import as one compound object or separate objects.
5. You then need to Tessellate the Objects and set its GDMLmaterial via any of the following Icons/Commands
> * **Tessellate**. 

![Tessellate](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Tessellate.svg)
> * **Tessellate via Gmsh**. 

![TessellateGmsh](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Tessellate_Gmsh.svg)

> * [Using the Mesh Design Workbench](https://github.com/KeithSloan/GDML/wiki/UsingMeshWorkBench) to mesh an Object, then to convert the Mesh to a GDML Tessellated Object using.
The Mesh Design Workbench offers a number of facilities for Meshing an Object
    
    - Standard
    - Mefisto
    - Netgen
    - gmsh

> * **Convert the Mesh to a Tessellated Object**

![Mesh2Tess](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDML_Mesh2Tess.svg)  


6. There is also the option of simplifying the Mesh with FreeCAD's mesh decimate facility
'**Decimate Selected Object**' Command/Icon. 

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

## STEP files with Colour
If your STEP files have Objects with colour information you can use a Colour to Material mapping facility to set an Objects GDML material.
Click on 

![Col2Mat](https://github.com/KeithSloan/GDML/wiki/wiki_images/GDMLColourMapFeature.svg)

This will open a window that lists the colours used in the FreeCAD document and allows them to be allocated to a GDML material.

## Avoiding Potentially overlapping shapes in Geant4 analysis
If there are shapes of different materials that end up touching, one approach would be to adjust one of their sizes by a very small amount using the Part::Offset tool in the Part Workbench. An Alternative would be to use the OpenSCAD workbench to perform a Minkowski operation with one of the shapes and a very small sphere or cube.
## Trouble shooting
If you have problems with your Tessellated Object this may be due to how the mesh was created.
It is suggested that you check the undelying mesh as follows
1. Use **Tess2Mesh** to convert your GDML Object to a FreeCAD mesh.
2. Switch to the Mesh Design workbench
3. Use the tool/icon to analyse and repair a mesh
   - You may have to make several passes depending on the problem
4. When happy with the mesh use the GDML Workbench icon/tool **Mesh 3 Tess** to convert the mesh back to GDML Tessellated Object