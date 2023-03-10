CTRL Tools - A Maya tool for animators
======================================
***
**Version 0.9**  
**March 2023**

**Tested on: Maya 2023 - Python 3**

**CTRL Tools** is an Autodesk Maya tool for 3D animators developed by *[Roberto Menicatti](https://linktr.ee/robertomenicatti)*, which allows you to easily create controls and handle constraints
for additional props you might want to use in your animation shots.

Give a look at the video or read the guide below if you want to see its functionalities.

***

- [Quick Guide](https://robertom89.github.io/CTRLTools_Docs/#quick-guide)
- [Download and Install](https://robertom89.github.io/CTRLTools_Docs/#download-and-install)
- [Create Control](https://robertom89.github.io/CTRLTools_Docs/#create-control)
- [Create Locator](https://robertom89.github.io/CTRLTools_Docs/#create-locator)
- [Replace Color](https://robertom89.github.io/CTRLTools_Docs/#replace-color)
- [Replace Control Shape](https://robertom89.github.io/CTRLTools_Docs/#replace-control-shape)
- [Change Shape Scale](https://robertom89.github.io/CTRLTools_Docs/#change-shape-scale)
- [Change Line Width](https://robertom89.github.io/CTRLTools_Docs/#change-line-width)
- [Store Pose and Apply Pose](https://robertom89.github.io/CTRLTools_Docs/#store-pose-and-apply-pose)
- [Passive Constraint](https://robertom89.github.io/CTRLTools_Docs/#passive-constraint)
- [Active Constraint](https://robertom89.github.io/CTRLTools_Docs/#active-constraint)


***

## Quick Guide

On the menu bar, click on *Help → Help* to read a description of each command directly from **CTRLTools** interface, or *Help  → Online Guide* to be redirected to this page.
Read the following Sections to have a better understanding of each and every step and function.

***
## Download and Install

After downloading the zipped folder, uncompress it wherever you want and move the inner content, i.e. *CTRLTools* folder, to Maya scripts folder. Depending on how you unzipped the folder, you may have two nested CTRLTools folders; 
make sure to copy the inner one, which is the one containing the Python files.

You cand find Maya scripts folder here:

- on **Windows**   
~~~
    <user’s directory>/Documents/maya/scripts/  
~~~
- on **macOS**  
~~~
    Library/Preferences/Autodesk/maya/scripts/  
~~~

With Maya open, simply drag the file **CTRLTools_installer.py** onto the viewport to add the tool to the current shelf.
Click on the new shelf button to run **CTRL Tools**.

***
## Create Control
Select a mesh and click on *Create Control* to create a 4-arrows shaped control around the mesh.
Translate and rotate the new control to translate and rotate the mesh.
Use the *Override Scale X/Y/Z* attributes of the control in the channel box to scale the mesh.

You have two options:
- **At Pivot**

  Check this box if you want the control to be created where the pivot of the object is;

- **At Locators**

  Check this if box you want the control to be created at specific points, defined by custom locators.
  
  Select the object first and then the locator (even more than one if you want offset controls) before running the command.
  
  The last selected locator will determine which is the topmost parent, i.e. the Main control of the object.

  Untick *Delete Locators* if you want to keep the original locators after the creation of the control.

## Create Locator
This command creates a Locator object on the grid. It's the same as Maya command under *Create -> Locator*.

## Replace Color
Click on the color field to choose a color from the color wheel pop-up window and click on *Replace Color*
to change the color of the selected controls.

## Replace Control Shape
With a control selected, click on any of the UI icons to replace the original shape of the selected control
with the one you choose.

## Change Shape Scale
With a control selected, drag the slider towards the right/left to increase/decrease its relative scale.

## Change Line Width
With a control selected, drag the slider to change the line width of the control shape.
Set the value at -1 to reset the line width to its default value (set in Maya's *Settings and Preferences*
under the *Display* tab).
Values between 0 and 1 count as 1.

## Store Pose and Apply Pose
Click on *Store Pose* to temporarily store the pose of the selected object in Maya world space.
Click on *Apply Pose* to apply the previously stored pose to the selected object.
These two commands can be very useful when you have to switch the object's parent when
dealing with parent constraints, to keep the object in the position it had before the switch.

***
## Passive Constraint
Use *Passive Constraint* if you want to constrain the object to some other moving elements (a character hand or anything else, for example), i.e. if you want to make the object follow the motion of other animated elements in the scene.

Select all the controls that will guide the motion first (parents) and the object's control at last (child), and click on *Passive Constraint*.

Two new controls are created around the object. 
- The circular one (OFFSET) has a *Constraint* attribute in the Channel Box that allows you to select which one among the different parents is currently active. 

  This control will also be used from now on to translate and rotate the object with rispect to the location and orientation of the active parent.

- The locator (FREE) is an additional parent object which is created to let the object free and independent when it doesn't need to follow anything.

  For example: imagine that a character is holding a ball in his left hand for a while, then takes the ball with the right hand and then throws it away. 
  
  You can select the left hand control, the right hand control and the ball's control and create a Passive Constraint for the ball. From the new OFFSET control you will key the *Constraint* attribute so that the left hand is parent at first, then you will switch the attribute to have the right hand as parent and finally, when character throws the ball, you will swith the attribute to have the FREE control as parent, so that the ball can follow its trajectory in the air without being influenced by any of the hands constraints.  

This constraint works with referenced elements too.

## Active Constraint
Use *Active Constraint* if you want to constraint some other elements of the scene to your object, i.e. if you want to make the object drive the motion of something else.

Select the object's control first (parent) and then all the controls that should follow the object (children), and click on *Active Constraint*.

- A new circular control is created around the object.
  
  This control has a *Constraint* attribute in the Channel Box for each child element.
  You can activate or deactivate any of the constraints by setting their respective value to on/off.
  
  This control will also be used from now on to translate and rotate the object.

- A new locator control is also created around each child.
  
  Since the translations and rotations of each child are now constrained to the object and can't be keyed anymore, the new locator controls are created to let you rotate and translate the children elements despite the parent constraint.

This constraint works with referenced elements too.

<button onclick="topFunction()" id="myBtn" title="Go to top" style="display: none;
  width: 50px;
  height: 50px;
  position: fixed;
  bottom: 20px;
  right: 30px;
  z-index: 99;
  font-size: 18px;
  display: inline-flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: none;
  outline: none;
  background-color: #2D7180;
  color: white;
  cursor: pointer;
  padding: 15px;
  border-radius: 100%;">Top</button>

<script>
//Get the button
var mybutton = document.getElementById("myBtn");

// When the user scrolls down 20px from the top of the document, show the button
window.onscroll = function() {scrollFunction()};

function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    mybutton.style.display = "block";
  } else {
    mybutton.style.display = "none";
  }
}

// When the user clicks on the button, scroll to the top of the document
function topFunction() {
  document.body.scrollTop = 0;
  document.documentElement.scrollTop = 0;
}
</script>

<style>
* {
  box-sizing: border-box;
}

.column {
  float: left;
  width: 50%;
  padding: 5px;
}

/* Clearfix (clear floats) */
.row::after {
  content: "";
  clear: both;
  display: table;
}
</style>
