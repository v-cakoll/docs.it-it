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
ms.openlocfilehash: 35de20b1cb35fdcd87a653f1ac202c01d345c317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="e3023-102">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3023-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="e3023-103">La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="e3023-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="e3023-104">I provider di dati .NET Framework di ADO.NET fungono da ponte tra un'applicazione e un'origine dati, consentendo di eseguire comandi e di recuperare i dati utilizzando un **DataReader** o **DataAdapter** .</span><span class="sxs-lookup"><span data-stu-id="e3023-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="e3023-105">Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="e3023-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="e3023-106">In ADO.NET l'aggiornamento dei dati prevede l'uso di **DataAdapter** e <xref:System.Data.DataSet>, e **comando** degli oggetti può anche comprendere l'utilizzo delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="e3023-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3023-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e3023-107">In This Section</span></span>  
 [<span data-ttu-id="e3023-108">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="e3023-108">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 <span data-ttu-id="e3023-109">Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.</span><span class="sxs-lookup"><span data-stu-id="e3023-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="e3023-110">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="e3023-110">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 <span data-ttu-id="e3023-111">Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="e3023-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="e3023-112">Il pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="e3023-112">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 <span data-ttu-id="e3023-113">Vengono descritti i pool di connessioni per i provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3023-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="e3023-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="e3023-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 <span data-ttu-id="e3023-115">Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="e3023-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="e3023-116">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="e3023-116">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 <span data-ttu-id="e3023-117">Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.</span><span class="sxs-lookup"><span data-stu-id="e3023-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="e3023-118">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="e3023-118">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 <span data-ttu-id="e3023-119">Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="e3023-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="e3023-120">Recupero di identità o valori numerati automaticamente</span><span class="sxs-lookup"><span data-stu-id="e3023-120">Retrieving Identity or Autonumber Values</span></span>](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="e3023-121">Fornisce un esempio di mapping i valori generati per un **identità** colonna in un [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] tabella o per un **contatore** campo in una tabella di Microsoft Access, a una colonna di una riga inserita in una tabella.</span><span class="sxs-lookup"><span data-stu-id="e3023-121">Provides an example of mapping the values generated for an **identity** column in a [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="e3023-122">Viene descritta l'unione di valori Identity in un oggetto `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="e3023-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="e3023-123">Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="e3023-123">Retrieving Binary Data</span></span>](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 <span data-ttu-id="e3023-124">Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="e3023-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="e3023-125">Per modificare il comportamento predefinito di un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="e3023-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="e3023-126">Modifica dei dati con le Stored procedure</span><span class="sxs-lookup"><span data-stu-id="e3023-126">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="e3023-127">Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="e3023-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="e3023-128">Durante il recupero delle informazioni sullo Schema di Database</span><span class="sxs-lookup"><span data-stu-id="e3023-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 <span data-ttu-id="e3023-129">Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.</span><span class="sxs-lookup"><span data-stu-id="e3023-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="e3023-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="e3023-130">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="e3023-131">Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="e3023-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="e3023-132">Traccia dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3023-132">Data Tracing in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-tracing.md)  
 <span data-ttu-id="e3023-133">Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e3023-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="e3023-134">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e3023-134">Performance Counters</span></span>](../../../../docs/framework/data/adonet/performance-counters.md)  
 <span data-ttu-id="e3023-135">Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="e3023-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="e3023-136">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="e3023-136">Asynchronous Programming</span></span>](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 <span data-ttu-id="e3023-137">Viene descritto il supporto di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="e3023-137">Describes [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="e3023-138">Supporto del flusso SqlClient</span><span class="sxs-lookup"><span data-stu-id="e3023-138">SqlClient Streaming Support</span></span>](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 <span data-ttu-id="e3023-139">Viene illustrato come scrivere applicazioni che trasmettono i dati da [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] senza doverli caricare completamente in memoria.</span><span class="sxs-lookup"><span data-stu-id="e3023-139">Discusses how to write applications that stream data from [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3023-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3023-140">See Also</span></span>  
 [<span data-ttu-id="e3023-141">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3023-141">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="e3023-142">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="e3023-142">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="e3023-143">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3023-143">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="e3023-144">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3023-144">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="e3023-145">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="e3023-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
