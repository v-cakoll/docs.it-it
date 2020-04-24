---
title: Funzioni di Azure-app senza server
description: Funzioni di Azure offre funzionalità senza server tra più linguaggi (C#, JavaScript, Java) e piattaforme per fornire codice di scalabilità immediata basato sugli eventi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 2dee60e3635be94a55ee26a7f04942bc59cb8dec
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135724"
---
# <a name="azure-functions"></a><span data-ttu-id="99353-103">Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="99353-103">Azure Functions</span></span>

<span data-ttu-id="99353-104">Funzioni di Azure offre un'esperienza di calcolo senza server.</span><span class="sxs-lookup"><span data-stu-id="99353-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="99353-105">Una funzione viene richiamata da un *trigger* , ad esempio l'accesso a un endpoint HTTP o un timer, ed esegue un blocco di codice o logica di business.</span><span class="sxs-lookup"><span data-stu-id="99353-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="99353-106">Le funzioni supportano inoltre *associazioni* specializzate che si connettono a risorse come l'archiviazione e le code.</span><span class="sxs-lookup"><span data-stu-id="99353-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logo di funzioni di Azure](./media/azure-functions-logo.png)

<span data-ttu-id="99353-108">La versione corrente del runtime 3,0 supporta le applicazioni .NET Core 3,1 multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="99353-108">The current runtime version 3.0 supports cross-platform .NET Core 3.1 applications.</span></span> <span data-ttu-id="99353-109">Sono supportate altre lingue oltre a C#, ad esempio JavaScript, F # e Java.</span><span class="sxs-lookup"><span data-stu-id="99353-109">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="99353-110">Le funzioni create nel portale forniscono una sintassi di scripting avanzata.</span><span class="sxs-lookup"><span data-stu-id="99353-110">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="99353-111">Le funzioni create come progetti autonomi possono essere distribuite con funzionalità e supporto completo per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="99353-111">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="99353-112">Per altre informazioni, vedere la [documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="99353-112">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="99353-113">Supporto del linguaggio di programmazione</span><span class="sxs-lookup"><span data-stu-id="99353-113">Programming language support</span></span>

<span data-ttu-id="99353-114">Le lingue seguenti sono tutte supportate in disponibilità generale (GA).</span><span class="sxs-lookup"><span data-stu-id="99353-114">The following languages are all supported in general availability (GA).</span></span>

|<span data-ttu-id="99353-115">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="99353-115">Language</span></span>      |<span data-ttu-id="99353-116">Runtime supportati</span><span class="sxs-lookup"><span data-stu-id="99353-116">Supported runtimes</span></span>|
|--------------|------------------|
|<span data-ttu-id="99353-117">**C#**</span><span class="sxs-lookup"><span data-stu-id="99353-117">**C#**</span></span>        |<span data-ttu-id="99353-118">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="99353-118">.NET Core 3.1</span></span>     |
|<span data-ttu-id="99353-119">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="99353-119">**JavaScript**</span></span>|<span data-ttu-id="99353-120">Nodo 10 & 12</span><span class="sxs-lookup"><span data-stu-id="99353-120">Node 10 & 12</span></span>      |
|<span data-ttu-id="99353-121">**F#**</span><span class="sxs-lookup"><span data-stu-id="99353-121">**F#**</span></span>        |<span data-ttu-id="99353-122">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="99353-122">.NET Core 3.1</span></span>     |
|<span data-ttu-id="99353-123">**Java**</span><span class="sxs-lookup"><span data-stu-id="99353-123">**Java**</span></span>      |<span data-ttu-id="99353-124">Java 8</span><span class="sxs-lookup"><span data-stu-id="99353-124">Java 8</span></span>            |
|<span data-ttu-id="99353-125">**Python**</span><span class="sxs-lookup"><span data-stu-id="99353-125">**Python**</span></span>    |<span data-ttu-id="99353-126">Python 3,6, 3,7, & 3,8</span><span class="sxs-lookup"><span data-stu-id="99353-126">Python 3.6, 3.7, & 3.8</span></span>|
|<span data-ttu-id="99353-127">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="99353-127">**TypeScript**</span></span>|<span data-ttu-id="99353-128">Nodo 10 & 12 (tramite JavaScript)</span><span class="sxs-lookup"><span data-stu-id="99353-128">Node 10 & 12 (via JavaScript)</span></span>|
|<span data-ttu-id="99353-129">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="99353-129">**PowerShell**</span></span>|<span data-ttu-id="99353-130">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="99353-130">PowerShell Core 6</span></span>|

