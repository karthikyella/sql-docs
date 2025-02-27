---
title: "sp_add_log_shipping_primary_secondary (Transact-SQL)"
description: "sp_add_log_shipping_primary_secondary (Transact-SQL)"
author: MashaMSFT
ms.author: mathoma
ms.date: "03/14/2017"
ms.service: sql
ms.subservice: system-objects
ms.topic: "reference"
f1_keywords:
  - "sp_add_log_shipping_primary_secondary_TSQL"
  - "sp_add_log_shipping_primary_secondary"
helpviewer_keywords:
  - "sp_add_log_shipping_primary_secondary"
dev_langs:
  - "TSQL"
---
# sp_add_log_shipping_primary_secondary (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  This stored procedure adds an entry for a secondary database on the primary server.  
  
 :::image type="icon" source="../../includes/media/topic-link-icon.svg" border="false"::: [Transact-SQL syntax conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```  
  
sp_add_log_shipping_primary_secondary  
[ @primary_database = ] 'primary_database',  
[ @secondary_server = ] 'secondary_server',   
[ @secondary_database = ] 'secondary_database'  
```  
  
## Arguments  
`[ @primary_database = ] 'primary_database'`
 Is the name of the database on the primary server. *primary_database* is **sysname**, with no default.  
  
`[ @secondary_server = ] 'secondary_server',`
 Is the name of the secondary server. *secondary_server* is **sysname**, with no default.  
  
`[ @secondary_database = ] 'secondary_database'`
 Is the name of the secondary database. *secondary_database* is **sysname**, with no default.  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Result Sets  
 None  
  
## Remarks  
 **sp_add_log_shipping_primary_secondary** must be run from the **master** database on the primary server.  
  
## Permissions  
 Only members of the **sysadmin** fixed server role can run this procedure.  
  
## Examples  
 This example illustrates using **sp_add_log_shipping_primary_secondary** to add an entry for the secondary database **LogShipAdventureWorks** to the secondary server FLATIRON.  
  
```  
EXEC master.dbo.sp_add_log_shipping_primary_secondary   
@primary_database = N'AdventureWorks'   
, @secondary_server = N'flatiron'   
, @secondary_database = N'LogShipAdventureWorks' ;  
GO  
```  
  
## See Also  
 [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [System Stored Procedures &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
