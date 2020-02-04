---
title: Recupero e modifica di dati
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: 65c373ecff004e219527754bf2e9cc56837dc305
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980054"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="f6c72-102">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-102">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="f6c72-103">La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="f6c72-103">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="f6c72-104">I provider di dati .NET Framework di ADO.NET servono come bridge tra un'applicazione e un'origine dati, consentendo di eseguire i comandi e di recuperare i dati usando un **DataReader** o un **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="f6c72-104">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="f6c72-105">Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="f6c72-105">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="f6c72-106">In ADO.NET l'aggiornamento dei dati comporta l'utilizzo degli oggetti **DataAdapter** e <xref:System.Data.DataSet>e **Command** ; Inoltre, può comportare l'utilizzo delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="f6c72-106">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6c72-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f6c72-107">In This Section</span></span>  
 [<span data-ttu-id="f6c72-108">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="f6c72-108">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="f6c72-109">Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.</span><span class="sxs-lookup"><span data-stu-id="f6c72-109">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="f6c72-110">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="f6c72-110">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="f6c72-111">Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="f6c72-111">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="f6c72-112">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="f6c72-112">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="f6c72-113">Vengono descritti i pool di connessioni per i provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6c72-113">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="f6c72-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="f6c72-114">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="f6c72-115">Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="f6c72-115">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="f6c72-116">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="f6c72-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="f6c72-117">Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.</span><span class="sxs-lookup"><span data-stu-id="f6c72-117">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="f6c72-118">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="f6c72-118">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="f6c72-119">Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="f6c72-119">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="f6c72-120">Recupero di identità o di valori numerati automaticamente</span><span class="sxs-lookup"><span data-stu-id="f6c72-120">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="f6c72-121">Viene fornito un esempio di mapping dei valori generati per una colonna **Identity** in una tabella SQL Server o per un campo **Autonumber** in una tabella di Microsoft Access a una colonna di una riga inserita in una tabella.</span><span class="sxs-lookup"><span data-stu-id="f6c72-121">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="f6c72-122">Viene descritta l'unione di valori Identity in un oggetto `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="f6c72-122">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="f6c72-123">Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="f6c72-123">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="f6c72-124">Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior`.`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="f6c72-124">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="f6c72-125">per modificare il comportamento predefinito di un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="f6c72-125">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="f6c72-126">Modifica di dati con stored procedure</span><span class="sxs-lookup"><span data-stu-id="f6c72-126">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="f6c72-127">Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="f6c72-127">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="f6c72-128">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="f6c72-128">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="f6c72-129">Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.</span><span class="sxs-lookup"><span data-stu-id="f6c72-129">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="f6c72-130">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="f6c72-130">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="f6c72-131">Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="f6c72-131">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="f6c72-132">Traccia dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-132">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="f6c72-133">Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f6c72-133">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="f6c72-134">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="f6c72-134">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="f6c72-135">Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="f6c72-135">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="f6c72-136">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="f6c72-136">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="f6c72-137">Viene descritto il supporto ADO.NET per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="f6c72-137">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="f6c72-138">Supporto per flusso SqlClient</span><span class="sxs-lookup"><span data-stu-id="f6c72-138">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="f6c72-139">Viene illustrato come scrivere applicazioni in grado di trasmettere dati da SQL Server senza che siano completamente caricate in memoria.</span><span class="sxs-lookup"><span data-stu-id="f6c72-139">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c72-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6c72-140">See also</span></span>

- [<span data-ttu-id="f6c72-141">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-141">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="f6c72-142">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="f6c72-142">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f6c72-143">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-143">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="f6c72-144">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-144">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="f6c72-145">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f6c72-145">ADO.NET Overview</span></span>](ado-net-overview.md)
