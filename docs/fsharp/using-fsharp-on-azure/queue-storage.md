---
title: Introduzione all'archiviazione code di Azure con F#
description: Le code di Azure forniscono una messaggistica asincrona affidabile tra i componenti dell'applicazione. La messaggistica cloud consente di ridimensionare i componenti dell'applicazione in modo indipendente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 841068ac91aecc53811359e27d984907569a2c6d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935499"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="087bd-104">Introduzione all'archiviazione code di Azure con F\#</span><span class="sxs-lookup"><span data-stu-id="087bd-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="087bd-105">L'archivio code di Azure fornisce la messaggistica cloud tra i componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="087bd-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="087bd-106">Durante la progettazione di applicazioni scalabili, i componenti dell'applicazione vengono spesso separati, per poter essere scalati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="087bd-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="087bd-107">L'archivio code fornisce la messaggistica asincrona per la comunicazione tra i componenti dell'applicazione, che possono essere eseguiti nel cloud, in un desktop, in un server locale o in un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="087bd-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="087bd-108">Archiviazione code supporta anche la gestione di attività asincrone e la creazione di flussi di lavoro dei processi.</span><span class="sxs-lookup"><span data-stu-id="087bd-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="087bd-109">Informazioni su questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="087bd-109">About this tutorial</span></span>

<span data-ttu-id="087bd-110">Questa esercitazione illustra come scrivere F# codice per alcune attività comuni usando l'archiviazione code di Azure.</span><span class="sxs-lookup"><span data-stu-id="087bd-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="087bd-111">Le attività descritte includono creazione ed eliminazione di code e aggiunta, lettura ed eliminazione dei messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="087bd-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="087bd-112">Per una panoramica concettuale dell'archiviazione code, vedere [la Guida di .NET per l'archiviazione code](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="087bd-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="087bd-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="087bd-113">Prerequisites</span></span>

