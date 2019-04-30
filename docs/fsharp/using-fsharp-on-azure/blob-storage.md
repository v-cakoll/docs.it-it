---
title: Iniziare a usare archiviazione Blob di AzureF#
description: Store dati non strutturati nel cloud con archiviazione Blob di Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 62178edf22ad48d0388f34488b68d135068d50a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982514"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="b8868-103">Introduzione all'archiviazione Blob di Azure con F\#</span><span class="sxs-lookup"><span data-stu-id="b8868-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="b8868-104">Archiviazione BLOB di Azure è un servizio che archivia dati non strutturati nel cloud come oggetti/BLOB.</span><span class="sxs-lookup"><span data-stu-id="b8868-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="b8868-105">Archiviazione BLOB può archiviare qualsiasi tipo di dati di testo o binari, ad esempio un documento, un file multimediale o il programma di installazione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="b8868-106">Il servizio Archiviazione BLOB è detto anche archiviazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b8868-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="b8868-107">Questo articolo illustra come eseguire attività comuni usando l'archiviazione Blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="b8868-108">Gli esempi sono scritti usando F# usando la libreria Client di archiviazione di Azure per .NET.</span><span class="sxs-lookup"><span data-stu-id="b8868-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="b8868-109">Argomenti trattati includono come caricare, elencare, scaricare ed eliminare i BLOB.</span><span class="sxs-lookup"><span data-stu-id="b8868-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="b8868-110">Per una panoramica concettuale dell'archiviazione blob, vedere [la Guida di .NET per l'archiviazione blob](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="b8868-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8868-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b8868-111">Prerequisites</span></span>

<span data-ttu-id="b8868-112">Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b8868-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="b8868-113">Occorre anche la chiave di accesso di archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="b8868-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b8868-114">Creare un F# creare uno Script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="b8868-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b8868-115">Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script.</span><span class="sxs-lookup"><span data-stu-id="b8868-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b8868-116">Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `blobs.fsx`, nella F# ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b8868-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b8868-117">Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` e `Microsoft.WindowsAzure.ConfigurationManager` pacchetti e riferimento `WindowsAzure.Storage.dll` e`Microsoft.WindowsAzure.Configuration.dll` nel script utilizzando un `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="b8868-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b8868-118">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="b8868-118">Add namespace declarations</span></span>

<span data-ttu-id="b8868-119">Aggiungere il codice seguente `open` istruzioni all'inizio del `blobs.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="b8868-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b8868-120">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="b8868-120">Get your connection string</span></span>

<span data-ttu-id="b8868-121">Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b8868-122">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="b8868-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b8868-123">Per l'esercitazione, immettere la stringa di connessione nello script, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b8868-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="b8868-124">Si tratta tuttavia **sconsigliato** progetti per il real.</span><span class="sxs-lookup"><span data-stu-id="b8868-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b8868-125">La chiave dell'account è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b8868-126">Prestare sempre attenzione proteggere la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="b8868-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b8868-127">Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="b8868-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b8868-128">È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="b8868-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b8868-129">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b8868-130">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="b8868-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="b8868-131">Usando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b8868-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b8868-132">È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="b8868-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b8868-133">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="b8868-133">Parse the connection string</span></span>

<span data-ttu-id="b8868-134">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="b8868-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="b8868-135">Restituisce un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="b8868-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="b8868-136">Creare alcuni dati fittizi locali</span><span class="sxs-lookup"><span data-stu-id="b8868-136">Create some local dummy data</span></span>

<span data-ttu-id="b8868-137">Prima di iniziare, creare alcuni dati fittizi locali nella directory dello script.</span><span class="sxs-lookup"><span data-stu-id="b8868-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="b8868-138">In un secondo momento è caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="b8868-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="b8868-139">Creare il client del servizio Blob</span><span class="sxs-lookup"><span data-stu-id="b8868-139">Create the Blob service client</span></span>

<span data-ttu-id="b8868-140">Il `CloudBlobClient` tipo consente di recuperare contenitori e BLOB archiviati nell'archivio Blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="b8868-141">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="b8868-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="b8868-142">A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archiviazione Blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="b8868-143">Creare un contenitore</span><span class="sxs-lookup"><span data-stu-id="b8868-143">Create a container</span></span>

