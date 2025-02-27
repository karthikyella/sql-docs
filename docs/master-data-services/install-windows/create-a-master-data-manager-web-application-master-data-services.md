---
title: Create master data manager web application
description: The Master Data Manager web application provides an interface for users to work with master data and for administrators to configure and administer MDS.
author: CordeliaGrey
ms.author: jiwang6
ms.date: "12/13/2019"
ms.service: sql
ms.subservice: master-data-services
ms.topic: conceptual
---
# Create a master data manager web application (Master Data Services)

[!INCLUDE [SQL Server Windows Only - ASDBMI ](../../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.  
  
 A web application must always be contained by a website. To create a web application, you must either:  
  
-   Use the Default website and then create the web application,  
  
-   Use an existing website and then create the web application, or  
  
-   Create a new website, which automatically creates a web application.  
  
 After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.  
  
## Prerequisites  
  
-   For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](../../master-data-services/install-windows/web-application-requirements-master-data-services.md).  
  
## To create a Master Data Manager web application in a new website  
 When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application. The web application is also added to a new application pool.  
  
> [!NOTE]  
>  If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application. If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.  
  
 Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only. To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](../../master-data-services/install-windows/secure-a-master-data-manager-web-application.md) for more information.  
  
#### To create a Master Data Manager web application in a new website  
  
1.  Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].  
  
2.  In the left pane, click **Web Configuration**.  
  
3.  On the **Web Configuration** page, in the Website list, select **Create new website**.  
  
4.  On the **Create Website** dialog box, specify information for a new website. For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).  
  
5.  Click **OK**.  
  
## To create a Master Data Manager web application in an existing website  
 When you create a web application in an existing website, you can choose the virtual path and alias of the web application. The web application is added to a new application pool.  
  
#### To create a Master Data Manager web application in an existing website  
  
1.  Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].  
  
2.  In the left pane, click **Web Configuration**.  
  
3.  On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.  
  
4.  Click **Create Application**.  
  
5.  On the **Create Web Application** dialog box, specify information for a new web application. For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../master-data-services/create-web-application-dialog-box-master-data-services-configuration-manager.md).  
  
6.  Click **OK**.  
  
## Next Steps  
  
-   Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database. For more information, see [Associate a Master Data Services Database and Web Application](../../master-data-services/install-windows/associate-a-master-data-services-database-and-web-application.md).  
  
-   Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Transport Layer Security (TLS), previously known as Secure Sockets Layer (SSL). You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the TLS settings for the site. For more information, see [Secure a Master Data Manager Web Application](../../master-data-services/install-windows/secure-a-master-data-manager-web-application.md).  
  
## See Also  
 [Install Master Data Services](../../master-data-services/install-windows/install-master-data-services.md)  
  
  
