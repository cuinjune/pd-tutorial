# Pure Data Tutorial for beginners

## Description
This is a short step-by-step Pure Data tutorial for complete beginners.  
After this tutorial, you will be able to understand the basics of Pure Data and create a simple musical instrument using it.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [The Interface](#the-interface)
- [Building a Simple Sequencer](#building-a-simple-sequencer)
- [More Resources](#more-resources)

## Introduction

Pure Data (or Pd) is a real-time visual programming language designed for musicians, visual artists and performers to create software without writing lines of code. Pure Data is commonly used for live music performance, VJing, sound design, 2D/3D graphics processing, composition, audio analysis, interfacing with sensors, and cross-platform app and web development. Pure Data runs on macOS, Windows, Linux, Raspberry Pi, iOS, Android, and web browsers.

<img src="introduction1.png" width="400"/>

Programming with Pure Data is a unique interaction that is much closer to the experience of manipulating things in the physical world. The most basic unit of functionality is a box, and the program is formed by connecting these boxes together into diagrams that both represent the flow of data while actually performing the operations mapped out in the diagram. Because the programming is done visually, many artists find it a more intuitive tool than traditional text-oriented programming languages.

<img src="introduction2.png" width="200"/>

The real advantage of Pure Data is that it works in "real time". This means that changes can be made in the program even as it is running, and the user can see or hear the results immediately. This makes it a powerful tool for artists who would like to make sound or video in a live performance situation.

<img src="introduction3.png" width="400"/>

Pure Data has been used as the basis of a number of projects, as a prototyping language and a sound engine.

<img src="introduction4.png" width="400"/>


## Installation
Visit https://puredata.info/downloads/pure-data and click one of the download links depending on your platform.

<img src="installation.png" width="400"/>

If you are using **Windows**, open the downloaded installer file and follow the default instructions.

If you are using **macOS**, unzip the downloaded file and move it to the Applications folder.  
In case the app doesn't open because of the verification issue, open the app while holding down the Control key.

If you are using **Linux**, run the following terminal commands to install and open Pure Data:
```
sudo apt-get update -y
sudo apt-get install -y puredata
puredata
```

## The Interface

If you open Pure Data, you will see a console window that looks like this:

<img src="interface1.png" width="500"/>

The console window is mainly used to see information about the patch you are working on, as well as for debugging (correcting errors in your patch). So keep this window in a place where you can find it on your screen.

Under the "File" menu in the console window, select "New" to create a patch:

<img src="interface2.png" width="200"/>

You will see a patch window that looks like this:

<img src="interface3.png" width="500"/>

Under the "Put" menu in the patch window, select "Object" to place an object in your patch.

<img src="interface4.png" width="200"/>

Click on the patch to drop the object in its place. Type "print" inside this object and click again outside the box, you will create the [print] object.

<img src="interface5.png" width="500"/>

<img src="interface6.png" width="500"/>


## Building a Simple Sequencer

[![example](Untitled.svg)](#pd-tutorial)

## More Resources


