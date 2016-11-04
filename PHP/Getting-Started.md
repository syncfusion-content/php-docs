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

#### Download

* Download the setup file (.exe) of Essential Studio for Essential PHP product from this [link](https://www.syncfusion.com/downloads/php) with your Syncfusion account.

Downloaded package contains the following directories.

1. /Src - PHP files required to use Essential PHP.
2. /Samples - Sample PHP Web Site.
3. /Samples/Scripts - Minified EJ and external JavaScript files.
4. /Samples/Content - Minified EJ & external CSS files and background images used by the themes.


### Create a simple PHP Application


#### Prerequisites

You can find a sample PHP web site in the `/Samples` directory of the Essential PHP distribution. To run the web site, copy this directory to your web root. Then navigate to index.php.


#### Configuration

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
        <?php require_once 'Src\AutoLoad.php'; ?>
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
