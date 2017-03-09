--
title: Group
description: Overview of Group ribbon control.
platform: php
control: ribbon
documentation: ug
keywords: ribbon features, key features, ribbon overview 
---

# Group

Group is a collection of logical content groups that are combined under related Tab. Each group can be defined using content groups or custom content.

## Adding Tab Groups

Group items can be added to Tabs by specifying text and corresponding content to be displayed. The content of group can be specified as either with content collection, contentID or customContent.

### Adding Content

Add content to Group item which is based on type of content specified. The available types are button, splitButton, toggleButton,gallery, and dropDownList.

Groups and defaults settings can be added with the content.

## Defaults

The height, width, type, isBig property to the controls in the group can be specified commonly.
The height & width applicable to button, split button, dropdown list ,Toggle button controls and isBig applicable to only button controls ( button, split , toggle)

## Adding Content Groups

Controls such as button, split button, dropdown list, toggle button, gallery in the subgroup of the Ribbon tab can be rendered. All of these can be customized using its corresponding settings property such as buttonSettings, dropdownSettings, etc.

Custom controls or items (such as table, div etc.) can be added when the type set as custom. defaults control settings of group can be specified for an individual group instead of specifying them to groups collection commonly.

Tooltip and Custom Tooltip can be specified for each group controls.

{% highlight html %}

                <div id="Ribbon"></div>
	            <ul id="ribbonmenu">
		            <li>
		            <a>FILE</a>
		            <ul>
		            <li><a>Open</a></li>
		            </ul>
		            </li>
	            </ul>
	            <ul id="pasteSplit">
		            <li>Paste</li>
		            <li>Paste Special</li>
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
                $splitButtonSettings = array('contentType'=>'imageonly','targetID'=>'pasteSplit','imagePosition'=>'imagetop','prefixIcon'=>'e-icon e-ribbon e-ribbonpaste'); 
                $contentgroup->id('paste')->text('Paste')->toolTip('Paste')->splitButtonSettings($splitButtonSettings);   
                $default= new \EJ\Ribbon\Defaults();
                $default->width(60)->height(40)->type("splitbutton");
                $grpcontent->groups(array($contentgroup))->defaults($default);
                $clipboard->text('ClipBoard')->content(array($grpcontent));
                $clipboard1  = new \EJ\Ribbon\Group();
                $grpcontent1 = new \EJ\Ribbon\Content();
                $contentgroup1=new \EJ\Ribbon\ContentGroup();
                $contentgroup2=new \EJ\Ribbon\ContentGroup();
                $togglebutton =  array('defaultText'=>'Cut','targetID'=>'pasteSplit','activeText'=>'Cut Over'); 
                $togglebutton1 =  array('defaultText'=>'Copy','targetID'=>'pasteSplit','activeText'=>'Copy Over'); 
                $contentgroup1->id('cut')->toggleButtonSettings($togglebutton);
                $contentgroup2->id('copy')->toggleButtonSettings($togglebutton1);
                $default1= new \EJ\Ribbon\Defaults();
                $default1->width(75)->height(30)->type("togglebutton");
                $grpcontent1->groups(array($contentgroup1,$contentgroup2))->defaults($default1);
                $clipboard1->text('Font')->alignType("columns")->content(array($grpcontent1));
                $hometab->id('home')->text('HOME')->groups(array($clipboard,$clipboard1));
                echo $ribbon ->width('500px')->applicationTab($aTab)->tabs(array($hometab))->render();
                ?>

{% endhighlight %}

![](group_img1.png)

## Enable Separator

Separates the control from the next control in the group when group alignType is row. Set “true” to enableSeparator.

{% highlight html %}

                <div id="Ribbon"></div>
	            <ul id="ribbonmenu">
		            <li>
			        <a>FILE</a>
			    <ul>
				    <li><a>New</a></li>
                    <li><a>Open</a></li>
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
                $contentgroup1=new \EJ\Ribbon\ContentGroup();
                $btnsettings = array('width'=> 100); 
                $contentgroup->id('new')->text('New')->toolTip('New')->enableSeparator('true')->buttonSettings($btnsettings);   
                $btnsettings1 = array('width'=> 150);
                $contentgroup1->id('font')->text('Font')->toolTip('Font')->buttonSettings($btnsettings1);  
                $default= new \EJ\Ribbon\Defaults();
                $default->width(70)->type('button');
                $grpcontent->groups(array($contentgroup,$contentgroup1))->defaults($default);
                $clipboard->text('New')->alignType('rows')->content(array($grpcontent));
                $hometab->id('home')->text('HOME')->groups(array($clipboard));
                echo $ribbon ->width('500px')->applicationTab($aTab)->tabs(array($hometab))->render();
                ?>

{% endhighlight %}

![](group_img2.png)

