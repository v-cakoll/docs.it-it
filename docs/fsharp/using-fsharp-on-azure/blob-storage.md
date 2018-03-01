---
title: 'Introduzione all''archiviazione Blob di Azure con F #'
description: Archiviare dati non strutturati nel cloud con archiviazione Blob di Azure.
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c5b74a4f-dcd1-4849-930c-904b6c8a04e1
ms.openlocfilehash: 5be948e100c496bc6613f1fdfb826ece5de6df8e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="85a14-104">Introduzione all'archiviazione Blob di Azure con F #</span><span class="sxs-lookup"><span data-stu-id="85a14-104">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="85a14-105">Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB.</span><span class="sxs-lookup"><span data-stu-id="85a14-105">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="85a14-106">Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-106">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="85a14-107">Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="85a14-107">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="85a14-108">In questo articolo viene illustrato come eseguire attività comuni di utilizzo dell'archiviazione Blob.</span><span class="sxs-lookup"><span data-stu-id="85a14-108">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="85a14-109">Gli esempi sono scritte in F # utilizzando la libreria Client di archiviazione di Azure per .NET.</span><span class="sxs-lookup"><span data-stu-id="85a14-109">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="85a14-110">Argomenti trattati includono le modalità caricare, elenco, scaricare ed eliminare i BLOB.</span><span class="sxs-lookup"><span data-stu-id="85a14-110">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="85a14-111">Per una panoramica concettuale dell'archiviazione blob, vedere [la Guida di .NET per l'archiviazione blob](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="85a14-111">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85a14-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="85a14-112">Prerequisites</span></span>

<span data-ttu-id="85a14-113">Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="85a14-113">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="85a14-114">È necessario anche la chiave di accesso di archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="85a14-114">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="85a14-115">Creare un Script F # e avvio di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="85a14-115">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="85a14-116">Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #.</span><span class="sxs-lookup"><span data-stu-id="85a14-116">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="85a14-117">Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `blobs.fsx`, nell'ambiente di sviluppo F #.</span><span class="sxs-lookup"><span data-stu-id="85a14-117">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="85a14-118">Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` e `Microsoft.WindowsAzure.ConfigurationManager` pacchetti e riferimento `WindowsAzure.Storage.dll` e `Microsoft.WindowsAzure.Configuration.dll` nel script utilizzando un `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="85a14-118">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="85a14-119">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="85a14-119">Add namespace declarations</span></span>

<span data-ttu-id="85a14-120">Aggiungere il seguente `open` istruzioni all'inizio di `blobs.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="85a14-120">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="85a14-121">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="85a14-121">Get your connection string</span></span>

<span data-ttu-id="85a14-122">Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-122">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="85a14-123">Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="85a14-123">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="85a14-124">Per l'esercitazione, immettere la stringa di connessione nello script, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-124">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="85a14-125">Si tratta tuttavia **non è consigliabile** di progetti.</span><span class="sxs-lookup"><span data-stu-id="85a14-125">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="85a14-126">La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-126">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="85a14-127">Prestare sempre attenzione proteggere la chiave di account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-127">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="85a14-128">Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="85a14-128">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="85a14-129">È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.</span><span class="sxs-lookup"><span data-stu-id="85a14-129">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="85a14-130">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-130">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="85a14-131">Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:</span><span class="sxs-lookup"><span data-stu-id="85a14-131">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="85a14-132">Utilizzando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="85a14-132">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="85a14-133">È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="85a14-133">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="85a14-134">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="85a14-134">Parse the connection string</span></span>

<span data-ttu-id="85a14-135">Per analizzare la stringa di connessione, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="85a14-135">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="85a14-136">Restituisce un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="85a14-136">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="85a14-137">Creare alcuni dati fittizi locali</span><span class="sxs-lookup"><span data-stu-id="85a14-137">Create some local dummy data</span></span>

<span data-ttu-id="85a14-138">Prima di iniziare, creare alcuni dati fittizi locali nella directory dello script.</span><span class="sxs-lookup"><span data-stu-id="85a14-138">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="85a14-139">In un secondo momento caricare questi dati.</span><span class="sxs-lookup"><span data-stu-id="85a14-139">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="85a14-140">Creare il client del servizio Blob</span><span class="sxs-lookup"><span data-stu-id="85a14-140">Create the Blob service client</span></span>

