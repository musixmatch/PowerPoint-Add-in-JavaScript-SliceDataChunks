# PowerPoint Add-in: Send a PowerPoint document in chunks to a service

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
This sample shows how to use JavaScript in a PowerPoint 2013 task pane add-in to get the current presentation and slice it into chunks of data in user-defined sizes. The data could then be submitted to a service (such as an e-book publishing service).

<a name="prerequisites"></a>
## Prerequisites ##

This sample requires the following:  

  - PowerPoint 2013.
  - Visual Studio 2013 (Update 5) or Visual Studio 2015, with Microsoft Office Developer Tools.  
  - Any browser that supports ECMAScript 5.1, HTML5, and CSS3, such as Chrome 13, Firefox 5, Safari 5.0.6, or a later version of these browsers. If using Internet Explorer, requires Internet Explorer 10 to support the *btoa* encoding method.
  

<a name="components"></a>
## Key components of the sample
The sample solution contains the following key files:

**EBookPublisher** project

- [EBookPublisher.xml](https://github.com/OfficeDev/PowerPoint-Add-in-JavaScript-SliceDataChunks/blob/master/EBookPublisher/EBookPublisherManifest/EBookPublisher.xml): The manifest file for the PowerPoint add-in.  
- [Adventure Works.ppt](https://github.com/OfficeDev/PowerPoint-Add-in-JavaScript-SliceDataChunks/blob/master/EBookPublisher/Adventure%20Works.pptx): Start Document with 1,024 slides. 
 
**EBookPublisherWeb** project

- [App/Home/Home.html](https://github.com/OfficeDev/PowerPoint-Add-in-JavaScript-SliceDataChunks/blob/master/EBookPublisherWeb/App/Home/Home.html). The HTML user interface that is displayed in the task pane. 
- [App/Home/Home.js](https://github.com/OfficeDev/PowerPoint-Add-in-JavaScript-SliceDataChunks/blob/master/EBookPublisherWeb/App/Home/Home.js). Logic that runs when the add-in is loaded. 


<a name="codedescription"></a>
##Description of the code
The Adventure Works.pptx file is set as the **Start Document** property of the task pane add-in. The presentation is large enough (1,204 slides) to be sliced into a number of discrete chunks of data. 

The sample demonstrates:

- How to use JavaScript to retrieve the selected value from a drop-down list.
- How to use the **getFileAsync** method to slice the file into chunks of data of particular sizes.
- How to retrieve the data from each slice of the file by using the **getSliceAsync** method.


<a name="build"></a>
## Build and debug ##

1. In Visual Studio, press F5 to build and deploy the sample add-in. The Adventure Works.pptx file opens in PowerPoint.
2. In the task pane add-in, choose a size for the data chunk.
3. Click the **Publish now!** button. 

The add-in displays the number of slices and the size of each slice, along with buttons you can use to view the content of each slice.

>This sample displays the slice information to the user, but your add-in will probably send the data slices to a web service. The web service can then rebuild the presentation from the slices.

<a name="troubleshooting"></a>
## Troubleshooting

- If the add-in starts with a blank presentation, ensure that the **Start Document** property of the EBookPublisher project is set to *Adventure Works.pptx* (not to *New PowerPoint Presentation*).
- If the presentation opens in read-only mode, click the **Enable editing** button.
- If the add-in does not appear in the task pane of the presentation, Choose **Insert > My Add-ins > EBook Publisher**.


<a name="questions"></a>
## Questions and comments

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/PowerPoint-Add-in-JavaScript-SliceDataChunks/issues).
- Questions about Office Add-ins development in general should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/office-addins). Make sure that your questions or comments are tagged with [office-addins].


<a name="additional-resources"></a>
## Additional resources ##

- [Office Add-ins](http://msdn.microsoft.com/library/office/jj220060.aspx) documentation on MSDN
- [Get the whole document from an add-in for PowerPoint or Word](https://msdn.microsoft.com/library/office/jj715279.aspx)
- [Document.getFileAsync method](http://msdn.microsoft.com/library/office/apps/jj715284.aspx)
- [File.getSliceAsync method](http://msdn.microsoft.com/library/office/apps/jj715281.aspx)
- [More Add-in samples](https://github.com/OfficeDev?utf8=%E2%9C%93&query=-Add-in)

## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.
