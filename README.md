# Revit / Dynamo / Python
Python coding repository for Autodesk Revit Dynamo environment.

THE PYTHON NODE BASICS
Expand the library on the left side of the screen.
Expand Editor-section.
Click Python Script and place it in the work-space.
You can increase the input amount by clicking the +, and decrease by clicking -. We can have as many inputs as we like.
Open the Python Script Editor by double-clicking the node, which will open up as default;

# Enable Python support and DesignScript library
import clr
clr.AddReference(‘ProtoGeometry’)
from Autodesk.DesignScript.Geometry import *

# The inputs to this node will be stored as a list in the IN variables.
dataEnteringNode = IN

# Place your code below this line

# Assign your output to the OUT variable.
OUT = 0

The 4 lines in the top are essentially importeing Dynamo Geometry Nodes. Line 7 is controlling the input(s). If we change this to, for example;

dataEnteringNode = IN[1], we will operate based on the inputs of IN[1].

If we want mulitple outputs from our Python Script node, we can manually edit the outputs to;
OUT = 0, 1, 2.

We hav etwo options of closing our Python Script window; one, “Save changes” that we have made, or two; discard changes that we have made, “Revert”.

# this is a comment, and will not be executed

One of the cool things about Python Script, this version, is that we can have multiple script-windows open at the same time, so that we can copy/paste code from one to another and testing scripts together, and will generally save time from opening and closing scripts.

How does the error-handling work, in the Python-script node?
If we, for instance, change the input (IN[0]) to let’s say IN[2], without there being three inputs, we will get an error notice, and the Python Script node will turn yellow.

Hover the cursor over the top, with the small, yellow text-bubble, and the error-message will show.

WHAT IS OPP?
Object-oriented programming. A software programming methodology that separates the software development into different objects containing data and methods in a logical manner.

ATTRIBUTE:
Curve —> Attribute: length —> CurveObject -> This will return the length value of the curve.

DOT NOTATION: METHOD:
Curve -> Method: reverse -> CurveObject.Reverse() -> In some instances, the brackets will need inputs, in order to work properly. 

Therefore, all instances of a object of for instance the type line, has their own attributes, and all can use the same methods, which is accessed by dot-notation.

STATIC METHODS (ACCESSED WITH DOT-NOTATION)
Point Class: Methods -> Point.ByCoordinates(0,0,0)

FUNCTIONS (NOT ACCESED WITH DOT-NOTATION)
Function: range(parameter)
Function: sum(parameter)
Function: len(parameter)
Function: sorted(parameter)

We will come across functions that are NOT associated with specific object-types, and therefore ww will not need the dot-notation. These are know as functions.

The only thing we need to understand at this point, is that Python data is made up of objects of which attributes and methods can be accessed by using dot-notation.

IMPORTING THE DYNAMO LIBRARY
Right click the canvas and search for “Python” and enter it by double-click it.

The clr.AddReference(‘ProtoGeometry’)-line of the code is importing classes that we can use to make points, curves, cubes and other geometric objects.

Expand the Geometry menu, revealing the sub-menus such as ‘Abstract’, ‘Curves’, ‘Meshes’, etc.

Expand the Points -> Point -> … here we see all the METHODS and ATTRIBUTES.

Green are the CONSTRUCTION METHODS. These are used to create point objects.
Red are ACTION METHODS. These are used with point objects.
Blue are POINT ATTRIBUTES. 

Create a Point.ByCoordinates.

Hover the cursor over the title of the node, and it will give us information on what the input type should be.

Point.ByCoordinates: X (Point.ByCoordinates(x: double = 0, y: double = 0, z: double = 0)

“Point” on the right side of the node, is the end-type.

Back in he Python Script node, change the OUT to;

OUT = Point. -> auto-menu opens -> shows all the METHODS of the Point-class.
OUT = Point.ByCoordinates(0,0,0).

Click Run.

Update the coordinates, and click Run. The point will update it’s location.
# 00. Introduktion
# 01. Dynamo and Python
# 02. Python basics
# 03. Working with libraries
# 04. Revit API
# 05. Conclusion