<span data-ttu-id="85a14-141">Il `CloudBlobClient` tipo consente di recuperare i contenitori e BLOB archiviati nell'archiviazione Blob.</span><span class="sxs-lookup"><span data-stu-id="85a14-141">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="85a14-142">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="85a14-142">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="85a14-143">A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati nell'archiviazione Blob.</span><span class="sxs-lookup"><span data-stu-id="85a14-143">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="85a14-144">Creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="85a14-144">Create a container</span></span>

<span data-ttu-id="85a14-145">In questo esempio viene illustrato come creare un contenitore, se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="85a14-145">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="85a14-146">Per impostazione predefinita, il nuovo contenitore è privato, vale a dire che è necessario specificare la chiave di accesso di archiviazione per il download di BLOB da questo contenitore.</span><span class="sxs-lookup"><span data-stu-id="85a14-146">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="85a14-147">Se si desidera rendere disponibili i file all'interno del contenitore per tutti gli utenti, è possibile impostare il contenitore sia pubblico utilizzando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-147">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="85a14-148">Chiunque su Internet può visualizzare i BLOB in un contenitore pubblico, ma è possibile modificare o eliminare solo se è la chiave di accesso account appropriato o una firma di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="85a14-148">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="85a14-149">Caricare un blob in un contenitore</span><span class="sxs-lookup"><span data-stu-id="85a14-149">Upload a blob into a container</span></span>

<span data-ttu-id="85a14-150">Archiviazione Blob di Azure supporta i BLOB in blocchi e BLOB di pagine.</span><span class="sxs-lookup"><span data-stu-id="85a14-150">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="85a14-151">Nella maggior parte dei casi, un blob in blocchi è il tipo consigliato da usare.</span><span class="sxs-lookup"><span data-stu-id="85a14-151">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="85a14-152">Per caricare un file di un blob in blocchi, ottenere un riferimento a un contenitore e usarlo per ottenere un riferimento di blob di blocco.</span><span class="sxs-lookup"><span data-stu-id="85a14-152">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="85a14-153">Dopo aver creato un riferimento di blob, è possibile caricare qualsiasi flusso di dati a esso tramite la chiamata di `UploadFromFile` metodo.</span><span class="sxs-lookup"><span data-stu-id="85a14-153">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="85a14-154">Questa operazione crea il blob se non è stata precedentemente esiste, o sovrascrivere il file se esiste.</span><span class="sxs-lookup"><span data-stu-id="85a14-154">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="85a14-155">Elencare i BLOB in un contenitore</span><span class="sxs-lookup"><span data-stu-id="85a14-155">List the blobs in a container</span></span>

