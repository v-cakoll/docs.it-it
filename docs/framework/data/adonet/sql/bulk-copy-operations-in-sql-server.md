---
title: Operazioni di copia di massa in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31da2fbc7dca4c0c2c077991ddec39e8979b08b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="cb7c6-102">Operazioni di copia di massa in SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb7c6-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="cb7c6-103">Microsoft SQL Server include una popolare utilità della riga di comando denominata **bcp** per rapidamente la copia di massa file di grandi dimensioni in tabelle o viste nei database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="cb7c6-104">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere soluzioni di codice gestito che offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="cb7c6-105">Esistono altri metodi per caricare dati in una tabella SQL Server (ad esempio con l'istruzione INSERT) ma <xref:System.Data.SqlClient.SqlBulkCopy> offre prestazioni molto più vantaggiose.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="cb7c6-106">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere dati solo su tabelle SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="cb7c6-107">Tuttavia l'origine dati non si limita a SQL Server ed è possibile usare qualsiasi origine i cui dati possano essere caricati in un'istanza <xref:System.Data.DataTable> oppure letti con un'istanza <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="cb7c6-108">Con la classe <xref:System.Data.SqlClient.SqlBulkCopy> è possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="cb7c6-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
-   <span data-ttu-id="cb7c6-109">Copia di massa singola</span><span class="sxs-lookup"><span data-stu-id="cb7c6-109">A single bulk copy operation</span></span>  
  
-   <span data-ttu-id="cb7c6-110">Più copie di massa</span><span class="sxs-lookup"><span data-stu-id="cb7c6-110">Multiple bulk copy operations</span></span>  
  
-   <span data-ttu-id="cb7c6-111">Copia bulk all'interno di una transazione</span><span class="sxs-lookup"><span data-stu-id="cb7c6-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb7c6-112">Quando si utilizza .NET Framework versione 1.1 o precedente (che non supporta il <xref:System.Data.SqlClient.SqlBulkCopy> classe), è possibile eseguire SQL Server Transact-SQL **BULK INSERT** istruzione tramite il <xref:System.Data.SqlClient.SqlCommand> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb7c6-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cb7c6-113">In This Section</span></span>  
 [<span data-ttu-id="cb7c6-114">Installazione di esempio della copia bulk</span><span class="sxs-lookup"><span data-stu-id="cb7c6-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="cb7c6-115">Vengono descritte le tabelle usate negli esempi di copia di massa e vengono forniti gli script SQL per la creazione di tabelle nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="cb7c6-116">Operazioni di copia di massa singola</span><span class="sxs-lookup"><span data-stu-id="cb7c6-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="cb7c6-117">Viene descritto come eseguire una copia di massa singola di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy> e come eseguire la copia di massa con istruzioni Transact-SQL e con la classe <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="cb7c6-118">Più operazioni di copia Bulk</span><span class="sxs-lookup"><span data-stu-id="cb7c6-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="cb7c6-119">Viene descritto come eseguire più copie di massa di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="cb7c6-120">Transazioni e operazioni di copia Bulk</span><span class="sxs-lookup"><span data-stu-id="cb7c6-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="cb7c6-121">Viene descritto come eseguire una copia bulk all'interno di una transazione e come eseguire il commit e il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="cb7c6-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7c6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb7c6-122">See Also</span></span>  
 [<span data-ttu-id="cb7c6-123">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cb7c6-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="cb7c6-124">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="cb7c6-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
