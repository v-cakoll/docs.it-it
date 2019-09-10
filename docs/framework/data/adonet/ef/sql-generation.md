---
title: Generazione SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854361"
---
# <a name="sql-generation"></a>Generazione SQL
Quando si scrive un provider per la Entity Framework, è necessario tradurre Entity Framework alberi dei comandi in SQL che possono essere riconoscibili da un database specifico, ad esempio Transact-SQL per SQL Server o PL/SQL per Oracle. In questa sezione verrà illustrato come sviluppare un componente di generazione SQL (per le query SELECT) per un provider di Entity Framework. Per informazioni sulle query di inserimento, aggiornamento ed eliminazione, vedere la pagina relativa alla [modifica della generazione SQL](modification-sql-generation.md).  
  
 Per comprendere questa sezione, è necessario avere familiarità con il Entity Framework e il modello di provider ADO.NET. È inoltre necessario conoscere gli alberi dei comandi e <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Ruolo del modulo di generazione SQL  
 Il modulo di generazione SQL di un provider di Entity Framework converte una struttura ad albero dei comandi di query specifica in un'unica istruzione SQL SELECT destinata a un database conforme a SQL: 1999. Se possibile, il codice SQL generato deve contenere alcune query annidate. Il modulo di generazione SQL non semplifica l'albero dei comandi di query di output. Il Entity Framework esegue questa operazione, ad esempio eliminando i join e comprimendo i nodi di filtro consecutivi.  
  
 La classe <xref:System.Data.Common.DbProviderServices> è il punto di partenza per l'accesso al livello di generazione SQL per convertire gli alberi dei comandi in <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Forma degli alberi dei comandi](the-shape-of-the-command-trees.md)  
  
 [Procedure consigliate per la generazione di SQL dagli alberi dei comandi](generating-sql-from-command-trees-best-practices.md)  
  
 [Generazione di comandi SQL nel provider di esempio](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Vedere anche

- [Scrittura di un provider di dati Entity Framework](writing-an-ef-data-provider.md)
