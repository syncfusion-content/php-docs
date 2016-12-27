---
layout: post
title: Getting Started | PHP | Syncfusion
description: Getting Started.
platform: php 
control: Common 
documentation: ug
---


# Essential PHP 

## System Requirements

To work with PHP, you need install PHP on your machine

* PHP [5.3.3+ version](http://php.net/downloads.php).

* Unzip the downloaded file and move the unzipped folder to the desired drive.

## Download and Install 

Download and install the Essential PHP component setup from this link after logging in with your Syncfusion account. 

You can download the Essential PHP components in two ways.

* Setup file(.exe).
* Zipped file.

If you are installing the setup file (.exe), then the Essential PHP component packages will be available under the installed location of Syncfusion, refer below.

   (installed location) \Syncfusion\Essential Studio\14.4.0.15\PHP\.

You can also find the PHP samples (demo website) available under the below installed location.

  (installed location) \Syncfusion\Essential Studio\14.4.0.15\PHP\Samples\.

If you are downloading the zipped package, Downloaded package contains the following directories.

1. /Src - Comprises of required PHP class files to use Essential PHP.
2. /Samples - Sample PHP Web Site.
3. /scripts - Contains necessary widget scripts as well as culture scripts for Syncfusion Essential PHP components. Also contains external dependency files such as jQuery, jsRender etc.
4. /themes - Contains the style sheets for web components.

## Run the Essential PHP demo web site

To run the Essential PHP demo site, kindly refer the ReadMe.html file in `/Samples` location.

## Create a simple PHP Application

To use Essential PHP in your PHP web site, follow the below steps:

1. Copy Essential JavaScript and CSS files from `/scripts` and `/themes` to your web site root. And include the necessary files in your PHP page.

{% highlight html %}
    <head>
        <link rel="stylesheet" href="themes/bootstrap-theme/ej.web.all.min.css" />
		<script src="scripts/external/jquery-3.1.1.min.js"></script> 
		<script src="scripts/web/ej.web.all.min.js"> </script>
    </head>
{% endhighlight %}

2. Copy the individual component source files from `/Src` to your directory. Include the Essential PHP **Autoload.php** file available in the `/Src` directory. This file *automatically retreieves the required source class files* to render the specified controls.

{% highlight html %}
    <body>
        <?php require_once 'Src/AutoLoad.php'; ?>
        <!--Enter your code to render EJ controls -->
    </body>
{% endhighlight %}

3. Use any Essnetial PHP wrapper. For Example, to use DatePicker refer below.

{% highlight html %}
    <?php
    $date = new \EJ\DatePicker("datepicker"); // initialize a new instance of DatePicker with id
    echo $date->width("100%")->height("40px")->watermarkText("select a date")->render(); // configure the DatePicker using the fluent API and display the output
    ?>
{% endhighlight %}

4. Run the PHP web site, the DatePicker widget will be displayed as shown below,

   ![](/PHP/Getting-Started_images/Getteing-Started_img1.JPG)
