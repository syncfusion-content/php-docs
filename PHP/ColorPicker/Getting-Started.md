---
title: Getting Started with ColorPicker | ColorPicker | PHP | Syncfusion
description: Getting Started with ColorPicker
platform: php
control: ColorPicker
documentation: ug
keywords: Colorpicker getting started, Colorpicker php
---

# Getting Started

This section illustrates the details on how to render and configure a Colorpicker control using the methods available in PHP wrapper classes. 

Create a PHP Project and add necessary scripts and styles with the help of the given PHP [Getting Started](https://help.syncfusion.com/php/getting-started) Documentation.

## Create Colorpicker

Create a Colorpicker control by instantiating the ColorPicker class available in EJ namespace and configure it.

{% highlight html %}

    <?php
        $color = new \EJ\ColorPicker("colorpicker");
        echo $color->value("#278787")->render();
    ?>

{% endhighlight %} 

The following screenshot illustrates the output of above code.

![](Getting-Started_images/colorpicker.png)

