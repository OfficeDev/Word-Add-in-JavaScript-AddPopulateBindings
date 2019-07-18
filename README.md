---
topic: sample
products:
- office-word
- office-365
languages:
- javascript
extensions:
  contentType: samples
  technologies:
  - Add-ins
  createdDate: 8/18/2015 7:35:17 PM
---
# Word Add-in: Add, bind to, and populate a rich text content control

**Table of contents**

* [Summary](#summary)
* [Prerequisites](#prerequisites)
* [Key components of the sample](#components)
* [Description of the code](#codedescription)
* [Build and debug](#build)
* [Troubleshooting](#troubleshooting)
* [Questions and comments](#questions)
* [Additional resources](#additional-resources)

<a name="summary"></a>
##Summary
This sample shows how to add and bind to a named rich text content control in Word, and how to insert content at the bound location. 

<a name="prerequisites"></a>
## Prerequisites ##

This sample requires the following:  

  - Word 2013 or Word 2016.
  - Visual Studio 2013 (Update 5) or Visual Studio 2015, with Microsoft Office Developer Tools.  
  - Any browser that supports ECMAScript 5.1, HTML5, and CSS3, such as Internet Explorer 9, Chrome 13, Firefox 5, Safari 5.0.6, or a later version of these browsers.
  

<a name="components"></a>
## Key components of the sample
The sample solution contains the following key files:

**PopulateBindings** project

- [PopulateBindings.xml](https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings/blob/master/PopulateBindings/PopulateBindingsManifest/PopulateBindings.xml): The manifest file for the Word add-in.
 
**PopulateBindingsWeb** project

- [App/Home/Home.html](https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings/blob/master/PopulateBindingsWeb/App/Home/Home.html). The HTML user interface that is displayed in the task pane. It contains one button to insert a rich text content control and bind to it, and two buttons to populate the binding (with two interchangeable content options).
- [App/Home/Home.js](https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings/blob/master/PopulateBindingsWeb/App/Home/Home.js). Logic that runs when the add-in is loaded. 
- [Snippets_BindAndPopulate folder](https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings/tree/master/PopulateBindingsWeb/Snippets_BindAndPopulate). Contains three XML files that define the markup for the rich text content control and for the two content samples.


<a name="codedescription"></a>
##Description of the code
The sample demonstrates how to:

- Use the **setSelectedDataAsync** method with the **ooxml** coercion type to add a rich text content control.
- Use the **addFromNamedItemAsync** method to bind to the control.
- Use the **setDataAsync** method with the **ooxml** coercion type to populate the binding.

The add-in initializes in a blank Word document. The following screenshot shows the initial view of the task pane add-in.

   ![The initial view of the add-in with its three buttons](/images/Word_PopulateBindings_1.png)

Bindings can greatly expand the options for Word add-ins. Use bindings to add content at a specified location in the document, not just at the user's active selection point. 
 In Word add-ins, rich text controls are the only type of content control you can bind to. Note that the control placeholder content must include at least one complete paragraph in order 
 to enable you to populate the binding with multi-paragraph content. The file ContentControl.xml in the Snippets_BindAndPopulate folder in this solution shows how to structure your 
 content control for successful binding. To learn more about working with bindings in Word add-ins, see [Creating Better Word Add-ins with Office Open XML](http://msdn.microsoft.com/library/office/apps/dn423225.aspx).

<a name="build"></a>
## Build and debug ##

1. In Visual Studio, press F5 to build and deploy the solution. You can optionally add content in the document.
2. In the **Home** ribbon, click **Open** in the **Populate Bindings** group.
2. In the add-in, click **Add and Bind Control**. The placeholder text for the control appears in the document.

   ![Document showing the control's placeholder text](/images/Word_PopulateBindings_2.png)

3. Click one of the **Insert** buttons to populate the binding initially, and the other to replace the contents of the binding with new content. 

   ![Document showing new image and formatted text content in the control](/images/Word_PopulateBindings_3.png)

<a name="troubleshooting"></a>
## Troubleshooting

- If the add-in does not appear in the task pane of the presentation, Choose **Insert > My Add-ins > Populate Bindings**.

<a name="questions"></a>
## Questions and comments

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/Word-Add-in-JavaScript-AddPopulateBindings/issues).
- Questions about Office Add-ins development in general should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/office-addins). Make sure that your questions or comments are tagged with [office-addins].


<a name="additional-resources"></a>
## Additional resources ##

- [Office Add-ins](http://msdn.microsoft.com/library/office/jj220060.aspx) documentation on MSDN
- [Standard ECMA-376: Office Open XML File Formats](http://www.ecma-international.org/publications/standards/Ecma-376.htm)
- [Creating Better Word Add-ins with Office Open XML](http://msdn.microsoft.com/library/office/apps/dn423225.aspx)
- [More Add-in samples](https://github.com/OfficeDev?utf8=%E2%9C%93&query=-Add-in)


## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.


This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
