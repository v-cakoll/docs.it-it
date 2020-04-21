---
title: Introduzione all'archiviazione file di Azure con F#
description: Archiviare i dati dei file nel cloud con Archiviazione file di Azure e montare la condivisione di file nel cloud da una macchina virtuale Azure (VM) o da un'applicazione locale che esegue Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 1b38ee53f2f73f7b7f4ee12f712f487cb726d41e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739599"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="fa42d-103">Introduzione all'archiviazione dei file di Azure tramite FGet started with Azure File storage using F\#</span><span class="sxs-lookup"><span data-stu-id="fa42d-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="fa42d-104">Archiviazione file di Azure offre condivisioni file nel cloud usando il [protocollo Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)standard.</span><span class="sxs-lookup"><span data-stu-id="fa42d-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="fa42d-105">Sono supportati sia SMB 2.1 che SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="fa42d-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="fa42d-106">Con Archiviazione file di Azure si può eseguire la migrazione ad Azure delle applicazioni legacy basate su condivisioni file velocemente e senza costose riscritture.</span><span class="sxs-lookup"><span data-stu-id="fa42d-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="fa42d-107">Le applicazioni in esecuzione in macchine virtuali di Azure o in servizi cloud oppure in client locali possono montare una condivisione file nel cloud, esattamente come un'applicazione desktop monta una tipica condivisione SMB.</span><span class="sxs-lookup"><span data-stu-id="fa42d-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="fa42d-108">Non ci sono limiti per i componenti delle applicazioni che possono montare e accedere contemporaneamente alla condivisione di archiviazione file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="fa42d-109">Per una panoramica concettuale dell'archiviazione dei file, vedere [la guida .NET per l'archiviazione dei file](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="fa42d-109">For a conceptual overview of file storage, see [the .NET guide for file storage](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa42d-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fa42d-110">Prerequisites</span></span>

