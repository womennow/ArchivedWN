---
layout: post
title: Adding Annotations for Forms in the Service Portal
author: Paige
tags: []
---

Form annotations do not appear on forms when rendered in Service Portal.  While you can use a solution like a field level Client Script, I do not find that to provide the look and feel I'm often looking for.  Instead, you can embed a widget on the form to take the place of form annotations.

## Step 1:  Build the Widget

For my annotations, the requirement was pretty simple.  I just needed some header text.  You can certainly be more creative, but for this example I'm just going to use some very basic HTML.  Below is a simple example of a form 'annotation' and how to add it to the form.



### HTML
```HTML
<pre class="wp-block-code"><code>&lt;div class="h2">
My Header
&lt;/div>
&lt;hr></code></pre>
```


### CSS

```CSS
<pre class="wp-block-code"><code>hr {
  height: 1px;
  background-color:#FF0080;
  margin-top: 5px;
}

.h2 {
  margin-bottom: 0px;
  font-weight: 300;
  color: #FF0080;
  padding-top: 20px;
}</code></pre>
```


## Step 2: Create Service Portal UI Formatter

If this is the first time you've ever used this table, you will need to adjust the create acl on the table to allow admins to create records.  The table (sp_ui_formatter) itself is hidden, I've added a module in our Service Portal App Menu.  If you do not wish to create a module, then navigate to sp_ui_formatter and create a new record.

1. Formatter: Name for your formatter.  It should not contain spaces and should end with .xml
1. Widget: Select your widget from Step 1

## Step 3: Create UI Formatter

Navigate to System UI > Formatters and create a new record.  

1. Name: Name for your formatter.  This will appear in the Form Layout list.
1. Formatter: This should match the name from the Formatter field on the Service Portal UI Formatter you created in Step 2.
1. Table: The table you want to be able to add this new formatter to.

## Step 4: Adding a Formatter to your Form

* Navigate to the form you want to add the new Formatter/Widget to.
* Right click in the header, go to Configure, then Form Layout
* Look for your new formatter in the Available list and move it to the left side of the slush bucket and Save your changes.  
  * Note: Formatter are usually listed after the form field and * Annotation option.

## Step 5: Test it out

You will not see you widget in the fulfiller UI version of the form.  So navigate to the form in the Service Portal to verify that your widget is now showing.

You can do more than just add "Annotations", but these instructions should provide the ground work for placing Portal Widgets on forms.
