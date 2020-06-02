---
title: Operazioni di copia di massa in SQL Server
description: Viene illustrato come utilizzare la classe SqlBulkCopy per scrivere soluzioni di codice gestito per la copia bulk di file di grandi dimensioni in tabelle o viste di database SQL Server.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 4f877836aa45efe162cce3c42cb5733f86deab2c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286520"
---
# <a name="bulk-copy-operations-in-sql-server"></a>Operazioni di copia di massa in SQL Server
Microsoft SQL Server include una popolare utilità della riga di comando denominata **bcp** per eseguire rapidamente la copia bulk di file di grandi dimensioni in tabelle o viste nei database di SQL Server. La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere soluzioni di codice gestito che offrono funzionalità simili. Esistono altri modi per caricare dati in una tabella di SQL Server (ad esempio, istruzioni INSERT) ma <xref:System.Data.SqlClient.SqlBulkCopy> offre un significativo vantaggio in termini di prestazioni.  
  
 La classe <xref:System.Data.SqlClient.SqlBulkCopy> può essere usata per scrivere dati solo in tabelle di SQL Server. Tuttavia l'origine dati non si limita a SQL Server ed è possibile usare qualsiasi origine i cui dati possano essere caricati in un'istanza <xref:System.Data.DataTable> oppure letti con un'istanza <xref:System.Data.IDataReader>.  
  
 Con la classe <xref:System.Data.SqlClient.SqlBulkCopy> è possibile eseguire:  
  
- Una singola operazione di copia bulk  
  
- Più operazioni di copia bulk  
  
- Un'operazione di copia bulk all'interno di una transazione  
  
> [!NOTE]
> Con .NET Framework versione 1.1 o precedenti (in cui non è supportata la classe <xref:System.Data.SqlClient.SqlBulkCopy>), è possibile eseguire l'istruzione **BULK INSERT** di SQL Server Transact-SQL usando l'oggetto <xref:System.Data.SqlClient.SqlCommand>.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Configurazione di esempio per la copia bulk](bulk-copy-example-setup.md)  
 Descrive le tabelle usate negli esempi di copia bulk e fornisce script SQL per la creazione delle tabelle nel database AdventureWorks.  
  
 [Singole operazioni di copia bulk](single-bulk-copy-operations.md)  
 Viene descritto come eseguire una singola copia bulk dei dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy> e come eseguire l'operazione di copia bulk usando istruzioni Transact-SQL e la classe <xref:System.Data.SqlClient.SqlCommand>.  
  
 [Più operazioni di copia bulk](multiple-bulk-copy-operations.md)  
 Viene descritto come eseguire più operazioni di copia bulk dei dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 [Transazioni e operazioni di copia bulk](transaction-and-bulk-copy-operations.md)  
 Viene descritto come eseguire un'operazione di copia bulk all'interno di una transazione e come eseguire il commit o il ripristino dello stato precedente della transazione.  
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
