---
title: SQL Server e ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: f30d9d715a2d94deee788f92cfc8eed0cba706de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172770"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="a8e54-102">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="a8e54-103">Questa sezione descrive le funzionalità e i comportamenti specifici del provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="a8e54-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="a8e54-104"><xref:System.Data.SqlClient> fornisce accesso alle versioni di SQL Server, che include protocolli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="a8e54-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="a8e54-105">La funzionalità del provider di dati è simile a quella presente nei provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="a8e54-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="a8e54-106"><xref:System.Data.SqlClient> include un parser del flusso TDS per comunicare direttamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e54-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8e54-107">Per usare il provider di dati .NET Framework per SQL Server, è necessario che l'applicazione faccia riferimento allo spazio dei nomi <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="a8e54-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8e54-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a8e54-108">In This Section</span></span>  
 [<span data-ttu-id="a8e54-109">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8e54-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="a8e54-110">Viene fornita una panoramica delle funzionalità di sicurezza di SQL Server e vengono illustrati scenari per la creazione di applicazioni ADO.NET protette da usare con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e54-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="a8e54-111">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="a8e54-112">Viene descritto come usare i tipi di dati SQL Server e in che modo questi tipi interagiscono con i tipi di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e54-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="a8e54-113">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8e54-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="a8e54-114">Viene descritto come usare tipi di dati con valori di grandi dimensioni in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e54-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="a8e54-115">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="a8e54-116">Viene descritto come usare i dati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e54-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="a8e54-117">Sono incluse sezioni su operazioni di copia di massa, MARS, operazioni asincrone e parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="a8e54-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="a8e54-118">Funzionalità di SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="a8e54-119">Vengono descritte le funzionalità di SQL Server utili per gli sviluppatori di applicazioni ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a8e54-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="a8e54-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a8e54-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="a8e54-121">Vengono descritti i processi, le tecniche e i blocchi di compilazione di base necessari per la creazione di applicazioni LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="a8e54-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="a8e54-122">Per informazioni complete sul Motore di database di SQL Server, vedere la documentazione online di SQL Server relativa alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="a8e54-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="a8e54-123">Documentazione online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8e54-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="a8e54-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8e54-124">See also</span></span>

- [<span data-ttu-id="a8e54-125">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="a8e54-126">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="a8e54-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="a8e54-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="a8e54-128">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8e54-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="a8e54-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a8e54-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
