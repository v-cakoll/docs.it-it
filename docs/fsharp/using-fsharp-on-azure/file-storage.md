---
title: Iniziare a usare archiviazione File di AzureF#
description: Store i dati dei file nel cloud con archiviazione File di Azure e montare la condivisione file nel cloud da una macchina virtuale di Azure (VM) o da un'applicazione in locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969596"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="134e2-103">Introduzione all'archiviazione File di Azure con F\#</span><span class="sxs-lookup"><span data-stu-id="134e2-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="134e2-104">Archiviazione File di Azure è un servizio che offre condivisioni file nel cloud usando lo standard [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="134e2-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="134e2-105">Sono supportati sia SMB 2.1 che SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="134e2-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="134e2-106">Con archiviazione File di Azure, è possibile eseguire la migrazione delle applicazioni legacy basate su condivisioni file in Azure velocemente e senza costose riscritture.</span><span class="sxs-lookup"><span data-stu-id="134e2-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="134e2-107">Le applicazioni in esecuzione in macchine virtuali di Azure o servizi cloud o da client locali possono montare una condivisione file nel cloud, esattamente come un'applicazione desktop Monta una tipica condivisione SMB.</span><span class="sxs-lookup"><span data-stu-id="134e2-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="134e2-108">Qualsiasi numero di componenti dell'applicazione può quindi montare e accedere contemporaneamente alla condivisione di archiviazione File.</span><span class="sxs-lookup"><span data-stu-id="134e2-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="134e2-109">Per una panoramica concettuale dell'archiviazione file, vedi [la Guida di .NET per archiviazione file](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="134e2-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="134e2-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="134e2-110">Prerequisites</span></span>

<span data-ttu-id="134e2-111">Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="134e2-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="134e2-112">È necessario anche la chiave di accesso di archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="134e2-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="134e2-113">Creare un F# creare uno Script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="134e2-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="134e2-114">Gli esempi in questo articolo possono essere utilizzati in un F# dell'applicazione o un oggetto F# dello script.</span><span class="sxs-lookup"><span data-stu-id="134e2-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="134e2-115">Per creare un F# creare uno script, creare un file con il `.fsx` estensione, ad esempio `files.fsx`, nella F# ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="134e2-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="134e2-116">Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva.</span><span class="sxs-lookup"><span data-stu-id="134e2-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="134e2-117">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="134e2-117">Add namespace declarations</span></span>

<span data-ttu-id="134e2-118">Aggiungere il codice seguente `open` istruzioni all'inizio del `files.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="134e2-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="134e2-119">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="134e2-119">Get your connection string</span></span>

<span data-ttu-id="134e2-120">Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="134e2-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="134e2-121">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="134e2-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="134e2-122">Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="134e2-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="134e2-123">Si tratta tuttavia **sconsigliato** progetti per il real.</span><span class="sxs-lookup"><span data-stu-id="134e2-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="134e2-124">La chiave dell'account è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="134e2-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="134e2-125">Prestare sempre attenzione proteggere la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="134e2-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="134e2-126">Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="134e2-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="134e2-127">È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="134e2-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="134e2-128">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="134e2-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="134e2-129">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="134e2-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="134e2-130">Usando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="134e2-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="134e2-131">È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="134e2-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="134e2-132">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="134e2-132">Parse the connection string</span></span>

<span data-ttu-id="134e2-133">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="134e2-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="134e2-134">Verrà restituito un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="134e2-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="134e2-135">Creare il client del servizio File</span><span class="sxs-lookup"><span data-stu-id="134e2-135">Create the File service client</span></span>

<span data-ttu-id="134e2-136">Il `CloudFileClient` tipo consente di utilizzare a livello di programmazione i file archiviati in archiviazione File.</span><span class="sxs-lookup"><span data-stu-id="134e2-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="134e2-137">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="134e2-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="134e2-138">A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione File.</span><span class="sxs-lookup"><span data-stu-id="134e2-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="134e2-139">Creare una condivisione file</span><span class="sxs-lookup"><span data-stu-id="134e2-139">Create a file share</span></span>

<span data-ttu-id="134e2-140">In questo esempio viene illustrato come creare una condivisione file se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="134e2-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="134e2-141">Creare una directory radice e una sottodirectory</span><span class="sxs-lookup"><span data-stu-id="134e2-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="134e2-142">In questo caso, si ottiene la directory radice e ottenere una sottodirectory della radice.</span><span class="sxs-lookup"><span data-stu-id="134e2-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="134e2-143">Creare entrambi se non sono già presenti.</span><span class="sxs-lookup"><span data-stu-id="134e2-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="134e2-144">Caricare il testo come un file</span><span class="sxs-lookup"><span data-stu-id="134e2-144">Upload text as a file</span></span>

