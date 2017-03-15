---
title: Application Tab	
description: Overview of Application tab ribbon control.
platform: php
control: ribbon
documentation: ug
keywords: ribbon features, key features, ribbon overview 
---

# Application Tab

The Application Tab is used to represent a Menu that do some operations, such as File menu to create, open, and print documents. Application Tab classified by type property with the following:

* [menu]
* [backstage]

# Application Menu

The Application Menu is similar to traditional file menu options and Syncfusion ejMenu control is used internally to render this. To show Application Menu in Ribbon, set the type as menu and menuSettings to customize properties of ejMenu.

## Create Using Template

Set the UL element id to menuItemID property to create Application Menu and it will acts as template to render menu.

{% highlight html %}

          <div id="Ribbon"></div>
          <ul id="ribbonmenu">
              <li><a>FILE</a>
          <ul>
              <li><a>New</a></li>
              <li><a>Open</a></li>
              <li><a>Save</a></li>
              <li><a>Print</a></li>
          </ul>
              </li>
          </ul>
          <?php 
          require_once 'EJ\AutoLoad.php';
          $ribbon = new  \EJ\Ribbon('defaultRibbon');
          $aTab = new \EJ\Ribbon\ApplicationTab();           
          $aTab->type('menu')->menuItemID('ribbonmenu');
		  $hometab  = new \EJ\Ribbon\Tab();
          $clipboard  = new \EJ\Ribbon\Group();
          $grpcontent = new \EJ\Ribbon\Content();
          $contentgroup=new \EJ\Ribbon\ContentGroup();
          $btnsettings=array('contentType'=>'imageonly','prefixIcon'=>'e-icon e-ribbon e-new');
          $contentgroup->text('New')->type('custom')->contentID('Contents')->buttonSettings($btnsettings);   
          $grpcontent->groups(array($contentgroup));
          $clipboard->text('New')->content(array($grpcontent));
          $hometab->id('home')->text('HOME')->groups(array($clipboard));
          echo $ribbon ->width('500px')->applicationTab($aTab)->tabs(array($hometab))->render();
          ?>

{% endhighlight %}

![](Application/application_img1.png)


## Backstage Page

The Backstage page is where documents and related data of those can be managed, such as Create, Save and other information.

The Backstage page has a feature to add custom Control in left side of the page which contains menu items and the right side contains corresponding user controls.

You can set Application Tab type as backstage and set id , text to backstage items. Backstage pages can be added with required itemType and contentID as template id to render template into Backstage.

Separator between Backstage items can be enabled by setting enableSeparator as true. Width of back stage side header can be customized using headerWidth, If not set based on content given width will be considered.

To render the Ribbon with the Backstage page, refer to the following code snippet.


{% highlight html %}

           <div id="Ribbon"></div>
           <div id="newCon">
           <table>
             <tr>
                <td><button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button></td>
             </tr>
           </table>
           </div>
           <div id="infoCon">
		   <div style="padding-top:20px">
                <span style="font-size:17px">User Information</span>
           <div>
           <div class="e-accuser e-newpageicon" style="display:table-cell"></div>
           <div style="display:table-cell;vertical-align:middle">
               <div>user</div>
               <div>xyz@syncfusion.com</div>
           </div>
           </div>
           </div>
               <a href="#">Sign out</a>
           </div>
           <?php 
           require_once 'EJ\AutoLoad.php';
           $btn1 =  new EJ\Button("btn1");
           echo $btn1->contentType("textandimage")->prefixIcon("e-blank e-infopageicon")->imagePosition("imagetop")->width(205)->height(200)->size("large")->render();
           $ribbon = new  \EJ\Ribbon("defaultRibbon");
           $aTab = new \EJ\Ribbon\ApplicationTab();      
           $backstage = new \EJ\Ribbon\BackstageSetting();
           $backstagepages1=new EJ\Ribbon\Page();
           $backstagepages1->id("new")->text("New")->contentID("newCon");
           $backstagepages2=new EJ\Ribbon\Page();
           $backstagepages2->id("close")->text("Close")->enableSeparator("true")->itemType("button");
           $backstagepages3=new EJ\Ribbon\Page();
           $backstagepages3->id("account")->text("Office Account")->contentID("infoCon");
           $backstage->text("FILE")->height("350")->width("600px")->headerWidth("120px")->pages(array($backstagepages1,$backstagepages2,$backstagepages3));
           $aTab->type("backstage")->backstageSettings($backstage);
           $hometab  = new \EJ\Ribbon\Tab();
           $clipboard  = new \EJ\Ribbon\Group();
           $grpcontent = new \EJ\Ribbon\Content();
           $contentgroup=new \EJ\Ribbon\ContentGroup();
           $contentgroup->text('New')->type('custom')->contentID('ribbonContent');   
           $grpcontent->groups(array($contentgroup));
           $clipboard->text('New')->content(array($grpcontent));
           $hometab->id('home')->text('HOME')->groups(array($clipboard));
           echo $ribbon ->width('500px')->applicationTab($aTab)->render();
           ?>
		   <style type="text/css">
                .e-accuser {
                    background-image: url"themes/common-images/ribbon/User.jpg");
                }
                .e-blank {
                    background-image: url("themes/common-images/ribbon/blank.png");
                }
                .e-infopageicon {
                    background-repeat: no-repeat;
                    height: 150px;
                    width: 198px;
                }
                .e-newpageicon {
                    background-repeat: no-repeat;
                    height: 42px;
                    width: 42px;
                }
                .e-bspagestyle {
                    line-height: 0;
                    font-size: 30px;
                }
                .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
                    color: #212121;
                    background: #fdfdfd;
                    margin: 20px;
                }
           </style>

{% endhighlight %}

![](Application/application_img3.png)

N> Height & width of backstage can be set using height and width, if these are not set, Ribbon�s height & width will be considered.


