---
title: Introduzione all'archiviazione tabelle di Azure con F#
description: Archiviare dati strutturati nel cloud usando l'archiviazione tabelle di Azure o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 23f5e40e1d9b3d5a0ee27d675362930ef86e90c5
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935580"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="cf2b6-103">Introduzione all'archiviazione tabelle di Azure e Azure Cosmos DB API Tabella con F\#</span><span class="sxs-lookup"><span data-stu-id="cf2b6-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="cf2b6-104">Il servizio di archiviazione tabelle di Azure archivia dati NoSQL non strutturati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="cf2b6-105">Archiviazione tabelle è un archivio di chiavi/attributi con una struttura senza schema.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="cf2b6-106">Poiché l'archiviazione tabelle è senza schema, è facile adattare i dati con il variare delle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="cf2b6-107">L'accesso ai dati è rapido e conveniente per tutti i tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="cf2b6-108">L'archiviazione tabelle presenta in genere costi decisamente più bassi rispetto alle soluzioni SQL tradizionali per volumi simili di dati.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="cf2b6-109">È possibile usare l'archiviazione tabelle per archiviare set di dati flessibili, ad esempio i dati utente per le applicazioni Web, le rubriche, le informazioni sui dispositivi e altri tipi di metadati richiesti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="cf2b6-110">In una tabella possono essere archiviate il numero desiderato di tabelle e un account di archiviazione può contenere un numero qualsiasi di tabelle, fino a che non viene raggiunto il limite di capacità dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="cf2b6-111">Azure Cosmos DB fornisce le API Tabella per le applicazioni scritte per l'archiviazione tabelle di Azure e che richiedono funzionalità Premium, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="cf2b6-112">Distribuzione globale chiavi in mano.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="cf2b6-113">Velocità effettiva dedicata in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="cf2b6-114">Latenze pari a singole unità di millisecondi al 99° percentile.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="cf2b6-115">Disponibilità elevata garantita.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="cf2b6-116">Indicizzazione secondaria automatica.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="cf2b6-117">Le applicazioni scritte per l'archivio tabelle di Azure possono essere trasferite in Azure Cosmos DB usando l'API di tabella senza modifiche al codice e sfruttare quindi i vantaggi offerti dalle funzionalità Premium.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="cf2b6-118">L'API Tabelle include SDK client per .NET, Java, Python e Node.js.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="cf2b6-119">Per ulteriori informazioni, vedere [Introduzione a Azure Cosmos DB API tabella](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="cf2b6-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="cf2b6-120">Informazioni su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="cf2b6-120">About this tutorial</span></span>

<span data-ttu-id="cf2b6-121">Questa esercitazione illustra come scrivere F# codice per eseguire alcune attività comuni usando l'archiviazione tabelle di Azure o il Azure Cosmos DB API tabella, tra cui la creazione e l'eliminazione di una tabella e l'inserimento, l'aggiornamento, l'eliminazione e l'esecuzione di query sui dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf2b6-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="cf2b6-122">Prerequisites</span></span>

<span data-ttu-id="cf2b6-123">Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure o un](/azure/storage/storage-create-storage-account) [account Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="cf2b6-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="cf2b6-124">Creare uno F# script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="cf2b6-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="cf2b6-125">Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="cf2b6-126">Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `tables.fsx`, nell'ambiente F# di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="cf2b6-127">Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto di `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="cf2b6-128">Ripetere l'operazione per `Microsoft.WindowsAzure.ConfigurationManager` per ottenere lo spazio dei nomi Microsoft. Azure.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="cf2b6-129">Aggiungere dichiarazioni di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="cf2b6-129">Add namespace declarations</span></span>

<span data-ttu-id="cf2b6-130">Aggiungere le istruzioni `open` seguenti all'inizio del file `tables.fsx`:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="cf2b6-131">Ottenere la stringa di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="cf2b6-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="cf2b6-132">Se ci si connette al servizio tabelle di archiviazione di Azure, per questa esercitazione è necessaria la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="cf2b6-133">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="cf2b6-134">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="cf2b6-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="cf2b6-135">Ottenere la stringa di connessione Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="cf2b6-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="cf2b6-136">Se ci si connette a Azure Cosmos DB, per questa esercitazione è necessaria la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="cf2b6-137">È possibile copiare la stringa di connessione dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="cf2b6-138">Nel portale di Azure, nell'account Cosmos DB, passare a **impostazioni** > stringa di **connessione**e fare clic sul pulsante **copia** per copiare la stringa di connessione primaria.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span>

<span data-ttu-id="cf2b6-139">Per l'esercitazione, immettere la stringa di connessione nello script, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="cf2b6-140">Questa operazione non è tuttavia **consigliata** per i progetti reali.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="cf2b6-141">La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="cf2b6-142">È consigliabile proteggere sempre la chiave dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="cf2b6-143">Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="cf2b6-144">È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="cf2b6-145">Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="cf2b6-146">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="cf2b6-147">L'uso di Gestione configurazione di Azure è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="cf2b6-148">È anche possibile usare un'API, ad esempio il tipo di `ConfigurationManager` del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="cf2b6-149">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="cf2b6-149">Parse the connection string</span></span>

<span data-ttu-id="cf2b6-150">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="cf2b6-151">Viene restituito un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="cf2b6-152">Creare il client del servizio tabelle</span><span class="sxs-lookup"><span data-stu-id="cf2b6-152">Create the Table service client</span></span>

<span data-ttu-id="cf2b6-153">La classe `CloudTableClient` consente di recuperare tabelle ed entità nell'archivio tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="cf2b6-154">Ecco come creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="cf2b6-155">A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archivio tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="cf2b6-156">Creare una tabella</span><span class="sxs-lookup"><span data-stu-id="cf2b6-156">Create a table</span></span>

<span data-ttu-id="cf2b6-157">Questo esempio illustra come creare una tabella, se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="cf2b6-158">Aggiungere un'entità a una tabella</span><span class="sxs-lookup"><span data-stu-id="cf2b6-158">Add an entity to a table</span></span>

<span data-ttu-id="cf2b6-159">Un'entità deve avere un tipo che eredita da `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="cf2b6-160">Puoi estendere `TableEntity` nel modo che preferisci, ma il tipo *deve* avere un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="cf2b6-161">Solo le proprietà con `get` e `set` vengono archiviate nella tabella di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="cf2b6-162">La chiave di partizione e di riga di un'entità identifica in modo univoco l'entità nella tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="cf2b6-163">Le query su entità con la stessa chiave di partizione vengono eseguite più rapidamente di quelle con chiavi di partizione diverse, tuttavia l'utilizzo di chiavi di partizione diverse assicura una maggiore scalabilità delle operazioni parallele.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="cf2b6-164">Di seguito è riportato un esempio di `Customer` che usa il `lastName` come chiave di partizione e il `firstName` come chiave di riga.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="cf2b6-165">A questo punto aggiungere `Customer` alla tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="cf2b6-166">A tale scopo, creare una `TableOperation` eseguita sulla tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="cf2b6-167">In questo caso, si crea un'operazione di `Insert`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="cf2b6-168">Inserire un batch di entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-168">Insert a batch of entities</span></span>

<span data-ttu-id="cf2b6-169">È possibile inserire un batch di entità in una tabella utilizzando una singola operazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="cf2b6-170">Le operazioni batch consentono di combinare le operazioni in una singola esecuzione, ma presentano alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="cf2b6-171">È possibile eseguire aggiornamenti, eliminazioni e inserimenti nella stessa operazione batch.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="cf2b6-172">Un'operazione batch può includere fino a 100 entità.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="cf2b6-173">Tutte le entità in un'operazione batch devono avere la stessa chiave di partizione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="cf2b6-174">Sebbene sia possibile eseguire una query in un'operazione batch, è necessario che sia l'unica operazione nel batch.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="cf2b6-175">Ecco il codice che combina due inserimenti in un'operazione batch:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="cf2b6-176">Recuperare tutte le entità di una partizione</span><span class="sxs-lookup"><span data-stu-id="cf2b6-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="cf2b6-177">Per eseguire una query su una tabella per tutte le entità di una partizione, usare un oggetto `TableQuery`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="cf2b6-178">Qui viene filtrato per le entità in cui "Smith" è la chiave di partizione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="cf2b6-179">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="cf2b6-180">Recuperare un intervallo di entità in una partizione</span><span class="sxs-lookup"><span data-stu-id="cf2b6-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="cf2b6-181">Se non si desidera eseguire una query su tutte le entità di una partizione, è possibile specificare un intervallo combinando il filtro della chiave di partizione con quello della chiave di riga.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="cf2b6-182">In questo caso, si usano due filtri per recuperare tutte le entità nella partizione "Smith", dove la chiave di riga (nome) inizia con una lettera precedente a "M" nell'alfabeto.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="cf2b6-183">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="cf2b6-184">Recuperare una singola entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-184">Retrieve a single entity</span></span>

<span data-ttu-id="cf2b6-185">Per recuperare una singola entità specifica, è possibile scrivere una query.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="cf2b6-186">Qui viene usato un `TableOperation` per specificare il cliente "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="cf2b6-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="cf2b6-187">Anziché una raccolta, viene restituito un `Customer`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="cf2b6-188">La definizione della chiave di partizione e della chiave di riga in una query rappresenta il modo più rapido per recuperare una singola entità dal servizio tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="cf2b6-189">È ora possibile stampare i risultati:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="cf2b6-190">Sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-190">Replace an entity</span></span>

<span data-ttu-id="cf2b6-191">Per aggiornare un'entità, recuperarla dal servizio tabelle, modificare l'oggetto entità, quindi salvare di nuovo le modifiche nel servizio tabelle utilizzando un'operazione di `Replace`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="cf2b6-192">In questo modo l'entità viene completamente sostituita nel server, a meno che l'entità nel server non sia cambiata dopo che è stata recuperata, nel qual caso l'operazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="cf2b6-193">Questo errore impedisce all'applicazione di sovrascrivere inavvertitamente le modifiche da altre origini.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="cf2b6-194">Inserire o sostituire un'entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="cf2b6-195">In alcuni casi non è possibile sapere se un'entità è presente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="cf2b6-196">In caso contrario, i valori correnti archiviati non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="cf2b6-197">È possibile utilizzare `InsertOrReplace` per creare l'entità o sostituirla, se esistente, indipendentemente dal relativo stato.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="cf2b6-198">Eseguire query su un subset di proprietà di entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-198">Query a subset of entity properties</span></span>

<span data-ttu-id="cf2b6-199">Una query di tabella può recuperare solo alcune proprietà da un'entità anziché tutte.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="cf2b6-200">Questa tecnica, denominata proiezione, può migliorare le prestazioni delle query, in particolare per entità di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="cf2b6-201">In questo caso, vengono restituiti solo gli indirizzi di posta elettronica usando `DynamicTableEntity` e `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="cf2b6-202">Si noti che la proiezione non è supportata nell'emulatore di archiviazione locale, pertanto questo codice viene eseguito solo se si usa un account sul servizio tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="cf2b6-203">Recuperare entità nelle pagine in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="cf2b6-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="cf2b6-204">Se si sta leggendo un numero elevato di entità e si vuole elaborarle quando vengono recuperate, anziché attendere che vengano restituite tutte, è possibile usare una query segmentata.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="cf2b6-205">In questo caso, si restituiscono i risultati nelle pagine usando un flusso di lavoro asincrono, in modo che l'esecuzione non venga bloccata durante l'attesa della restituzione di un set di risultati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="cf2b6-206">È ora possibile eseguire questo calcolo in modo sincrono:</span><span class="sxs-lookup"><span data-stu-id="cf2b6-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="cf2b6-207">Eliminare un'entità</span><span class="sxs-lookup"><span data-stu-id="cf2b6-207">Delete an entity</span></span>

<span data-ttu-id="cf2b6-208">È possibile eliminare un'entità dopo averla recuperata.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="cf2b6-209">Come per l'aggiornamento di un'entità, questa operazione ha esito negativo se l'entità è cambiata dopo che è stata recuperata.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="cf2b6-210">Eliminare una tabella</span><span class="sxs-lookup"><span data-stu-id="cf2b6-210">Delete a table</span></span>

<span data-ttu-id="cf2b6-211">È possibile eliminare una tabella da un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="cf2b6-212">Una tabella eliminata non potrà essere creata nuovamente per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="cf2b6-213">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="cf2b6-213">Next steps</span></span>

<span data-ttu-id="cf2b6-214">Ora che sono state apprese le nozioni di base dell'archiviazione tabelle, seguire i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse e la Azure Cosmos DB API Tabella.</span><span class="sxs-lookup"><span data-stu-id="cf2b6-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="cf2b6-215">Introduzione ad Azure Cosmos DB: API Table</span><span class="sxs-lookup"><span data-stu-id="cf2b6-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="cf2b6-216">Informazioni di riferimento sulla libreria client di archiviazione per .NET</span><span class="sxs-lookup"><span data-stu-id="cf2b6-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="cf2b6-217">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="cf2b6-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="cf2b6-218">Blog del team di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="cf2b6-218">Azure Storage Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="cf2b6-219">Configurazione delle stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="cf2b6-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
