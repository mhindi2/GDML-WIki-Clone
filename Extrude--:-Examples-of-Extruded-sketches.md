# Comparison Timings 
Timing for extruded sketches, exported as Booleans of solids versus being Tessellated
## Displayed in Geant4
### Booleans from extruded sketch
![extrude_0000](https://user-images.githubusercontent.com/2291247/153726003-52abf421-62b4-4190-9d3b-96471fa575e9.png)
### Same objects Tessellated
![tess_0000](https://user-images.githubusercontent.com/2291247/153726004-76bce4a0-391b-4c51-9ee7-4a1500aa0a7b.png)
### Simulation timings
````
With 10^6 geantinos:

extrusions: 7.25 s
tesselation: 17.35 s


With 10^6 2 MeV gamma rays:

extrusion: 17.35 s
tessellation: 146 s 
````

