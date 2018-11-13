---
title: Introduzione all'archiviazione code di Azure con F#
description: Le code di Azure offrono messaggistica asincrona affidabile tra i componenti dell'applicazione. Messaggistica cloud consente di ridimensionare in modo indipendente i componenti dell'applicazione.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 14bbc657f965fc262d2a83b1fdf982fe5e75d55e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "33569418"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="15729-104">Introduzione all'archiviazione code di Azure con F#</span><span class="sxs-lookup"><span data-stu-id="15729-104">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="15729-105">Archiviazione code di Azure fornisce messaggistica cloud tra i componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15729-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="15729-106">Durante la progettazione di applicazioni scalabili, i componenti dell'applicazione vengono spesso separati, in modo che sia possibile ridimensionarli in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="15729-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="15729-107">L'archivio Code fornisce la messaggistica asincrona per la comunicazione tra componenti dell'applicazione, che possono essere eseguiti nel cloud, sul desktop, in un server in locale o in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="15729-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="15729-108">Archiviazione code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro processi.</span><span class="sxs-lookup"><span data-stu-id="15729-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="15729-109">Informazioni su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="15729-109">About this tutorial</span></span>

<span data-ttu-id="15729-110">Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure.</span><span class="sxs-lookup"><span data-stu-id="15729-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="15729-111">Argomenti trattati includono la creazione e l'eliminazione di code e aggiunta, la lettura e l'eliminazione dei messaggi di coda.</span><span class="sxs-lookup"><span data-stu-id="15729-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="15729-112">Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="15729-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15729-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="15729-113">Prerequisites</span></span>

