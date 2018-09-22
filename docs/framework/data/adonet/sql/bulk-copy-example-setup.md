---
title: Creazione di esempi di copia di massa
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 71daf489fdf5e7e12594e798bc3ac01b1c76b027
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46579459"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="68bbc-102">Creazione di esempi di copia di massa</span><span class="sxs-lookup"><span data-stu-id="68bbc-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="68bbc-103">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere dati solo su tabelle SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68bbc-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="68bbc-104">Gli esempi di codice illustrati in questo argomento usano il database di esempio di SQL Server, **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="68bbc-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="68bbc-105">Per evitare di modificare gli esempi di codice delle tabelle esistenti, è necessario creare tabelle in cui scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="68bbc-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="68bbc-106">Il **BulkCopyDemoMatchingColumns** e **BulkCopyDemoDifferentColumns** sono entrambe basate sulle tabelle di **AdventureWorks** **Production. Products**  tabella.</span><span class="sxs-lookup"><span data-stu-id="68bbc-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="68bbc-107">Negli esempi di codice che usano queste tabelle, i dati vengono aggiunti dal **Production. Products** tabella a una di queste tabelle di esempio.</span><span class="sxs-lookup"><span data-stu-id="68bbc-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="68bbc-108">Il **BulkCopyDemoDifferentColumns** tabella viene utilizzata quando l'esempio illustra come eseguire il mapping di colonne dall'origine dati alla tabella di destinazione. **BulkCopyDemoMatchingColumns** viene usato per la maggior parte degli altri esempi.</span><span class="sxs-lookup"><span data-stu-id="68bbc-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="68bbc-109">Alcuni degli esempi di codice illustrano come usare una classe <xref:System.Data.SqlClient.SqlBulkCopy> per scrivere più tabelle.</span><span class="sxs-lookup"><span data-stu-id="68bbc-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="68bbc-110">Per questi esempi, il **BulkCopyDemoOrderHeader** e **BulkCopyDemoOrderDetail** tabelle vengono usate come tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="68bbc-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="68bbc-111">Queste tabelle sono basate sulle **Sales. SalesOrderHeader** e **Sales. SalesOrderDetail** nelle tabelle **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="68bbc-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68bbc-112">Il **SqlBulkCopy** vengono forniti esempi di codice per illustrare la sintassi per usare **SqlBulkCopy** solo.</span><span class="sxs-lookup"><span data-stu-id="68bbc-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="68bbc-113">Se la tabella di origine e quella di destinazione risiedono nella stessa istanza di SQL Server, per copiare i dati è più semplice e rapido usare un'istruzione `INSERT … SELECT` Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="68bbc-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="68bbc-114">Impostazione delle tabelle</span><span class="sxs-lookup"><span data-stu-id="68bbc-114">Table Setup</span></span>  
 <span data-ttu-id="68bbc-115">Per creare le tabelle necessarie affinché i codici di esempio vengano eseguiti correttamente, è necessario eseguire le seguenti istruzioni Transact-SQL su un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68bbc-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68bbc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68bbc-116">See Also</span></span>  
 [<span data-ttu-id="68bbc-117">Operazioni di copia di massa in SQL Server</span><span class="sxs-lookup"><span data-stu-id="68bbc-117">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="68bbc-118">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="68bbc-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
