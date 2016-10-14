---
title: Getting Started for Essential JavaScript Spreadsheet
description: How to create a Spreadsheet with data source, apply format and export it as excel file.
platform: PHP
control: Spreadsheet
documentation: ug
keywords: 
---
# Getting started

This section explains you the steps required to populate the Spreadsheet with data, format, and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

# Adding Script Reference

Create an **HTML** page and add the scripts references in the order mentioned in the following code example.

{% tabs %}
{% highlight html %}

<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <meta name="description" content="Essential Studio for JavaScript">
        <meta name="author" content="Syncfusion">
          <title></title>
          <!-- Essential Studio for JavaScript theme reference -->
          <link rel="stylesheet" href="http://cdn.syncfusion.com/13.4.0.53/js/web/flat-azure/ej.web.all.min.css" />
          <!-- Essential Studio for JavaScript script references -->
          <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
          <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>
          <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
          <script src="http://cdn.syncfusion.com/13.4.0.53/js/web/ej.web.all.min.js"> </script>
          <!-- Add your custom scripts here -->
        </head>
  <body> </body>
</html>

{% endhighlight %}
{% endtabs %}

In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use [`CSG`](http://csg.syncfusion.com/# "CSG") utility to generate a custom script file with the required widgets for deployment purpose.

N> For details about Spreadsheet internal and external dependencies refer following [`link`](http://help.syncfusion.com/js/spreadsheet/dependencies "link")

## Initialize Spreadsheet


Initialize the Spreadsheet by using the ejSpreadsheet method. The Spreadsheet is rendered based on default `width` and `height`. You can also customize the Spreadsheet dimension by setting the [`width`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings-width "width") and [`height`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings-height "height") property in [`scrollSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings "scrollSettings").


{% highlight html %}

<?php
require_once '..\EJ\AutoLoad.php';
?>
<div class="cols-sample-area">
  <?php
   
    $sheet1 = new EJ\Spreadsheet\Sheet();
    $sheets = array($sheet1);
    $scroll = new EJ\Spreadsheet\ScrollSetting();
    $scroll->height(500)->width(900);
	
    echo $spreadsheet -> sheets($sheets)->scrollSettings($scroll)-> render();


    ?>
</div>

{% endhighlight %}

Now, the Spreadsheet is rendered with default row and column count.

![Getting-Started_images/md_img1.png](Getting-Started_images/md_img1.png)

## Populate Spreadsheet with data

Now, this section explains how to populate JSON data to the Spreadsheet. You can set[`dataSource`](http://help.syncfusion.com/js/api/ejspreadsheet#members:sheets-datasource "dataSource") property in [`sheet`](http://help.syncfusion.com/js/api/ejspreadsheet#members:sheets "sheet") settings to populate JSON data in Spreadsheet.

{% highlight html %}

<?php
require_once '..\EJ\AutoLoad.php';
?>
<div class="cols-sample-area">
  <?php
   
    $Json = json_decode(file_get_contents("Data.json"), true);
    $rangeSetting1 = new EJ\Spreadsheet\RangeSetting();
    $rangeSetting1->dataSource($Json);
    $rangeSettings = array($rangeSetting1);
    $sheet1 = new EJ\Spreadsheet\Sheet();
    $sheet1->rangeSettings($rangeSettings);
    $sheets = array($sheet1);
    $spreadsheet =  new EJ\Spreadsheet('Spreadsheet');
    $scroll = new EJ\Spreadsheet\ScrollSetting();
    $scroll->height(500)->width(900);
	
    echo $spreadsheet -> sheets($sheets)->scrollSettings($scroll)->render();


    ?>
</div>
{% endhighlight %}

![Getting-Started_images/md_img2.png](Getting-Started_images/md_img2.png)

N> For more details about `data binding` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-binding# "link")

## Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain colour based on the cells values. You can use [`allowConditionalFormats`](http://help.syncfusion.com/js/api/ejspreadsheet#members:allowconditionalformats "allowConditionalFormats") property to enable/disable Conditional formats.

To apply conditional formats for a range use [`setCFRule`](http://help.syncfusion.com/js/api/ejspreadsheet#methods:xlcformat-setcfrule "setCFRule") method. The following code example illustrates this,


{% highlight html %}

<?php
require_once '..\EJ\AutoLoad.php';
?>
<div class="cols-sample-area">
  <?php
   
    // ...                                        
    echo $spreadsheet -> sheets($sheets)->scrollSettings($scroll)->loadComplete('loadComplete')->render();


    ?>
</div>
function loadComplete() {                
    this.XLCFormat.setCFRule({ "action": "greaterthan", "input1": "10", "color": "redft", "range": "D3:D8" });
}

{% endhighlight %}

![Getting-Started_images/md_img3.png](Getting-Started_images/md_img3.png)

N> For more details about `Conditional Formatting` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-presentation#conditional-formatting "link")

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set [`allowExporting`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-allowexporting "allowExporting") option in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") as `true`. Since Spreadsheet uses server side helper to save documents set [`excelUrl`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-excelurl "excelUrl") in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") option. The following code example illustrates this,


{% highlight html %}

<?php
require_once '..\EJ\AutoLoad.php';
?>
<div class="cols-sample-area">
    <?php
   
    // ...                    
    $exportSetting = new EJ\Spreadsheet\ExportSetting();
	  $exportSetting->excelUrl('http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToExcel')->csvUrl('http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToCsv')->pdfUrl('http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToPdf');

    // ...
    ?>
</div>

{% endhighlight %}

Use shortcut [`Ctrl + S`](http://help.syncfusion.com/js/spreadsheet/keyboard-shortcuts# "Ctrl + S") to save Spreadsheet as excel file.


N> 1. For more details about `Export` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#save "link")
N> 2. For more details about `Server Configuration` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#server-configuration "link")
