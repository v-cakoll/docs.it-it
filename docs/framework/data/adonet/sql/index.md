---
title: SQL Server e ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: 6e88c35936de72f0d426c23493bbe5a08e707ee1
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979976"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="35619-102">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="35619-103">Questa sezione descrive le funzionalità e i comportamenti specifici del provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="35619-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="35619-104"><xref:System.Data.SqlClient> fornisce accesso alle versioni di SQL Server, che include protocolli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="35619-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="35619-105">La funzionalità del provider di dati è simile a quella presente nei provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="35619-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="35619-106"><xref:System.Data.SqlClient> include un parser del flusso TDS per comunicare direttamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35619-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35619-107">Per usare il provider di dati .NET Framework per SQL Server, è necessario che l'applicazione faccia riferimento allo spazio dei nomi <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="35619-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35619-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="35619-108">In This Section</span></span>  
 [<span data-ttu-id="35619-109">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="35619-109">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="35619-110">Viene fornita una panoramica delle funzionalità di sicurezza di SQL Server e vengono illustrati scenari per la creazione di applicazioni ADO.NET protette da usare con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35619-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="35619-111">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-111">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="35619-112">Viene descritto come usare i tipi di dati SQL Server e in che modo questi tipi interagiscono con i tipi di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35619-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="35619-113">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="35619-113">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="35619-114">Viene descritto come usare tipi di dati con valori di grandi dimensioni in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35619-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="35619-115">Operazioni sui dati SQL Server in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-115">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="35619-116">Viene descritto come usare i dati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35619-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="35619-117">Sono incluse sezioni su operazioni di copia di massa, MARS, operazioni asincrone e parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="35619-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="35619-118">Funzionalità di SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-118">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="35619-119">Vengono descritte le funzionalità di SQL Server utili per gli sviluppatori di applicazioni ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="35619-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="35619-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="35619-120">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="35619-121">Vengono descritti i processi, le tecniche e i blocchi di compilazione di base necessari per la creazione di applicazioni LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="35619-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="35619-122">Per informazioni complete sul Motore di database di SQL Server, vedere la documentazione online di SQL Server relativa alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="35619-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="35619-123">Documentazione online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="35619-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="35619-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35619-124">See also</span></span>

- [<span data-ttu-id="35619-125">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-125">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="35619-126">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-126">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="35619-127">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="35619-127">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="35619-128">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-128">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="35619-129">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="35619-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
