---
title: "Introduzione all'archiviazione tabelle di Azure con F #"
description: Archiviare dati strutturati nel cloud tramite archiviazione tabelle di Azure o Azure Cosmos DB.
keywords: 'Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure'
author: sylvanc
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: 6d40211e13e8d213aa5a40d585dd384abf49ddfa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="df395-104">Introduzione all'archiviazione tabelle di Azure e l'API Azure Cosmos DB tabella utilizzo di F #</span><span class="sxs-lookup"><span data-stu-id="df395-104">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="df395-105">Archiviazione tabelle di Azure è un servizio che archivia dati NoSQL strutturati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="df395-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="df395-106">Archiviazione tabelle è un archivio o l'attributo chiave con una progettazione schemaless.</span><span class="sxs-lookup"><span data-stu-id="df395-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="df395-107">Poiché l'archiviazione tabelle è schemaless, è facile adattare i dati come le esigenze di evolve l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="df395-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="df395-108">Accesso ai dati è veloce e conveniente per tutti i tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="df395-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="df395-109">Archiviazione tabelle è in genere notevolmente inferiore costo SQL tradizionale per i volumi di dati simili.</span><span class="sxs-lookup"><span data-stu-id="df395-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="df395-110">È possibile utilizzare l'archiviazione tabelle per archiviare i set di dati flessibile, ad esempio i dati utente per applicazioni web, rubriche, informazioni sul dispositivo e qualsiasi altro tipo di metadati che richiede il servizio.</span><span class="sxs-lookup"><span data-stu-id="df395-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="df395-111">È possibile archiviare qualsiasi numero di entità in una tabella e un account di archiviazione può contenere qualsiasi numero di tabelle, fino al limite di capacità dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="df395-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="df395-112">DB Cosmos Azure fornisce l'API di tabella per le applicazioni che vengono scritti per l'archiviazione tabelle di Azure e che richiedono funzionalità premium, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="df395-112">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="df395-113">Distribuzione globale pronte all'uso.</span><span class="sxs-lookup"><span data-stu-id="df395-113">Turnkey global distribution.</span></span>
- <span data-ttu-id="df395-114">Velocità effettiva dedicata in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="df395-114">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="df395-115">Latenze cifra millisecondo al 99th dato percentile.</span><span class="sxs-lookup"><span data-stu-id="df395-115">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="df395-116">Garantire la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="df395-116">Guaranteed high availability.</span></span>
- <span data-ttu-id="df395-117">Secondario indicizzazione automatica.</span><span class="sxs-lookup"><span data-stu-id="df395-117">Automatic secondary indexing.</span></span>

<span data-ttu-id="df395-118">Le applicazioni scritte per l'archiviazione tabelle di Azure possono eseguire la migrazione a Azure Cosmos DB tramite l'API di tabella senza apportare modifiche al codice e sfruttare funzionalità premium.</span><span class="sxs-lookup"><span data-stu-id="df395-118">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="df395-119">L'API di tabella è disponibile al client SDK per .NET, Java, Python e Node.js.</span><span class="sxs-lookup"><span data-stu-id="df395-119">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="df395-120">Per altre informazioni, vedere [Introduzione all'API di Azure Cosmos DB tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="df395-120">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="df395-121">Su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="df395-121">About this tutorial</span></span>

<span data-ttu-id="df395-122">Questa esercitazione viene illustrato come scrivere codice F # per eseguire alcune attività comuni utilizzando Azure Cosmos DB tabella API, inclusa la creazione e l'eliminazione di una tabella e inserimento, aggiornamento, eliminazione e query sui dati di tabella o l'archiviazione tabelle di Azure.</span><span class="sxs-lookup"><span data-stu-id="df395-122">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df395-123">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="df395-123">Prerequisites</span></span>

