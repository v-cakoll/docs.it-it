---
title: 'Introduzione all''archiviazione di Accodamento di Azure con F #'
description: Le code di Azure offrono una messaggistica affidabile e asincrono tra i componenti dell'applicazione. Cloud della messaggistica consentono di aumentare in modo indipendente i componenti dell'applicazione.
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: 8ec4652bab591dedc687d22c617b9466bc351f10
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="8a303-105">Introduzione all'archiviazione di Accodamento di Azure con F #</span><span class="sxs-lookup"><span data-stu-id="8a303-105">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="8a303-106">Archiviazione delle code di Azure fornisce cloud scambio di messaggi tra i componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-106">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="8a303-107">Nella progettazione di applicazioni per la scala, i componenti delle applicazioni sono spesso separati, in modo che sia possibile adattarli in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="8a303-107">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="8a303-108">L'archiviazione delle code recapita la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, se sono in esecuzione nel cloud, sul desktop, su un server locale o in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="8a303-108">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="8a303-109">L'archiviazione delle code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro di processo.</span><span class="sxs-lookup"><span data-stu-id="8a303-109">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="8a303-110">Su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="8a303-110">About this tutorial</span></span>

<span data-ttu-id="8a303-111">In questa esercitazione viene illustrato come scrivere codice F # per alcune attività comuni tramite l'archiviazione delle code di Azure.</span><span class="sxs-lookup"><span data-stu-id="8a303-111">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="8a303-112">Argomenti trattati includono la creazione e l'eliminazione di code e aggiunta, lettura e l'eliminazione di messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-112">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="8a303-113">Per una panoramica concettuale di archiviazione delle code, vedere [la Guida di .NET per l'archiviazione delle code](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="8a303-113">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a303-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8a303-114">Prerequisites</span></span>

