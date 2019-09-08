---
title: Operazioni di copia di massa in SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: ae97bcdd6776d573cf9e523133c2c00a42c273bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782521"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Operazioni di copia di massa in SQL Server
Microsoft SQL Server include una nota utilità da riga di comando denominata **bcp** per la copia bulk di file di grandi dimensioni in tabelle o viste nei database SQL Server. La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere soluzioni di codice gestito che offrono funzionalità simili. Esistono altri metodi per caricare dati in una tabella SQL Server (ad esempio con l'istruzione INSERT) ma <xref:System.Data.SqlClient.SqlBulkCopy> offre prestazioni molto più vantaggiose.  
  
 La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere dati solo su tabelle SQL Server. Tuttavia l'origine dati non si limita a SQL Server ed è possibile usare qualsiasi origine i cui dati possano essere caricati in un'istanza <xref:System.Data.DataTable> oppure letti con un'istanza <xref:System.Data.IDataReader>.  
  
 Con la classe <xref:System.Data.SqlClient.SqlBulkCopy> è possibile eseguire le seguenti operazioni:  
  
- Copia di massa singola  
  
- Più copie di massa  
  
- Copia bulk all'interno di una transazione  
  
> [!NOTE]
> Quando si usa .NET Framework versione 1,1 o precedente (che non supporta la <xref:System.Data.SqlClient.SqlBulkCopy> classe), è possibile eseguire l'istruzione SQL Server **BULK INSERT** Transact-SQL usando l' <xref:System.Data.SqlClient.SqlCommand> oggetto.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di esempi di copia di massa](bulk-copy-example-setup.md)  
 Vengono descritte le tabelle usate negli esempi di copia di massa e vengono forniti gli script SQL per la creazione di tabelle nel database AdventureWorks.  
  
 [Singole operazioni di copia di massa](single-bulk-copy-operations.md)  
 Viene descritto come eseguire una copia di massa singola di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy> e come eseguire la copia di massa con istruzioni Transact-SQL e con la classe <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Più operazioni di copia di massa](multiple-bulk-copy-operations.md)  
 Viene descritto come eseguire più copie di massa di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Transazioni e operazioni di copia bulk](transaction-and-bulk-copy-operations.md)  
 Viene descritto come eseguire una copia bulk all'interno di una transazione e come eseguire il commit e il rollback della transazione.  
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
