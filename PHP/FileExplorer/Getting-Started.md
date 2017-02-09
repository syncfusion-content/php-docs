---
layout: post
title: Getting-Started with FileExplorer
description: getting started
platform: php
control: File Explorer
documentation: ug
---

# Getting Started

The external script dependencies of the FileExplorer widget are,

* [jQuery 1.7.1](http://jquery.com/) and later versions.

And the internal script dependencies of the FileExplorer widget are:

<table>
<tr>
<th>
File</th><th>
Description/Usage</th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Must be referred always before using all the JS controls.<br/><br/></td></tr>
<tr>
<td>
ej.data.min.js<br/><br/></td><td>
Used to handle data operation and should be used while binding data to JS controls.<br/><br/></td></tr>
<tr>
<td>
ej. draggable.min.js<br/><br/></td><td>
Used to handle the drag and drop functionality<br/><br/></td></tr>
<tr>
<td>
ej.scroller.min.js<br/><br/></td><td>
Used to show the scroller in the layout area<br/><br/></td></tr>
<tr>
<td>
ej.button.min.js<br/><br/></td><td>
Used to display the buttons in the toolbar<br/><br/></td></tr>
<tr>
<td>
ej.treeview.min.js<br/><br/></td><td>
Used to display the treeview in the navigation pane<br/><br/></td></tr>
<tr>
<td>
ej.uploadbox.min.js<br/><br/></td><td>
Used to perform the upload functionality <br/><br/></td></tr>
<tr>
<td>
ej.waitingpopup.min.js<br/><br/></td><td>
Used to showcase the waiting popup<br/><br/></td></tr>
<tr>
<td>
ej.dialog.min.js<br/><br/></td><td>
Used to create the alert windows <br/><br/></td></tr>
<tr>
<td>
ej.splitter.min.js<br/><br/></td><td>
Used as the body section to separate the navigation and layout area<br/><br/></td></tr>
<tr>
<td>
ej.toolbar.min.js<br/><br/></td><td>
Used to showcase the hearer section<br/><br/></td></tr>
<tr>
<td>
ej.menu.min.js<br/><br/></td><td>
Used to showcase the context menu<br/><br/></td></tr>
<tr>
<td>
ej.grid.min.js<br/><br/></td><td>
Used to showcase the grid layout view<br/><br/></td></tr>

</table>

For getting started you can use the ‘ej.web.all.min.js’ file, which encapsulates all the 'ej' controls and frameworks in one single file.<br/> 

For themes, you can use the ‘ej.web.all.min.css’ CDN link from the snippet given. To add the themes in your application, please refer [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components#adding-specific-theme-to-your-application).


## Preparing HTML document

You can create a PHP Project and add necessary scripts and styles with the help of the given PHP Getting Started Documentation.

Create a first PHP file in Xampp and name it appropriately with `.php` extension and also place it under the newly created sample folder. For example, say Index.php with the initial code as shown below 

Refer the required scripts and CSS files in your PHP page as mentioned below in order to render the FileExplorer control  

{% highlight html %}

    <!DOCTYPE html>
       <html>
        <head>
                <title>Getting Started - DropDownList</title>
                <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
                <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css" rel="stylesheet" />
                <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
                <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
                <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
        </head>
        <body>
           <?php require_once 'EJ/AutoLoad.php'; ?>
        </body>
    </html>

{% endhighlight %}

## Creating FileExplorer

The FileExplorer can be created in **PHP** by using the below given code.

{% highlight html %}
	
	<?php
        $fileexplorer=new EJ\FileExplorer('default');
        echo $fileexplorer->width('100%')->minWidth('150px')->layout('grid')->path('http://mvc.syncfusion.com/ODataServices/FileBrowser/')->ajaxAction('http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction')->isResponsive(true)->fileTypes('*.png, *.gif, *.jpg, *.jpeg, *.docx')->render();
        ?>
{% endhighlight %}
	
![](Getting-Started_images/Getting-Started_img1.png)