<span data-ttu-id="b8868-144">In questo esempio viene illustrato come creare un contenitore, se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="b8868-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="b8868-145">Per impostazione predefinita, il nuovo contenitore è privato, vale a dire che è necessario specificare la chiave di accesso di archiviazione per scaricare BLOB da questo contenitore.</span><span class="sxs-lookup"><span data-stu-id="b8868-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="b8868-146">Se si desidera rendere disponibili per tutti i file all'interno del contenitore, è possibile impostare il contenitore come pubblico utilizzando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b8868-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="b8868-147">Chiunque su Internet può visualizzare i BLOB in un contenitore pubblico, ma è possibile modificarli o eliminarli solo se disponibile la chiave di accesso account appropriato o una firma di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="b8868-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="b8868-148">Caricare un blob in un contenitore</span><span class="sxs-lookup"><span data-stu-id="b8868-148">Upload a blob into a container</span></span>

<span data-ttu-id="b8868-149">Archiviazione Blob di Azure supporta BLOB in blocchi e BLOB di pagine.</span><span class="sxs-lookup"><span data-stu-id="b8868-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="b8868-150">Nella maggior parte dei casi, un blob in blocchi è il tipo consigliato da usare.</span><span class="sxs-lookup"><span data-stu-id="b8868-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="b8868-151">Per caricare un file in un blob in blocchi, ottenere un riferimento al contenitore e utilizzarlo per ottenere un riferimento al blob di blocco.</span><span class="sxs-lookup"><span data-stu-id="b8868-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="b8868-152">Dopo aver creato un riferimento al blob, è possibile caricarvi qualsiasi flusso di dati a esso chiamando il `UploadFromFile` (metodo).</span><span class="sxs-lookup"><span data-stu-id="b8868-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="b8868-153">Questa operazione crea il blob se non è stata precedentemente esiste o di sovrascriverlo se esiste.</span><span class="sxs-lookup"><span data-stu-id="b8868-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="b8868-154">Elencare i BLOB in un contenitore</span><span class="sxs-lookup"><span data-stu-id="b8868-154">List the blobs in a container</span></span>

<span data-ttu-id="b8868-155">Per elencare i BLOB in un contenitore, ottenere prima un riferimento al contenitore.</span><span class="sxs-lookup"><span data-stu-id="b8868-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="b8868-156">È quindi possibile usare il contenitore `ListBlobs` metodo per recuperare i BLOB e/o le directory in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="b8868-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="b8868-157">Per accedere all'insieme avanzato di proprietà e metodi per un `IListBlobItem`, è necessario eseguirne il cast a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b8868-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="b8868-158">Se il tipo è sconosciuto, è possibile usare un controllo del tipo per determinare quale eseguire il cast a.</span><span class="sxs-lookup"><span data-stu-id="b8868-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="b8868-159">Il codice seguente viene illustrato come recuperare e visualizzare l'URI di ogni elemento di `mydata` contenitore:</span><span class="sxs-lookup"><span data-stu-id="b8868-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="b8868-160">È anche possibile BLOB name con le informazioni sul percorso nei nomi.</span><span class="sxs-lookup"><span data-stu-id="b8868-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="b8868-161">In questo modo viene creata una struttura di directory virtuale che è possibile organizzare e attraversare come un file system tradizionale.</span><span class="sxs-lookup"><span data-stu-id="b8868-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="b8868-162">Si noti che la struttura di directory è solo virtuale, le uniche risorse disponibili nell'archiviazione Blob sono contenitori e BLOB.</span><span class="sxs-lookup"><span data-stu-id="b8868-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="b8868-163">Tuttavia, la libreria client di archiviazione offre un `CloudBlobDirectory` oggetto per fare riferimento a una directory virtuale e semplificare il processo di utilizzo dei blob organizzati in questo modo.</span><span class="sxs-lookup"><span data-stu-id="b8868-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="b8868-164">Ad esempio, si consideri il seguente set di BLOB in blocchi in un contenitore denominato `photos`:</span><span class="sxs-lookup"><span data-stu-id="b8868-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="b8868-165">*photo1.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-165">*photo1.jpg*\\</span></span>
<span data-ttu-id="b8868-166">*2015/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-166">*2015/architecture/description.txt*\\</span></span>
<span data-ttu-id="b8868-167">*2015/architecture/photo3.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-167">*2015/architecture/photo3.jpg*\\</span></span>
<span data-ttu-id="b8868-168">*2015/architecture/photo4.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-168">*2015/architecture/photo4.jpg*\\</span></span>
<span data-ttu-id="b8868-169">*2016/architecture/photo5.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-169">*2016/architecture/photo5.jpg*\\</span></span>
<span data-ttu-id="b8868-170">*2016/architecture/photo6.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-170">*2016/architecture/photo6.jpg*\\</span></span>
<span data-ttu-id="b8868-171">*2016/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-171">*2016/architecture/description.txt*\\</span></span>
<span data-ttu-id="b8868-172">*2016/photo7.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="b8868-172">*2016/photo7.jpg*\\</span></span>

