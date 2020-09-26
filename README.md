# Pure Data Tutorial for beginners

<img src="images/logo.png" width="100"/>

## Description
This is a short step-by-step Pure Data tutorial for complete beginners.  
After this tutorial, you will be able to understand the basics of Pure Data and create a simple musical instrument using it.

## Table of Contents
* [Introduction](#introduction)
* [Installation](#installation)
* [The Interface](#the-interface)
* [Building a Simple Sequencer](#building-a-simple-sequencer)
* [More Resources](#more-resources)

## Introduction

**Pure Data** (or Pd) is a real-time visual programming language designed for musicians, visual artists, and performers to create software without writing lines of code. Pure Data is commonly used for live music performance, VJing, sound design, 2D/3D graphics processing, composition, audio analysis, interfacing with sensors, and cross-platform app and web development. Pure Data runs on macOS, Windows, Linux, Raspberry Pi, iOS, Android, and web browsers.

<img src="images/introduction1.png" width="400"/>

Programming with Pure Data is a unique interaction that is much closer to the experience of manipulating things in the physical world. The most basic unit of functionality is a box, and the program is formed by connecting these boxes together into diagrams that both represent the flow of data while actually performing the operations mapped out in the diagram. Because the programming is done visually, many artists find it a more intuitive tool than traditional text-oriented programming languages.

<img src="images/introduction2.png" width="200"/>

The real advantage of Pure Data is that it works in "real-time". This means that changes can be made in the program even as it is running, and the user can see or hear the results immediately. This makes it a powerful tool for artists who would like to make sound or video in a live performance situation.

<img src="images/introduction3.png" width="400"/>

Pure Data has been used as the basis of a number of projects, as a prototyping language and a sound engine.

<img src="images/introduction4.png" width="400"/>


## Installation
Visit https://puredata.info/downloads/pure-data and click one of the download links depending on your platform.

<img src="images/installation.png" width="400"/>

If you are using **Windows**, open the downloaded installer file and follow the default instructions.

If you are using **macOS**, unzip the downloaded file and move it to the **Applications** folder.  
In case the app doesn't open because of the verification issue, open the app while holding down the **Ctrl** key.

If you are using **Linux**, run the following terminal commands to install and open Pure Data:
```
sudo apt-get update -y
sudo apt-get install -y puredata
puredata
```

## The Interface

If you open Pure Data, you will see a console window that looks like this:

<img src="images/interface1.png" width="500"/>

The console window is mainly used to see information about the patch you are working on, as well as for debugging (correcting errors in your patch). So keep this window in a place where you can find it on your screen.

Under the "**File**" menu in the console window, select "**New**" to create a patch:

<img src="images/interface2.png" width="165"/>

You will see a patch window that looks like this:

<img src="images/interface3.png" width="500"/>

Under the "**Put**" menu in the patch window, select "**Object**" to place an object box in your patch.

<img src="images/interface4.png" width="150"/>

Click on the patch to drop the object box in its place. Type "print" inside the box and click again outside the box, you will create a **[print]** object.

<img src="images/interface5.png" width="500"/>

Under the "**Put**" menu in the patch window, select "**Message**" and type "Hello World" inside the box.

<img src="images/interface6.png" width="500"/>

You should notice that both the object and the message boxes have small rectangles at the corners.   
If these are at the top of the object, they are called "**inlets**", and at the bottom, they are called "**outlets**".  
The inlets and outlets are used to receive and send data between objects while they are connected.  
Click the outlet of **[Hello World(**, then drag the cable to the inlet of **[print]** to make a connection like this:

<img src="images/interface7.png" width="500"/>

There are types of objects that you can interact with your mouse. A message box is one of them.  
To make the message box clickable, we need to change out of "**Edit Mode**" and into "**Play Mode**".  
You can do this by clicking on the "**Edit Mode**" item in the "**Edit**" menu, or by using the shortcut **Ctrl+E**. (**Cmd+E** on macOS)

When you enter into "**Play Mode**", you will see that the pointing finger cursor changes into an arrow cursor.  
This change signifies that the mouse will interact differently with the elements within the patch.

<img src="images/interface8.png" width="500"/>

Now, if you click on the **[Hello World(** message box, you will see the message printed to the console window like this:

<img src="images/interface9.png" width="500"/>

In "**Edit Mode**", click on a cable to select it, then hit the **Backspace** key to delete the cable.

<img src="images/interface6.png" width="500"/>

Now, if you click on the **[Hello World(** message box again in "**Play Mode**", you will no longer see the message printed to the console window since they are disconnected.

<img src="images/interface9.png" width="500"/>

In "**Edit Mode**", clicking on the patch and dragging will select multiple objects to move, copy, duplicate, or delete.  

<img src="images/interface10.png" width="500"/>

You can edit the selected objects by clicking on one of the items in the "**Edit**" menu or by using the shortcuts.  

<img src="images/interface11.png" width="190"/>

Try duplicating and deleting the selected objects using the shortcuts. 
* Duplicate: **Ctrl+D** (**Cmd+D** on macOS)
* Delete: **Backspace**

<img src="images/interface12.png" width="500"/>

To get help associated with a specific object, you can right-click it then select "**Help**" from the drop-down menu.

<img src="images/interface13.png" width="500"/>

You will see a help patch that explains what the object does and also shows several examples of its use.

<img src="images/interface14.png" width="500"/>

## Building a Simple Sequencer

Now let's create a simple step sequencer. A step sequencer is a tool that allows us to store musical data (e.g. note, velocity) into individual steps to create musical patterns. In this tutorial, we are going to create a simple 4-step sequencer that stores 4 note values that are played in a loop. 

<img src="images/sequencer1.jpg" width="500"/>

In an empty patch window, under the "**Put**" menu, select "**Bang**" to create a bang button.

<img src="images/sequencer2.png" width="500"/>

Create an object box using **Ctrl+1** (**Cmd+1** on macOS) and type "**float**" inside it to create a **[float]** object.

<img src="images/sequencer3.png" width="500"/>

Under the "**Put**" menu, select "**Number**" to create a number box, duplicate it and make connections like the following:

<img src="images/sequencer4.png" width="500"/>

In "**Play Mode**", try dragging the upper number box up or down to change its value.

<img src="images/sequencer5.png" width="500"/>

If you click on the bang button, the **[float]** object will output its stored value.

<img src="images/sequencer6.png" width="500"/>

As you can see, the **[float]** object stores a number through its right inlet, and outputs the value when it receives a message named "**bang**" through its left inlet. "**bang**" is a special message, which many objects interpret as "do an action right now!".

Create a **[+ 1]** object above the upper number box and make connections like the following:

<img src="images/sequencer7.png" width="500"/>

In "**Play Mode**", if you click on the bang button, the output number will be increased by 1.  
This is because the **output number + 1** is stored in the **[float]** object whenever it outputs a value.  
Note: The number boxes are being used in this example as a visual aid and it will work identically without going through them.

<img src="images/sequencer8.png" width="500"/>

Create a **[mod 4]** object which outputs the remainder when the input number is divided by 4.  
And then create another number box below it and make connections like the following:

<img src="images/sequencer9.png" width="500"/>

In "**Play Mode**", if you click on the bang button, the output number will be wrapped between 0 and 3.

<img src="images/sequencer10.png" width="500"/>

Create a **[select 0 1 2 3]** object which receives a number and distributes the "**bang**" messages to the corresponding outlets.  
Place it at the bottom and make a connection like the following:

<img src="images/sequencer11.png" width="500"/>

Create four bang buttons that will be used as a visual aid.  
Place them at the bottom and make connections like the following:

<img src="images/sequencer12.png" width="500"/>

In "**Play Mode**", if you click on the bang button at the top, the below 4 bang buttons will flash according to the output number.

<img src="images/sequencer13.png" width="500"/>

Instead of you clicking the bang button to output a "**bang**" message, we can automate this using a **[metro]** object.  
A **[metro]** object outputs "**bang**" messages periodically given the time interval between them.  
Under the "**Put**" menu, select "**Toggle**" to create a toggle button and also create a **[metro 300]** object below it.  
Place them at the top and make connections like the following:

<img src="images/sequencer14.png" width="500"/>

In "**Play Mode**", if you click on the toggle button to enable it, the **[metro 300]** object will start and output "**bang**" messages at 300-millisecond intervals.  

<img src="images/sequencer15.png" width="500"/>

You can stop the **[metro 300]** object by clicking on the toggle button again to disable it.  
Now, create and connect the four **[float]** objects to each bang button at the bottom like the following:

<img src="images/sequencer16.png" width="500"/>

Under the "**Put**" menu, select "**Vslider**" to create a vertical slider.  
Create four vertical sliders and four number boxes and make connections like the following:

<img src="images/sequencer17.png" width="500"/>

Create a number box at the bottom and make connections like the following:

<img src="images/sequencer18.png" width="500"/>

In "**Play Mode**", enable the toggle button and try changing values of sliders by dragging them up or down.  
You will see the bottom number box outputs the slider values according to the step.

<img src="images/sequencer19.png" width="500"/>

This output number will be used as a MIDI note number in our sequencer to change the pitch (or the frequency of a sound wave).  
To do this, create a **[mtof]** (midi to frequency) object at the bottom which converts the incoming midi numbers to frequency.  
Also, create an **[osc~]** (oscillator) object which outputs a pure sine wave audio, given the input frequency.  
Make connections like the following:

<img src="images/sequencer20.png" width="500"/>

Create a **[dac~]** (digital-to-analog converter) object at the bottom and make connections like the following:

<img src="images/sequencer21.png" width="500"/>

**Warning: Be sure to set the audio volume on your computer fairly low since it can be pretty loud.**  
In the console window, click on the DSP toggle button to turn the audio on.  

<img src="images/sequencer22.png" width="500"/>

Try moving the sliders to create musical patterns.  
You can change the slider's output range by right-clicking on a slider and selecting **Properties** from the drop-down menu.

<img src="images/sequencer23.png" width="500"/>

Change each slider's output range to between 36 and 84. (C2 ~ 	C6)  
You can also change other properties such as size and colors.

<img src="images/sequencer24.png" width="500"/>

Under the "**File**" menu in the patch window, select "**Save**" to save the patch.

<img src="images/sequencer25.png" width="165"/>

Congratulations! You have now created a functioning sequencer in Pure Data.  
We have chosen the above methods to build a sequencer however there are many other ways to build one, including using a table.   
You will discover these as you delve deeper into the world of Pure Data.

## More Resources

* Video tutorials:
  * [Tutorials by Dr. Rafael Hernandez](https://www.youtube.com/playlist?list=PL12DC9A161D8DC5DC)
  * [Learning Synthesis with Pure Data Series](https://youtu.be/Fx5nTjUrK-g)
  * [Pure Data Tutorials - Rich Synthesis](https://www.youtube.com/playlist?list=PLqJgTfn3kSMW3AAAl2liJRKd-7DhZwLlq)
  * [Pure Data GEM Tutorials](https://www.youtube.com/playlist?list=PLUnWNyI8WKO2_LF59jbOC3wFg5AYaY5Sf)
  * [Miller Puckette MUS171 Videos](http://pd-la.info/pd-media/miller-puckette-mus171-videos/)

* Text tutorials:
  * [Pure Data Floss Manuals](http://write.flossmanuals.net/pure-data/introduction2/)
  * [Programming Electronic Music in Pd](http://www.pd-tutorial.com/english/index.html)
  * [Practical synthetic sound design](https://www.moz.ac.at/sem/lehre/lib/pd-sounddesign/index.html)
  * [PureData Algorithmic Composition Tutorials](http://www.algorithmiccomposer.com/)
  
* Books:
  * [The Theory and Technique of Electronic Music](http://msp.ucsd.edu/techniques/latest/book.pdf)
  * [Programming Sound with Pure Data](https://www.amazon.com/Programming-Sound-Pure-Data-Dynamic/dp/1937785661)
  * [Designing Sound](https://www.amazon.com/Designing-Sound-Andy-Farnell/dp/0262014416)
  * [Making Musical Apps](https://www.amazon.com/Making-Musical-Apps-Real-time-synthesis/dp/1449314902)

* Communities:
  * [Pure Data Forum](https://forum.pdpatchrepo.info/)
  * [Pure Data Facebook Group](https://www.facebook.com/groups/puredata/)
  * [Pure Data Reddit Community](https://www.reddit.com/r/puredata/)
  * [Discord Pure Data Chat](https://discord.com/invite/AZ43djV)
  

