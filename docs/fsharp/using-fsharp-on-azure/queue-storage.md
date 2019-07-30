---
title: Introduzione all'archiviazione code di Azure con F#
description: Le code di Azure forniscono messaggistica asincrona e affidabile tra i componenti dell'applicazione. La messaggistica cloud consente di ridimensionare i componenti dell'applicazione in modo indipendente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 65af98fb88e91d709eb0e35907cbc2dc097634d0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630479"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="c2024-104">Introduzione all'archiviazione code di Azure con F\#</span><span class="sxs-lookup"><span data-stu-id="c2024-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="c2024-105">Archiviazione code di Azure fornisce la messaggistica cloud tra i componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2024-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="c2024-106">Nella progettazione di applicazioni per la scalabilità, i componenti dell'applicazione vengono spesso separati, in modo che possano essere ridimensionati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c2024-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="c2024-107">L'archiviazione di Accodamento offre la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, indipendentemente dal fatto che siano in esecuzione nel cloud, sul desktop, in un server locale o in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c2024-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="c2024-108">L'archiviazione Code supporta anche la gestione di attività asincrone e la compilazione di flussi di lavoro di processo.</span><span class="sxs-lookup"><span data-stu-id="c2024-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="c2024-109">Informazioni su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="c2024-109">About this tutorial</span></span>

<span data-ttu-id="c2024-110">Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure.</span><span class="sxs-lookup"><span data-stu-id="c2024-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="c2024-111">Le attività descritte includono creazione ed eliminazione di code e aggiunta, lettura ed eliminazione dei messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="c2024-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="c2024-112">Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="c2024-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2024-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c2024-113">Prerequisites</span></span>

<span data-ttu-id="c2024-114">Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c2024-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="c2024-115">Sarà necessaria anche la chiave di accesso alle archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="c2024-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="c2024-116">Creare uno F# script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="c2024-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="c2024-117">Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script.</span><span class="sxs-lookup"><span data-stu-id="c2024-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="c2024-118">Per creare uno F# script, creare un file con l' `.fsx` estensione, ad esempio `queues.fsx`, nell'ambiente F# di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c2024-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="c2024-119">Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare `WindowsAzure.Storage` il pacchetto e `WindowsAzure.Storage.dll` il riferimento nello script usando `#r` una direttiva.</span><span class="sxs-lookup"><span data-stu-id="c2024-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="c2024-120">Aggiungi dichiarazioni dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c2024-120">Add namespace declarations</span></span>

<span data-ttu-id="c2024-121">Aggiungere le seguenti `open` istruzioni all'inizio `queues.fsx` del file:</span><span class="sxs-lookup"><span data-stu-id="c2024-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="c2024-122">Ottenere la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="c2024-122">Get your connection string</span></span>

<span data-ttu-id="c2024-123">Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="c2024-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="c2024-124">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="c2024-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="c2024-125">Per l'esercitazione, immettere la stringa di connessione nello script, come segue:</span><span class="sxs-lookup"><span data-stu-id="c2024-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="c2024-126">Questa operazione **non** è tuttavia consigliata per i progetti reali.</span><span class="sxs-lookup"><span data-stu-id="c2024-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="c2024-127">La chiave dell'account di archiviazione è simile alla password radice dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c2024-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="c2024-128">Prestare sempre attenzione a proteggere la chiave dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c2024-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="c2024-129">Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="c2024-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="c2024-130">È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="c2024-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="c2024-131">Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2024-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="c2024-132">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c2024-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="c2024-133">L'uso di Configuration Manager di Azure è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c2024-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="c2024-134">È anche possibile usare un'API, ad esempio il tipo `ConfigurationManager` di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2024-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="c2024-135">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="c2024-135">Parse the connection string</span></span>

<span data-ttu-id="c2024-136">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="c2024-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="c2024-137">Verrà restituito un oggetto `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="c2024-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="c2024-138">Creare il client di Servizio di accodamento</span><span class="sxs-lookup"><span data-stu-id="c2024-138">Create the Queue service client</span></span>

<span data-ttu-id="c2024-139">La `CloudQueueClient` classe consente di recuperare le code archiviate nell'archivio code.</span><span class="sxs-lookup"><span data-stu-id="c2024-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="c2024-140">Ecco un modo per creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="c2024-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="c2024-141">A questo punto si è pronti per scrivere codice che legge e scrive i dati nell'archivio code.</span><span class="sxs-lookup"><span data-stu-id="c2024-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="c2024-142">Creare una coda</span><span class="sxs-lookup"><span data-stu-id="c2024-142">Create a queue</span></span>

<span data-ttu-id="c2024-143">Questo esempio illustra come creare una coda se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="c2024-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="c2024-144">Inserire un messaggio in una coda</span><span class="sxs-lookup"><span data-stu-id="c2024-144">Insert a message into a queue</span></span>

<span data-ttu-id="c2024-145">Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2024-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="c2024-146">Chiamare quindi il `AddMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="c2024-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="c2024-147">Un `CloudQueueMessage` oggetto può essere creato da una stringa (in formato UTF-8) o da `byte` una matrice, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c2024-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="c2024-148">Visualizza il messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c2024-148">Peek at the next message</span></span>

<span data-ttu-id="c2024-149">È possibile visualizzare il messaggio nella parte anteriore di una coda senza rimuoverlo dalla coda, chiamando il `PeekMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="c2024-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="c2024-150">Ottenere il messaggio successivo per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="c2024-150">Get the next message for processing</span></span>