<span data-ttu-id="b8868-173">Quando si chiama `ListBlobs` su un contenitore (come nell'esempio precedente), viene restituito un elenco gerarchico.</span><span class="sxs-lookup"><span data-stu-id="b8868-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="b8868-174">Se contiene entrambe `CloudBlobDirectory` e `CloudBlockBlob` oggetti, che rappresenta la directory e i BLOB nel contenitore, rispettivamente, quindi l'output risultante è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b8868-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="b8868-175">Facoltativamente, è possibile impostare il `UseFlatBlobListing` parametro del `ListBlobs` metodo `true`.</span><span class="sxs-lookup"><span data-stu-id="b8868-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="b8868-176">In questo caso, tutti i blob nel contenitore viene restituito come un `CloudBlockBlob` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b8868-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="b8868-177">La chiamata a `ListBlobs` per restituire un elenco semplice si presenta come segue:</span><span class="sxs-lookup"><span data-stu-id="b8868-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="b8868-178">e, in base al contenuto corrente del contenitore, i risultati un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b8868-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="b8868-179">Scaricare i BLOB</span><span class="sxs-lookup"><span data-stu-id="b8868-179">Download blobs</span></span>

<span data-ttu-id="b8868-180">Per scaricare BLOB, recuperare prima un riferimento al blob e quindi chiamare il `DownloadToStream` (metodo).</span><span class="sxs-lookup"><span data-stu-id="b8868-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="b8868-181">L'esempio seguente usa il `DownloadToStream` metodo per trasferire il contenuto del blob a un oggetto stream che è quindi possibile rendere persistente in un file locale.</span><span class="sxs-lookup"><span data-stu-id="b8868-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="b8868-182">È anche possibile usare il `DownloadToStream` metodo per scaricare il contenuto di un blob come stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="b8868-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="b8868-183">Eliminare i BLOB</span><span class="sxs-lookup"><span data-stu-id="b8868-183">Delete blobs</span></span>

<span data-ttu-id="b8868-184">Per eliminare un blob, ottenere prima un riferimento al blob e quindi chiamare il `Delete` metodo su di esso.</span><span class="sxs-lookup"><span data-stu-id="b8868-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="b8868-185">Elencare i BLOB di pagine in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="b8868-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="b8868-186">Se si sta elencando un numero elevato di BLOB o si desidera controllare il numero di risultati restituiti in un'operazione di elenco, è possibile elencare i BLOB di pagine dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b8868-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="b8868-187">In questo esempio viene illustrato come restituire i risultati nelle pagine in modo asincrono, in modo che l'esecuzione non venga bloccata durante l'attesa della restituzione di un ampio set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b8868-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="b8868-188">In questo esempio mostra un elenco di blob lineare, ma è anche possibile eseguire un elenco gerarchico impostando il `useFlatBlobListing` parametro del `ListBlobsSegmentedAsync` metodo `false`.</span><span class="sxs-lookup"><span data-stu-id="b8868-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="b8868-189">L'esempio definisce un metodo asincrono, tramite un `async` blocco.</span><span class="sxs-lookup"><span data-stu-id="b8868-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="b8868-190">Il ``let!`` parola chiave sospende l'esecuzione del metodo di esempio fino al completamento dell'attività di elenco.</span><span class="sxs-lookup"><span data-stu-id="b8868-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="b8868-191">È ora possibile usare questa routine asincrona come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b8868-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="b8868-192">È innanzitutto necessario caricare alcuni dati fittizi (tramite il file locale creato in precedenza in questa esercitazione).</span><span class="sxs-lookup"><span data-stu-id="b8868-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="b8868-193">A questo punto, chiamare la routine.</span><span class="sxs-lookup"><span data-stu-id="b8868-193">Now, call the routine.</span></span> <span data-ttu-id="b8868-194">Si utilizza `Async.RunSynchronously` per forzare l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b8868-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="b8868-195">La scrittura in un blob di Accodamento</span><span class="sxs-lookup"><span data-stu-id="b8868-195">Writing to an append blob</span></span>

<span data-ttu-id="b8868-196">Un blob di accodamento è ottimizzato per operazioni di accodamento, ad esempio la registrazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="b8868-197">Come un blob in blocchi, un blob di accodamento è costituito da blocchi, ma quando si aggiunge un nuovo blocco per un blob di accodamento, viene aggiunto sempre alla fine del blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="b8868-198">È possibile aggiornare o eliminare un blocco esistente in un blob di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="b8868-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="b8868-199">L'ID del blocco per un blob di accodamento non sono esposti come lo sono per un blob in blocchi.</span><span class="sxs-lookup"><span data-stu-id="b8868-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="b8868-200">Ogni blocco in un blob di accodamento può avere dimensioni diverse, con un massimo di 4 MB, e un blob di accodamento può includere un massimo di 50.000 blocchi.</span><span class="sxs-lookup"><span data-stu-id="b8868-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="b8868-201">Le dimensioni massime di un blob di accodamento sono pertanto leggermente superiore a 195 GB (4 MB X 50.000 blocchi).</span><span class="sxs-lookup"><span data-stu-id="b8868-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="b8868-202">Nell'esempio seguente crea un nuovo blob di accodamento e aggiunge alcuni dati, simulazione di un'operazione di registrazione semplice.</span><span class="sxs-lookup"><span data-stu-id="b8868-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="b8868-203">Visualizzare [informazioni sui BLOB in blocchi, BLOB di pagine e BLOB di Accodamento](https://msdn.microsoft.com/library/azure/ee691964.aspx) per altre informazioni sulle differenze tra i tre tipi di BLOB.</span><span class="sxs-lookup"><span data-stu-id="b8868-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="b8868-204">Accesso simultaneo</span><span class="sxs-lookup"><span data-stu-id="b8868-204">Concurrent access</span></span>

<span data-ttu-id="b8868-205">Per supportare l'accesso simultaneo a un blob da più client o più istanze di processo, è possibile usare **ETags** oppure **lease**.</span><span class="sxs-lookup"><span data-stu-id="b8868-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="b8868-206">**ETag** -fornisce un modo per rilevare che il blob o contenitore è stato modificato da un altro processo</span><span class="sxs-lookup"><span data-stu-id="b8868-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="b8868-207">**Lease** -fornisce un modo per ottenere esclusivo, rinnovabile, scrivere o eliminare l'accesso a un blob per un periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="b8868-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="b8868-208">Per altre informazioni, vedere [gestione della concorrenza in archiviazione di Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="b8868-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="b8868-209">Denominazione dei contenitori</span><span class="sxs-lookup"><span data-stu-id="b8868-209">Naming containers</span></span>

<span data-ttu-id="b8868-210">Ogni blob in archiviazione di Azure deve risiedere in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="b8868-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="b8868-211">Il contenitore fa parte del nome del blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-211">The container forms part of the blob name.</span></span> <span data-ttu-id="b8868-212">Ad esempio, `mydata` è il nome del contenitore in questi URI del blob di esempio:</span><span class="sxs-lookup"><span data-stu-id="b8868-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="b8868-213">Nome del contenitore deve essere un nome DNS valido, conforme alle regole di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="b8868-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="b8868-214">I nomi dei contenitori devono iniziare con una lettera o un numero e può contenere solo lettere, numeri e il carattere trattino (-).</span><span class="sxs-lookup"><span data-stu-id="b8868-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="b8868-215">Ogni trattino (-) deve essere immediatamente preceduto e seguito da una lettera o un numero. nei nomi dei contenitori non sono consentiti trattini consecutivi.</span><span class="sxs-lookup"><span data-stu-id="b8868-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="b8868-216">Tutte le lettere di un nome di contenitore devono essere minuscole.</span><span class="sxs-lookup"><span data-stu-id="b8868-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="b8868-217">I nomi dei contenitori deve essere compresa tra 3 e 63 caratteri.</span><span class="sxs-lookup"><span data-stu-id="b8868-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="b8868-218">Si noti che il nome di un contenitore deve sempre essere minuscolo.</span><span class="sxs-lookup"><span data-stu-id="b8868-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="b8868-219">Se si include una lettera maiuscola nel nome del contenitore o altrimenti viola le regole di denominazione del contenitore, si potrebbe ricevere un errore 400 (richiesta non valida).</span><span class="sxs-lookup"><span data-stu-id="b8868-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="b8868-220">Gestione della sicurezza per i BLOB</span><span class="sxs-lookup"><span data-stu-id="b8868-220">Managing security for blobs</span></span>

<span data-ttu-id="b8868-221">Per impostazione predefinita, archiviazione di Azure protegge i dati, limitando l'accesso al proprietario dell'account, che possiede le chiavi dell'account l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b8868-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="b8868-222">Quando è necessario condividere dati blob nell'account di archiviazione, è importante farlo senza compromettere la protezione delle chiavi di accesso dell'account.</span><span class="sxs-lookup"><span data-stu-id="b8868-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="b8868-223">Inoltre, è possibile crittografare i dati blob per assicurarsi che sia sicuro accedere in rete e in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="b8868-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="b8868-224">Controllo dell'accesso ai dati blob</span><span class="sxs-lookup"><span data-stu-id="b8868-224">Controlling access to blob data</span></span>

<span data-ttu-id="b8868-225">Per impostazione predefinita, i dati blob nell'account di archiviazione sono accessibili solo al proprietario dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b8868-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="b8868-226">Autenticare le richieste all'archiviazione Blob richiede la chiave di accesso di account per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b8868-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="b8868-227">Tuttavia, si potrebbe voler rendere disponibile ad altri utenti determinati dati blob.</span><span class="sxs-lookup"><span data-stu-id="b8868-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="b8868-228">La crittografia dei dati blob</span><span class="sxs-lookup"><span data-stu-id="b8868-228">Encrypting blob data</span></span>

<span data-ttu-id="b8868-229">Archiviazione di Azure supporta la crittografia dei dati blob sia nel client e nel server.</span><span class="sxs-lookup"><span data-stu-id="b8868-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8868-230">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b8868-230">Next steps</span></span>

<span data-ttu-id="b8868-231">A questo punto, dopo aver appreso le nozioni di base dell'archiviazione Blob, visitare i collegamenti seguenti per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b8868-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="b8868-232">Strumenti</span><span class="sxs-lookup"><span data-stu-id="b8868-232">Tools</span></span>

- <span data-ttu-id="b8868-233">[F#AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span><span class="sxs-lookup"><span data-stu-id="b8868-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span></span>
<span data-ttu-id="b8868-234">Un F# Provider di tipi che può essere usato per esplorare le risorse Blob, tabelle e archiviazione code di Azure e applicare facilmente operazioni CRUD su di essi.</span><span class="sxs-lookup"><span data-stu-id="b8868-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="b8868-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span><span class="sxs-lookup"><span data-stu-id="b8868-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span></span>
<span data-ttu-id="b8868-236">Un F# API per l'uso del servizio di archiviazione tabelle di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b8868-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="b8868-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span><span class="sxs-lookup"><span data-stu-id="b8868-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span></span>
<span data-ttu-id="b8868-238">Un'app autonoma gratuita di Microsoft che consente di rappresentare facilmente dati di archiviazione di Azure in Windows, OS X e Linux.</span><span class="sxs-lookup"><span data-stu-id="b8868-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="b8868-239">Riferimento all'archiviazione BLOB</span><span class="sxs-lookup"><span data-stu-id="b8868-239">Blob storage reference</span></span>

- [<span data-ttu-id="b8868-240">API di archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="b8868-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="b8868-241">Riferimento all'API REST dei servizi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="b8868-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="b8868-242">Guide correlate</span><span class="sxs-lookup"><span data-stu-id="b8868-242">Related guides</span></span>

- [<span data-ttu-id="b8868-243">Introduzione all'archiviazione Blob di Azure nel linguaggio c#</span><span class="sxs-lookup"><span data-stu-id="b8868-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="b8868-244">Trasferire dati con l'utilità della riga di comando di AzCopy in Windows</span><span class="sxs-lookup"><span data-stu-id="b8868-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="b8868-245">Trasferire dati con l'utilità della riga di comando di AzCopy in Linux</span><span class="sxs-lookup"><span data-stu-id="b8868-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="b8868-246">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="b8868-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="b8868-247">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="b8868-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="b8868-248">Avvio rapido: Usare .NET per creare un blob in archiviazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="b8868-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
