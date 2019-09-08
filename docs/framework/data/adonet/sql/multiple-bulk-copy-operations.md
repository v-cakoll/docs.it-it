---
title: Più operazioni di copia di massa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 838f56311f165c99c71cc734576bbdb53a946b7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792070"
---
# <a name="multiple-bulk-copy-operations"></a>Più operazioni di copia di massa
È possibile eseguire più operazioni di copia di massa usando una singola istanza di una classe <xref:System.Data.SqlClient.SqlBulkCopy>. Se i parametri dell'operazione cambiano tra le copie (ad esempio, il nome della tabella di destinazione), è necessario aggiornarli prima di qualsiasi chiamata successiva a uno dei metodi **WriteToServer** , come illustrato nell'esempio seguente. Se non vengono modificati in modo esplicito, tutti i valori delle proprietà rimangono identici a quelli dell'operazione di copia di massa precedente per una determinata istanza.  
  
> [!NOTE]
> L'esecuzione di più operazioni di copia di massa con la stessa istanza di <xref:System.Data.SqlClient.SqlBulkCopy> è generalmente più efficace rispetto all'utilizzo di un'istanza distinta per ogni operazione.  
  
 Se si eseguono diverse operazioni di copia di massa usando lo stesso oggetto <xref:System.Data.SqlClient.SqlBulkCopy>, non vi sono restrizioni sulla corrispondenza o meno tra le informazioni di origine o di destinazione di ciascuna operazione. Tuttavia, è necessario verificare che le informazioni di associazione della colonna siano impostate correttamente ogni volta che si scrive sul server.  
  
> [!IMPORTANT]
> Questo esempio non verrà eseguito a meno che non siano state create le tabelle di lavoro come descritto in configurazione di esempio per la [copia bulk](bulk-copy-example-setup.md). Questo codice viene fornito per illustrare la sintassi per l'utilizzo solo di **SqlBulkCopy** . Se la tabella di origine e quella di destinazione risiedono nella stessa istanza di SQL Server, per copiare i dati è più semplice e rapido usare un'istruzione `INSERT … SELECT` Transact-SQL.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Operazioni di copia di massa in SQL Server](bulk-copy-operations-in-sql-server.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
