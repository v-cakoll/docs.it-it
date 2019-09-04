---
title: Generazione SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 2c18e88967fcba2b8414bfc171412eba908002b3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248407"
---
# <a name="sql-generation"></a>Generazione SQL
Quando si scrive un provider per [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], è necessario convertire gli alberi dei comandi di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] in codice SQL comprensibile per un determinato database, ad esempio Transact-SQL per SQL Server o PL/SQL per Oracle. Contenuto della sezione viene illustrato come sviluppare un componente di generazione SQL (per le query SELECT) per un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per informazioni sulle query di inserimento, aggiornamento ed eliminazione, vedere la pagina relativa alla [modifica della generazione SQL](modification-sql-generation.md).  
  
 Per comprendere questa sezione è necessario avere familiarità con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e il modello di provider ADO.NET. È inoltre necessario conoscere gli alberi dei comandi e <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Ruolo del modulo di generazione SQL  
 Il modulo di generazione SQL di un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] converte un determinato albero dei comandi di query in una singola istruzione SQL SELECT destinata a un database conforme a SQL:1999. Se possibile, il codice SQL generato deve contenere alcune query annidate. Il modulo di generazione SQL non semplifica l'albero dei comandi di query di output. Tale semplificazione viene garantita da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] mediante, ad esempio, l'eliminazione di join e la compressione di nodi di filtro consecutivi.  
  
 La classe <xref:System.Data.Common.DbProviderServices> è il punto di partenza per l'accesso al livello di generazione SQL per convertire gli alberi dei comandi in <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Forma degli alberi dei comandi](the-shape-of-the-command-trees.md)  
  
 [Procedure consigliate per la generazione di SQL dagli alberi dei comandi](generating-sql-from-command-trees-best-practices.md)  
  
 [Generazione di comandi SQL nel provider di esempio](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Vedere anche

- [Scrittura di un provider di dati Entity Framework](writing-an-ef-data-provider.md)
