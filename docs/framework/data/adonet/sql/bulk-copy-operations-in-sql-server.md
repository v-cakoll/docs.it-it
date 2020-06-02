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
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="5e9fa-103">Operazioni di copia di massa in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e9fa-103">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="5e9fa-104">Microsoft SQL Server include una popolare utilità della riga di comando denominata **bcp** per eseguire rapidamente la copia bulk di file di grandi dimensioni in tabelle o viste nei database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="5e9fa-105">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere soluzioni di codice gestito che offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="5e9fa-106">Esistono altri modi per caricare dati in una tabella di SQL Server (ad esempio, istruzioni INSERT) ma <xref:System.Data.SqlClient.SqlBulkCopy> offre un significativo vantaggio in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="5e9fa-107">La classe <xref:System.Data.SqlClient.SqlBulkCopy> può essere usata per scrivere dati solo in tabelle di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="5e9fa-108">Tuttavia l'origine dati non si limita a SQL Server ed è possibile usare qualsiasi origine i cui dati possano essere caricati in un'istanza <xref:System.Data.DataTable> oppure letti con un'istanza <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="5e9fa-109">Con la classe <xref:System.Data.SqlClient.SqlBulkCopy> è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="5e9fa-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="5e9fa-110">Una singola operazione di copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="5e9fa-111">Più operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="5e9fa-112">Un'operazione di copia bulk all'interno di una transazione</span><span class="sxs-lookup"><span data-stu-id="5e9fa-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e9fa-113">Con .NET Framework versione 1.1 o precedenti (in cui non è supportata la classe <xref:System.Data.SqlClient.SqlBulkCopy>), è possibile eseguire l'istruzione **BULK INSERT** di SQL Server Transact-SQL usando l'oggetto <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e9fa-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5e9fa-114">In This Section</span></span>  
 [<span data-ttu-id="5e9fa-115">Configurazione di esempio per la copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="5e9fa-116">Descrive le tabelle usate negli esempi di copia bulk e fornisce script SQL per la creazione delle tabelle nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="5e9fa-117">Singole operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="5e9fa-118">Viene descritto come eseguire una singola copia bulk dei dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy> e come eseguire l'operazione di copia bulk usando istruzioni Transact-SQL e la classe <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="5e9fa-119">Più operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="5e9fa-120">Viene descritto come eseguire più operazioni di copia bulk dei dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="5e9fa-121">Transazioni e operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="5e9fa-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="5e9fa-122">Viene descritto come eseguire un'operazione di copia bulk all'interno di una transazione e come eseguire il commit o il ripristino dello stato precedente della transazione.</span><span class="sxs-lookup"><span data-stu-id="5e9fa-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9fa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e9fa-123">See also</span></span>

- [<span data-ttu-id="5e9fa-124">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e9fa-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="5e9fa-125">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5e9fa-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
