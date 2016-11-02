---
title: Getting Started with TimePicker | TimePicker | PHP | Syncfusion
description: Getting Started with TimePicker
platform: php
control: TimePicker
documentation: ug
keywords: Timepicker getting started, Timepicker features
---

# Getting Started

To get start with the TimePicker control using PHP wrapper classes, either of the following prerequisites needs to be installed in your machine to deploy and run those samples locally.

* [PHP tools for Visual Studio](https://visualstudiogallery.msdn.microsoft.com/6eb51f05-ef01-4513-ac83-4c5f50c95fb5)
* [Xampp](https://www.apachefriends.org/download.html)

In this section, let's see how to create, deploy and run the TimePicker samples using Xampp server.

## Creating a Sample Folder 

Usually, the Xampp gets installed in **C:\\** drive. Now, create a new sample folder namely **TimePicker_PHP** within `C:\\xampp\\htdocs` and place all the below mentioned folders within it.
You can create a PHP Project and add necessary scripts and styles with the help of the given PHP Getting Started Documentation.

### Adding Scripts and CSS files

The required scripts and CSS files can be copied into the above created sample folder namely **TimePicker_PHP** and then can be manually referred on the sample page or else the cdn links can be referred directly. In case, if you are manually referring the scripts and CSS files in your PHP sample, refer this [topic](https://help.syncfusion.com/js/control-initialization#manual-reference-of-scripts-and-style-sheets-in-a-html-page) to know how to copy the required scripts and CSS from the installed location.  

### Adding PHP Class libraries

Copy the PHP class libraries into your sample folder, which is a collection of PHP wrapper files created individually for all the controls in order to access and process its server-side values and then send it back to client-side. These libraries are available within the following installed location - 

* **(Installed Location)\\Syncfusion\\Essential Studio\\{{ site.releaseversion }}\\PHP\\Src** 

## Create a PHP file

Create your first php file in the newly created folder **TimePicker_PHP** and name it with ".php" extension.

You can either refer the `ej.web.all.min.js` file which inludes all the Syncfusion EJ controls or the TimePicker dependencies alone as given below.

TimePicker control has the following internal and should be referred before `ej` script files.

* [`jQuery`](http://jquery.com) 1.7.1 and later versions

and the internal dependencies which includes `ej.core` and [`child controls`](https://help.syncfusion.com/api/js/ejtimepicker#requires)

Refer the required script and CSS dependencies in your PHP page as show below to render the TimePicker control.

{% highlight html %}

    <!DOCTYPE html>
    <html>
        <head>
                <title>Getting Started - TimePicker</title>
                <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
                <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
                <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
        </head>
        <body>
            <?php
            ?>
        </body>
    </html>

{% endhighlight %}

N> 1. In case if you don’t want to use `ej.web.all.min.js` file, you can use our [`custom script generator`](https://help.syncfusion.com/api/js/ejtimepicker#requires) to create custom script file with required controls and its dependencies alone.

## AutoLoad file reference

Include the PHP AutoLoad file, which includes the necessary classes in the page on demand, within the `body` section of the PHP page.

{% highlight html %}

    <!DOCTYPE html>
    <html>
        <head>
                <title>Getting Started - TimePicker</title>
                <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /> 
                <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
                <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
        </head>
        <body>
            <?php require_once 'EJ\AutoLoad.php'; ?>
        </body>
    </html>

{% endhighlight %} 

## Control Initialization

Create a TimePicker control by instantiating the TimePicker class available in EJ namespace using `new` keyword as given below.
Store the instance in a variable and customize it (say, the initial value of the control) by calling the methods available in TimePicker class.
Finally, to render the created instance on browser, call the **render method** as shown below.

Return the created object by using `echo` function. 

{% highlight html %}

    <?php
       $dtp = new \EJ\TimePicker("dtp");
       echo $dtp->width("100%")->height("40px")->value(new DateTime())->render();
    ?>

{% endhighlight %} 

Add the above code in the body section.

## Running the PHP file

Open the **XAMPP control panel** and start the **Apache** module as shown in the below image. 

![](getting-started_images/control_panel.png)

Now, the sample can be run directly on the browser through localhost with appropriate port numbers, on which the Apache server is currently listening. For example, say if the Apache is configured to listen on port 7777, then type http://localhost:7777/ on your browser and press enter. Also, make sure that your sample folder is present within this location `C:\\xampp\\htdocs` as mentioned earlier.

The following output shows up on the browser, when you type http://localhost:7777/TimePicker_PHP/index.php and press enter - 

![](getting-started_images/timepicker.png)

N> In case, if you face any problem with default port 80 while running your sample, make the Apache to listen on some other available ports. The port number changes needs to be done on both the `httpd.conf` and `httpd-ssl.conf` files, in order to get rid of this problem.(Refer [here](http://stackoverflow.com/questions/20558410/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4-12)) 

