---
title: Export FAQ
page_title: Export FAQ
description: Export FAQ
slug: gridview-export-faq
tags: export,faq
published: True
position: 6
---

# Export FAQ


You can find listed some questions and their answers bellow

## Exporting

For a general example on how to Export the data, you can check our Exporting
{% if site.site_name == 'WPF' %}[ WPF Demos.](http://demos.telerik.com/wpf/){% endif %}{% if site.site_name == 'Silverlight' %}[online demos.](http://demos.telerik.com/silverlight/#GridView/Exporting){% endif %}

* __How to export paged data:__

* Save the PageSize and the PageIndex of RadDataPager
                  

* Set the PageSize of RadDataPager to 0
                  

* Export the data (you can use the (IEnumerable) dataPager.PagedSource as GridViewExportOptions.Items)
                  

* Set the PageSize and the PageIndex back
                  

* __How to avoid error warning when exporting and 'xls' extension__: The alert is a new security feature in Excel 2007 called Extension Hardening, which ensures that the file content being opened matches the extension type specified in the shell command that is attempting to open the file.
In order to avoid getting this warning, you should export to ExcelML format with XML extension. You can also refer to this [help article]({%slug gridview-troubleshooting-warning-message-excel%}) for an additional information.
            

* __Export with .xlsx extension:__ The best option we can currently suggest is exporting with __RadSpreadSheet__  creating a __RadWorkBook__ as demonstrated in the 
{% if site.site_name == 'WPF' %}[RadGridViewIntegration demo.](http://demos.telerik.com/wpf/){% endif %}{% if site.site_name == 'Silverlight' %}[RadGridViewIntegration demo.](http://demos.telerik.com/silverlight/#SpreadProcessing/RadGridViewIntegration){% endif %}

* __Some columns are exported with a minimum Width:__ RadGridView exports the respective header cells with the minimum width value (which is 20 by default) if they have not been measured by the layout mechanism at the time the exporting operation takes place.To get all the columns exported with their actual width, you should first assure that they have been realized.As an alternative solution, if you do not have that much columns, you can set EnableColumnVirtualization="False" for __RadGridView__.
            

* __Do not export a particular column:__ You can subscribe for the __ElementExporting__ event of RadGridView to control which columns will be exported.  Once the event is raised, you can cancel the export (setting e.Cancel = true) when the Column of the currently exported element is a column you would like to skip.
            

* __How to export row details:__ You could export the data in row-details subscribing to the __ElementExported__ event of main RadGridView to export additional rows based on the content in details. Please check the
[Exporting Row Details](http://demos.telerik.com/silverlight/#GridView/ExportingRowDetails) online demo for a further reference.
            
* __Modify the exported value:__ You could subscribe for the __ElementExporting__ event of RadGridView and change the __e.Value__ to be exported.
            
* __Export data on multiple worksheets of the same workbook:__ You can export data on different worksheets with [RadSpreadProcessing]({%slug radspreadprocessing-overview%}), which model is completely independent from UI. You can also check our new example {% if site.site_name == 'WPF' %}[Export with RadSpreadProcessing](http://demos.telerik.com/wpf/){% endif %}{% if site.site_name == 'Silverlight' %}[Export with RadSpreadProcessing](http://demos.telerik.com/silverlight/#SpreadProcessing/RadGridViewIntegration){% endif %} on how to do so.
            
* __OutOfMemoryException:__ All the data to be exported is saved in memory, so the exporting capacities are not huge. For more complex scenarios, you consider using our [Reporting tools](http://www.telerik.com/products/reporting.aspx) built to suit various exporting scenarios.
            

>tipYou can also export data with __RadSpreadProcessing__, which model is completely independent from UI. You can check our new example {% if site.site_name == 'WPF' %}[Export with RadSpreadProcessing](http://demos.telerik.com/wpf/){% endif %}{% if site.site_name == 'Silverlight' %}[Export with RadSpreadProcessing](http://demos.telerik.com/silverlight/#SpreadProcessing/RadGridViewIntegration){% endif %} on how to do so.
        
## Printing

* __How to print a document:__ One way would be to follow the approach illustrated in the "Print and Export with RadDocument" {% if site.site_name == 'WPF' %}[ demo.](http://demos.telerik.com/wpf/){% endif %}{% if site.site_name == 'Silverlight' %}[online demo.](http://demos.telerik.com/silverlight/#GridView/PrintAndExportWithRadDocument){% endif %}Another way would be to manually create the document to be exported.
You can go through the articles about using the [RadDocument]({%slug radrichtextbox-features-document-elements-raddocument%}) and about the document viewer control - [RadRichTextBox]({%slug radrichtextbox-overview%}). You could as well review [this article]({%slug radrichtextbox-features-document-elements-tables%}) on how you could create the document elements.

## 

>In order to print or export with more advanced options you can check the __Telerik Reporting__ product. You can find more information about it [here.](http://www.telerik.com/products/reporting.aspx)

# See Also

 * [Grid Export]({%slug gridview-export%})

 * [Grid Async Export]({%slug gridview-export-async%})