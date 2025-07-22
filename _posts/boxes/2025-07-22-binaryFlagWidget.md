---
layout: page-fullwidth
subheadline: "systems"
title:  "BinaryFlagCube Added to Application Builder"
teaser: "to graphically display digital status"
breadcrumb: true
tags:
    - post systems
categories:
    - boxes
image:
    thumb: /2025-07-22/binaryFlagCubeThumb.png
header: no
---
<div class="row t30">
    <div class="medium-3 columns"><span style="color: #083357;">.</span></div>
    <div class="medium-6 columns">
        <a href="{{ site.urlimg }}/2025-07-22/binaryFlagCube.png"><img style="border: 5px solid #ff6100;" src="{{ site.urlimg }}/2025-07-22/binaryFlagCube.png" ></a>
    </div>
    <div class="medium-3 columns"></div>
</div>

Often, digital status for many devices is stored as a single integer with the individual bits signifting the digital status. This can be difficult to display so we just add the BinaryFlagCube widget to the Blinky-Lite [application builder](https://www.blinky-lite.org/boxes/appbuilder/) to make it easy to add this functionality to customized user applications.  When the cursor is rolled over the bit display, a tool-tip describing the flag is displayed. The display can be set to a subset of the bits in the flag and the direction of the bits can also be changed.

An example JSON object is:
```
{
  type: 'BinaryFlagCube',
  config: 
  {
    trayIndex: 0,
    cubeName: 'watchdog',
    cubeLabel: 'Watchdog',
    startBit: 0,
    stopBit: 14,
    bitLabels: ['b0','b1','b2','b3','b4','b5','b6','b7','b8','b9','b10','b11','b12','b13','b14'],
    offColor: 'blue',
    onColor: 'yellow',
    borderColor: 'green'
  }
}
```