# renderdoc2fbx
renderdoc python extension for exporting fbx data

## About this fork

- Fixed bug with latest renderdoc (v1.3).
- Improved this readme explaining better how this tool works.

## Installation

copy `fbx_exporter` folder to `%appdata%\qrenderdoc\extensions`

If you are in the windows platform, you can use `install.bat` to install the extension.

## Feature

Export ASCII FBX File Support

+ **Vertex** 
+ **Normal** 
+ **UV**
+ **Tangent**
+ **VertexColor**

![FBX](image/01.png)

## Usage (original)

make sure you copy the extension to the `%appdata%\qrenderdoc\extensions` directory

launch `renderdoc` and open the `Extension Manager`

![FBX](image/02.png)

then go to the Mesh Viewer click the extension icon menu to export the current data as the FBX file.

![FBX](image/03.png)

## Usage (improved)

In renderdoc, in the Mesh Viewer you can see two tables, one is for vertex shader input and the other is for vertex shader output. This extension will only output data from the first table (vertex shader input). 

This extension will allow you to choose between Unity or Unreal, but this is useless and makes no sense. It does not matter. 

What you have to do is:
- First look at vertex shader input table.
- Take note of the table column names.
- Ignore Unity/Unreal dropdown.
- Fill the other fields with the corresponding column names. If the vertex shader input does not have UV2 or something, leave these fields empty.

## Notice 

~~Export Large Mesh especially more than 30000 vertices need several seconds~~  
~~Python extension not efficient enough for that large Mesh. ~~

I change the export method which greatly enhance the export performance. 
