---
layout: post
title: Getting Started with PHP Button Control | Syncfusion
description: Learn here about getting started with Syncfusion Essential PHP Button Control, its elements, and more.
platform: js
control: Button
documentation: ug
---

# Getting Started with PHP Button

This section explains briefly about the necessary steps required to render and configure EJ Button control using PHP wrapper classes.

Create a PHP Project and add necessary scripts and styles with the help of the given PHP [Getting Started](https://help.syncfusion.com/php/getting-started) Documentation.


## Create Button Widget

Create a Button control by instantiating the PHP wrapper class available in EJ namespace as shown below.

{% highlight html %}

<table>
    <tr>
        <td >My First Button</td>
        <td>
            <?php
            $button =  new EJ\Button("myButton");
            echo $button ->text("BUTTON")->render();
            ?>
        </td>
    </tr>
</table>

{% endhighlight %}

Execute the above code to render the following output.

![PHP Button Widget](Getting-Started_images/Getting-Started_img1.JPG)