<span data-ttu-id="134e2-145">In questo esempio viene illustrato come caricare un file di testo.</span><span class="sxs-lookup"><span data-stu-id="134e2-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="134e2-146">Scaricare un file in una copia locale del file</span><span class="sxs-lookup"><span data-stu-id="134e2-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="134e2-147">Qui è scaricare il file appena creato, l'accodamento del contenuto in un file locale.</span><span class="sxs-lookup"><span data-stu-id="134e2-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="134e2-148">Impostare le dimensioni massime per una condivisione file</span><span class="sxs-lookup"><span data-stu-id="134e2-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="134e2-149">L'esempio seguente viene illustrato come controllare l'utilizzo corrente per una condivisione e come impostare la quota per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="134e2-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="134e2-150">`FetchAttributes` deve essere chiamato per popolare una condivisione `Properties`, e `SetProperties` per propagare le modifiche locali con archiviazione File di Azure.</span><span class="sxs-lookup"><span data-stu-id="134e2-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="134e2-151">Generare una firma di accesso condiviso per un file o condivisione file</span><span class="sxs-lookup"><span data-stu-id="134e2-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="134e2-152">È possibile generare una firma di accesso condiviso (SAS) per una condivisione file o per un singolo file.</span><span class="sxs-lookup"><span data-stu-id="134e2-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="134e2-153">È anche possibile creare un criterio di accesso condiviso in una condivisione file per gestire le firme di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="134e2-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="134e2-154">È consigliabile creare un criterio di accesso condiviso, in quanto forniscono un modo per revocare la firma di accesso condiviso se si deve essere compromesso.</span><span class="sxs-lookup"><span data-stu-id="134e2-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="134e2-155">In questo caso, si crea un oggetto condiviso in una condivisione di criteri di accesso e quindi usare tale criterio per fornire i vincoli per una firma di accesso condiviso in un file nella condivisione.</span><span class="sxs-lookup"><span data-stu-id="134e2-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="134e2-156">Per altre informazioni sulla creazione e uso delle firme di accesso condiviso, vedere [uso di firme di accesso condiviso (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) e [creare e usare una firma di accesso condiviso con l'archiviazione Blob](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="134e2-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="134e2-157">Copiare i file</span><span class="sxs-lookup"><span data-stu-id="134e2-157">Copy files</span></span>

<span data-ttu-id="134e2-158">È possibile copiare un file in un altro file o in un blob o un blob in un file.</span><span class="sxs-lookup"><span data-stu-id="134e2-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="134e2-159">Se si copia un blob in un file o un file in un blob, si *necessario* usare una firma di accesso condiviso (SAS) per autenticare l'oggetto di origine, anche se si copia nello stesso account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="134e2-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="134e2-160">Copiare un file in un altro file</span><span class="sxs-lookup"><span data-stu-id="134e2-160">Copy a file to another file</span></span>

<span data-ttu-id="134e2-161">In questo caso, si copia un file in un altro file nella stessa condivisione.</span><span class="sxs-lookup"><span data-stu-id="134e2-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="134e2-162">Poiché questa operazione esegue la copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.</span><span class="sxs-lookup"><span data-stu-id="134e2-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="134e2-163">Copiare un file in un blob</span><span class="sxs-lookup"><span data-stu-id="134e2-163">Copy a file to a blob</span></span>

<span data-ttu-id="134e2-164">In questo caso, si crea un file e copiarlo in un blob nello stesso account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="134e2-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="134e2-165">Si crea una firma di accesso condiviso per il file di origine, il servizio Usa per autenticare l'accesso al file di origine durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="134e2-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="134e2-166">È possibile copiare un blob in un file nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="134e2-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="134e2-167">Se l'oggetto di origine è un blob, creare una firma di accesso condiviso per autenticare l'accesso al blob durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="134e2-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="134e2-168">Risoluzione dei problemi di archiviazione di File con le metriche</span><span class="sxs-lookup"><span data-stu-id="134e2-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="134e2-169">Analitica di archiviazione di Azure supporta le metriche per archiviazione File.</span><span class="sxs-lookup"><span data-stu-id="134e2-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="134e2-170">Con i dati delle metriche, è possibile tenere traccia delle richieste e diagnosticare i problemi.</span><span class="sxs-lookup"><span data-stu-id="134e2-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="134e2-171">È possibile abilitare le metriche per archiviazione File dal [portale di Azure](https://portal.azure.com), oppure è possibile farlo da F# simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="134e2-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="134e2-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="134e2-172">Next steps</span></span>

<span data-ttu-id="134e2-173">Vedere i collegamenti seguenti per altre informazioni sull'archiviazione File di Azure.</span><span class="sxs-lookup"><span data-stu-id="134e2-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="134e2-174">Articoli concettuali e video</span><span class="sxs-lookup"><span data-stu-id="134e2-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="134e2-175">Archiviazione file di Azure: file di SMB nel cloud del sistema per Windows e Linux</span><span class="sxs-lookup"><span data-stu-id="134e2-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="134e2-176">Come usare archiviazione File di Azure con Linux</span><span class="sxs-lookup"><span data-stu-id="134e2-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="134e2-177">Supporto degli strumenti per archiviazione File</span><span class="sxs-lookup"><span data-stu-id="134e2-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="134e2-178">Uso di Azure PowerShell con archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="134e2-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="134e2-179">Come usare AzCopy con archiviazione di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="134e2-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="134e2-180">Tramite la CLI di Azure con archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="134e2-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="134e2-181">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="134e2-181">Reference</span></span>

- [<span data-ttu-id="134e2-182">Storage Client Library per .NET</span><span class="sxs-lookup"><span data-stu-id="134e2-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="134e2-183">Riferimento API REST del servizio file</span><span class="sxs-lookup"><span data-stu-id="134e2-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="134e2-184">Post di blog</span><span class="sxs-lookup"><span data-stu-id="134e2-184">Blog posts</span></span>

- [<span data-ttu-id="134e2-185">Archiviazione File di Azure è ora disponibile a livello generale</span><span class="sxs-lookup"><span data-stu-id="134e2-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="134e2-186">Inside Azure File Storage</span><span class="sxs-lookup"><span data-stu-id="134e2-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="134e2-187">Introduzione a servizio File di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="134e2-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="134e2-188">Mantenimento delle connessioni ai file di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="134e2-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