<span data-ttu-id="99353-131">Per altre informazioni, vedere [Linguaggi supportati](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="99353-131">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="99353-132">Piani di servizio app</span><span class="sxs-lookup"><span data-stu-id="99353-132">App service plans</span></span>

<span data-ttu-id="99353-133">Le funzioni sono supportate da un *piano di servizio app*.</span><span class="sxs-lookup"><span data-stu-id="99353-133">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="99353-134">Il piano definisce le risorse usate dall'app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="99353-134">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="99353-135">È possibile assegnare piani a un'area, determinare le dimensioni e il numero di macchine virtuali che verranno usate e scegliere un piano tariffario.</span><span class="sxs-lookup"><span data-stu-id="99353-135">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="99353-136">Per un vero approccio senza server, le app per le funzioni possono usare il piano a **consumo** .</span><span class="sxs-lookup"><span data-stu-id="99353-136">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="99353-137">Il piano a consumo eseguirà il ridimensionamento automatico del back-end in base al carico.</span><span class="sxs-lookup"><span data-stu-id="99353-137">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="99353-138">Un'altra opzione di hosting per le app per le funzioni è il [piano Premium](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan).</span><span class="sxs-lookup"><span data-stu-id="99353-138">Another hosting option for function apps is the [Premium plan](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan).</span></span> <span data-ttu-id="99353-139">Questo piano fornisce un'istanza "always on" per evitare l'avvio a freddo, supporta funzionalità avanzate, come la connettività VNet, e viene eseguito su hardware Premium.</span><span class="sxs-lookup"><span data-stu-id="99353-139">This plan provides an "always on" instance to avoid cold start, supports advanced features like VNet connectivity, and runs on premium hardware.</span></span>

<span data-ttu-id="99353-140">Per altre informazioni, vedere [piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="99353-140">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="99353-141">Creare la prima funzione</span><span class="sxs-lookup"><span data-stu-id="99353-141">Create your first function</span></span>

<span data-ttu-id="99353-142">Esistono tre modi comuni per creare app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="99353-142">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="99353-143">Funzioni di script nel portale.</span><span class="sxs-lookup"><span data-stu-id="99353-143">Script functions in the portal.</span></span>
- <span data-ttu-id="99353-144">Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure.</span><span class="sxs-lookup"><span data-stu-id="99353-144">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="99353-145">Consente di compilare localmente le funzioni usando l'IDE preferito e di pubblicarle in Azure.</span><span class="sxs-lookup"><span data-stu-id="99353-145">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="99353-146">Per altre informazioni sulla creazione di una funzione con script nel portale, vedere [creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="99353-146">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="99353-147">Per compilare dall'interfaccia della riga di comando di Azure, vedere [creare la prima funzione usando l'interfaccia della](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)riga di comando di Azure.</span><span class="sxs-lookup"><span data-stu-id="99353-147">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="99353-148">Per creare una funzione da Visual Studio, vedere [creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="99353-148">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="99353-149">Informazioni sui trigger e sulle associazioni</span><span class="sxs-lookup"><span data-stu-id="99353-149">Understand triggers and bindings</span></span>

<span data-ttu-id="99353-150">Le funzioni vengono richiamate da un *trigger* e possono avere esattamente una.</span><span class="sxs-lookup"><span data-stu-id="99353-150">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="99353-151">Oltre a richiamare la funzione, alcuni trigger vengono utilizzati anche come associazioni.</span><span class="sxs-lookup"><span data-stu-id="99353-151">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="99353-152">È anche possibile definire più associazioni oltre al trigger.</span><span class="sxs-lookup"><span data-stu-id="99353-152">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="99353-153">Le *associazioni* forniscono una modalità dichiarativa per connettere i dati al codice.</span><span class="sxs-lookup"><span data-stu-id="99353-153">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="99353-154">Possono essere passati (input) o ricevere dati (output).</span><span class="sxs-lookup"><span data-stu-id="99353-154">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="99353-155">I trigger e le associazioni facilitano l'utilizzo delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="99353-155">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="99353-156">Le associazioni rimuovono l'overhead della creazione manuale di connessioni di database o file system.</span><span class="sxs-lookup"><span data-stu-id="99353-156">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="99353-157">Tutte le informazioni necessarie per le associazioni sono contenute in un file *Functions. JSON* speciale per gli script o dichiarati con attributi nel codice.</span><span class="sxs-lookup"><span data-stu-id="99353-157">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="99353-158">Alcuni trigger comuni includono:</span><span class="sxs-lookup"><span data-stu-id="99353-158">Some common triggers include:</span></span>

- <span data-ttu-id="99353-159">Archiviazione BLOB: richiamare la funzione quando un file o una cartella viene caricata o modificata nello spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="99353-159">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="99353-160">HTTP: richiama la funzione come un'API REST.</span><span class="sxs-lookup"><span data-stu-id="99353-160">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="99353-161">Queue: richiama la funzione quando gli elementi sono presenti in una coda.</span><span class="sxs-lookup"><span data-stu-id="99353-161">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="99353-162">Timer: richiamare la funzione a cadenza regolare.</span><span class="sxs-lookup"><span data-stu-id="99353-162">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="99353-163">Di seguito sono riportati alcuni esempi di binding:</span><span class="sxs-lookup"><span data-stu-id="99353-163">Examples of bindings include:</span></span>

- <span data-ttu-id="99353-164">CosmosDB: consente di connettersi facilmente al database per caricare o salvare i file.</span><span class="sxs-lookup"><span data-stu-id="99353-164">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="99353-165">Archiviazione tabelle: usare l'archiviazione di chiave/valore dall'app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="99353-165">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="99353-166">Archiviazione code: è possibile recuperare facilmente elementi da una coda o inserire nuovi elementi nella coda.</span><span class="sxs-lookup"><span data-stu-id="99353-166">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="99353-167">Il file *Functions. JSON* di esempio seguente definisce un trigger e un'associazione:</span><span class="sxs-lookup"><span data-stu-id="99353-167">The following example *functions.json* file defines a trigger and a binding:</span></span>

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

<span data-ttu-id="99353-168">In questo esempio, la funzione viene attivata da una modifica all'archiviazione BLOB nel `images` contenitore.</span><span class="sxs-lookup"><span data-stu-id="99353-168">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="99353-169">Le informazioni per il file vengono passate, quindi il trigger funge anche da Binding.</span><span class="sxs-lookup"><span data-stu-id="99353-169">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="99353-170">Esiste un'altra associazione per inserire le informazioni in una `images`coda denominata.</span><span class="sxs-lookup"><span data-stu-id="99353-170">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="99353-171">Di seguito è riportato lo script C# per la funzione:</span><span class="sxs-lookup"><span data-stu-id="99353-171">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="99353-172">L'esempio è una funzione semplice che accetta il nome del file che è stato modificato o caricato nell'archivio BLOB e lo inserisce in una coda per l'elaborazione successiva.</span><span class="sxs-lookup"><span data-stu-id="99353-172">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="99353-173">Per un elenco completo dei trigger e delle associazioni, vedere [concetti relativi a trigger e associazioni di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="99353-173">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="99353-174">[Precedente](azure-serverless-platform.md)
>[successivo](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="99353-174">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