<span data-ttu-id="c2024-151">È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il `GetMessage` metodo.</span><span class="sxs-lookup"><span data-stu-id="c2024-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="c2024-152">In un secondo momento si indicherà la corretta elaborazione `DeleteMessage`del messaggio tramite.</span><span class="sxs-lookup"><span data-stu-id="c2024-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="c2024-153">Modificare il contenuto di un messaggio in coda</span><span class="sxs-lookup"><span data-stu-id="c2024-153">Change the contents of a queued message</span></span>

<span data-ttu-id="c2024-154">È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda.</span><span class="sxs-lookup"><span data-stu-id="c2024-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="c2024-155">Se il messaggio rappresenta un'attività di lavoro, è possibile usare questa funzionalità per aggiornare lo stato dell'attività di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c2024-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="c2024-156">Il codice seguente aggiorna il messaggio della coda con nuovo contenuto e imposta il timeout di visibilità per estendere altri 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="c2024-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="c2024-157">In questo modo si salva lo stato del lavoro associato al messaggio e si concede al client un altro minuto per continuare a lavorare sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2024-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="c2024-158">È possibile utilizzare questa tecnica per tenere traccia dei flussi di lavoro in più passaggi nei messaggi in coda, senza dover ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di un errore hardware o software.</span><span class="sxs-lookup"><span data-stu-id="c2024-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="c2024-159">In genere si mantiene anche un numero di tentativi e se il messaggio viene ritentato più di un determinato numero di volte, è necessario eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c2024-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="c2024-160">In questo modo si protegge da un messaggio che attiva un errore dell'applicazione ogni volta che viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="c2024-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="c2024-161">Annulla la coda del messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c2024-161">De-queue the next message</span></span>

<span data-ttu-id="c2024-162">Il codice rimuove un messaggio da una coda in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="c2024-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="c2024-163">Quando si chiama `GetMessage`, si ottiene il messaggio successivo in una coda.</span><span class="sxs-lookup"><span data-stu-id="c2024-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="c2024-164">Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro codice che legge i messaggi da questa coda.</span><span class="sxs-lookup"><span data-stu-id="c2024-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="c2024-165">Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="c2024-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="c2024-166">Per completare la rimozione del messaggio dalla coda, è necessario chiamare `DeleteMessage`anche.</span><span class="sxs-lookup"><span data-stu-id="c2024-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="c2024-167">Questo processo in due passaggi di rimozione di un messaggio assicura che se il codice non riesce a elaborare un messaggio a causa di un errore hardware o software, un'altra istanza del codice può ottenere lo stesso messaggio e riprovare.</span><span class="sxs-lookup"><span data-stu-id="c2024-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="c2024-168">Il codice chiama `DeleteMessage` subito dopo l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2024-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="c2024-169">Usare i flussi di lavoro asincroni con API di archiviazione code comuni</span><span class="sxs-lookup"><span data-stu-id="c2024-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="c2024-170">Questo esempio illustra come usare un flusso di lavoro asincrono con API di archiviazione di accodamento comuni.</span><span class="sxs-lookup"><span data-stu-id="c2024-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="c2024-171">Opzioni aggiuntive per rimuovere i messaggi dalla coda di Accodamento</span><span class="sxs-lookup"><span data-stu-id="c2024-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="c2024-172">È possibile personalizzare il recupero dei messaggi da una coda in due modi.</span><span class="sxs-lookup"><span data-stu-id="c2024-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="c2024-173">Per prima cosa, è possibile ottenere un batch di messaggi (fino a 32).</span><span class="sxs-lookup"><span data-stu-id="c2024-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="c2024-174">In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o più breve, consentendo al codice più o meno tempo di elaborare completamente ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2024-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="c2024-175">Nell'esempio di codice seguente `GetMessages` viene usato per ottenere 20 messaggi in una sola chiamata e quindi elaborare ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2024-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="c2024-176">Imposta anche il timeout di invisibilità su cinque minuti per ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2024-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="c2024-177">Si noti che i 5 minuti iniziano per tutti i messaggi contemporaneamente, quindi dopo che sono trascorsi 5 minuti dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventeranno nuovamente visibili.</span><span class="sxs-lookup"><span data-stu-id="c2024-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="c2024-178">Ottenere la lunghezza della coda</span><span class="sxs-lookup"><span data-stu-id="c2024-178">Get the queue length</span></span>

<span data-ttu-id="c2024-179">È possibile ottenere una stima del numero di messaggi in una coda.</span><span class="sxs-lookup"><span data-stu-id="c2024-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="c2024-180">Il `FetchAttributes` metodo richiede all'servizio di Accodamento di recuperare gli attributi della coda, incluso il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c2024-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="c2024-181">La `ApproximateMessageCount` proprietà restituisce l'ultimo valore recuperato `FetchAttributes` dal metodo senza chiamare il servizio di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="c2024-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="c2024-182">Eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="c2024-182">Delete a queue</span></span>

<span data-ttu-id="c2024-183">Per eliminare una coda e tutti i messaggi che contiene, chiamare il `Delete` metodo sull'oggetto Queue.</span><span class="sxs-lookup"><span data-stu-id="c2024-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="c2024-184">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c2024-184">Next steps</span></span>

<span data-ttu-id="c2024-185">Ora che sono state apprese le nozioni di base dell'archiviazione code, seguire i collegamenti seguenti per informazioni sulle attività di archiviazione più complesse.</span><span class="sxs-lookup"><span data-stu-id="c2024-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="c2024-186">API di archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="c2024-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="c2024-187">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c2024-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="c2024-188">Blog del team di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c2024-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="c2024-189">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c2024-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="c2024-190">Informazioni di riferimento sull'API REST dei servizi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c2024-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
