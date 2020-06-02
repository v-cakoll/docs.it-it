---
title: Recupero e modifica di dati
description: Nel .NET Framework i provider di dati in ADO.NET fungeranno da Bridge tra un'applicazione e un'origine dati per leggere e aggiornare i dati.
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: f916324dc829526a5e6b0078021b09786755f666
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286611"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="92b50-103">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-103">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="92b50-104">La connessione a un'origine dati e il recupero dei dati in essa contenuti sono funzioni fondamentali nelle applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="92b50-104">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="92b50-105">I provider di dati .NET Framework di ADO.NET servono come bridge tra un'applicazione e un'origine dati, consentendo di eseguire i comandi e di recuperare i dati usando un **DataReader** o un **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="92b50-105">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="92b50-106">Una funzione chiave di qualsiasi applicazione di database è la capacità di aggiornare i dati archiviati nel database.</span><span class="sxs-lookup"><span data-stu-id="92b50-106">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="92b50-107">In ADO.NET l'aggiornamento dei dati comporta l'utilizzo degli oggetti **DataAdapter** e e <xref:System.Data.DataSet> **Command** e può inoltre comportare l'utilizzo di transazioni.</span><span class="sxs-lookup"><span data-stu-id="92b50-107">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92b50-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="92b50-108">In This Section</span></span>  
 [<span data-ttu-id="92b50-109">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="92b50-109">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="92b50-110">Viene descritto come stabilire una connessione a un'origine dati e come usare gli eventi di connessione.</span><span class="sxs-lookup"><span data-stu-id="92b50-110">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="92b50-111">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="92b50-111">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="92b50-112">Sono inclusi argomenti in cui vengono descritti diversi aspetti relativi all'utilizzo delle stringhe di connessione, quali le parole chiave, le informazioni di sicurezza e l'archiviazione e il recupero delle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="92b50-112">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="92b50-113">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="92b50-113">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="92b50-114">Vengono descritti i pool di connessioni per i provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92b50-114">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="92b50-115">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="92b50-115">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="92b50-116">Sono inclusi argomenti in cui viene descritto come creare comandi e compilatori di comandi, come configurare parametri e come eseguire comandi per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="92b50-116">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="92b50-117">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="92b50-117">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="92b50-118">Sono inclusi argomenti in cui vengono descritti DataReaders, DataAdapters, i parametri, la gestione di eventi DataAdapter e l'esecuzione di operazioni batch.</span><span class="sxs-lookup"><span data-stu-id="92b50-118">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="92b50-119">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="92b50-119">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="92b50-120">Sono inclusi argomenti in cui viene descritto come eseguire transazioni locali e transazioni distribuite e come usare concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="92b50-120">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="92b50-121">Recupero di identità o di valori numerati automaticamente</span><span class="sxs-lookup"><span data-stu-id="92b50-121">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="92b50-122">Viene fornito un esempio di mapping dei valori generati per una colonna **Identity** in una tabella SQL Server o per un campo **Autonumber** in una tabella di Microsoft Access a una colonna di una riga inserita in una tabella.</span><span class="sxs-lookup"><span data-stu-id="92b50-122">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="92b50-123">Viene descritta l'unione di valori Identity in un oggetto `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="92b50-123">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="92b50-124">Recupero di dati binari</span><span class="sxs-lookup"><span data-stu-id="92b50-124">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="92b50-125">Viene descritto come recuperare dati binari o strutture di dati di grandi dimensioni utilizzando `CommandBehavior` .`SequentialAccess`</span><span class="sxs-lookup"><span data-stu-id="92b50-125">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="92b50-126">per modificare il comportamento predefinito di un oggetto `DataReader` .</span><span class="sxs-lookup"><span data-stu-id="92b50-126">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="92b50-127">Modifica di dati con stored procedure</span><span class="sxs-lookup"><span data-stu-id="92b50-127">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="92b50-128">Viene descritto come usare i parametri di input e di output della stored procedure per inserire una riga in un database, restituendo un nuovo valore Identity.</span><span class="sxs-lookup"><span data-stu-id="92b50-128">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="92b50-129">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="92b50-129">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="92b50-130">Viene descritto come ottenere da un'origine dati database o cataloghi disponibili, tabelle e visualizzazioni in un database, vincoli esistenti per tabelle e altre informazioni relative allo schema.</span><span class="sxs-lookup"><span data-stu-id="92b50-130">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="92b50-131">Oggetti DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="92b50-131">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="92b50-132">Viene descritto il modello a livello di factory del provider e viene illustrato come usare le classi base nello spazio dei nomi `System.Data.Common`.</span><span class="sxs-lookup"><span data-stu-id="92b50-132">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="92b50-133">Traccia dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-133">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="92b50-134">Vengono descritte le funzionalità di analisi dei dati predefinite di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="92b50-134">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="92b50-135">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="92b50-135">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="92b50-136">Vengono descritti i contatori delle prestazioni disponibili per `SqlClient` e `OracleClient`.</span><span class="sxs-lookup"><span data-stu-id="92b50-136">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="92b50-137">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="92b50-137">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="92b50-138">Viene descritto il supporto ADO.NET per la programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="92b50-138">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="92b50-139">Supporto del flusso SqlClient</span><span class="sxs-lookup"><span data-stu-id="92b50-139">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="92b50-140">Viene illustrato come scrivere applicazioni in grado di trasmettere dati da SQL Server senza che siano completamente caricate in memoria.</span><span class="sxs-lookup"><span data-stu-id="92b50-140">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b50-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92b50-141">See also</span></span>

- [<span data-ttu-id="92b50-142">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-142">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="92b50-143">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="92b50-143">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="92b50-144">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-144">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="92b50-145">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-145">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="92b50-146">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92b50-146">ADO.NET Overview</span></span>](ado-net-overview.md)
