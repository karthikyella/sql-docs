---
title: "How to: Deploy a Custom Report Item"
description: Learn how to deploy a custom report item. You'll modify the report server configuration files and copy the component assemblies to the appropriate folders.
author: maggiesMSFT
ms.author: maggies
ms.date: 03/18/2017
ms.service: reporting-services
ms.subservice: custom-report-items
ms.topic: reference
helpviewer_keywords:
  - "custom report items, deploying"
---
# How to: Deploy a Custom Report Item
  To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.  
  
### To deploy a custom report item  
  
1.  Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer. Note that the **ReportItemName** entry must match the **CustomReportItemAttribute** attribute used in your **CustomReportItemDesigner** class. For example:  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  Edit the Rsreportserver.config file to register the custom report item run-time component. For example:  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  Edit the Rsssrvpolicy.config file to add a **CodeGroup** that grants the proper permissions to the custom report item. For example:  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.  
  
5.  Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.  
  
## See Also  
 [Reporting Services Configuration Files](../../reporting-services/report-server/reporting-services-configuration-files.md)   
 [Custom Report Item Class Libraries](../../reporting-services/custom-report-items/custom-report-item-class-libraries.md)  
  
  
