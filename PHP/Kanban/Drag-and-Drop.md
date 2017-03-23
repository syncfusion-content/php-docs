---
layout: post
title:  Drag and Drop
description: Drag and Drop
documentation: ug
platform: php
keywords: drag and drop,kanban drag and drop
---

# Drag and Drop

By default `allowDragAndDrop` is true.Cards can be transited from one column to another column, by dragging and dropping. And it has drop position indicator which enables easier positioning of cards

## Prioritization of cards

Prioritizing cards is easy with drag-and-drop re-ordering that helps you to categorize most important work at the top.Cards can be categorized with priority by mapping specific database field into `priority` property.

`RankId` defined in the dataSource which is consist priority of cards. The `RankId` will be changed while card ordering changes through `Drag and Drop` and `Editing`.

The following code example describes the above behavior.

{% highlight html %}

    <?php
    require_once '../EJ/AutoLoad.php';
    ?>
    <div class="cols-sample-area">
    <?php    
    $Json = '[{"Id": 1, "Status": "Open", "Summary": "Analyze the new requirements gathered from the customer.", "Type": "Story", "Priority": "Low", "Tags": "Analyze,Customer", "Estimate": 3.5, "Assignee": "Nancy Davloio", "ImgUrl": "Content/images/kanban/1.png", "RankId":1 }, { "Id": 2, "Status": "InProgress", "Summary": "Improve application performance", "Type": "Improvement", "Priority": "Normal", "Tags": "Improvement", "Estimate": 6, "Assignee": "Andrew Fuller", "ImgUrl": "Content/images/kanban/2.png", "RankId":1 }, { "Id": 3, "Status": "Open", "Summary": "Arrange a web meeting with the customer to get new requirements.", "Type": "Others", "Priority": "Critical", "Tags": "Meeting", "Estimate": 5.5, "Assignee": "Janet Leverling", "ImgUrl": "Content/images/kanban/3.png", "RankId":2 }, { "Id": 4, "Status": "InProgress", "Summary": "Fix the issues reported in the IE browser.", "Type": "Bug", "Priority": "Release Breaker", "Tags": "IE", "Estimate": 2.5, "Assignee": "Janet Leverling", "ImgUrl": "Content/images/kanban/3.png", "RankId":2 }, { "Id": 5, "Status": "Testing", "Summary": "Fix the issues reported by the customer.", "Type": "Bug", "Priority": "Low", "Tags": "Customer", "Estimate": "3.5", "Assignee": "Steven walker", "ImgUrl": "Content/images/kanban/5.png", "RankId":1 }, { "Id": 6, "Status": "Close", "Summary": "Arrange a web meeting with the customer to get the login page requirements.", "Type": "Others", "Priority": "Low", "Tags": "Meeting", "Estimate": 2, "Assignee": "Michael Suyama", "ImgUrl": "Content/images/kanban/6.png", "RankId":1 }, { "Id": 7, "Status": "Validate", "Summary": "Validate new requirements", "Type": "Improvement", "Priority": "Low", "Tags": "Validation", "Estimate": 1.5, "Assignee": "Robert King", "ImgUrl": "Content/images/kanban/7.png", "RankId":1 }, { "Id": 8, "Status": "Close", "Summary": "Login page validation", "Type": "Story", "Priority": "Release Breaker", "Tags": "Validation,Fix", "Estimate": 2.5, "Assignee": "Laura Callahan", "ImgUrl": "Content/images/kanban/8.png", "RankId":2 }, { "Id": 9, "Status": "Testing", "Summary": "Fix the issues reported in Safari browser.", "Type": "Bug", "Priority": "Release Breaker", "Tags": "Fix,Safari", "Estimate": 1.5, "Assignee": "Nancy Davloio", "ImgUrl": "Content/images/kanban/1.png", "RankId":2 }, { "Id": 10, "Status": "Close", "Summary": "Test the application in the IE browser.", "Type": "Story", "Priority": "Low", "Tags": "Testing,IE", "Estimate": 5.5, "Assignee": "Margaret hamilt", "ImgUrl": "Content/images/kanban/4.png", "RankId":3 }, { "Id": 11, "Status": "Validate", "Summary": "Validate the issues reported by the customer.", "Type": "Story", "Priority": "High", "Tags": "Validation,Fix", "Estimate": 1, "Assignee": "Steven walker", "ImgUrl": "Content/images/kanban/5.png", "RankId":1 }, { "Id": 12, "Status": "Testing", "Summary": "Check Login page validation.", "Type": "Story", "Priority": "Release Breaker", "Tags": "Testing", "Estimate": 0.5, "Assignee": "Michael Suyama", "ImgUrl": "Content/images/kanban/6.png", "RankId":3 }, { "Id": 13, "Status": "Open", "Summary": "API improvements.", "Type": "Improvement", "Priority": "High", "Tags": "Grid,API", "Estimate": 3.5, "Assignee": "Robert King", "ImgUrl": "Content/images/kanban/7.png", "RankId":3 }, { "Id": 14, "Status": "Validate", "Summary": "Add responsive support to application", "Type": "Epic", "Priority": "Critical", "Tags": "Responsive", "Estimate": 6, "Assignee": "Laura Callahan", "ImgUrl": "Content/images/kanban/8.png", "RankId":3 }, { "Id": 15, "Status": "Validate", "Summary": "Show the retrieved data from the server in grid control.", "Type": "Story", "Priority": "High", "Tags": "Database,SQL", "Estimate": 5.5, "Assignee": "Margaret hamilt", "ImgUrl": "Content/images/kanban/4.png", "RankId":4 }]';
    $Json = json_decode($Json,true);
    $kanban = new EJ\Kanban("default");    	
    $column = new EJ\Kanban\Column();
    $column ->key("Open")->headerText("Backlog");    
    $column1 = new EJ\Kanban\Column();
    $column1 ->key("InProgress")->headerText("In Progress");  	
    $column2 = new EJ\Kanban\Column();
    $column2 ->key("Close")->headerText("Done");   
    $fields = new EJ\Kanban\Field();
    $fields ->content("Summary")->primaryKey("Id")->priority("RankId");
    $columns = array( 
        $column,$column1,$column2
        );    
    echo $kanban ->columns($columns)->dataSource($Json)->fields($fields)->keyField("Status")->render();
    ?>
    </div>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Drag_and_Drop_images/drag_and_drop_img1.png)

