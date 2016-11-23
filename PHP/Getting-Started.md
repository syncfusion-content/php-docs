---
layout: post
title: Getting Started | PHP | Syncfusion
description: Getting Started.
platform: php 
control: Common 
documentation: ug
---


# Getting Started

## Essential PHP 

### System Requirements

To work with PHP, you need install PHP on your machine

* PHP [5.3.3+ version](http://php.net/downloads.php).

* Unzip the downloaded file and move the unzipped folder to the desired drive.

#### Download

* Download the setup file (.exe) of Essential Studio for Essential PHP product from this [link](https://www.syncfusion.com/downloads/php) with your Syncfusion account.

Downloaded package contains the following directories.

1. /Src - Comprises of required PHP class files to use Essential PHP.
2. /Samples - Sample PHP Web Site.
3. /scripts - Contains necessary widget scripts as well as culture scripts for Syncfusion Essential PHP components. Also contains external dependency files such as jQuery, jsRender etc.
4. /themes - Contains the style sheets for web components.

### Run the Essential PHP demo web site

* Run the RunSample.bat file from the /Samples directory.
* Enter the directory path of the unzipped PHP folder (which contains PHP web server for Windows) on your machine. For example `C:\php-5.5.38-nts-Win32-VC11-x86` (unzipped directory).
* Now Essential PHP demo site will be successfully launched.

### Create a simple PHP Application

To use Essential PHP in your PHP web site, follow the steps below:

1. Copy Essential JavaScript and CSS files from /Samples/Scripts and /Samples/Content to your web site root. And include this files in your PHP page.

{% highlight html %}
    <head>
        <link rel="stylesheet" href="Content/ejthemes/bootstrap-theme/ej.web.all.min.css" />
		<script src="Scripts/jquery-3.0.0.min.js"></script> 
		<script src="Scripts/ej.web.all.min.js"> </script>
    </head>
{% endhighlight %}

2. Copy the individual component source files from /Src to your directory. Include the Essential PHP Autoload file available in the /Src directory. This file retreieves the required source files to render the specified controls.

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
