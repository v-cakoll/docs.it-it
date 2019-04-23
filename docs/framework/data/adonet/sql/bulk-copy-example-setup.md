---
title: Creazione di esempi di copia di massa
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 6244afff348edbde46fdfda7481910aca2b25939
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117274"
---
# <a name="bulk-copy-example-setup"></a>Creazione di esempi di copia di massa
La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere dati solo su tabelle SQL Server. Gli esempi di codice illustrati in questo argomento usano il database di esempio di SQL Server, **AdventureWorks**. Per evitare di modificare gli esempi di codice delle tabelle esistenti, è necessario creare tabelle in cui scrivere i dati.  
  
 Il **BulkCopyDemoMatchingColumns** e **BulkCopyDemoDifferentColumns** sono entrambe basate sulle tabelle di **AdventureWorks** **Production. Products**  tabella. Negli esempi di codice che usano queste tabelle, i dati vengono aggiunti dal **Production. Products** tabella a una di queste tabelle di esempio. Il **BulkCopyDemoDifferentColumns** tabella viene utilizzata quando l'esempio illustra come eseguire il mapping di colonne dall'origine dati alla tabella di destinazione. **BulkCopyDemoMatchingColumns** viene usato per la maggior parte degli altri esempi.  
  
 Alcuni degli esempi di codice illustrano come usare una classe <xref:System.Data.SqlClient.SqlBulkCopy> per scrivere più tabelle. Per questi esempi, il **BulkCopyDemoOrderHeader** e **BulkCopyDemoOrderDetail** tabelle vengono usate come tabelle di destinazione. Queste tabelle sono basate sulle **Sales. SalesOrderHeader** e **Sales. SalesOrderDetail** nelle tabelle **AdventureWorks**.  
  
> [!NOTE]
>  Il **SqlBulkCopy** vengono forniti esempi di codice per illustrare la sintassi per usare **SqlBulkCopy** solo. Se la tabella di origine e quella di destinazione risiedono nella stessa istanza di SQL Server, per copiare i dati è più semplice e rapido usare un'istruzione `INSERT … SELECT` Transact-SQL.  
  
## <a name="table-setup"></a>Impostazione delle tabelle  
 Per creare le tabelle necessarie affinché i codici di esempio vengano eseguiti correttamente, è necessario eseguire le seguenti istruzioni Transact-SQL su un database SQL Server.  
  
```  
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a>Vedere anche

- [Operazioni di copia di massa in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
