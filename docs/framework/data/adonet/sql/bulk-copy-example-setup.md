---
title: Creazione di esempi di copia di massa
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 80350d112da03c00e422432ce271ca5ea3ac58ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148842"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="5efa2-102">Creazione di esempi di copia di massa</span><span class="sxs-lookup"><span data-stu-id="5efa2-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="5efa2-103">La classe <xref:System.Data.SqlClient.SqlBulkCopy> può essere usata per scrivere dati solo in tabelle di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5efa2-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="5efa2-104">Negli esempi di codice illustrati in questo argomento viene usato il database di esempio di SQL Server, **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="5efa2-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="5efa2-105">Per evitare di modificare le tabelle esistenti, gli esempi di codice scrivono i dati in tabelle che è prima necessario creare.</span><span class="sxs-lookup"><span data-stu-id="5efa2-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="5efa2-106">Le tabelle **BulkCopyDemoMatchingColumns** e **BulkCopyDemoDifferentColumns** sono entrambe basate sulla tabella **AdventureWorks** **Production.Products.**</span><span class="sxs-lookup"><span data-stu-id="5efa2-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="5efa2-107">Negli esempi di codice che usano queste tabelle, i dati vengono aggiunti dalla tabella **Production.Products** a una di queste tabelle di esempio.</span><span class="sxs-lookup"><span data-stu-id="5efa2-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="5efa2-108">La tabella **BulkCopyDemoDifferentColumns** viene usata quando l'esempio illustra come eseguire il mapping delle colonne dall'origine dati alla tabella di destinazione. **BulkCopyDemoMatchingColumns** viene usata per la maggior parte degli altri esempi.</span><span class="sxs-lookup"><span data-stu-id="5efa2-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="5efa2-109">Alcuni esempi di codice illustrano come usare una sola classe <xref:System.Data.SqlClient.SqlBulkCopy> per scrivere in più tabelle.</span><span class="sxs-lookup"><span data-stu-id="5efa2-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="5efa2-110">Per questi esempi, le tabelle **BulkCopyDemoOrderHeader** e **BulkCopyDemoOrderDetail** vengono utilizzate come tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5efa2-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="5efa2-111">Queste tabelle sono basate sulle tabelle **Sales.SalesOrderHeader** e **Sales.SalesOrderDetail** in **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="5efa2-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5efa2-112">Negli esempi di codice di **SqlBulkCopy** viene illustrata la sintassi che consente di usare solo **SqlBulkCopy**.</span><span class="sxs-lookup"><span data-stu-id="5efa2-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="5efa2-113">Se le tabelle di origine e di destinazione si trovano nella stessa istanza di SQL Server, è più semplice e rapido usare un'istruzione Transact-SQL `INSERT … SELECT` per copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="5efa2-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="5efa2-114">Impostazione delle tabelle</span><span class="sxs-lookup"><span data-stu-id="5efa2-114">Table Setup</span></span>  
 <span data-ttu-id="5efa2-115">Per creare le tabelle necessarie per il corretto funzionamento degli esempi di codice, è necessario eseguire le seguenti istruzioni Transact-SQL in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5efa2-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```sql
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
  
## <a name="see-also"></a><span data-ttu-id="5efa2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5efa2-116">See also</span></span>

- [<span data-ttu-id="5efa2-117">Bulk Copy Operations in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5efa2-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="5efa2-118">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5efa2-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
