---
title: Generazione SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b2d4ba925af61f89b47c494f5fb17f5f9f0d995
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="sql-generation"></a>Generazione SQL
Quando si scrive un provider per [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è necessario convertire gli alberi dei comandi di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] in codice SQL comprensibile per un determinato database, ad esempio Transact-SQL per SQL Server o PL/SQL per Oracle. Contenuto della sezione viene illustrato come sviluppare un componente di generazione SQL (per le query SELECT) per un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per informazioni sull'inserimento, aggiornamento, eliminazione di query, vedere [generazione SQL di modifica](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).  
  
 Per comprendere questa sezione è necessario avere familiarità con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e il modello di provider ADO.NET. È inoltre necessario conoscere gli alberi dei comandi e <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Ruolo del modulo di generazione SQL  
 Il modulo di generazione SQL di un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] converte un determinato albero dei comandi di query in una singola istruzione SQL SELECT destinata a un database conforme a SQL:1999. Se possibile, il codice SQL generato deve contenere alcune query annidate. Il modulo di generazione SQL non semplifica l'albero dei comandi di query di output. Tale semplificazione viene garantita da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] mediante, ad esempio, l'eliminazione di join e la compressione di nodi di filtro consecutivi.  
  
 La classe <xref:System.Data.Common.DbProviderServices> è il punto di partenza per l'accesso al livello di generazione SQL per convertire gli alberi dei comandi in <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Forma degli alberi dei comandi](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [Procedure consigliate per la generazione di SQL dagli alberi dei comandi](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [Generazione di comandi SQL nel provider di esempio](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Scrittura di un provider di dati Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
