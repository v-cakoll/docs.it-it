---
title: Funzioni di Azure - App senza server
description: Funzioni di Azure offrono funzionalità senza server in più lingue (c#, JavaScript, Java) e le piattaforme per fornire immediata guidato dagli eventi scalabilità codice.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4febcc01eebf3efce3fc1eb42e19c2ec6c0baa52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754226"
---
# <a name="azure-functions"></a><span data-ttu-id="3eb79-103">Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="3eb79-103">Azure Functions</span></span>

<span data-ttu-id="3eb79-104">Funzioni di Azure offre un'esperienza di calcolo senza server.</span><span class="sxs-lookup"><span data-stu-id="3eb79-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="3eb79-105">Una funzione viene richiamata da un *trigger* (ad esempio l'accesso a un endpoint HTTP o un timer) ed esegue un blocco di codice o logica di business.</span><span class="sxs-lookup"><span data-stu-id="3eb79-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="3eb79-106">Funzioni anche supporto specializzato *associazioni* che si connettono a risorse quali archiviazione e code.</span><span class="sxs-lookup"><span data-stu-id="3eb79-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logo di funzioni di Azure](./media/azure-functions-logo.png)

<span data-ttu-id="3eb79-108">Sono disponibili due versioni di framework funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="3eb79-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="3eb79-109">La versione legacy supporta la versione completa di .NET Framework e il nuovo runtime supporta le applicazioni .NET Core multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="3eb79-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="3eb79-110">Lingue aggiuntive oltre a C# , ad esempio JavaScript, F#, e sono supportati Java.</span><span class="sxs-lookup"><span data-stu-id="3eb79-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="3eb79-111">Creati nel portale di funzioni forniscono una sintassi di scripting avanzata.</span><span class="sxs-lookup"><span data-stu-id="3eb79-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="3eb79-112">Funzioni create come progetti autonomi possono essere distribuite con le funzionalità e supporto della piattaforma completa.</span><span class="sxs-lookup"><span data-stu-id="3eb79-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="3eb79-113">Per altre informazioni, vedere [documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions).</span><span class="sxs-lookup"><span data-stu-id="3eb79-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="3eb79-114">Funzioni v1 e v2</span><span class="sxs-lookup"><span data-stu-id="3eb79-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="3eb79-115">Sono disponibili due versioni del runtime di funzioni di Azure: versioni 1.x e 2.x.</span><span class="sxs-lookup"><span data-stu-id="3eb79-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="3eb79-116">Versione 1.x è disponibile a livello generale (GA).</span><span class="sxs-lookup"><span data-stu-id="3eb79-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="3eb79-117">Supporta lo sviluppo .NET dal portale o le macchine Windows e Usa .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3eb79-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="3eb79-118">1.x supporta C#, JavaScript, e F#, con il supporto sperimentale per Python, PHP, TypeScript, Batch, Bash e PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3eb79-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="3eb79-119">[Versione 2.x è disponibile a livello generale anche ora](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="3eb79-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="3eb79-120">Si usa .NET Core che supporta lo sviluppo multipiattaforma in Windows, macOS e Linux macchine.</span><span class="sxs-lookup"><span data-stu-id="3eb79-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="3eb79-121">Aggiunge un eccellente supporto per Java 2.x, ma non ancora direttamente supporta uno dei linguaggi sperimentali.</span><span class="sxs-lookup"><span data-stu-id="3eb79-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="3eb79-122">Versione 2.x Usa un nuovo modello di estendibilità di associazione che abilitano estensioni di terze parti per la piattaforma, controllo delle versioni indipendente delle associazioni, e una più semplice l'ambiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3eb79-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="3eb79-123">**Si verifica un problema noto nella versione 1.x con [supporto di reindirizzamento dell'associazione](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="3eb79-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="3eb79-124">Il problema è specifico per lo sviluppo .NET.</span><span class="sxs-lookup"><span data-stu-id="3eb79-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="3eb79-125">I progetti con dipendenze da librerie che hanno una versione diversa dalle librerie incluse in fase di esecuzione sono interessati.</span><span class="sxs-lookup"><span data-stu-id="3eb79-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="3eb79-126">Il team di funzioni ha eseguito il commit sta facendo progressi concreto sul problema.</span><span class="sxs-lookup"><span data-stu-id="3eb79-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="3eb79-127">Il team di risolvere i reindirizzamenti di associazione nella versione 2.x prima dell'aggiunta alla disponibilità generale.</span><span class="sxs-lookup"><span data-stu-id="3eb79-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="3eb79-128">L'istruzione ufficiale del team con le correzioni consigliate e le soluzioni alternative è disponibile qui: [Risoluzione dell'assembly in funzioni di Azure](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span><span class="sxs-lookup"><span data-stu-id="3eb79-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="3eb79-129">Per altre informazioni, vedere [confrontare 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="3eb79-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="3eb79-130">Supporto di linguaggi di programmazione</span><span class="sxs-lookup"><span data-stu-id="3eb79-130">Programming language support</span></span>

