---
title: Mapping dei tipi di dati SQL Server e ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 878bbe41f259f1e50cd0a41669c7a352e78bc0f1
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320880"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="ce073-102">Mapping dei tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce073-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="ce073-103">SQL Server e .NET Framework sono basati su sistemi di tipi diversi che possono comportare una potenziale perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="ce073-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="ce073-104">Per mantenere l'integrità dei dati, il provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>) fornisce metodi delle funzioni di accesso tipizzate per l'uso dei dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce073-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="ce073-105">È possibile usare le enumerazioni nelle classi <xref:System.Data.SqlDbType> per specificare i tipi di dati <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="ce073-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="ce073-106">Per altre informazioni e una tabella che descrive i dati di tipo i mapping tra SQL Server e i tipi di dati .NET Framework, vedere [mapping dei tipi di dati di SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="ce073-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="ce073-107">In SQL Server 2008 vengono introdotti nuovi tipi di dati progettati per soddisfare le esigenze aziendali di uso di dati relativi a data e ora, strutturati, semistrutturati e non strutturati.</span><span class="sxs-lookup"><span data-stu-id="ce073-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="ce073-108">Questi tipi sono illustrati nella documentazione online di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ce073-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="ce073-109">I tipi di dati SQL Server disponibili per l'uso nell'applicazione dipendono dalla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="ce073-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="ce073-110">Per altre informazioni, vedere la versione rilevante della documentazione online di SQL Server nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ce073-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="ce073-111">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ce073-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="ce073-112">Tipi di dati (motore di Database)</span><span class="sxs-lookup"><span data-stu-id="ce073-112">Data Types (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="ce073-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ce073-113">In This Section</span></span>  
 [<span data-ttu-id="ce073-114">SqlTypes e DataSet</span><span class="sxs-lookup"><span data-stu-id="ce073-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="ce073-115">Viene descritto il supporto dei tipi per `SqlTypes` in `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ce073-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="ce073-116">Gestione dei valori null</span><span class="sxs-lookup"><span data-stu-id="ce073-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="ce073-117">Viene illustrato come usare i valori null e la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="ce073-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="ce073-118">Confronto tra GUID e valori uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ce073-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="ce073-119">Viene illustrato come usare valori GUID e uniqueidentifier in SQL Server e in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce073-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="ce073-120">Dati relativi a data e ora</span><span class="sxs-lookup"><span data-stu-id="ce073-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="ce073-121">Viene descritto come usare i nuovi tipi di dati relativi a data e ora in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ce073-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="ce073-122">Tipi di grandi dimensioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="ce073-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="ce073-123">Viene illustrato come recuperare i dati dai tipi UDT con valori di grandi dimensioni introdotti in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ce073-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="ce073-124">Dati XML in SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce073-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="ce073-125">Viene descritto come usare i dati XML recuperati da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce073-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ce073-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ce073-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="ce073-127">Vengono descritti la classe `DataSet` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ce073-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="ce073-128">Vengono descritti lo spazio dei nomi `SqlTypes` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ce073-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="ce073-129">Vengono descritti l'enumerazione `SqlDbType` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ce073-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="ce073-130">Vengono descritti l'enumerazione `DbType` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ce073-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce073-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce073-131">See Also</span></span>  
 [<span data-ttu-id="ce073-132">Mapping dei tipi di dati SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce073-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="ce073-133">Configurazione di parametri e tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="ce073-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="ce073-134">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="ce073-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="ce073-135">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce073-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="ce073-136">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ce073-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
