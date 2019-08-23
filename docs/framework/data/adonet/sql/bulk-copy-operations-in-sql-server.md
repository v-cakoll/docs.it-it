---
title: Operazioni di copia di massa in SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: efa13eb1633fce3b59040ef8da79dba0f6ea81d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918056"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="0bbd7-102">Operazioni di copia di massa in SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bbd7-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="0bbd7-103">Microsoft SQL Server include una nota utilità da riga di comando denominata **bcp** per la copia bulk di file di grandi dimensioni in tabelle o viste nei database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="0bbd7-104">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere soluzioni di codice gestito che offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="0bbd7-105">Esistono altri metodi per caricare dati in una tabella SQL Server (ad esempio con l'istruzione INSERT) ma <xref:System.Data.SqlClient.SqlBulkCopy> offre prestazioni molto più vantaggiose.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="0bbd7-106">La classe <xref:System.Data.SqlClient.SqlBulkCopy> consente di scrivere dati solo su tabelle SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="0bbd7-107">Tuttavia l'origine dati non si limita a SQL Server ed è possibile usare qualsiasi origine i cui dati possano essere caricati in un'istanza <xref:System.Data.DataTable> oppure letti con un'istanza <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="0bbd7-108">Con la classe <xref:System.Data.SqlClient.SqlBulkCopy> è possibile eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="0bbd7-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="0bbd7-109">Copia di massa singola</span><span class="sxs-lookup"><span data-stu-id="0bbd7-109">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="0bbd7-110">Più copie di massa</span><span class="sxs-lookup"><span data-stu-id="0bbd7-110">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="0bbd7-111">Copia bulk all'interno di una transazione</span><span class="sxs-lookup"><span data-stu-id="0bbd7-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bbd7-112">Quando si usa .NET Framework versione 1,1 o precedente (che non supporta la <xref:System.Data.SqlClient.SqlBulkCopy> classe), è possibile eseguire l'istruzione SQL Server **BULK INSERT** Transact-SQL usando l' <xref:System.Data.SqlClient.SqlCommand> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bbd7-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0bbd7-113">In This Section</span></span>  
 [<span data-ttu-id="0bbd7-114">Creazione di esempi di copia di massa</span><span class="sxs-lookup"><span data-stu-id="0bbd7-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="0bbd7-115">Vengono descritte le tabelle usate negli esempi di copia di massa e vengono forniti gli script SQL per la creazione di tabelle nel database AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="0bbd7-116">Singole operazioni di copia di massa</span><span class="sxs-lookup"><span data-stu-id="0bbd7-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="0bbd7-117">Viene descritto come eseguire una copia di massa singola di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy> e come eseguire la copia di massa con istruzioni Transact-SQL e con la classe <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="0bbd7-118">Più operazioni di copia di massa</span><span class="sxs-lookup"><span data-stu-id="0bbd7-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="0bbd7-119">Viene descritto come eseguire più copie di massa di dati in un'istanza di SQL Server usando la classe <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="0bbd7-120">Transazioni e operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="0bbd7-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="0bbd7-121">Viene descritto come eseguire una copia bulk all'interno di una transazione e come eseguire il commit e il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="0bbd7-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbd7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bbd7-122">See also</span></span>

- [<span data-ttu-id="0bbd7-123">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0bbd7-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="0bbd7-124">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0bbd7-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