<span data-ttu-id="df395-124">Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account) oppure [account Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="df395-124">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="df395-125">Creare un Script F # e avvio di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="df395-125">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="df395-126">Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #.</span><span class="sxs-lookup"><span data-stu-id="df395-126">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="df395-127">Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `tables.fsx`, nell'ambiente di sviluppo F #.</span><span class="sxs-lookup"><span data-stu-id="df395-127">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="df395-128">Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`direttiva.</span><span class="sxs-lookup"><span data-stu-id="df395-128">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="df395-129">Eseguire l'operazione per `Microsoft.WindowsAzure.ConfigurationManager` per ottenere lo spazio dei nomi Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="df395-129">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="df395-130">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="df395-130">Add namespace declarations</span></span>

<span data-ttu-id="df395-131">Aggiungere il seguente `open` istruzioni all'inizio di `tables.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="df395-131">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="df395-132">Ottenere la stringa di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="df395-132">Get your Azure Storage connection string</span></span>

<span data-ttu-id="df395-133">Se ci si connette al servizio tabella di archiviazione di Azure, è necessario la stringa di connessione per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="df395-133">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="df395-134">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="df395-134">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="df395-135">Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="df395-135">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="df395-136">Ottenere la stringa di connessione Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="df395-136">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="df395-137">Se ci si connette al database Cosmos di Azure, è necessario la stringa di connessione per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="df395-137">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="df395-138">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="df395-138">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="df395-139">Nel portale di Azure, nell'account di DB Cosmos, passare a **impostazioni** > **stringa di connessione**, fare clic sui **copia** per copiare la connessione primaria Stringa.</span><span class="sxs-lookup"><span data-stu-id="df395-139">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="df395-140">Per l'esercitazione, immettere la stringa di connessione nello script, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="df395-140">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="df395-141">Si tratta tuttavia **non è consigliabile** di progetti.</span><span class="sxs-lookup"><span data-stu-id="df395-141">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="df395-142">La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="df395-142">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="df395-143">Prestare sempre attenzione proteggere la chiave di account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="df395-143">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="df395-144">Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="df395-144">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="df395-145">È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.</span><span class="sxs-lookup"><span data-stu-id="df395-145">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="df395-146">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="df395-146">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="df395-147">Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:</span><span class="sxs-lookup"><span data-stu-id="df395-147">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="df395-148">Utilizzando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="df395-148">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="df395-149">È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="df395-149">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="df395-150">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="df395-150">Parse the connection string</span></span>

<span data-ttu-id="df395-151">Per analizzare la stringa di connessione, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="df395-151">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="df395-152">Restituisce un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="df395-152">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="df395-153">Creare il client del servizio tabelle</span><span class="sxs-lookup"><span data-stu-id="df395-153">Create the Table service client</span></span>

<span data-ttu-id="df395-154">Il `CloudTableClient` classe consente di recuperare tabelle ed entità nell'archiviazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="df395-154">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="df395-155">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="df395-155">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="df395-156">A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati in archiviazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="df395-156">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="df395-157">Creare una tabella</span><span class="sxs-lookup"><span data-stu-id="df395-157">Create a table</span></span>

<span data-ttu-id="df395-158">In questo esempio viene illustrato come creare una tabella se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="df395-158">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="df395-159">Aggiungere un'entità a una tabella</span><span class="sxs-lookup"><span data-stu-id="df395-159">Add an entity to a table</span></span>

<span data-ttu-id="df395-160">Un'entità deve disporre di un tipo che eredita da `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="df395-160">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="df395-161">È possibile estendere `TableEntity` nel modo desiderato, ma il tipo di *deve* dispone di un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="df395-161">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="df395-162">Solo le proprietà che dispongono entrambi `get` e `set` vengono archiviati nella tabella di Azure.</span><span class="sxs-lookup"><span data-stu-id="df395-162">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="df395-163">Chiave di riga e di partizione dell'entità è necessario identificare in modo univoco l'entità nella tabella.</span><span class="sxs-lookup"><span data-stu-id="df395-163">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="df395-164">Le entità con la stessa chiave di partizione è possibile eseguire query più velocemente rispetto a quelle con le chiavi di partizione diverso, ma con le chiavi di partizione diverse consente una maggiore scalabilità di operazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="df395-164">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="df395-165">Di seguito è riportato un esempio di un `Customer` che utilizza il `lastName` come chiave di partizione e `firstName` come chiave di riga.</span><span class="sxs-lookup"><span data-stu-id="df395-165">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="df395-166">A questo punto aggiungere `Customer` alla tabella.</span><span class="sxs-lookup"><span data-stu-id="df395-166">Now add `Customer` to the table.</span></span> <span data-ttu-id="df395-167">A tale scopo, creare un `TableOperation` che viene eseguita sulla tabella.</span><span class="sxs-lookup"><span data-stu-id="df395-167">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="df395-168">In questo caso, si crea un `Insert` operazione.</span><span class="sxs-lookup"><span data-stu-id="df395-168">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="df395-169">Inserire un batch di entità</span><span class="sxs-lookup"><span data-stu-id="df395-169">Insert a batch of entities</span></span>

<span data-ttu-id="df395-170">È possibile inserire un batch di entità in una tabella utilizzando una sola operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="df395-170">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="df395-171">Operazioni batch consentono di combinare operazioni in una singola esecuzione, ma presentano alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="df395-171">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="df395-172">È possibile eseguire aggiornamenti, Elimina e lo inserisce nella stessa operazione batch.</span><span class="sxs-lookup"><span data-stu-id="df395-172">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="df395-173">Un'operazione batch può includere fino a 100 entità.</span><span class="sxs-lookup"><span data-stu-id="df395-173">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="df395-174">Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.</span><span class="sxs-lookup"><span data-stu-id="df395-174">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="df395-175">Sebbene sia possibile eseguire una query in un'operazione batch, deve essere l'unica operazione nel batch.</span><span class="sxs-lookup"><span data-stu-id="df395-175">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="df395-176">Ecco alcuni codice che combina due istruzioni INSERT in un'operazione batch:</span><span class="sxs-lookup"><span data-stu-id="df395-176">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="df395-177">Recuperare tutte le entità in una partizione</span><span class="sxs-lookup"><span data-stu-id="df395-177">Retrieve all entities in a partition</span></span>

<span data-ttu-id="df395-178">Per una query sulla tabella per tutte le entità in una partizione, utilizzare un `TableQuery` oggetto.</span><span class="sxs-lookup"><span data-stu-id="df395-178">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="df395-179">In questo caso, Filtra per le entità in cui la chiave di partizione "Smith".</span><span class="sxs-lookup"><span data-stu-id="df395-179">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="df395-180">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="df395-180">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="df395-181">Recuperare un intervallo di entità in una partizione</span><span class="sxs-lookup"><span data-stu-id="df395-181">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="df395-182">Se non si desidera eseguire una query di tutte le entità in una partizione, è possibile specificare un intervallo combinando il filtro di chiave di partizione con un filtro di riga di chiave.</span><span class="sxs-lookup"><span data-stu-id="df395-182">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="df395-183">In questo caso, utilizzare due filtri per ottenere tutte le entità nella partizione "Smith" in cui la chiave di riga (nome) inizia con una lettera "M" nell'alfabeto precedenti.</span><span class="sxs-lookup"><span data-stu-id="df395-183">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="df395-184">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="df395-184">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="df395-185">Recuperare una singola entità</span><span class="sxs-lookup"><span data-stu-id="df395-185">Retrieve a single entity</span></span>

<span data-ttu-id="df395-186">È possibile scrivere una query per recuperare un'entità singola e specifica.</span><span class="sxs-lookup"><span data-stu-id="df395-186">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="df395-187">In questo caso, Usa un `TableOperation` per specificare il cliente "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="df395-187">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="df395-188">Invece di una raccolta, verrà restituito un `Customer`.</span><span class="sxs-lookup"><span data-stu-id="df395-188">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="df395-189">Specifica la chiave di partizione sia la chiave di riga in una query è il modo più rapido per recuperare una singola entità dal servizio tabelle.</span><span class="sxs-lookup"><span data-stu-id="df395-189">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="df395-190">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="df395-190">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="df395-191">Sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="df395-191">Replace an entity</span></span>

<span data-ttu-id="df395-192">Per aggiornare un'entità, recuperarlo dal servizio tabelle, modificare l'oggetto entità e quindi salvare le modifiche al servizio tabella utilizzando un `Replace` operazione.</span><span class="sxs-lookup"><span data-stu-id="df395-192">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="df395-193">In questo modo l'entità da sostituire completamente nel server, a meno che l'entità nel server è stato modificato dopo che è stata recuperata, nel qual caso l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="df395-193">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="df395-194">Questo errore consiste nell'impedire all'applicazione inavvertitamente sovrascrivendo le modifiche apportate da altre origini.</span><span class="sxs-lookup"><span data-stu-id="df395-194">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="df395-195">Inserire o sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="df395-195">Insert-or-replace an entity</span></span>

<span data-ttu-id="df395-196">In alcuni casi, non si conosce se un'entità è presente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="df395-196">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="df395-197">E in tal caso, i valori correnti archiviati in essa contenuti non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="df395-197">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="df395-198">È possibile utilizzare `InsertOrReplace` per creare l'entità o sostituirlo se esiste, indipendentemente dal suo stato.</span><span class="sxs-lookup"><span data-stu-id="df395-198">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="df395-199">Query a un subset di proprietà dell'entità</span><span class="sxs-lookup"><span data-stu-id="df395-199">Query a subset of entity properties</span></span>

<span data-ttu-id="df395-200">Una query di tabella è possibile recuperare solo alcune proprietà di un'entità anziché tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="df395-200">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="df395-201">Questa tecnica, denominata proiezione, è possibile migliorare le prestazioni delle query, in particolare per le entità di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="df395-201">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="df395-202">In questo caso, si restituiscono gli indirizzi e-mail solo `DynamicTableEntity` e `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="df395-202">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="df395-203">Si noti che proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo quando si utilizza un account del servizio di tabella.</span><span class="sxs-lookup"><span data-stu-id="df395-203">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="df395-204">Recuperare le entità in pagine in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="df395-204">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="df395-205">Se si legge un numero elevato di entità e si desidera elaborarle quando vengono recuperate anziché attenderne tutte restituito, è possibile utilizzare una query segmentata.</span><span class="sxs-lookup"><span data-stu-id="df395-205">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="df395-206">In questo caso, per restituire risultati nelle pagine utilizzando un flusso di lavoro asincroni in modo che non l'esecuzione viene bloccata durante l'attesa per un ampio set di risultati da restituire.</span><span class="sxs-lookup"><span data-stu-id="df395-206">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="df395-207">È ora eseguire il calcolo in modo sincrono:</span><span class="sxs-lookup"><span data-stu-id="df395-207">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="df395-208">Eliminare un'entità</span><span class="sxs-lookup"><span data-stu-id="df395-208">Delete an entity</span></span>

<span data-ttu-id="df395-209">Dopo avere recuperato, è possibile eliminare un'entità.</span><span class="sxs-lookup"><span data-stu-id="df395-209">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="df395-210">Come con l'aggiornamento di un'entità, l'operazione non riesce se l'entità è stata modificata dopo che è stato recuperato.</span><span class="sxs-lookup"><span data-stu-id="df395-210">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="df395-211">Eliminare una tabella</span><span class="sxs-lookup"><span data-stu-id="df395-211">Delete a table</span></span>

<span data-ttu-id="df395-212">È possibile eliminare una tabella da un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="df395-212">You can delete a table from a storage account.</span></span> <span data-ttu-id="df395-213">Una tabella in cui è stata eliminata non sarà disponibile per essere ricreati per un periodo di tempo in seguito all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="df395-213">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="df395-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="df395-214">Next steps</span></span>

<span data-ttu-id="df395-215">Ora che si è appreso le nozioni di base dell'archiviazione tabelle, vedere i collegamenti seguenti per apprendere le attività più complesse di archiviazione e l'API di tabelle di Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="df395-215">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="df395-216">Introduzione a Azure Cosmos API di tabelle di database</span><span class="sxs-lookup"><span data-stu-id="df395-216">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="df395-217">Libreria Client di archiviazione per il riferimento di .NET</span><span class="sxs-lookup"><span data-stu-id="df395-217">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="df395-218">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="df395-218">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="df395-219">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="df395-219">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="df395-220">Configurazione delle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="df395-220">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="df395-221">Introduzione all'archiviazione tabelle di Azure in .NET</span><span class="sxs-lookup"><span data-stu-id="df395-221">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