<span data-ttu-id="087bd-114">Per usare questa guida, è necessario [creare prima un account di archiviazione di Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="087bd-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="087bd-115">Sarà necessaria anche la chiave di accesso alle archiviazione per questo account.</span><span class="sxs-lookup"><span data-stu-id="087bd-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="087bd-116">Creare uno F# script e avviare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="087bd-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="087bd-117">Gli esempi in questo articolo possono essere usati in un' F# applicazione o uno F# script.</span><span class="sxs-lookup"><span data-stu-id="087bd-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="087bd-118">Per creare uno F# script, creare un file con l'estensione `.fsx`, ad esempio `queues.fsx`, nell'ambiente F# di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="087bd-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="087bd-119">Usare quindi una [Gestione pacchetti](package-management.md) , ad esempio [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) , per installare il pacchetto di `WindowsAzure.Storage` e fare riferimento `WindowsAzure.Storage.dll` nello script usando una direttiva `#r`.</span><span class="sxs-lookup"><span data-stu-id="087bd-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="087bd-120">Aggiungere dichiarazioni di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="087bd-120">Add namespace declarations</span></span>

<span data-ttu-id="087bd-121">Aggiungere le istruzioni `open` seguenti all'inizio del file `queues.fsx`:</span><span class="sxs-lookup"><span data-stu-id="087bd-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="087bd-122">Ottenere una stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="087bd-122">Get your connection string</span></span>

<span data-ttu-id="087bd-123">Per questa esercitazione è necessaria una stringa di connessione di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="087bd-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="087bd-124">Per altre informazioni sulle stringhe di connessione, vedere [configurare le stringhe di connessione di archiviazione](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="087bd-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="087bd-125">Per l'esercitazione, immettere la stringa di connessione nello script, come segue:</span><span class="sxs-lookup"><span data-stu-id="087bd-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="087bd-126">Questa operazione non è tuttavia **consigliata** per i progetti reali.</span><span class="sxs-lookup"><span data-stu-id="087bd-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="087bd-127">La chiave dell’account di archiviazione è simile alla password radice per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="087bd-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="087bd-128">È consigliabile proteggere sempre la chiave dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="087bd-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="087bd-129">Evitare di distribuirla ad altri utenti, impostarla come hardcoded o salvarla in un file di testo normale accessibile ad altri.</span><span class="sxs-lookup"><span data-stu-id="087bd-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="087bd-130">È possibile rigenerare la chiave usando il portale di Azure se si ritiene che possa essere stata compromessa.</span><span class="sxs-lookup"><span data-stu-id="087bd-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="087bd-131">Per le applicazioni reali, il modo migliore per gestire la stringa di connessione di archiviazione è in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="087bd-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="087bd-132">Per recuperare la stringa di connessione da un file di configurazione, è possibile eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="087bd-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="087bd-133">L'uso di Gestione configurazione di Azure è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="087bd-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="087bd-134">È anche possibile usare un'API, ad esempio il tipo di `ConfigurationManager` del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="087bd-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="087bd-135">Analizzare la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="087bd-135">Parse the connection string</span></span>

<span data-ttu-id="087bd-136">Per analizzare la stringa di connessione, usare:</span><span class="sxs-lookup"><span data-stu-id="087bd-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="087bd-137">Verrà restituito un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="087bd-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="087bd-138">Creare il client del servizio di accodamento</span><span class="sxs-lookup"><span data-stu-id="087bd-138">Create the Queue service client</span></span>

<span data-ttu-id="087bd-139">La classe `CloudQueueClient` consente di recuperare le code archiviate nell'archivio code.</span><span class="sxs-lookup"><span data-stu-id="087bd-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="087bd-140">Ecco come creare il client del servizio:</span><span class="sxs-lookup"><span data-stu-id="087bd-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="087bd-141">A questo punto si è pronti a scrivere codice che legge e scrive i dati nell'archivio code.</span><span class="sxs-lookup"><span data-stu-id="087bd-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="087bd-142">Crea una coda</span><span class="sxs-lookup"><span data-stu-id="087bd-142">Create a queue</span></span>

<span data-ttu-id="087bd-143">Questo esempio illustra come creare una coda se non esiste già:</span><span class="sxs-lookup"><span data-stu-id="087bd-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="087bd-144">Inserire un messaggio in una coda</span><span class="sxs-lookup"><span data-stu-id="087bd-144">Insert a message into a queue</span></span>

<span data-ttu-id="087bd-145">Per inserire un messaggio in una coda esistente, creare innanzitutto un nuovo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="087bd-146">Chiamare quindi il metodo `AddMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="087bd-147">È possibile creare un `CloudQueueMessage` da una stringa (in formato UTF-8) o da una matrice di `byte`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="087bd-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="087bd-148">Visualizzare il messaggio successivo</span><span class="sxs-lookup"><span data-stu-id="087bd-148">Peek at the next message</span></span>

<span data-ttu-id="087bd-149">È possibile visualizzare il messaggio nella parte anteriore di una coda senza rimuoverlo dalla coda, chiamando il metodo `PeekMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="087bd-150">Ottenere il messaggio successivo per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="087bd-150">Get the next message for processing</span></span>

<span data-ttu-id="087bd-151">È possibile recuperare il messaggio all'inizio di una coda per l'elaborazione chiamando il metodo `GetMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="087bd-152">In un secondo momento si indicherà la corretta elaborazione del messaggio utilizzando `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="087bd-153">Cambiare il contenuto di un messaggio in coda</span><span class="sxs-lookup"><span data-stu-id="087bd-153">Change the contents of a queued message</span></span>

<span data-ttu-id="087bd-154">È possibile modificare il contenuto di un messaggio recuperato sul posto nella coda.</span><span class="sxs-lookup"><span data-stu-id="087bd-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="087bd-155">Se il messaggio rappresenta un'attività di lavoro, è possibile utilizzare questa funzionalità per aggiornarne lo stato.</span><span class="sxs-lookup"><span data-stu-id="087bd-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="087bd-156">Il codice seguente consente di aggiornare il messaggio in coda con nuovo contenuto e di impostarne il timeout di visibilità per prolungarlo di altri 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="087bd-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="087bd-157">In questo modo lo stato del lavoro associato al messaggio viene salvato e il client ha a disposizione un altro minuto per continuare l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="087bd-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="087bd-158">È possibile usare questa tecnica per tenere traccia di flussi di lavoro composti da più passaggi nei messaggi in coda, senza la necessità di ricominciare dall'inizio se un passaggio di elaborazione non riesce a causa di errori hardware o software.</span><span class="sxs-lookup"><span data-stu-id="087bd-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="087bd-159">In genere si mantiene anche un numero di tentativi e se il messaggio viene ritentato più di un determinato numero di volte, è necessario eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="087bd-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="087bd-160">In questo modo è possibile evitare che un messaggio attivi un errore dell'applicazione ogni volta che viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="087bd-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="087bd-161">Rimuovere il messaggio successivo dalla coda</span><span class="sxs-lookup"><span data-stu-id="087bd-161">De-queue the next message</span></span>

<span data-ttu-id="087bd-162">Il codice consente di rimuovere un messaggio da una coda in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="087bd-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="087bd-163">Quando si chiama `GetMessage`, si ottiene il messaggio successivo in una coda.</span><span class="sxs-lookup"><span data-stu-id="087bd-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="087bd-164">Un messaggio restituito da `GetMessage` diventa invisibile a qualsiasi altro elemento di codice che legge i messaggi di questa coda.</span><span class="sxs-lookup"><span data-stu-id="087bd-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="087bd-165">Per impostazione predefinita, il messaggio rimane invisibile per 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="087bd-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="087bd-166">Per completare la rimozione del messaggio dalla coda, è necessario chiamare anche `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="087bd-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="087bd-167">Questo processo in due passaggi di rimozione di un messaggio assicura che, qualora l'elaborazione di un messaggio non riesca a causa di errori hardware o software, un'altra istanza del codice sia in grado di ottenere lo stesso messaggio e di riprovare.</span><span class="sxs-lookup"><span data-stu-id="087bd-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="087bd-168">Il codice chiama `DeleteMessage` subito dopo l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="087bd-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="087bd-169">Usare i flussi di lavoro asincroni con API di archiviazione code comuni</span><span class="sxs-lookup"><span data-stu-id="087bd-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="087bd-170">Questo esempio illustra come usare un flusso di lavoro asincrono con API di archiviazione di accodamento comuni.</span><span class="sxs-lookup"><span data-stu-id="087bd-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="087bd-171">Opzioni aggiuntive per rimuovere i messaggi dalla coda</span><span class="sxs-lookup"><span data-stu-id="087bd-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="087bd-172">È possibile personalizzare il recupero di messaggi da una coda in due modi.</span><span class="sxs-lookup"><span data-stu-id="087bd-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="087bd-173">Innanzitutto, è possibile recuperare un batch di messaggi (massimo 32).</span><span class="sxs-lookup"><span data-stu-id="087bd-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="087bd-174">In secondo luogo, è possibile impostare un timeout di invisibilità più lungo o più breve assegnando al codice più o meno tempo per l'elaborazione completa di ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="087bd-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="087bd-175">Nell'esempio di codice seguente viene usato `GetMessages` per ottenere 20 messaggi in una sola chiamata e quindi elaborare ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="087bd-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="087bd-176">Per ogni messaggio, inoltre, il timeout di invisibilità viene impostato su cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="087bd-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="087bd-177">Si noti che i 5 minuti iniziano per tutti i messaggi contemporaneamente, quindi dopo che sono trascorsi 5 minuti dalla chiamata a `GetMessages`, tutti i messaggi che non sono stati eliminati diventeranno nuovamente visibili.</span><span class="sxs-lookup"><span data-stu-id="087bd-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="087bd-178">Recuperare la lunghezza della coda</span><span class="sxs-lookup"><span data-stu-id="087bd-178">Get the queue length</span></span>

<span data-ttu-id="087bd-179">È possibile ottenere una stima sul numero di messaggi presenti in una coda.</span><span class="sxs-lookup"><span data-stu-id="087bd-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="087bd-180">Il metodo `FetchAttributes` chiede al Servizio di accodamento di recuperare gli attributi della coda, incluso il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="087bd-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="087bd-181">La proprietà `ApproximateMessageCount` restituisce l'ultimo valore recuperato dal metodo `FetchAttributes`, senza chiamare il Servizio di accodamento.</span><span class="sxs-lookup"><span data-stu-id="087bd-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="087bd-182">Eliminare una coda</span><span class="sxs-lookup"><span data-stu-id="087bd-182">Delete a queue</span></span>

<span data-ttu-id="087bd-183">Per eliminare una coda e tutti i messaggi che contiene, chiamare il metodo `Delete` sull'oggetto Queue.</span><span class="sxs-lookup"><span data-stu-id="087bd-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="087bd-184">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="087bd-184">Next steps</span></span>

<span data-ttu-id="087bd-185">A questo punto, dopo aver appreso le nozioni di base dell'archiviazione di accodamento, visitare i collegamenti seguenti per altre informazioni sulle attività di archiviazione più complesse.</span><span class="sxs-lookup"><span data-stu-id="087bd-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="087bd-186">API di Archiviazione di Azure per .NET</span><span class="sxs-lookup"><span data-stu-id="087bd-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="087bd-187">Provider di tipi di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="087bd-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="087bd-188">Blog del team di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="087bd-188">Azure Storage Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="087bd-189">Configurare le stringhe di connessione di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="087bd-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="087bd-190">Informazioni di riferimento sulle API REST dei servizi di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="087bd-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
