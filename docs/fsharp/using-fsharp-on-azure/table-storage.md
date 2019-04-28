---
title: Iniziare a usare archiviazione tabelle di AzureF#
description: Store dati strutturati nel cloud con archiviazione tabelle di Azure o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 54c777acd454e4f675175b814675c185e41ad9a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756351"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="60bf9-103">Introduzione all'archiviazione tabelle di Azure e l'API Table di Azure Cosmos DB con F\#</span><span class="sxs-lookup"><span data-stu-id="60bf9-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="60bf9-104">Archiviazione tabelle di Azure è un servizio che archivia dati NoSQL strutturati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="60bf9-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="60bf9-105">Archiviazione tabelle è un archivio di chiavi/attributi con una struttura senza schema.</span><span class="sxs-lookup"><span data-stu-id="60bf9-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="60bf9-106">Poiché l'archiviazione tabelle è senza schema, è facile adattare i dati come le esigenze priva di.</span><span class="sxs-lookup"><span data-stu-id="60bf9-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="60bf9-107">Accesso ai dati è rapido ed economico per tutti i tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="60bf9-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="60bf9-108">Archiviazione tabelle è in genere costo notevolmente inferiore rispetto alle soluzioni SQL tradizionali per volumi simili di dati.</span><span class="sxs-lookup"><span data-stu-id="60bf9-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="60bf9-109">È possibile usare l'archiviazione tabelle per archiviare set di dati flessibili, ad esempio i dati utente per le applicazioni web, rubriche, informazioni sul dispositivo e qualsiasi altro tipo di metadati richiesti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="60bf9-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="60bf9-110">È possibile archiviare qualsiasi numero di entità in una tabella e un account di archiviazione può contenere un numero qualsiasi di tabelle, fino al limite di capacità dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="60bf9-111">Azure Cosmos DB offre l'API di tabella per le applicazioni scritte per l'archiviazione tabelle di Azure e che richiedono funzionalità premium, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60bf9-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="60bf9-112">Distribuzione globale chiavi in mano.</span><span class="sxs-lookup"><span data-stu-id="60bf9-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="60bf9-113">Velocità effettiva dedicata in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="60bf9-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="60bf9-114">Latenze di millisecondi in pochissimi millisecondi al 99 ° percentile.</span><span class="sxs-lookup"><span data-stu-id="60bf9-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="60bf9-115">Disponibilità elevata garantita.</span><span class="sxs-lookup"><span data-stu-id="60bf9-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="60bf9-116">Indicizzazione secondaria automatica.</span><span class="sxs-lookup"><span data-stu-id="60bf9-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="60bf9-117">Le applicazioni scritte per l'archiviazione tabelle di Azure possono eseguire la migrazione ad Azure Cosmos DB usando l'API di tabella senza modifiche al codice e sfruttare i vantaggi delle funzionalità premium.</span><span class="sxs-lookup"><span data-stu-id="60bf9-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="60bf9-118">L'API tabelle include SDK client per .NET, Java, Python e Node. js.</span><span class="sxs-lookup"><span data-stu-id="60bf9-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="60bf9-119">Per altre informazioni, vedere [Introduzione all'API tabelle di Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="60bf9-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="60bf9-120">Informazioni su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="60bf9-120">About this tutorial</span></span>

<span data-ttu-id="60bf9-121">Questa esercitazione illustra come scrivere F# codice per eseguire alcune attività comuni usando l'API Azure Cosmos DB nella tabella, incluse la creazione e l'eliminazione di una tabella e inserimento, l'aggiornamento, eliminazione e query sui dati di tabella o archiviazione tabelle di Azure.</span><span class="sxs-lookup"><span data-stu-id="60bf9-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60bf9-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="60bf9-122">Prerequisites</span></span>

<span data-ttu-id="60bf9-123">Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account) oppure [account Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="60bf9-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="60bf9-124">Creare un F# creare uno Script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="60bf9-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="60bf9-125">Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script.</span><span class="sxs-lookup"><span data-stu-id="60bf9-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="60bf9-126">Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `tables.fsx`, nella F# ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="60bf9-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="60bf9-127">Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva.</span><span class="sxs-lookup"><span data-stu-id="60bf9-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="60bf9-128">Eseguire quindi un nuovo `Microsoft.WindowsAzure.ConfigurationManager` per ottenere lo spazio dei nomi Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="60bf9-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="60bf9-129">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="60bf9-129">Add namespace declarations</span></span>

<span data-ttu-id="60bf9-130">Aggiungere il codice seguente `open` istruzioni all'inizio del `tables.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="60bf9-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="60bf9-131">Ottenere la stringa di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="60bf9-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="60bf9-132">Se ci si connette al servizio di archiviazione tabelle di Azure, la stringa di connessione è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="60bf9-133">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="60bf9-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="60bf9-134">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="60bf9-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="60bf9-135">Ottenere la stringa di connessione di Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="60bf9-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="60bf9-136">Se ci si connette ad Azure Cosmos DB, la stringa di connessione è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="60bf9-137">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="60bf9-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="60bf9-138">Nel portale di Azure nell'account Cosmos DB, passare a **le impostazioni** > **stringa di connessione**, fare clic sui **copia** per copiare la connessione primaria Stringa.</span><span class="sxs-lookup"><span data-stu-id="60bf9-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="60bf9-139">Per l'esercitazione, immettere la stringa di connessione nello script, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="60bf9-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="60bf9-140">Si tratta tuttavia **sconsigliato** progetti per il real.</span><span class="sxs-lookup"><span data-stu-id="60bf9-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="60bf9-141">La chiave dell'account è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="60bf9-142">Prestare sempre attenzione proteggere la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="60bf9-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="60bf9-143">Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="60bf9-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="60bf9-144">È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="60bf9-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="60bf9-145">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="60bf9-146">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="60bf9-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="60bf9-147">Usando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="60bf9-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="60bf9-148">È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="60bf9-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="60bf9-149">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="60bf9-149">Parse the connection string</span></span>

<span data-ttu-id="60bf9-150">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="60bf9-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="60bf9-151">Restituisce un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="60bf9-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="60bf9-152">Creare il client del servizio tabelle</span><span class="sxs-lookup"><span data-stu-id="60bf9-152">Create the Table service client</span></span>

<span data-ttu-id="60bf9-153">Il `CloudTableClient` classe consente di recuperare le tabelle e le entità nell'archiviazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="60bf9-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="60bf9-154">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="60bf9-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="60bf9-155">A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="60bf9-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="60bf9-156">Creare una tabella</span><span class="sxs-lookup"><span data-stu-id="60bf9-156">Create a table</span></span>

<span data-ttu-id="60bf9-157">In questo esempio viene illustrato come creare una tabella se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="60bf9-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="60bf9-158">Aggiungere un'entità a una tabella</span><span class="sxs-lookup"><span data-stu-id="60bf9-158">Add an entity to a table</span></span>

<span data-ttu-id="60bf9-159">È necessario che un tipo che eredita da un'entità `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="60bf9-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="60bf9-160">È possibile estendere `TableEntity` nel modo desiderato, ma il tipo *necessario* dispone di un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="60bf9-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="60bf9-161">Solo le proprietà che hanno entrambe `get` e `set` vengono archiviati nella tabella di Azure.</span><span class="sxs-lookup"><span data-stu-id="60bf9-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="60bf9-162">Partizione di un'entità e la chiave di riga identificare in modo univoco l'entità nella tabella.</span><span class="sxs-lookup"><span data-stu-id="60bf9-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="60bf9-163">Le entità con la stessa chiave di partizione è possibile eseguire query più velocemente rispetto a quelle con chiavi di partizione diverse, tuttavia usando chiavi di partizione diverse assicura maggiore scalabilità delle operazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="60bf9-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="60bf9-164">Di seguito è riportato un esempio di un `Customer` che usa la `lastName` come chiave di partizione e il `firstName` come chiave di riga.</span><span class="sxs-lookup"><span data-stu-id="60bf9-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="60bf9-165">A questo punto aggiungere `Customer` alla tabella.</span><span class="sxs-lookup"><span data-stu-id="60bf9-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="60bf9-166">A tale scopo, creare un `TableOperation` che viene eseguita sulla tabella.</span><span class="sxs-lookup"><span data-stu-id="60bf9-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="60bf9-167">In questo caso, si crea un `Insert` operazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="60bf9-168">Inserire un batch di entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-168">Insert a batch of entities</span></span>

<span data-ttu-id="60bf9-169">È possibile inserire un batch di entità in una tabella utilizzando una sola operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="60bf9-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="60bf9-170">Operazioni batch consentono di combinare le operazioni in un'unica esecuzione, ma presentano alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="60bf9-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="60bf9-171">È possibile eseguire gli aggiornamenti, eliminazione e inserimento nella stessa operazione batch.</span><span class="sxs-lookup"><span data-stu-id="60bf9-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="60bf9-172">Un'operazione batch può includere fino a 100 entità.</span><span class="sxs-lookup"><span data-stu-id="60bf9-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="60bf9-173">Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="60bf9-174">Sebbene sia possibile eseguire una query in un'operazione batch, deve essere l'unica operazione nel batch.</span><span class="sxs-lookup"><span data-stu-id="60bf9-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="60bf9-175">Ecco un codice che combina due istruzioni INSERT in un'operazione batch:</span><span class="sxs-lookup"><span data-stu-id="60bf9-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="60bf9-176">Recuperare tutte le entità in una partizione</span><span class="sxs-lookup"><span data-stu-id="60bf9-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="60bf9-177">Per eseguire query su una tabella per tutte le entità in una partizione, usare un `TableQuery` oggetto.</span><span class="sxs-lookup"><span data-stu-id="60bf9-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="60bf9-178">In questo caso, Filtra per le entità in cui la chiave di partizione "Smith".</span><span class="sxs-lookup"><span data-stu-id="60bf9-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="60bf9-179">Ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="60bf9-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="60bf9-180">Recuperare un intervallo di entità in una partizione</span><span class="sxs-lookup"><span data-stu-id="60bf9-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="60bf9-181">Se non si desidera eseguire una query di tutte le entità in una partizione, è possibile specificare un intervallo combinando il filtro della chiave di partizione con un filtro della chiave di riga.</span><span class="sxs-lookup"><span data-stu-id="60bf9-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="60bf9-182">In questo caso, si usano due filtri per ottenere tutte le entità nella partizione "Smith" in cui la chiave di riga (nome) inizia con una lettera precedente a "M" nell'alfabeto.</span><span class="sxs-lookup"><span data-stu-id="60bf9-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="60bf9-183">Ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="60bf9-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="60bf9-184">Recuperare una singola entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-184">Retrieve a single entity</span></span>

<span data-ttu-id="60bf9-185">È possibile scrivere una query per recuperare una singola entità specifica.</span><span class="sxs-lookup"><span data-stu-id="60bf9-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="60bf9-186">In questo caso, si utilizza un `TableOperation` per specificare il cliente "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="60bf9-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="60bf9-187">Invece di una raccolta, si ottiene un `Customer`.</span><span class="sxs-lookup"><span data-stu-id="60bf9-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="60bf9-188">Specifica la chiave di partizione sia la chiave di riga in una query è il modo più rapido per recuperare una singola entità dal servizio tabelle.</span><span class="sxs-lookup"><span data-stu-id="60bf9-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="60bf9-189">Ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="60bf9-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="60bf9-190">Sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-190">Replace an entity</span></span>

<span data-ttu-id="60bf9-191">Per aggiornare un'entità, recuperarla dal servizio tabelle, modificare l'oggetto entità e quindi salvare le modifiche nuovamente al servizio tabella tramite un `Replace` operazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="60bf9-192">In questo modo l'entità viene completamente sostituita nel server, a meno che l'entità nel server è stato modificato dopo essere stata recuperata, nel qual caso l'operazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="60bf9-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="60bf9-193">Questo errore è impedire all'applicazione di sovrascrivere inavvertitamente le modifiche apportate da altre origini.</span><span class="sxs-lookup"><span data-stu-id="60bf9-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="60bf9-194">Inserire o sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="60bf9-195">In alcuni casi, è possibile capire se esiste un'entità nella tabella.</span><span class="sxs-lookup"><span data-stu-id="60bf9-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="60bf9-196">E in caso affermativo, i valori correnti in essa archiviati non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="60bf9-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="60bf9-197">È possibile usare `InsertOrReplace` per creare l'entità o sostituirlo se esiste, indipendentemente dallo stato.</span><span class="sxs-lookup"><span data-stu-id="60bf9-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="60bf9-198">Eseguire query su un subset delle proprietà dell'entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-198">Query a subset of entity properties</span></span>

<span data-ttu-id="60bf9-199">Una query di tabella può recuperare solo alcune proprietà da un'entità invece di tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="60bf9-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="60bf9-200">Questa tecnica, denominata proiezione, è possibile migliorare le prestazioni delle query, in particolare per entità di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="60bf9-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="60bf9-201">In questo caso, si restituiscono indirizzi di posta elettronica solo usando `DynamicTableEntity` e `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="60bf9-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="60bf9-202">Si noti che proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo quando si usa un account sul servizio tabelle.</span><span class="sxs-lookup"><span data-stu-id="60bf9-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="60bf9-203">Recuperare entità nelle pagine in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="60bf9-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="60bf9-204">Se si esegue la lettura di un numero elevato di entità e si desidera elaborarle quando vengono recuperate anziché attendere vengano tutte restituite, è possibile usare una query segmentata.</span><span class="sxs-lookup"><span data-stu-id="60bf9-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="60bf9-205">In questo caso, per restituire i risultati nelle pagine utilizzando un flusso di lavoro asincroni in modo che l'esecuzione non venga bloccata durante l'attesa per un ampio set di risultati da restituire.</span><span class="sxs-lookup"><span data-stu-id="60bf9-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="60bf9-206">È ora necessario eseguire il calcolo in modo sincrono:</span><span class="sxs-lookup"><span data-stu-id="60bf9-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="60bf9-207">Eliminare un'entità</span><span class="sxs-lookup"><span data-stu-id="60bf9-207">Delete an entity</span></span>

<span data-ttu-id="60bf9-208">È possibile eliminare un'entità dopo averla recuperata.</span><span class="sxs-lookup"><span data-stu-id="60bf9-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="60bf9-209">Come con l'aggiornamento di un'entità, l'operazione non riesce se l'entità è stato modificato dopo che è stato recuperato.</span><span class="sxs-lookup"><span data-stu-id="60bf9-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="60bf9-210">Eliminare una tabella</span><span class="sxs-lookup"><span data-stu-id="60bf9-210">Delete a table</span></span>

<span data-ttu-id="60bf9-211">È possibile eliminare una tabella da un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="60bf9-212">Una tabella in cui è stata eliminata non sarà disponibile per essere creata nuovamente per un periodo di tempo dopo l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="60bf9-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="60bf9-213">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="60bf9-213">Next steps</span></span>

<span data-ttu-id="60bf9-214">A questo punto, dopo aver appreso le nozioni di base dell'archiviazione tabelle, visitare i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse e l'API Table di Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="60bf9-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="60bf9-215">Introduzione ad Azure Cosmos DB API di tabella</span><span class="sxs-lookup"><span data-stu-id="60bf9-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="60bf9-216">Storage Client Library per .NET</span><span class="sxs-lookup"><span data-stu-id="60bf9-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="60bf9-217">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="60bf9-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="60bf9-218">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="60bf9-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="60bf9-219">Configurazione delle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="60bf9-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="60bf9-220">Introduzione all'archiviazione tabelle di Azure in .NET</span><span class="sxs-lookup"><span data-stu-id="60bf9-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
