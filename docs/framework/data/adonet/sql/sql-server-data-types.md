---
title: Mapping dei tipi di dati SQL Server e ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: f727c69b1dd5c23c6a89911005256de70255fd4c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452331"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="a347e-102">Mapping dei tipi di dati SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a347e-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="a347e-103">SQL Server e .NET Framework sono basati su sistemi di tipi diversi che possono comportare una potenziale perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="a347e-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="a347e-104">Per mantenere l'integrità dei dati, il provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>) fornisce metodi delle funzioni di accesso tipizzate per l'uso dei dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a347e-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="a347e-105">È possibile usare le enumerazioni nelle classi <xref:System.Data.SqlDbType> per specificare i tipi di dati <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="a347e-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="a347e-106">Per ulteriori informazioni e per una tabella in cui vengono descritti i mapping dei tipi di dati tra SQL Server e .NET Framework tipi di dati, vedere [SQL Server mapping dei](../sql-server-data-type-mappings.md)tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="a347e-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="a347e-107">In SQL Server 2008 vengono introdotti nuovi tipi di dati progettati per soddisfare le esigenze aziendali di uso di dati relativi a data e ora, strutturati, semistrutturati e non strutturati.</span><span class="sxs-lookup"><span data-stu-id="a347e-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="a347e-108">Questi tipi sono illustrati nella documentazione online di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a347e-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="a347e-109">I tipi di dati SQL Server disponibili per l'uso nell'applicazione dipendono dalla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="a347e-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="a347e-110">Per altre informazioni, vedere la versione rilevante della documentazione online di SQL Server nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a347e-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="a347e-111">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a347e-111">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="a347e-112">Tipi di dati (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a347e-112">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a><span data-ttu-id="a347e-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a347e-113">In This Section</span></span>  
 [<span data-ttu-id="a347e-114">SqlTypes e DataSet</span><span class="sxs-lookup"><span data-stu-id="a347e-114">SqlTypes and the DataSet</span></span>](sqltypes-and-the-dataset.md)  
 <span data-ttu-id="a347e-115">Viene descritto il supporto dei tipi per `SqlTypes` in `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="a347e-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="a347e-116">Gestione dei valori null</span><span class="sxs-lookup"><span data-stu-id="a347e-116">Handling Null Values</span></span>](handling-null-values.md)  
 <span data-ttu-id="a347e-117">Viene illustrato come usare i valori null e la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="a347e-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="a347e-118">Confronto tra GUID e valori uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a347e-118">Comparing GUID and uniqueidentifier Values</span></span>](comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="a347e-119">Viene illustrato come usare valori GUID e uniqueidentifier in SQL Server e in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a347e-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="a347e-120">Dati relativi a data e ora</span><span class="sxs-lookup"><span data-stu-id="a347e-120">Date and Time Data</span></span>](date-and-time-data.md)  
 <span data-ttu-id="a347e-121">Viene descritto come usare i nuovi tipi di dati relativi a data e ora in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a347e-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="a347e-122">Tipi di grandi dimensioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a347e-122">Large UDTs</span></span>](large-udts.md)  
 <span data-ttu-id="a347e-123">Viene illustrato come recuperare i dati dai tipi UDT con valori di grandi dimensioni introdotti in SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a347e-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="a347e-124">Dati XML in SQL Server</span><span class="sxs-lookup"><span data-stu-id="a347e-124">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)  
 <span data-ttu-id="a347e-125">Viene descritto come usare i dati XML recuperati da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a347e-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a347e-126">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a347e-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="a347e-127">Vengono descritti la classe `DataSet` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a347e-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="a347e-128">Vengono descritti lo spazio dei nomi `SqlTypes` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a347e-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="a347e-129">Vengono descritti l'enumerazione `SqlDbType` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a347e-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="a347e-130">Vengono descritti l'enumerazione `DbType` e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a347e-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a347e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a347e-131">See also</span></span>

- [<span data-ttu-id="a347e-132">Mapping dei tipi di dati SQL Server</span><span class="sxs-lookup"><span data-stu-id="a347e-132">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="a347e-133">Configurazione di parametri e tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="a347e-133">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="a347e-134">Parametri valutati a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="a347e-134">Table-Valued Parameters</span></span>](table-valued-parameters.md)
- [<span data-ttu-id="a347e-135">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="a347e-135">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="a347e-136">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a347e-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