<span data-ttu-id="8a303-115">Per usare questa Guida, è innanzitutto necessario [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="8a303-115">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="8a303-116">Per questo account, è necessario anche la chiave di accesso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-116">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="8a303-117">Creare un Script F # e avvio di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="8a303-117">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="8a303-118">Gli esempi in questo articolo è utilizzabile in un'applicazione di F # o uno script F #.</span><span class="sxs-lookup"><span data-stu-id="8a303-118">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="8a303-119">Per creare uno script F #, creare un file con il `.fsx` estensione, ad esempio `queues.fsx`, nell'ambiente di sviluppo F #.</span><span class="sxs-lookup"><span data-stu-id="8a303-119">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="8a303-120">Successivamente, utilizzare un [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`direttiva.</span><span class="sxs-lookup"><span data-stu-id="8a303-120">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="8a303-121">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8a303-121">Add namespace declarations</span></span>

<span data-ttu-id="8a303-122">Aggiungere il seguente `open` istruzioni all'inizio di `queues.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="8a303-122">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="8a303-123">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="8a303-123">Get your connection string</span></span>

<span data-ttu-id="8a303-124">Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-124">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="8a303-125">Per ulteriori informazioni sulle stringhe di connessione, vedere [configurare stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="8a303-125">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="8a303-126">Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8a303-126">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="8a303-127">Si tratta tuttavia **non è consigliabile** di progetti.</span><span class="sxs-lookup"><span data-stu-id="8a303-127">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="8a303-128">La chiave di account di archiviazione è simile a quella radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-128">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="8a303-129">Prestare sempre attenzione proteggere la chiave di account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-129">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="8a303-130">Evitare di distribuirlo ad altri utenti, a livello di codice, o il salvataggio in un file di testo che è accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="8a303-130">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="8a303-131">È possibile rigenerare la chiave tramite il portale di Azure, se si ritiene che potrebbero essere state compromesse.</span><span class="sxs-lookup"><span data-stu-id="8a303-131">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="8a303-132">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8a303-132">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="8a303-133">Per recuperare la stringa di connessione da un file di configurazione, è possibile farlo:</span><span class="sxs-lookup"><span data-stu-id="8a303-133">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="8a303-134">Utilizzando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="8a303-134">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="8a303-135">È inoltre possibile utilizzare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="8a303-135">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="8a303-136">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="8a303-136">Parse the connection string</span></span>

<span data-ttu-id="8a303-137">Per analizzare la stringa di connessione, utilizzare:</span><span class="sxs-lookup"><span data-stu-id="8a303-137">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="8a303-138">Verrà restituito un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="8a303-138">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="8a303-139">Creare il client del servizio coda</span><span class="sxs-lookup"><span data-stu-id="8a303-139">Create the Queue service client</span></span>

<span data-ttu-id="8a303-140">La `CloudQueueClient` classe consente di recuperare le code archiviate in archiviazione di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="8a303-140">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="8a303-141">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="8a303-141">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="8a303-142">A questo punto si è pronti a scrivere codice che legge i dati da e scrive i dati per l'archiviazione delle code.</span><span class="sxs-lookup"><span data-stu-id="8a303-142">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="8a303-143">Creare una coda</span><span class="sxs-lookup"><span data-stu-id="8a303-143">Create a queue</span></span>

<span data-ttu-id="8a303-144">In questo esempio viene illustrato come creare una coda, se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="8a303-144">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="8a303-145">Inserire un messaggio in una coda</span><span class="sxs-lookup"><span data-stu-id="8a303-145">Insert a message into a queue</span></span>

<span data-ttu-id="8a303-146">Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="8a303-146">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="8a303-147">Chiamare quindi il `AddMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="8a303-147">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="8a303-148">Oggetto `CloudQueueMessage` può essere creato da una stringa (in formato UTF-8) o un `byte` matrice, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8a303-148">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="8a303-149">Visualizza il messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8a303-149">Peek at the next message</span></span>

<span data-ttu-id="8a303-150">È possibile anche visualizzare il messaggio all'inizio di una coda senza rimuoverlo dalla coda, chiamando la `PeekMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="8a303-150">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="8a303-151">Ottenere il messaggio successivo per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="8a303-151">Get the next message for processing</span></span>

<span data-ttu-id="8a303-152">È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il `GetMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="8a303-152">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="8a303-153">In un secondo momento indicare l'elaborazione corretta del messaggio utilizzando `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="8a303-153">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="8a303-154">Modificare il contenuto di un messaggio in coda</span><span class="sxs-lookup"><span data-stu-id="8a303-154">Change the contents of a queued message</span></span>

<span data-ttu-id="8a303-155">È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-155">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="8a303-156">Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornare lo stato dell'attività di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8a303-156">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="8a303-157">Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per estendere un altro 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="8a303-157">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="8a303-158">Questo consente di salvare lo stato del lavoro associata al messaggio e fornisce al client un altro minuto per continuare a utilizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a303-158">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="8a303-159">È possibile utilizzare questa tecnica per tenere traccia dei flussi di lavoro costituito da più passaggi in messaggi in coda, senza dover ricominciare dall'inizio, se un passaggio di elaborazione non riesce a causa di un errore hardware o software.</span><span class="sxs-lookup"><span data-stu-id="8a303-159">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="8a303-160">In genere, è consigliabile mantenere un numero di tentativi anche, e se il messaggio viene ritentato più di un numero di volte, è possibile eliminare.</span><span class="sxs-lookup"><span data-stu-id="8a303-160">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="8a303-161">Ciò consente di proteggere un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="8a303-161">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="8a303-162">Annullato l'accodamento del messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8a303-162">De-queue the next message</span></span>

<span data-ttu-id="8a303-163">Il codice coda un messaggio da una coda in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="8a303-163">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="8a303-164">Quando si chiama `GetMessage`, viene visualizzato il messaggio successivo in una coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-164">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="8a303-165">Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice la lettura dei messaggi dalla coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-165">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="8a303-166">Per impostazione predefinita, il messaggio rimarrà invisibile per 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="8a303-166">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="8a303-167">Per completare la rimozione del messaggio dalla coda, è necessario chiamare `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="8a303-167">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="8a303-168">Questo processo in due passaggi della rimozione di un messaggio garantisce che se il codice non riesce a elaborare un messaggio a causa di un errore hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare.</span><span class="sxs-lookup"><span data-stu-id="8a303-168">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="8a303-169">Il codice chiama `DeleteMessage` subito dopo il messaggio è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="8a303-169">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="8a303-170">Utilizzare i flussi di lavoro asincrono all'archiviazione di Accodamento comuni API</span><span class="sxs-lookup"><span data-stu-id="8a303-170">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="8a303-171">In questo esempio viene illustrato come utilizzare un flusso di lavoro asincrono all'archiviazione di Accodamento comuni API.</span><span class="sxs-lookup"><span data-stu-id="8a303-171">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="8a303-172">Opzioni aggiuntive per rimuovere Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="8a303-172">Additional options for de-queuing messages</span></span>

<span data-ttu-id="8a303-173">Esistono due modi per personalizzare il recupero dei messaggi da una coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-173">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="8a303-174">In primo luogo, è possibile ottenere un batch di messaggi (fino a 32).</span><span class="sxs-lookup"><span data-stu-id="8a303-174">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="8a303-175">In secondo luogo, è possibile impostare un timeout di invisibilità superiori o inferiori, consentendo al codice più o meno tempo per elaborare completamente ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a303-175">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="8a303-176">Nell'esempio di codice viene illustrato come utilizzare `GetMessages` per ottenere 20 messaggi in una chiamata e quindi elabora ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a303-176">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="8a303-177">Inoltre, imposta il timeout di invisibilità cinque minuti per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a303-177">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="8a303-178">Si noti che viene avviato 5 minuti per tutti i messaggi nello stesso momento, dopo 5 minuti hanno passato dopo la chiamata a `GetMessages`, eventuali messaggi di cui non sono stati eliminati verrà visualizzati nuovamente.</span><span class="sxs-lookup"><span data-stu-id="8a303-178">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="8a303-179">Ottenere la lunghezza della coda</span><span class="sxs-lookup"><span data-stu-id="8a303-179">Get the queue length</span></span>

<span data-ttu-id="8a303-180">È possibile ottenere una stima del numero di messaggi in una coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-180">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="8a303-181">Il `FetchAttributes` metodo richiede il servizio di Accodamento di recuperare gli attributi di coda, incluso il conteggio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="8a303-181">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="8a303-182">Il `ApproximateMessageCount` proprietà restituisce l'ultimo valore recuperato tramite il `FetchAttributes` metodo, senza chiamare il servizio di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="8a303-182">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="8a303-183">Eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="8a303-183">Delete a queue</span></span>

<span data-ttu-id="8a303-184">Per eliminare una coda e tutti i messaggi in esso contenuti, chiamare il `Delete` metodo sull'oggetto di coda.</span><span class="sxs-lookup"><span data-stu-id="8a303-184">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="8a303-185">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8a303-185">Next steps</span></span>

<span data-ttu-id="8a303-186">Ora che si è appreso le nozioni fondamentali sull'archiviazione delle code, vedere i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse.</span><span class="sxs-lookup"><span data-stu-id="8a303-186">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="8a303-187">API di archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="8a303-187">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="8a303-188">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8a303-188">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="8a303-189">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8a303-189">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="8a303-190">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8a303-190">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="8a303-191">Riferimento all'API REST di servizi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8a303-191">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
