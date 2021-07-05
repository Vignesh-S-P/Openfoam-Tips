
Objective
To use setExprFields in openfoam v8 

Issues
1. setExprFields is only available in openfoam v 2006 v2012 ...  (ESI OpenCFD release versions)

Solution
use "mapFields" utility to map the internalField data from v2012 to v8

1. Create two identical cases with same mesh in openfoam v8 and v2012
2. Open v2012 case and create the necessary expression based fields using setExprFields (terminal with of v2012)
3. Open New terminal with v8 
4. In the v8 case file, add "mapFieldsDict" to system directory using "foamGet mapFieldsDict"
5. Edit the mapFieldsDict as given in the case folders so that the patch information is also copied
6. With v8 terminal open, create the mesh and use the command "mapFields /path/to/v2012/case"
7. Check in paraview with "Skip 0" disabled.

How to use the case files

1. go in to "caseof2106"
2. open terminal and enable v2106 or v2012 environment
3. use script "./init" to create mesh, copy 0 folder and setExprFields
4. exit terminal
5. go in to "caseof8"
6. open terminal and enable v8 environment
7. use script "./mapU" to create mesh, copy 0 folder and map all the fields from the v2012 case
8. Check in paraview with "Skip 0" disabled.

use ./clean in any folder to clean the case folder completely