<span data-ttu-id="3eb79-131">Sono supportate le lingue seguenti sia in generale (GA), la disponibilità in anteprima, o sperimentale.</span><span class="sxs-lookup"><span data-stu-id="3eb79-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="3eb79-132">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="3eb79-132">Language</span></span>      |<span data-ttu-id="3eb79-133">1.x</span><span class="sxs-lookup"><span data-stu-id="3eb79-133">1.x</span></span>         |<span data-ttu-id="3eb79-134">2.x</span><span class="sxs-lookup"><span data-stu-id="3eb79-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="3eb79-135">**C#**</span><span class="sxs-lookup"><span data-stu-id="3eb79-135">**C#**</span></span>        |<span data-ttu-id="3eb79-136">GA</span><span class="sxs-lookup"><span data-stu-id="3eb79-136">GA</span></span>          |<span data-ttu-id="3eb79-137">Anteprima</span><span class="sxs-lookup"><span data-stu-id="3eb79-137">Preview</span></span>  |
|<span data-ttu-id="3eb79-138">**JavaScript**</span><span class="sxs-lookup"><span data-stu-id="3eb79-138">**JavaScript**</span></span>|<span data-ttu-id="3eb79-139">GA</span><span class="sxs-lookup"><span data-stu-id="3eb79-139">GA</span></span>          |<span data-ttu-id="3eb79-140">Anteprima</span><span class="sxs-lookup"><span data-stu-id="3eb79-140">Preview</span></span>  |
|<span data-ttu-id="3eb79-141">**F#**</span><span class="sxs-lookup"><span data-stu-id="3eb79-141">**F#**</span></span>        |<span data-ttu-id="3eb79-142">GA</span><span class="sxs-lookup"><span data-stu-id="3eb79-142">GA</span></span>          |         |
|<span data-ttu-id="3eb79-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="3eb79-143">**Java**</span></span>      |            |<span data-ttu-id="3eb79-144">Anteprima</span><span class="sxs-lookup"><span data-stu-id="3eb79-144">Preview</span></span>  |
|<span data-ttu-id="3eb79-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="3eb79-145">**Python**</span></span>    |<span data-ttu-id="3eb79-146">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-146">Experimental</span></span>|         |
|<span data-ttu-id="3eb79-147">**PHP**</span><span class="sxs-lookup"><span data-stu-id="3eb79-147">**PHP**</span></span>       |<span data-ttu-id="3eb79-148">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-148">Experimental</span></span>|         |
|<span data-ttu-id="3eb79-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="3eb79-149">**TypeScript**</span></span>|<span data-ttu-id="3eb79-150">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-150">Experimental</span></span>|         |
|<span data-ttu-id="3eb79-151">**Batch**</span><span class="sxs-lookup"><span data-stu-id="3eb79-151">**Batch**</span></span>     |<span data-ttu-id="3eb79-152">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-152">Experimental</span></span>|         |
|<span data-ttu-id="3eb79-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="3eb79-153">**Bash**</span></span>      |<span data-ttu-id="3eb79-154">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-154">Experimental</span></span>|         |
|<span data-ttu-id="3eb79-155">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3eb79-155">**PowerShell**</span></span>|<span data-ttu-id="3eb79-156">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="3eb79-156">Experimental</span></span>|         |

