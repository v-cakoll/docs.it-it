---
title: SQL Server e ADO.NET
description: Informazioni sulle funzionalità e sui comportamenti della provider di dati .NET Framework per SQL Server che incapsula i protocolli specifici del database.
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: eeb0ab69a68dfc2fc0faa1b4e833f80b307fffe5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286443"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="b39fe-103">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-103">SQL Server and ADO.NET</span></span>
<span data-ttu-id="b39fe-104">Questa sezione descrive le funzionalità e i comportamenti specifici del provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="b39fe-104">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="b39fe-105"><xref:System.Data.SqlClient> fornisce accesso alle versioni di SQL Server, che includono protocolli specifici del database.</span><span class="sxs-lookup"><span data-stu-id="b39fe-105"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="b39fe-106">La funzionalità del provider di dati è simile a quella presente nei provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="b39fe-106">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="b39fe-107"><xref:System.Data.SqlClient> include un parser TDS (Tabular Data Stream) per comunicare direttamente con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b39fe-107"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b39fe-108">Per usare il provider di dati .NET Framework per SQL Server, è necessario che l'applicazione faccia riferimento allo spazio dei nomi <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="b39fe-108">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b39fe-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b39fe-109">In This Section</span></span>  
 [<span data-ttu-id="b39fe-110">Sicurezza SQL Server</span><span class="sxs-lookup"><span data-stu-id="b39fe-110">SQL Server Security</span></span>](sql-server-security.md)  
 <span data-ttu-id="b39fe-111">Viene fornita una panoramica delle funzionalità di sicurezza di SQL Server e degli scenari per la creazione di applicazioni ADO.NET sicure da usare con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b39fe-111">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="b39fe-112">Tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-112">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)  
 <span data-ttu-id="b39fe-113">Viene descritto come usare i tipi di dati SQL Server e in che modo questi tipi interagiscono con i tipi di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b39fe-113">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="b39fe-114">SQL Server dati binari e per valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b39fe-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="b39fe-115">Viene descritto come usare i tipi di dati con valori di grandi dimensioni in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b39fe-115">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="b39fe-116">SQL Server operazioni sui dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-116">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)  
 <span data-ttu-id="b39fe-117">Viene descritto come usare i dati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b39fe-117">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="b39fe-118">Contiene sezioni sulle operazioni di copia bulk, MARS, le operazioni asincrone e i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="b39fe-118">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="b39fe-119">Funzionalità di SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-119">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)  
 <span data-ttu-id="b39fe-120">Descrive le funzionalità di SQL Server utili per gli sviluppatori di applicazioni ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b39fe-120">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="b39fe-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b39fe-121">LINQ to SQL</span></span>](./linq/index.md)  
 <span data-ttu-id="b39fe-122">Vengono descritti i processi, le tecniche e i blocchi di compilazione di base necessari per la creazione di applicazioni LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="b39fe-122">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="b39fe-123">Per la documentazione completa del motore di database di SQL Server, vedere la documentazione online di SQL Server per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="b39fe-123">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="b39fe-124">Documentazione online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b39fe-124">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="b39fe-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b39fe-125">See also</span></span>

- [<span data-ttu-id="b39fe-126">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-126">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="b39fe-127">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-127">Data Type Mappings in ADO.NET</span></span>](../data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="b39fe-128">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b39fe-128">DataSets, DataTables, and DataViews</span></span>](../dataset-datatable-dataview/index.md)
- [<span data-ttu-id="b39fe-129">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="b39fe-130">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b39fe-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
