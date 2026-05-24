<img src="/assets/images/simple3D-logo.png" alt="simple3D" width =100%>

# Overview

Simple3D is a javascript extension for [Turbowarp](https://turbowarp.org), which is a mod of [Scratch](https://scratch.mit.edu), the popular platform where you can create you own projects such as simple games using block-based programming. Simple3D, based on WebGL allows for advanced rendering capabilities such as 3D rendering and calculations on the GPU.

For more datails, check Simple3D's [documentation](https://extensions.turbowarp.org/Xeltalliv/simple3D). It will show how certain blocks work but woun't teach you how to make your own game.
You can also check Simple3D's website, which hyas a number of example projects to have a rough idea of what the extension is capable of, along with intercative tutorials that will teach you how to display simple shapes like triangles.

In this guide, we'll see how it works, how to use it and how to create a 3D world with camera movement and importing your own 3D models.

## Installation
In order to use Simple3D, open the [web Turbowarp editor](https://turbowarp.org/editor) or download the desktop app, open the extension menu by clicking on the button on the bottom left of the editor and search for Simple3D. From now, you can click on the extension to start a new project from scratch or you can click on <ins>Sample Project</ins> to have a base to build on.  
In this guide, we'll tackle both cases.

# Guide

## Starting up
Create a new project in Turbowarp, and add the Simple3D extension.
We wil start off by defining the *clear color*, which is like the "background" color :

![](/assets/scratchblocks/clear.svg)

This sets the background color to black, where the `Red`, `Green`, `Blue` and `Alpha` channels are set with a value between 0 and 1.

## Introduction to meshes

Now, time to create a mesh. A mesh is a 3D representation of an object. It consists of a collection of faces, edges and vertices that define the object's shape and structure. Let's say we want to display a simple plane which will be the ground of our 3D world.
Create two new list and name them "**planeX**" and "**planeY**". Fill them with the numbers shown below :

**planeX :**  
`-1`  
`1`  
`-1`  
`-1`  
`1`  
`1`  

**planeY :**  
`-1`  
`-1`  
`1`  
`1`  
`-1`  
`1`  

These are the *vertices*, or the corners of your mesh. They define the shape of your mesh.

### UV

Create a new costume for your sprite or import. We will use this costume as the *texture* of our mesh.
Next, create two other list, called "**planeU**" and "**planeV**". Fill them with the following values :

**planeU :**  
`0`  
`1`  
`0`  
`0`  
`1`  
`1`  

**planeV :**  
`0`  
`0`  
`1`  
`1`  
`0`  
`1`  

UV*s* 