<span data-ttu-id="3eb79-157">Per altre informazioni, vedere [lingue supportate](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="3eb79-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="3eb79-158">Piani di servizio App</span><span class="sxs-lookup"><span data-stu-id="3eb79-158">App service plans</span></span>

<span data-ttu-id="3eb79-159">Le funzioni sono supportate da un *piano di servizio app*.</span><span class="sxs-lookup"><span data-stu-id="3eb79-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="3eb79-160">Il piano definisce le risorse usate dall'app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="3eb79-161">È possibile assegnare i piani a un'area, determinare le dimensioni e numero di macchine virtuali che verranno usate e selezionare un piano tariffario.</span><span class="sxs-lookup"><span data-stu-id="3eb79-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="3eb79-162">Per un approccio senza server true, è possibile usare l'App per le funzioni di **consumo** piano.</span><span class="sxs-lookup"><span data-stu-id="3eb79-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="3eb79-163">Il piano a consumo verrà ridimensionato automaticamente in base al caricamento del back-end.</span><span class="sxs-lookup"><span data-stu-id="3eb79-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="3eb79-164">Per altre informazioni, vedere [piani di servizio App](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="3eb79-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="3eb79-165">Creare la prima funzione</span><span class="sxs-lookup"><span data-stu-id="3eb79-165">Create your first function</span></span>

<span data-ttu-id="3eb79-166">Esistono tre modi comuni per creare App per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-166">There are three common ways you can create function apps.</span></span>

* <span data-ttu-id="3eb79-167">Funzioni di script nel portale.</span><span class="sxs-lookup"><span data-stu-id="3eb79-167">Script functions in the portal.</span></span>
* <span data-ttu-id="3eb79-168">Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure (CLI).</span><span class="sxs-lookup"><span data-stu-id="3eb79-168">Create the necessary resources using the Azure Command Line Interface (CLI).</span></span>
* <span data-ttu-id="3eb79-169">Creare funzioni in locale usando l'IDE preferito e pubblicarli in Azure.</span><span class="sxs-lookup"><span data-stu-id="3eb79-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="3eb79-170">Per altre informazioni sulla creazione di una funzione con script nel portale, vedere [creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span><span class="sxs-lookup"><span data-stu-id="3eb79-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="3eb79-171">Per la compilazione della riga di comando di Azure, vedere [creare la prima funzione usando il comando di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span><span class="sxs-lookup"><span data-stu-id="3eb79-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="3eb79-172">Per creare una funzione da Visual Studio, vedere [creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="3eb79-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="3eb79-173">Comprendere i trigger e associazioni</span><span class="sxs-lookup"><span data-stu-id="3eb79-173">Understand triggers and bindings</span></span>

<span data-ttu-id="3eb79-174">Le funzioni vengono richiamate da un *trigger* e può avere uno e uno solo.</span><span class="sxs-lookup"><span data-stu-id="3eb79-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="3eb79-175">Oltre a richiamare la funzione, determinate trigger fungere anche da associazioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="3eb79-176">È anche possibile definire più associazioni oltre il trigger.</span><span class="sxs-lookup"><span data-stu-id="3eb79-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="3eb79-177">*Associazioni* forniscono una modalità dichiarativa per la connessione dati al codice.</span><span class="sxs-lookup"><span data-stu-id="3eb79-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="3eb79-178">Essi possono essere passati in (input) o la ricezione dei dati (output).</span><span class="sxs-lookup"><span data-stu-id="3eb79-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="3eb79-179">Trigger e associazioni apportare facile da usare con le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="3eb79-180">Associazioni di rimuovere l'overhead di creazione manuale di database o un file le connessioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="3eb79-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="3eb79-181">Tutte le informazioni necessarie per le associazioni sono contenute in una speciale *Functions* file per gli script o dichiarati con gli attributi nel codice.</span><span class="sxs-lookup"><span data-stu-id="3eb79-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="3eb79-182">Alcuni trigger comuni includono:</span><span class="sxs-lookup"><span data-stu-id="3eb79-182">Some common triggers include:</span></span>

* <span data-ttu-id="3eb79-183">Archivio BLOB: richiamare la funzione quando viene caricato o modificato in archiviazione di un file o cartella.</span><span class="sxs-lookup"><span data-stu-id="3eb79-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
* <span data-ttu-id="3eb79-184">HTTP: richiamare la funzione, ad esempio un'API REST.</span><span class="sxs-lookup"><span data-stu-id="3eb79-184">HTTP: invoke your function like a REST API.</span></span>
* <span data-ttu-id="3eb79-185">Coda: richiamare la funzione quando sono presenti gli elementi in una coda.</span><span class="sxs-lookup"><span data-stu-id="3eb79-185">Queue: invoke your function when items exist in a queue.</span></span>
* <span data-ttu-id="3eb79-186">Timer: richiamare la funzione cadenza regolare.</span><span class="sxs-lookup"><span data-stu-id="3eb79-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="3eb79-187">Esempi di associazioni:</span><span class="sxs-lookup"><span data-stu-id="3eb79-187">Examples of bindings include:</span></span>

* <span data-ttu-id="3eb79-188">COSMOS DB: connettersi facilmente al database per caricare o salvare i file.</span><span class="sxs-lookup"><span data-stu-id="3eb79-188">CosmosDB: easily connect to the database to load or save files.</span></span>
* <span data-ttu-id="3eb79-189">Archiviazione tabelle: funzionano con archivio chiave/valore da app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-189">Table Storage: work with key/value storage from your function app.</span></span>
* <span data-ttu-id="3eb79-190">Archiviazione di Accodamento: facilmente recuperare gli elementi da una coda o inserire nuovi elementi nella coda.</span><span class="sxs-lookup"><span data-stu-id="3eb79-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="3eb79-191">Nell'esempio seguente *Functions* file definisce un trigger e un'associazione:</span><span class="sxs-lookup"><span data-stu-id="3eb79-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="3eb79-192">In questo esempio, la funzione viene attivata da una modifica all'archiviazione blob nel `images` contenitore.</span><span class="sxs-lookup"><span data-stu-id="3eb79-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="3eb79-193">Le informazioni per il file viene passate, in modo che il trigger funge anche da un'associazione.</span><span class="sxs-lookup"><span data-stu-id="3eb79-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="3eb79-194">Esiste un'altra associazione per inserire le informazioni in una coda denominata `images`.</span><span class="sxs-lookup"><span data-stu-id="3eb79-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="3eb79-195">Ecco lo script c# per la funzione:</span><span class="sxs-lookup"><span data-stu-id="3eb79-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="3eb79-196">L'esempio è una funzione semplice che accetta il nome del file che è stata modificata o caricati nell'archiviazione blob e li inserisce in una coda per l'elaborazione successiva.</span><span class="sxs-lookup"><span data-stu-id="3eb79-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="3eb79-197">Per un elenco completo di trigger e associazioni, vedere [funzioni di Azure concetti di trigger e associazioni](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span><span class="sxs-lookup"><span data-stu-id="3eb79-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="3eb79-198">Proxy</span><span class="sxs-lookup"><span data-stu-id="3eb79-198">Proxies</span></span>

<span data-ttu-id="3eb79-199">I proxy forniscono funzionalità di reindirizzamento per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3eb79-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="3eb79-200">I proxy espongono un endpoint ed eseguire il mapping che l'endpoint a un'altra risorsa.</span><span class="sxs-lookup"><span data-stu-id="3eb79-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="3eb79-201">Con i proxy, è possibile:</span><span class="sxs-lookup"><span data-stu-id="3eb79-201">With proxies, you can:</span></span>

* <span data-ttu-id="3eb79-202">Reindirizza una richiesta in ingresso a un altro endpoint.</span><span class="sxs-lookup"><span data-stu-id="3eb79-202">Reroute an incoming request to another endpoint.</span></span>
* <span data-ttu-id="3eb79-203">Modificare la richiesta in ingresso prima che vengano passati insieme.</span><span class="sxs-lookup"><span data-stu-id="3eb79-203">Modify the incoming request before it's passed along.</span></span>
* <span data-ttu-id="3eb79-204">Modificare o fornire una risposta.</span><span class="sxs-lookup"><span data-stu-id="3eb79-204">Modify or provide a response.</span></span>

<span data-ttu-id="3eb79-205">I proxy vengono usati per scenari, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3eb79-205">Proxies are used for scenarios such as:</span></span>

* <span data-ttu-id="3eb79-206">Semplificazione, riduzione o la modifica dell'URL.</span><span class="sxs-lookup"><span data-stu-id="3eb79-206">Simplifying, shortening, or changing the URL.</span></span>
* <span data-ttu-id="3eb79-207">Fornire un prefisso API coerente a più servizi back-end.</span><span class="sxs-lookup"><span data-stu-id="3eb79-207">Providing a consistent API prefix to multiple back-end services.</span></span>
* <span data-ttu-id="3eb79-208">Il comportamento fittizio una risposta a un endpoint in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="3eb79-208">Mocking a response to an endpoint being developed.</span></span>
* <span data-ttu-id="3eb79-209">Fornire una risposta statica a un endpoint noto.</span><span class="sxs-lookup"><span data-stu-id="3eb79-209">Providing a static response to a well-known endpoint.</span></span>
* <span data-ttu-id="3eb79-210">Mentre il back-end è stato spostato o eseguire la migrazione, mantenendo coerenti con l'endpoint API.</span><span class="sxs-lookup"><span data-stu-id="3eb79-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="3eb79-211">I proxy vengono archiviati come le definizioni JSON.</span><span class="sxs-lookup"><span data-stu-id="3eb79-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="3eb79-212">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="3eb79-212">Here is an example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

<span data-ttu-id="3eb79-213">Il `Domain Redirect` proxy accetta una route abbreviata e ne esegue il mapping alla risorsa di funzione più lungo.</span><span class="sxs-lookup"><span data-stu-id="3eb79-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="3eb79-214">La trasformazione è simile a:</span><span class="sxs-lookup"><span data-stu-id="3eb79-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="3eb79-215">Il `Root` proxy accetta qualsiasi elemento inviato all'URL radice (`https://--shorturl--/`) e lo reindirizza al sito della documentazione.</span><span class="sxs-lookup"><span data-stu-id="3eb79-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="3eb79-216">Nel video viene illustrato un esempio di utilizzo di proxy [Azure: Crea la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/events/Connect/2017/E102).</span><span class="sxs-lookup"><span data-stu-id="3eb79-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="3eb79-217">In tempo reale, viene eseguita la migrazione di un'applicazione ASP.NET Core in esecuzione sul Server SQL locale al Cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="3eb79-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="3eb79-218">Proxy vengono usati per effettuare il refactoring di un progetto API Web tradizionale per usare le funzioni.</span><span class="sxs-lookup"><span data-stu-id="3eb79-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="3eb79-219">Per altre informazioni sui proxy, vedere [lavorare con il proxy di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="3eb79-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3eb79-220">[Precedente](azure-serverless-platform.md)
>[Successivo](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="3eb79-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
