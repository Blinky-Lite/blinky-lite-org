---
layout: page-fullwidth
subheadline: "systems"
title:  "Application Builder Upgrade"
teaser: "with 9 card types and 13 cube types"
breadcrumb: true
tags:
    - post systems
categories:
    - boxes
image:
    thumb: 2024-01-31/2024-01-31_thumb.png
header: no
---
<div class="row t30">
    <div class="medium-12 columns">
        <a href="{{ site.urlimg }}/2024-01-31/widgets.png"><img src="{{ site.urlimg }}/2024-01-31/widgets.png" ></a>
    </div>
</div>

Building event driven controls applications can be quite complicated so Blinky-Lite has an application builder that makes it easy for the user to build his own custom dashboard application <span style="color:#ff6100;font-weight:900;">without having to do any programming.</span> The user just configures a JSON file. An example file is given in the [Blinky-Lite docs](/docs/pages/Overview/appBuilderPreview.html#sample-application-builder-json-file). The application builder has a basic library of widgets based on [Boostrap 4 cards](https://getbootstrap.com/docs/4.0/components/card/). This widget library is easily extensible to more widgets.

We just revamped the entire library Application Builder Library adding more cards and widgets.

## Application Builder Cards
Cards can be arranged in an order and the can be more than one CubeRowCard. There are currently nine different types of cards. 

- [CubeRowCard]({{ site.urlimg }}/2024-01-31/cubeRows.png) 
- [BarPlotCard]({{ site.urlimg }}/2024-01-31/barPlot.png)
- [TimePlotCard]({{ site.urlimg }}/2024-01-31/timePlot.png)
- [ArchivePlotCard]({{ site.urlimg }}/2024-01-31/archivePlot.png)
- [VectorPlotCard]({{ site.urlimg }}/2024-01-31/vectorPlot.png)
- [IframeCard]({{ site.urlimg }}/2024-01-31/iframePlot.png)
- [UserCard]({{ site.urlimg }}/2024-01-31/userCard.png)
- [CustomCard]

## Application Builder CubeRowCard Widgets
For the CubeRowCard there are 13  widgets defined.

- [GaugeCube]({{ site.urlimg }}/2024-01-31/gaugePlots.png)
- [HbarCube]({{ site.urlimg }}/2024-01-31/gaugePlots.png)
- [UrlLaunchCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [TextReadCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [TextSetCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [NumberReadCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [TimeStampReadCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [OnOffSetCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [ImageReadCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [LabelReadCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [SettingIncrCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [StateChoiceCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
- [DropChoiceCube]({{ site.urlimg }}/2024-01-31/cubeRows.png)
