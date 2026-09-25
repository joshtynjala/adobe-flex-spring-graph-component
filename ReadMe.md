# SpringGraph Flex Component Version 2006/12/10

**SpringGraph** is a Flex 2.0 component that displays a set of items
that linked to each other. The component finds an appropriate layout for
the items based on tthe size and links of each item,. and draws lines to
represent the links. The component allows the end user to drag and/or
interact with individual items.

## What's in this document

- intro
- contents of the zipfile
- install instructions
- how to use SpringGraph in a Flex Application
- how to build SpringGraph and the samples
- how to work with the enclosed source code in FlexBuilder
- change log
- disclaimer, acknowledgements, contact info

## Contents of the zipfile

> *component_license.htm* - you should read and agree to this license
> before using the SpringGraph component and sample applications.
>
> *docs/* - API documentation for
> the SpringGraph component and associated classes.
>
> Samples/ - source code for various demo Flex applications
>
> > *Samples/SpringGraphDemo/* - interactively demonstrates various
> > features of SpringGraph component.
> >
> > *Samples/AmazonDemo/* - uses SpringGraph to explore Amazon.com.
> >
> > *Samples/XMLDemo/* - shows different ways of providing XML data to a
> > SpringGraph.
> >
> > *Samples/RoamerDemo/* - uses the Roamer component to explore large
> > graphs.
> >
> > *Samples/MoleculeViewer/* - uses the SpringGraph to draw schematic
> > diagrams of organic molecules
>
> *SpringGraph/* - source code and binaries for the SpringGraph
> component. There are 2 packages. The **forcelayout** package
> implements the iterative force-directed layout algorithm. This is pure
> actionscript code that is not coupled to the UI. The **springgraph**
> package contains the SpringGraph and Roamer components and their
> associated classes. This package takes care of managing the
> itemRenderers, link-drawing, timing, and other UI-related tasks.
>
> *build.bat* - a Windows batch file to build the component and the
> sample applications using the Flex SDK

## Install Instructions

Extract contents of zip file to any folder on your machine, mac or win.

## To use this component in a Flex application

If you're using a Flex Builder project, select Project \> Properties, go
to "Flex Build Path" \> "Library path" and add the file
*SpringGraph/bin/SpringGraph.swc* (this is the binary library file that
contains the SpringGraph and Roamer components).

If using command line compiler, copy SpringGraph.swc file to
"\frameworks\libs" folder of your Flex SDK installation, or use the
command line compiler's "library-path" configuration parameter.

To use the component, you provide a couple of things

- a **dataProvider -** information about what the items are, and what
  the links are. The dataProvider is an object of type **Graph** (which
  is included with the component), which has a simple API for defining
  items and links
- an **itemRenderer** - an MXML component that knows how to display an
  item. This can be a simple inline fragment of MXML, or a separate
  component that you've created.

You can find out how to use the SpringGraph component, the Graph class,
and the Item class by consulting the API
documentation and/or the example
applications.

## To build the component and the samples in the free Flex SDK

Make sure that your Flex SDK's bin folder is in your class path, open a
command shell, cd to the
SpringGraph_version folder, and run
"build.bat" file. FlexBuilder users can find a copy of the Flex SDK
inside their installation of FlexBuilder. See the batch file for more
info.

## To work with component or sample applications in FlexBuilder

These instructions should work on either mac or win.

1\. New \> Flex Library Project

- name: **SpringGraph**
- use default location: \<unchecked\>
- folder:
  **SpringGraph_version/SpringGraph**
- classes to include: \<all\>
- all other settings: \<leave as default\>

Go to the Project Properties \> Flex Library Compiler

- namespace URL: **`http://www.adobe.com/2006/fc`**
- manifest file: **manifest.xml**

Build the project. The resulting swc file appears in the bin folder.

2\. New \> Flex (or Apollo) Project

- access data: **Basic** (e.g XML or web service)
- project name:**SpringGraphDemo**
- use default location: \<unchecked\>
- folder:
  **SpringGraph\_version/Samples/SpringGraphDemo**
- library path:
  - either Add Project ... **SpringGraph**,
  - or Add SWC.. and locate **SpringGraph/bin/SpringGraph.swc**
- all other settings: \<leave as default\>

You can now build and run the project.

3\. repeat number 2 with **AmazonDemo**, **XMLDemo**,
**MoleculeViewer**, and **RoamerDemo** as the project name and folder

## Future possible improvements

Here's a few thoughts. Let me know your ideas.

- build a generic roaming framework
- improve performance on large graphs

## Change Log

### Version 2006/12/10

- added IViewFactory, SpringGraph.viewFactory
- added Roamer.back(), backOK, forward(), forwardOK
- added Roamer.history, historyIndex, tidyHistory, visibleHistoryItems

### Version 2006/12/02

- moved Roamer.autoFit to be SpringGraph.autoFit
- SpringGraph docs now tell you how to control the appearance of links
- new property SpringGraph.edgeRenderer
- new property Roamer.showHistory
- new functions Roamer.hideItem, resetHistory, resetShowHide, and
  showItem
- various small improvements to RoamerDemo

### Version 2006/11/19

- Graph.firstItem is now called Graph.distinguishedItem, and you can
  get/set it
- new function Roamer.setDataProvider
- new property Roamer.autoFit
- new properties Roamer.forceInvisible and Roamer.forceVisible
- new property SpringGraph.motionThreshold
- RoamerDemo has been updated with controls for autoFit, history, and
  hide item.

### Version 2006/11/06

- SpringGraph.dataProvider can now be an XML structure such as

         <stuff>
            <Nodes>
               <node id="2" otherstuff="bbb...."/>
               <node id="1" otherstuff="aaa...."/>
               <node id="3" otherstuff="ccc...."/>
            </Nodes>
            <Edges>
               <edge from="1" to="2"/>
               <edge from="2" to="3"/>
               <edge from="3" to="1"/>
            </Edges>
         </stuff>

- you can scroll the graph by clicking and dragging on the background

- a new Roamer component extends the SpringGraph by providing support
  for browsing large graphs (10,000's of items)

- you can define effects that are applied to items when adding or
  removing items from the view

- the SimpleGraph now automatically updates itself when the dataProvider
  Graph changes

### 2009-09-03

- updated the license to be the Apache 2.0 open source license. The
  version number is unchanged.

## Etc

This software is offered without support for any purpose you see fit. It
is informally maintained by Mark Shepherd of Adobe FlexBuilder
Engineering. Please let me know how you like it and whether it's working
for you.

SpringGraph was written by Mark Shepherd of Adobe Flex Builder
Engineering. The force-directed layout algorithm was translated and
adapted to ActionScript 3 from Java code written by Alexander Shapiro of
TouchGraph, Inc. (http://www.touchgraph.com).

Check out my blog at
http://mark-shepherd.com

You can email me at *mark.shepherd@adobe.com*. My AIM address is
me1shepherd.

-- Mark S, Dec 10, 2006

 

 

 