<span data-ttu-id="85a14-156">Per elencare i BLOB in un contenitore, innanzitutto ottenere un riferimento di contenitore.</span><span class="sxs-lookup"><span data-stu-id="85a14-156">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="85a14-157">È quindi possibile utilizzare il contenitore `ListBlobs` metodo per recuperare il BLOB e/o directory all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="85a14-157">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="85a14-158">Per accedere al set completo di proprietà e metodi per un tipo restituito `IListBlobItem`, è necessario eseguirne il cast a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` oggetto.</span><span class="sxs-lookup"><span data-stu-id="85a14-158">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="85a14-159">Se il tipo è sconosciuto, è possibile utilizzare un controllo del tipo per determinare quale eseguire il cast a.</span><span class="sxs-lookup"><span data-stu-id="85a14-159">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="85a14-160">Il codice seguente viene illustrato come recuperare e l'URI di ciascun elemento di output di `mydata` contenitore:</span><span class="sxs-lookup"><span data-stu-id="85a14-160">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="85a14-161">È inoltre possibile BLOB nome con informazioni sul percorso nei nomi.</span><span class="sxs-lookup"><span data-stu-id="85a14-161">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="85a14-162">Questo crea una struttura di directory virtuale che è possibile organizzare e attraversare come si farebbe un sistema di file tradizionali.</span><span class="sxs-lookup"><span data-stu-id="85a14-162">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="85a14-163">Si noti che la struttura di directory virtuale solo - solo le risorse disponibili nell'archiviazione Blob sono contenitori e BLOB.</span><span class="sxs-lookup"><span data-stu-id="85a14-163">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="85a14-164">Tuttavia, la libreria client di archiviazione offre un `CloudBlobDirectory` oggetto per fare riferimento a una directory virtuale e semplificare il processo d'uso di BLOB sono organizzati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="85a14-164">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="85a14-165">Ad esempio, si consideri il seguente set di BLOB in blocchi in un contenitore denominato `photos`:</span><span class="sxs-lookup"><span data-stu-id="85a14-165">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="85a14-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="85a14-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="85a14-167">Quando si chiama `ListBlobs` su un contenitore (come nell'esempio precedente), viene restituito un elenco gerarchico.</span><span class="sxs-lookup"><span data-stu-id="85a14-167">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="85a14-168">Se contiene entrambe `CloudBlobDirectory` e `CloudBlockBlob` oggetti, che rappresenta la directory e BLOB nel contenitore, rispettivamente, quindi l'output risulta sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-168">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="85a14-169">Facoltativamente, è possibile impostare il `UseFlatBlobListing` parametro del `ListBlobs` metodo `true`.</span><span class="sxs-lookup"><span data-stu-id="85a14-169">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="85a14-170">In questo caso, ogni blob nel contenitore viene restituito come un `CloudBlockBlob` oggetto.</span><span class="sxs-lookup"><span data-stu-id="85a14-170">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="85a14-171">La chiamata a `ListBlobs` per restituire un elenco semplice è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-171">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="85a14-172">Inoltre, a seconda del contenuto corrente del contenitore, i risultati simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-172">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="85a14-173">Scaricare BLOB</span><span class="sxs-lookup"><span data-stu-id="85a14-173">Download blobs</span></span>

<span data-ttu-id="85a14-174">Per scaricare i BLOB, recuperare innanzitutto un riferimento di blob e quindi chiamare il `DownloadToStream` metodo.</span><span class="sxs-lookup"><span data-stu-id="85a14-174">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="85a14-175">L'esempio seguente usa il `DownloadToStream` metodo per trasferire il contenuto del blob a un oggetto flusso che può quindi essere resa persistente in un file locale.</span><span class="sxs-lookup"><span data-stu-id="85a14-175">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="85a14-176">È inoltre possibile utilizzare il `DownloadToStream` metodo per scaricare il contenuto di un blob come una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="85a14-176">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="85a14-177">Eliminare i BLOB</span><span class="sxs-lookup"><span data-stu-id="85a14-177">Delete blobs</span></span>

<span data-ttu-id="85a14-178">Per eliminare un blob, innanzitutto ottenere un riferimento di blob e quindi chiamare il `Delete` metodo su di esso.</span><span class="sxs-lookup"><span data-stu-id="85a14-178">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="85a14-179">Elenco di BLOB di pagine in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="85a14-179">List blobs in pages asynchronously</span></span>

<span data-ttu-id="85a14-180">Elencare un numero elevato di BLOB, se si desidera controllare il numero di risultati che restituito in un'unica operazione di elenco, è possibile elencare i BLOB di pagine di risultati.</span><span class="sxs-lookup"><span data-stu-id="85a14-180">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="85a14-181">In questo esempio viene illustrato come restituire risultati in pagine in modo asincrono, in modo che non l'esecuzione viene bloccata durante l'attesa per restituire un ampio set di risultati.</span><span class="sxs-lookup"><span data-stu-id="85a14-181">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="85a14-182">Questo esempio viene illustrato un semplice elenco di blob, ma è anche possibile eseguire un elenco gerarchico, impostando il `useFlatBlobListing` parametro del `ListBlobsSegmentedAsync` metodo `false`.</span><span class="sxs-lookup"><span data-stu-id="85a14-182">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="85a14-183">L'esempio definisce un metodo asincrono, utilizzando un `async` blocco.</span><span class="sxs-lookup"><span data-stu-id="85a14-183">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="85a14-184">Il ``let!`` (parola chiave) sospende l'esecuzione del metodo di esempio fino al completamento dell'attività dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="85a14-184">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="85a14-185">È possibile utilizzare ora questa routine asincrona, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="85a14-185">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="85a14-186">È innanzitutto necessario caricare alcuni dati fittizi (con il file locale creato in precedenza in questa esercitazione).</span><span class="sxs-lookup"><span data-stu-id="85a14-186">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="85a14-187">A questo punto, chiamare la routine.</span><span class="sxs-lookup"><span data-stu-id="85a14-187">Now, call the routine.</span></span> <span data-ttu-id="85a14-188">Utilizzare ``Async.RunSynchronously`` per forzare l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="85a14-188">You use ``Async.RunSynchronously`` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="85a14-189">Scrittura in un blob di aggiunta</span><span class="sxs-lookup"><span data-stu-id="85a14-189">Writing to an append blob</span></span>

<span data-ttu-id="85a14-190">Un blob di aggiunta è ottimizzato per le operazioni di accodamento, ad esempio la registrazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-190">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="85a14-191">Come un blob in blocchi, un blob di aggiunta è costituito da blocchi, ma quando si aggiunge un nuovo blocco per un blob di aggiunta, vengono sempre aggiunte alla fine del blob.</span><span class="sxs-lookup"><span data-stu-id="85a14-191">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="85a14-192">È possibile aggiornare o eliminare un blocco esistente in un blob di aggiunta.</span><span class="sxs-lookup"><span data-stu-id="85a14-192">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="85a14-193">L'ID di blocco per un blob di aggiunta non vengono esposte come se fossero per un blob in blocchi.</span><span class="sxs-lookup"><span data-stu-id="85a14-193">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="85a14-194">Ogni blocco di un blob di aggiunta può avere dimensioni diverse, fino a un massimo di 4 MB, e un blob di aggiunta può includere un massimo di 50.000 blocchi.</span><span class="sxs-lookup"><span data-stu-id="85a14-194">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="85a14-195">Le dimensioni massime di un blob di aggiunta sono leggermente più 195 GB (4 MB X 50.000 blocchi).</span><span class="sxs-lookup"><span data-stu-id="85a14-195">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="85a14-196">Nell'esempio seguente crea un nuovo blob di aggiunta e aggiunge alcuni dati, simulazione di un'operazione di registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="85a14-196">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="85a14-197">Vedere [informazioni sui BLOB in blocchi, BLOB di pagine e BLOB, accodare](https://msdn.microsoft.com/library/azure/ee691964.aspx) per ulteriori informazioni sulle differenze tra i tre tipi di BLOB.</span><span class="sxs-lookup"><span data-stu-id="85a14-197">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="85a14-198">Accesso simultaneo</span><span class="sxs-lookup"><span data-stu-id="85a14-198">Concurrent access</span></span>

<span data-ttu-id="85a14-199">Per supportare l'accesso simultaneo a un blob da più client o più istanze di processo, è possibile utilizzare **eTag** o **lease**.</span><span class="sxs-lookup"><span data-stu-id="85a14-199">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="85a14-200">**ETag** -consente di rilevare che il blob o contenitore è stato modificato da un altro processo</span><span class="sxs-lookup"><span data-stu-id="85a14-200">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="85a14-201">**Lease** -consente di ottenere rinnovabile a vicenda, scrivere o eliminare l'accesso a un blob per un periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="85a14-201">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="85a14-202">Per ulteriori informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="85a14-202">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="85a14-203">Denominazione dei contenitori</span><span class="sxs-lookup"><span data-stu-id="85a14-203">Naming containers</span></span>

<span data-ttu-id="85a14-204">Ogni blob nell'archiviazione di Azure deve risiedere in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="85a14-204">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="85a14-205">Il contenitore costituisce parte del nome del blob.</span><span class="sxs-lookup"><span data-stu-id="85a14-205">The container forms part of the blob name.</span></span> <span data-ttu-id="85a14-206">Ad esempio, `mydata` è il nome del contenitore in questi blob URI di esempio:</span><span class="sxs-lookup"><span data-stu-id="85a14-206">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="85a14-207">Un nome di contenitore deve essere un nome DNS valido, conforme alle regole di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="85a14-207">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="85a14-208">Il nome del contenitore devono iniziare con una lettera o un numero e possono contenere solo lettere, numeri e trattini (-).</span><span class="sxs-lookup"><span data-stu-id="85a14-208">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="85a14-209">Ogni trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero. nei nomi dei contenitori non sono consentiti trattini consecutivi.</span><span class="sxs-lookup"><span data-stu-id="85a14-209">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="85a14-210">Tutte le lettere di un nome di contenitore devono essere minuscole.</span><span class="sxs-lookup"><span data-stu-id="85a14-210">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="85a14-211">Il nome del contenitore devono essere compresa tra 3 e 63 caratteri.</span><span class="sxs-lookup"><span data-stu-id="85a14-211">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="85a14-212">Si noti che il nome di un contenitore deve essere sempre lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="85a14-212">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="85a14-213">Se si include una lettera maiuscola in un nome di contenitore o in altro modo il contenitore di regole di denominazione, si potrebbe ricevere un errore 400 (richiesta non valida).</span><span class="sxs-lookup"><span data-stu-id="85a14-213">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="85a14-214">Gestione della sicurezza per i BLOB</span><span class="sxs-lookup"><span data-stu-id="85a14-214">Managing security for blobs</span></span>

<span data-ttu-id="85a14-215">Per impostazione predefinita, archiviazione di Azure i dati rimangono al sicuro limitando l'accesso al proprietario dell'account, che è in possesso delle chiavi di accesso account.</span><span class="sxs-lookup"><span data-stu-id="85a14-215">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="85a14-216">Quando è necessario condividere i dati blob nell'account di archiviazione, è importante eseguire questa operazione senza compromettere la protezione di chiavi di accesso account.</span><span class="sxs-lookup"><span data-stu-id="85a14-216">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="85a14-217">Inoltre, è possibile crittografare i dati blob per assicurarsi che sia sicuro accedere in rete e archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="85a14-217">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="85a14-218">Controllo dell'accesso ai dati blob</span><span class="sxs-lookup"><span data-stu-id="85a14-218">Controlling access to blob data</span></span>

<span data-ttu-id="85a14-219">Per impostazione predefinita, i dati blob nell'account di archiviazione sono accessibili solo al proprietario dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="85a14-219">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="85a14-220">Autenticazione delle richieste nel servizio di archiviazione Blob richiede la chiave di account di accesso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="85a14-220">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="85a14-221">Tuttavia, è consigliabile rendere determinati dati blob disponibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="85a14-221">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="85a14-222">Per informazioni dettagliate su come controllare l'accesso all'archiviazione blob, vedere [la Guida di .NET per la sezione di archiviazione blob sul controllo di accesso](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span><span class="sxs-lookup"><span data-stu-id="85a14-222">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="85a14-223">La crittografia dei dati blob</span><span class="sxs-lookup"><span data-stu-id="85a14-223">Encrypting blob data</span></span>

<span data-ttu-id="85a14-224">Archiviazione di Azure supporta la crittografia dei dati blob nel client e nel server.</span><span class="sxs-lookup"><span data-stu-id="85a14-224">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="85a14-225">Per informazioni dettagliate sulla crittografia dei dati blob, vedere [la Guida di .NET per la sezione di archiviazione blob su crittografia](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span><span class="sxs-lookup"><span data-stu-id="85a14-225">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="85a14-226">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="85a14-226">Next steps</span></span>

<span data-ttu-id="85a14-227">Ora che si è appreso le nozioni di base dell'archiviazione Blob, vedere i collegamenti seguenti per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="85a14-227">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="85a14-228">Strumenti</span><span class="sxs-lookup"><span data-stu-id="85a14-228">Tools</span></span>
- <span data-ttu-id="85a14-229">[F # AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An i Provider di tipi F # che può essere usato per esplorare le risorse Blob, tabella e coda di archiviazione di Azure e applicare facilmente operazioni CRUD su di essi.</span><span class="sxs-lookup"><span data-stu-id="85a14-229">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="85a14-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) F # un'API per l'utilizzo del servizio di archiviazione tabelle di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="85a14-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="85a14-231">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) è un'applicazione autonoma gratuita, da Microsoft che consente di utilizzare visivamente i dati di archiviazione di Azure in Windows, OS X e Linux.</span><span class="sxs-lookup"><span data-stu-id="85a14-231">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="85a14-232">Riferimento all'archiviazione BLOB</span><span class="sxs-lookup"><span data-stu-id="85a14-232">Blob storage reference</span></span>

- [<span data-ttu-id="85a14-233">API di archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="85a14-233">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="85a14-234">Riferimento all'API REST di servizi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="85a14-234">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="85a14-235">Guide correlate</span><span class="sxs-lookup"><span data-stu-id="85a14-235">Related guides</span></span>

- [<span data-ttu-id="85a14-236">Introduzione all'archiviazione Blob di Azure in c#</span><span class="sxs-lookup"><span data-stu-id="85a14-236">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/documentation/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="85a14-237">Trasferimento dati con l'utilità della riga di comando di AzCopy in Windows</span><span class="sxs-lookup"><span data-stu-id="85a14-237">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="85a14-238">Trasferimento dati con l'utilità della riga di comando di AzCopy su Linux</span><span class="sxs-lookup"><span data-stu-id="85a14-238">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="85a14-239">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="85a14-239">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="85a14-240">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="85a14-240">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