<span data-ttu-id="15729-114">Per usare questa Guida, è necessario innanzitutto [creare un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="15729-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="15729-115">È necessario anche la chiave di accesso di archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="15729-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="15729-116">Creare un Script F# e avvio di F# Interactive</span><span class="sxs-lookup"><span data-stu-id="15729-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="15729-117">Gli esempi in questo articolo possono essere utilizzati in un'applicazione F# o uno script F#.</span><span class="sxs-lookup"><span data-stu-id="15729-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="15729-118">Per creare uno script F#, creare un file con il `.fsx` estensione, ad esempio `queues.fsx`, nell'ambiente di sviluppo F#.</span><span class="sxs-lookup"><span data-stu-id="15729-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="15729-119">Successivamente, usare una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) oppure [NuGet](https://www.nuget.org/) per installare il `WindowsAzure.Storage` pacchetto e riferimento `WindowsAzure.Storage.dll` nello script utilizzando un `#r`della direttiva.</span><span class="sxs-lookup"><span data-stu-id="15729-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="15729-120">Aggiungere le dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="15729-120">Add namespace declarations</span></span>

<span data-ttu-id="15729-121">Aggiungere il codice seguente `open` istruzioni all'inizio del `queues.fsx` file:</span><span class="sxs-lookup"><span data-stu-id="15729-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="15729-122">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="15729-122">Get your connection string</span></span>

<span data-ttu-id="15729-123">Una stringa di connessione di archiviazione di Azure è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="15729-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="15729-124">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="15729-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="15729-125">Per l'esercitazione, si immetteranno la stringa di connessione nello script, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="15729-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="15729-126">Si tratta tuttavia **sconsigliato** progetti per il real.</span><span class="sxs-lookup"><span data-stu-id="15729-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="15729-127">La chiave dell'account è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="15729-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="15729-128">Prestare sempre attenzione proteggere la chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="15729-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="15729-129">Evitare di distribuirla ad altri utenti, hardcoded o salvarla in un file di testo normale accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="15729-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="15729-130">È possibile rigenerare la chiave tramite il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="15729-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="15729-131">In applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="15729-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="15729-132">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="15729-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="15729-133">Usando Gestione configurazione di Azure è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="15729-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="15729-134">È anche possibile usare un'API, ad esempio di .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="15729-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="15729-135">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="15729-135">Parse the connection string</span></span>

<span data-ttu-id="15729-136">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="15729-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="15729-137">Verrà restituito un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="15729-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="15729-138">Creare il client di servizio di Accodamento</span><span class="sxs-lookup"><span data-stu-id="15729-138">Create the Queue service client</span></span>

<span data-ttu-id="15729-139">Il `CloudQueueClient` classe consente di recuperare le code archiviate nell'archiviazione di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="15729-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="15729-140">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="15729-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="15729-141">A questo punto si è pronti a scrivere codice che legge e scrive i dati in archiviazione di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="15729-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="15729-142">Creare una coda</span><span class="sxs-lookup"><span data-stu-id="15729-142">Create a queue</span></span>

<span data-ttu-id="15729-143">In questo esempio viene illustrato come creare una coda, se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="15729-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="15729-144">Inserire un messaggio in una coda</span><span class="sxs-lookup"><span data-stu-id="15729-144">Insert a message into a queue</span></span>

<span data-ttu-id="15729-145">Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="15729-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="15729-146">Successivamente, chiamare il `AddMessage` (metodo).</span><span class="sxs-lookup"><span data-stu-id="15729-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="15729-147">Oggetto `CloudQueueMessage` possono essere creati da una stringa (in formato UTF-8) o un `byte` matrice, simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="15729-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="15729-148">Visualizza il messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="15729-148">Peek at the next message</span></span>

<span data-ttu-id="15729-149">È possibile visualizzare il messaggio successivo di una coda senza rimuoverlo dalla coda chiamando il `PeekMessage` (metodo).</span><span class="sxs-lookup"><span data-stu-id="15729-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="15729-150">Ottiene il messaggio successivo per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="15729-150">Get the next message for processing</span></span>

<span data-ttu-id="15729-151">È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione tramite la chiamata di `GetMessage` (metodo).</span><span class="sxs-lookup"><span data-stu-id="15729-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="15729-152">In un secondo momento indicano l'elaborazione corretta del messaggio utilizzando `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="15729-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="15729-153">Modificare il contenuto di un messaggio in coda</span><span class="sxs-lookup"><span data-stu-id="15729-153">Change the contents of a queued message</span></span>

<span data-ttu-id="15729-154">È possibile modificare il contenuto di un messaggio recuperato inserito nella coda.</span><span class="sxs-lookup"><span data-stu-id="15729-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="15729-155">Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornare lo stato dell'attività di lavoro.</span><span class="sxs-lookup"><span data-stu-id="15729-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="15729-156">Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per prolungarlo di altri 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="15729-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="15729-157">Questo consente di salvare lo stato del lavoro associata al messaggio e consente al client un altro minuto per continuare a utilizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="15729-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="15729-158">È possibile usare questa tecnica per tenere traccia dei flussi di lavoro costituito da più passaggi nei messaggi in coda, senza la necessità di ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di errori hardware o software.</span><span class="sxs-lookup"><span data-stu-id="15729-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="15729-159">In genere, è consigliabile mantenere anche un numero di tentativi e verrà effettuati più di un numero di volte in cui il messaggio, è necessario eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="15729-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="15729-160">Ciò consente di proteggere un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="15729-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="15729-161">Rimuovere il messaggio successivo dalla coda</span><span class="sxs-lookup"><span data-stu-id="15729-161">De-queue the next message</span></span>

<span data-ttu-id="15729-162">Il codice inseriscono nella coda un messaggio da una coda in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="15729-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="15729-163">Quando si chiama `GetMessage`, viene visualizzato il messaggio successivo in una coda.</span><span class="sxs-lookup"><span data-stu-id="15729-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="15729-164">Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice che legge messaggi dalla stessa coda.</span><span class="sxs-lookup"><span data-stu-id="15729-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="15729-165">Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="15729-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="15729-166">Per completare la rimozione del messaggio dalla coda, è necessario chiamare anche `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="15729-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="15729-167">Questo processo in due passaggi di rimozione di un messaggio assicura che se il codice non riesce a elaborare un messaggio a causa di errori hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare.</span><span class="sxs-lookup"><span data-stu-id="15729-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="15729-168">Il codice chiama `DeleteMessage` immediatamente dopo il messaggio è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="15729-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="15729-169">Usare flussi di lavoro asincroni con API comuni di archiviazione coda</span><span class="sxs-lookup"><span data-stu-id="15729-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="15729-170">In questo esempio mostra come usare un flusso di lavoro di async con API comuni di archiviazione coda.</span><span class="sxs-lookup"><span data-stu-id="15729-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="15729-171">Opzioni aggiuntive per i messaggi dalla coda deprovisioning</span><span class="sxs-lookup"><span data-stu-id="15729-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="15729-172">Esistono due modi per personalizzare il recupero di messaggi da una coda.</span><span class="sxs-lookup"><span data-stu-id="15729-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="15729-173">In primo luogo, è possibile recuperare un batch di messaggi (massimo 32).</span><span class="sxs-lookup"><span data-stu-id="15729-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="15729-174">In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o breve, consentendo al codice più o meno tempo per elaborare completamente ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="15729-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="15729-175">Il codice seguente viene illustrato come utilizzare `GetMessages` per ottenere i 20 messaggi in una chiamata e quindi elabori ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="15729-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="15729-176">Imposta inoltre il timeout di invisibilità viene impostato su cinque minuti per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="15729-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="15729-177">Si noti che i cinque minuti iniziano per tutti i messaggi contemporaneamente, pertanto, dopo 5 minuti trascorsi dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventano nuovamente visibili.</span><span class="sxs-lookup"><span data-stu-id="15729-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="15729-178">Ottenere la lunghezza della coda</span><span class="sxs-lookup"><span data-stu-id="15729-178">Get the queue length</span></span>

<span data-ttu-id="15729-179">È possibile ottenere una stima del numero di messaggi in una coda.</span><span class="sxs-lookup"><span data-stu-id="15729-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="15729-180">Il `FetchAttributes` metodo richiede il servizio di Accodamento di recuperare gli attributi della coda, incluso il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="15729-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="15729-181">Il `ApproximateMessageCount` proprietà restituisce l'ultimo valore recuperato dal `FetchAttributes` metodo, senza chiamare il servizio di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="15729-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="15729-182">Eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="15729-182">Delete a queue</span></span>

<span data-ttu-id="15729-183">Per eliminare una coda e tutti i messaggi in esso contenuti, chiamare il `Delete` metodo sull'oggetto coda.</span><span class="sxs-lookup"><span data-stu-id="15729-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="15729-184">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="15729-184">Next steps</span></span>

<span data-ttu-id="15729-185">A questo punto, dopo aver appreso le nozioni di base dell'archiviazione di accodamento, visitare i collegamenti seguenti per altre informazioni sulle attività di archiviazione più complesse.</span><span class="sxs-lookup"><span data-stu-id="15729-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="15729-186">API di archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="15729-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="15729-187">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="15729-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="15729-188">Blog del Team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="15729-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="15729-189">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="15729-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="15729-190">Riferimento all'API REST dei servizi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="15729-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
