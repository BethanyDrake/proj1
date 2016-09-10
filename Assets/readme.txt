Implementation of diamond square algorithm:
Used diamond square algorithm to generate a hightmap as a 33x33 float array. The four corners are intialised to a random number between -range and range. Then the algorithm continues as normal, iteratevly calculating all the squares and diamonds of size 32, then of 16, and so on until all values in the height map have been assigned. For each square and diamond, the midpoint is calculated as the average of the surrounding 4 (or 3) corners, plus an average number between -range and range. At each new square size, the range is halved.
A mesh is created from the heightmap, with a vertex for each entry in the array. The position in the array gives the x, z ordinates, the value in the array gives the y ordinate.

Implementation of camera movement:
Used Unity's inbuilt collision detection to inhibit movement through the terrain. Rotation is locked to prevent traumatic crash landing events, but the camera will slide along the terrain. There are invisible walls around the terrain, including a high ceiling.

Implementation of colouration:
The terrain is coloured using a custom shader adapted from the example shown in workshops. Each vertex of the terrain has a colour dependant on the height of the vertex relative to the highest and lowest points on the graph. The terrain is opaque, but each vertex passes an alpha value that is interpreted by the shader as glossiness (Ks value) for use in the specular compnant of the lighting calculations.
The top quarter of the map is white and very glossy (snow), the middle section is green and dull (grass), and the bottom third is yellow and very dull (sand).  
Additionally, a transparent blue plane cuts through the bottom quater of the terrain. This has its own custom shader. 