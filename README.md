CTRLTools - A Maya tool for animators
======================================
***
**Version 0.9**  
**March 2023**

**Compatibility: Maya 2023 - Python 3**

**CTRLTools** is an Autodesk Maya tool for 3D animators developed by *[Roberto Menicatti](https://linktr.ee/robertomenicatti)*, which allows you to easily create controls and handle constraints
for additional props you might want to use in your animation shots.

Give a look at the video or read the guide below if you want to see its functionalities.

***

- [Quick Guide](https://robertom89.github.io/CTRLTools_Docs/#quick-guide)
- [Download and Install](https://robertom89.github.io/CTRLTools_Docs/#download-and-install)
- [How to Create a Control](https://robertom89.github.io/CTRLTools_Docs/#how-to-create-a-control)
- [How to Change the Color of a Control](https://robertom89.github.io/CTRLTools_Docs/#how-to-change-the-color-of-a-control)
- [How to Change the Width of a Control](https://robertom89.github.io/CTRLTools_Docs/#how-to-change-the-width-of-a-control)

***

## Quick Guide

On the menu bar, click on *Help → Help* to read a description of each command directly from **CTRLTools** interface, or *Help  → Online Guide* to be redirected to this page.
Read the following Sections to have a better understanding of each and every step and function.

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
## How to Create a Control

If you want to create a control for an object, simply select the object and click on "Create Control". 
A circular control will appear around it. 
You can now translate and rotate your object by moving the newly created control.
If you want to scale the object, use the "override scale" attributes of the control in the channel box. 
Use the scale gizmo instead, if you just want to scale the shape of the control.

***
## How to Change the Color of a Control

If you want to change the color of a control, select the control, choose a color by clicking on the 
color field, and click on "Replace Color". 
If you want to change the shape of a control, select the control, and click on any of the icons in the 
UI to replace the original shape with the one you like.

***
## How to Change the Width of a Control

If you want to change the line width of a control to improve its visibility, select the control and 
drag the slider. When the slider is released, the line width of the control will change.
Keep the slider to -1 if you want the line width to be the one set in Maya's Settings and Preferences
under the Display tab.
Values between 0 and 1 are considered as 1.


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
