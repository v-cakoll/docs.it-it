---
title: Recupero e modifica di dati in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4ea157cd52bf92dace924baaa40f5b1bba6f13a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="088ec-102">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="088ec-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="088ec-103">La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="088ec-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="088ec-104">I provider di dati .NET Framework di ADO.NET fungono da ponte tra un'applicazione e un'origine dati, consentendo di eseguire comandi e di recuperare i dati utilizzando un **DataReader** o **DataAdapter** .</span><span class="sxs-lookup"><span data-stu-id="088ec-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="088ec-105">Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="088ec-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="088ec-106">In ADO.NET l'aggiornamento dei dati prevede l'uso di **DataAdapter** e <xref:System.Data.DataSet>, e **comando** degli oggetti può anche comprendere l'utilizzo delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="088ec-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="088ec-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="088ec-107">In This Section</span></span>  
 [<span data-ttu-id="088ec-108">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="088ec-108">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 <span data-ttu-id="088ec-109">Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.</span><span class="sxs-lookup"><span data-stu-id="088ec-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="088ec-110">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="088ec-110">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 <span data-ttu-id="088ec-111">Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="088ec-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="088ec-112">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="088ec-112">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 <span data-ttu-id="088ec-113">Vengono descritti i pool di connessioni per i provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="088ec-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="088ec-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="088ec-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 <span data-ttu-id="088ec-115">Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="088ec-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="088ec-116">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="088ec-116">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="088ec-117">Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.</span><span class="sxs-lookup"><span data-stu-id="088ec-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="088ec-118">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="088ec-118">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 <span data-ttu-id="088ec-119">Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="088ec-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="088ec-120">Recupero di identità o di valori numerati automaticamente</span><span class="sxs-lookup"><span data-stu-id="088ec-120">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="088ec-121">Fornisce un esempio di mapping i valori generati per un **identità** colonna in un [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] tabella o per un **contatore** campo in una tabella di Microsoft Access, a una colonna di una riga inserita in una tabella.</span><span class="sxs-lookup"><span data-stu-id="088ec-121">Provides an example of mapping the values generated for an **identity** column in a [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="088ec-122">Viene descritta l'unione di valori Identity in un oggetto `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="088ec-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="088ec-123">Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="088ec-123">Retrieving Binary Data</span></span>](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 <span data-ttu-id="088ec-124">Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="088ec-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="088ec-125">Per modificare il comportamento predefinito di un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="088ec-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="088ec-126">Modifica di dati con stored procedure</span><span class="sxs-lookup"><span data-stu-id="088ec-126">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="088ec-127">Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="088ec-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="088ec-128">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="088ec-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 <span data-ttu-id="088ec-129">Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.</span><span class="sxs-lookup"><span data-stu-id="088ec-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="088ec-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="088ec-130">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="088ec-131">Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="088ec-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="088ec-132">Traccia dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="088ec-132">Data Tracing in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-tracing.md)  
 <span data-ttu-id="088ec-133">Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="088ec-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="088ec-134">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="088ec-134">Performance Counters</span></span>](../../../../docs/framework/data/adonet/performance-counters.md)  
 <span data-ttu-id="088ec-135">Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="088ec-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="088ec-136">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="088ec-136">Asynchronous Programming</span></span>](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 <span data-ttu-id="088ec-137">Viene descritto il supporto di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="088ec-137">Describes [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="088ec-138">Supporto per flusso SqlClient</span><span class="sxs-lookup"><span data-stu-id="088ec-138">SqlClient Streaming Support</span></span>](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 <span data-ttu-id="088ec-139">Viene illustrato come scrivere applicazioni che trasmettono i dati da [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] senza doverli caricare completamente in memoria.</span><span class="sxs-lookup"><span data-stu-id="088ec-139">Discusses how to write applications that stream data from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088ec-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="088ec-140">See Also</span></span>  
 [<span data-ttu-id="088ec-141">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="088ec-141">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="088ec-142">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="088ec-142">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="088ec-143">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="088ec-143">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="088ec-144">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="088ec-144">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="088ec-145">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="088ec-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