<span data-ttu-id="fa42d-111">Per usare questa guida, è innanzitutto necessario creare un account di archiviazione di [Azure.To](https://docs.microsoft.com/azure/storage/storage-create-storage-account)use this guide, you must first create an Azure storage account .</span><span class="sxs-lookup"><span data-stu-id="fa42d-111">To use this guide, you must first [create an Azure storage account](https://docs.microsoft.com/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="fa42d-112">Sarà inoltre necessaria la chiave di accesso all'archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="fa42d-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="fa42d-113">Creare uno script F , e avviare F E Interactive</span><span class="sxs-lookup"><span data-stu-id="fa42d-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="fa42d-114">Gli esempi in questo articolo possono essere usati in un'applicazione F o in uno script F.</span><span class="sxs-lookup"><span data-stu-id="fa42d-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="fa42d-115">Per creare uno script F, creare `.fsx` un file `files.fsx`con l'estensione, ad esempio , nell'ambiente di sviluppo F.</span><span class="sxs-lookup"><span data-stu-id="fa42d-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="fa42d-116">Usare quindi un gestore di [pacchetti,](package-management.md) ad esempio `WindowsAzure.Storage` [Paket](https://fsprojects.github.io/Paket/) o [NuGet,](https://www.nuget.org/) per installare il pacchetto e il riferimento `WindowsAzure.Storage.dll` nello script usando una `#r` direttiva.</span><span class="sxs-lookup"><span data-stu-id="fa42d-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="fa42d-117">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fa42d-117">Add namespace declarations</span></span>

<span data-ttu-id="fa42d-118">Aggiungere le istruzioni `open` seguenti all'inizio del file `files.fsx`:</span><span class="sxs-lookup"><span data-stu-id="fa42d-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="fa42d-119">Ottenere una stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="fa42d-119">Get your connection string</span></span>

<span data-ttu-id="fa42d-120">Per questa esercitazione è necessaria una stringa di connessione di Archiviazione di Azure.You'll need an Azure Storage connection string for this tutorial.</span><span class="sxs-lookup"><span data-stu-id="fa42d-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="fa42d-121">Per ulteriori informazioni sulle stringhe di connessione, vedere [Configurare le stringhe](https://docs.microsoft.com/azure/storage/storage-configure-connection-string)di connessione di archiviazione .</span><span class="sxs-lookup"><span data-stu-id="fa42d-121">For more information about connection strings, see [Configure Storage Connection Strings](https://docs.microsoft.com/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="fa42d-122">Per l'esercitazione, immettere la stringa di connessione nello script, in questo modo:For the tutorial, you'll enter your connection string in your script, like this:</span><span class="sxs-lookup"><span data-stu-id="fa42d-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="fa42d-123">Tuttavia, questo non è **raccomandato** per i progetti reali.</span><span class="sxs-lookup"><span data-stu-id="fa42d-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="fa42d-124">La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="fa42d-125">È consigliabile proteggere sempre la chiave dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="fa42d-126">Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri.</span><span class="sxs-lookup"><span data-stu-id="fa42d-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="fa42d-127">È possibile rigenerare la chiave usando il portale di Azure se si ritiene che sia stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="fa42d-127">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="fa42d-128">Per le applicazioni reali, il modo migliore per mantenere la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="fa42d-129">Per recuperare la stringa di connessione da un file di configurazione, è possibile procedere come segue:To fetch the connection string from a configuration file, you can do this:</span><span class="sxs-lookup"><span data-stu-id="fa42d-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="fa42d-130">L'uso di Gestione configurazione di Azure è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa42d-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="fa42d-131">È anche possibile usare un'API, ad `ConfigurationManager` esempio il tipo di .NET Framework.You can also use an API such as the .NET Framework's type.</span><span class="sxs-lookup"><span data-stu-id="fa42d-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="fa42d-132">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="fa42d-132">Parse the connection string</span></span>

<span data-ttu-id="fa42d-133">Per analizzare la stringa di connessione, usare:To parse the connection string, use:</span><span class="sxs-lookup"><span data-stu-id="fa42d-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="fa42d-134">Verrà restituito `CloudStorageAccount`un file .</span><span class="sxs-lookup"><span data-stu-id="fa42d-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="fa42d-135">Creare il client del servizio FileCreate the File service client</span><span class="sxs-lookup"><span data-stu-id="fa42d-135">Create the File service client</span></span>

<span data-ttu-id="fa42d-136">Il `CloudFileClient` tipo consente di utilizzare a livello di codice i file archiviati in Archiviazione file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="fa42d-137">Ecco come creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="fa42d-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="fa42d-138">A questo punto si è pronti per scrivere codice che legge i dati e scrive i dati nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="fa42d-139">Creare una condivisione file</span><span class="sxs-lookup"><span data-stu-id="fa42d-139">Create a file share</span></span>

<span data-ttu-id="fa42d-140">In questo esempio viene illustrato come creare una condivisione file se non esiste già:This example shows how to create a file share if it does not already exist:</span><span class="sxs-lookup"><span data-stu-id="fa42d-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="fa42d-141">Creare una directory radice e una sottodirectory</span><span class="sxs-lookup"><span data-stu-id="fa42d-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="fa42d-142">Qui, si ottiene la directory radice e ottenere una sottodirectory della radice.</span><span class="sxs-lookup"><span data-stu-id="fa42d-142">Here, you get the root directory and get a subdirectory of the root.</span></span> <span data-ttu-id="fa42d-143">Entrambi vengono creati se non esistono già.</span><span class="sxs-lookup"><span data-stu-id="fa42d-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="fa42d-144">Caricare testo come file</span><span class="sxs-lookup"><span data-stu-id="fa42d-144">Upload text as a file</span></span>

<span data-ttu-id="fa42d-145">In questo esempio viene illustrato come caricare testo come file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="fa42d-146">Scaricare un file in una copia locale del file</span><span class="sxs-lookup"><span data-stu-id="fa42d-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="fa42d-147">Qui si scarica il file appena creato, aggiungendo il contenuto a un file locale.</span><span class="sxs-lookup"><span data-stu-id="fa42d-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="fa42d-148">Impostare la dimensione massima per una condivisione file</span><span class="sxs-lookup"><span data-stu-id="fa42d-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="fa42d-149">L'esempio seguente illustra come controllare l'uso corrente per una condivisione e come impostare la quota per la condivisione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="fa42d-150">`FetchAttributes`deve essere chiamato per popolare `Properties`le `SetProperties` modifiche locali all'archiviazione dei file di Azure di una condivisione e per propagare le modifiche locali all'archiviazione dei file di Azure.</span><span class="sxs-lookup"><span data-stu-id="fa42d-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="fa42d-151">Generare la firma di accesso condiviso per un file o una condivisione file</span><span class="sxs-lookup"><span data-stu-id="fa42d-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="fa42d-152">È possibile generare una firma di accesso condiviso per una condivisione file o un singolo file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="fa42d-153">È inoltre possibile creare un criterio di accesso condiviso in una condivisione file per gestire le firme di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="fa42d-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="fa42d-154">È consigliabile creare un criterio di accesso condiviso, in quanto fornisce un modo per revocare la firma SAS se necessario.</span><span class="sxs-lookup"><span data-stu-id="fa42d-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="fa42d-155">In questo caso, creare un criterio di accesso condiviso in una condivisione e quindi usare tale criterio per fornire i vincoli per una provider di servizi condivisi in un file nella condivisione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="fa42d-156">Per altre informazioni sulla creazione e sull'uso di firme di accesso condiviso, vedere [Uso delle firme di accesso condiviso](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) e [Creare e usare una firma di accesso condiviso con l'archiviazione BLOB](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="fa42d-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="fa42d-157">Copiare i file</span><span class="sxs-lookup"><span data-stu-id="fa42d-157">Copy files</span></span>

<span data-ttu-id="fa42d-158">È possibile copiare un file in un altro file o in un BLOB o un BLOB in un file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="fa42d-159">Se si copia un BLOB in un file o un file in un BLOB, è *necessario* usare una firma di accesso condiviso per autenticare l'oggetto di origine, anche se si esegue la copia all'interno dello stesso account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="fa42d-160">Copiare un file in un altro file</span><span class="sxs-lookup"><span data-stu-id="fa42d-160">Copy a file to another file</span></span>

<span data-ttu-id="fa42d-161">Qui, si copia un file in un altro file nella stessa condivisione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="fa42d-162">Poiché questa operazione esegue la copia tra file nello stesso account di archiviazione, è possibile utilizzare l'autenticazione chiave condivisa per eseguire la copia.</span><span class="sxs-lookup"><span data-stu-id="fa42d-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="fa42d-163">Copiare un file in un BLOB</span><span class="sxs-lookup"><span data-stu-id="fa42d-163">Copy a file to a blob</span></span>

<span data-ttu-id="fa42d-164">In questo caso, creare un file e copiarlo in un BLOB all'interno dello stesso account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fa42d-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="fa42d-165">Creare una firma di accesso client per il file di origine, che il servizio utilizza per autenticare l'accesso al file di origine durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="fa42d-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="fa42d-166">È possibile copiare un BLOB in un file nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="fa42d-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="fa42d-167">Se l'oggetto di origine è un BLOB, creare una firma di accesso condiviso per consentire l'accesso al BLOB durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="fa42d-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="fa42d-168">Risoluzione dei problemi di Archiviazione file con le metriche</span><span class="sxs-lookup"><span data-stu-id="fa42d-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="fa42d-169">Analisi archiviazione di Azure supporta le metriche per l'archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="fa42d-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="fa42d-170">Grazie ai dati di metrica, è possibile monitorare le richieste e diagnosticare i problemi.</span><span class="sxs-lookup"><span data-stu-id="fa42d-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="fa42d-171">È possibile abilitare le metriche per l'archiviazione dei file dal portale di [Azure](https://portal.azure.com)oppure eseguire questa operazione da F .</span><span class="sxs-lookup"><span data-stu-id="fa42d-171">You can enable metrics for File storage from the [Azure portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="fa42d-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fa42d-172">Next steps</span></span>

<span data-ttu-id="fa42d-173">Per altre informazioni sull'archiviazione dei file di Azure, vedere questi collegamenti.</span><span class="sxs-lookup"><span data-stu-id="fa42d-173">For more information about Azure File storage, see these links.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="fa42d-174">Articoli concettuali e video</span><span class="sxs-lookup"><span data-stu-id="fa42d-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="fa42d-175">Archiviazione di file in Azure: un file system SMB nel cloud senza problemi per Windows e Linux</span><span class="sxs-lookup"><span data-stu-id="fa42d-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="fa42d-176">Come usare l'archiviazione file di Azure con Linux</span><span class="sxs-lookup"><span data-stu-id="fa42d-176">How to use Azure File Storage with Linux</span></span>](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="fa42d-177">Supporto degli strumenti per Archiviazione file</span><span class="sxs-lookup"><span data-stu-id="fa42d-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="fa42d-178">Uso di Azure PowerShell con Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="fa42d-178">Using Azure PowerShell with Azure Storage</span></span>](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="fa42d-179">Come usare AzCopy con Archiviazione di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="fa42d-179">How to use AzCopy with Microsoft Azure Storage</span></span>](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="fa42d-180">Caricare, scaricare ed elencare BLOB con l'interfaccia della riga di comando di Azure</span><span class="sxs-lookup"><span data-stu-id="fa42d-180">Create, download, and list blobs with Azure CLI</span></span>](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="fa42d-181">Riferimento</span><span class="sxs-lookup"><span data-stu-id="fa42d-181">Reference</span></span>

- [<span data-ttu-id="fa42d-182">Informazioni di riferimento sulla libreria client di archiviazione per .NET</span><span class="sxs-lookup"><span data-stu-id="fa42d-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="fa42d-183">Riferimento API REST del servizio File</span><span class="sxs-lookup"><span data-stu-id="fa42d-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="fa42d-184">Post di BLOG</span><span class="sxs-lookup"><span data-stu-id="fa42d-184">Blog posts</span></span>

- [<span data-ttu-id="fa42d-185">Archiviazione file di Azure è attualmente disponibile a livello generale</span><span class="sxs-lookup"><span data-stu-id="fa42d-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="fa42d-186">Archiviazione file di AzureInside Azure File Storage</span><span class="sxs-lookup"><span data-stu-id="fa42d-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="fa42d-187">Introduzione al servizio File di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="fa42d-187">Introducing Microsoft Azure File Service</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [<span data-ttu-id="fa42d-188">Mantenimento delle connessioni ai file di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="fa42d-188">Persisting connections to Microsoft Azure Files</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
