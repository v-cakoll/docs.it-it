---
title: Funzioni di Azure - App senza serverAzure Functions - Serverless apps
description: Le funzioni di Azure offrono funzionalità senza server in più linguaggi (C, JavaScript, Java) e piattaforme per fornire codice con scalabilità istantanea basato su eventi.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401613"
---
# <a name="azure-functions"></a><span data-ttu-id="0e77f-103">Funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="0e77f-103">Azure Functions</span></span>

<span data-ttu-id="0e77f-104">Le funzioni di Azure offrono un'esperienza di calcolo senza server.</span><span class="sxs-lookup"><span data-stu-id="0e77f-104">Azure functions provide a serverless compute experience.</span></span> <span data-ttu-id="0e77f-105">Una funzione viene richiamata da un *trigger* (ad esempio l'accesso a un endpoint HTTP o un timer) ed esegue un blocco di codice o logica di business.</span><span class="sxs-lookup"><span data-stu-id="0e77f-105">A function is invoked by a *trigger* (such as access to an HTTP endpoint or a timer) and executes a block of code or business logic.</span></span> <span data-ttu-id="0e77f-106">Le funzioni supportano anche *associazioni specializzate* che si connettono a risorse come archiviazione e code.</span><span class="sxs-lookup"><span data-stu-id="0e77f-106">Functions also support specialized *bindings* that connect to resources like storage and queues.</span></span>

![Logo delle funzioni di AzureAzure functions logo](./media/azure-functions-logo.png)

<span data-ttu-id="0e77f-108">Esistono due versioni del framework Funzioni di Azure.There are two versions of the Azure Functions framework.</span><span class="sxs-lookup"><span data-stu-id="0e77f-108">There are two versions of the Azure Functions framework.</span></span> <span data-ttu-id="0e77f-109">La versione legacy supporta la versione completa di .NET Framework e il nuovo runtime supporta le applicazioni .NET Core multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="0e77f-109">The legacy version supports the full .NET Framework and the new runtime supports cross-platform .NET Core applications.</span></span> <span data-ttu-id="0e77f-110">Sono supportati linguaggi aggiuntivi oltre a C, ad esempio JavaScript, F e Java.</span><span class="sxs-lookup"><span data-stu-id="0e77f-110">Additional languages besides C# such as JavaScript, F#, and Java are supported.</span></span> <span data-ttu-id="0e77f-111">Le funzioni create nel portale forniscono una sintassi di script avanzata.</span><span class="sxs-lookup"><span data-stu-id="0e77f-111">Functions created in the portal provide a rich scripting syntax.</span></span> <span data-ttu-id="0e77f-112">Le funzioni create come progetti autonomi possono essere distribuite con funzionalità e supporto completo della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="0e77f-112">Functions created as standalone projects can be deployed with full platform support and capabilities.</span></span>

<span data-ttu-id="0e77f-113">Per altre informazioni, vedere la [documentazione](https://docs.microsoft.com/azure/azure-functions)relativa alle funzioni di Azure.For more information, see Azure Functions documentation .</span><span class="sxs-lookup"><span data-stu-id="0e77f-113">For more information, see [Azure Functions documentation](https://docs.microsoft.com/azure/azure-functions).</span></span>

## <a name="functions-v1-vs-v2"></a><span data-ttu-id="0e77f-114">Funzioni v1 e v2</span><span class="sxs-lookup"><span data-stu-id="0e77f-114">Functions v1 vs. v2</span></span>

<span data-ttu-id="0e77f-115">Esistono due versioni del runtime di Funzioni di Azure: 1.x e 2.x.There are two versions of the Azure Functions runtime: 1.x and 2.x.</span><span class="sxs-lookup"><span data-stu-id="0e77f-115">There are two versions of the Azure Functions runtime: 1.x and 2.x.</span></span> <span data-ttu-id="0e77f-116">La versione 1.x è generalmente disponibile (GA).</span><span class="sxs-lookup"><span data-stu-id="0e77f-116">Version 1.x is generally available (GA).</span></span> <span data-ttu-id="0e77f-117">Supporta lo sviluppo .NET dal portale o dai computer Windows e utilizza .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e77f-117">It supports .NET development from the portal or Windows machines and uses the .NET Framework.</span></span> <span data-ttu-id="0e77f-118">1.x supporta il linguaggio C, JavaScript e F, con il supporto sperimentale per Python, PHP, TypeScript, Batch, Bash e PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e77f-118">1.x supports C#, JavaScript, and F#, with experimental support for Python, PHP, TypeScript, Batch, Bash, and PowerShell.</span></span>

<span data-ttu-id="0e77f-119">Anche la [versione 2.x è generalmente disponibile ora](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span><span class="sxs-lookup"><span data-stu-id="0e77f-119">[Version 2.x is also generally available now](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/).</span></span> <span data-ttu-id="0e77f-120">Sfrutta .NET Core e supporta lo sviluppo multipiattaforma su computer Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="0e77f-120">It leverages .NET Core and supports cross-platform development on Windows, macOS, and Linux machines.</span></span> <span data-ttu-id="0e77f-121">2.x aggiunge il supporto di prima classe per Java, ma non supporta ancora direttamente nessuno dei linguaggi sperimentali.</span><span class="sxs-lookup"><span data-stu-id="0e77f-121">2.x adds first-class support for Java but doesn't yet directly support any of the experimental languages.</span></span> <span data-ttu-id="0e77f-122">La versione 2.x usa un nuovo modello di estendibilità dell'associazione che consente estensioni di terze parti alla piattaforma, il controllo delle versioni indipendente delle associazioni e un ambiente di esecuzione più semplificato.</span><span class="sxs-lookup"><span data-stu-id="0e77f-122">Version 2.x uses a new binding extensibility model that enables third-party extensions to the platform, independent versioning of bindings, and a more streamlined execution environment.</span></span>

> <span data-ttu-id="0e77f-123">**Esiste un problema noto in 1.x con [supporto di reindirizzamento binding](https://github.com/Azure/azure-functions-host/issues/992).**</span><span class="sxs-lookup"><span data-stu-id="0e77f-123">**There is a known issue in 1.x with [binding redirect support](https://github.com/Azure/azure-functions-host/issues/992).**</span></span> <span data-ttu-id="0e77f-124">Il problema è specifico per lo sviluppo .NET.</span><span class="sxs-lookup"><span data-stu-id="0e77f-124">The issue is specific to .NET development.</span></span> <span data-ttu-id="0e77f-125">I progetti con dipendenze da librerie che sono una versione diversa dalle librerie incluse nel runtime sono interessati.</span><span class="sxs-lookup"><span data-stu-id="0e77f-125">Projects with dependencies on libraries that are a different version from the libraries included in the runtime are impacted.</span></span> <span data-ttu-id="0e77f-126">Il team delle funzioni si è impegnato a compiere progressi concreti sul problema.</span><span class="sxs-lookup"><span data-stu-id="0e77f-126">The functions team has committed to making concrete progress on the problem.</span></span> <span data-ttu-id="0e77f-127">Il team si occuperà dei reindirizzamenti di binding in 2.x prima di passare alla disponibilità generale.</span><span class="sxs-lookup"><span data-stu-id="0e77f-127">The team will address binding redirects in 2.x before it goes into general availability.</span></span> <span data-ttu-id="0e77f-128">La dichiarazione ufficiale del team con le correzioni e le soluzioni alternative suggerite è disponibile qui: [Risoluzione dell'assembly in Funzioni](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)di Azure .</span><span class="sxs-lookup"><span data-stu-id="0e77f-128">The official team statement with suggested fixes and workarounds is available here: [Assembly resolution in Azure Functions](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).</span></span>

<span data-ttu-id="0e77f-129">Per ulteriori informazioni, vedere [Confrontare 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span><span class="sxs-lookup"><span data-stu-id="0e77f-129">For more information, see [Compare 1.x and 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions).</span></span>

## <a name="programming-language-support"></a><span data-ttu-id="0e77f-130">Supporto del linguaggio di programmazione</span><span class="sxs-lookup"><span data-stu-id="0e77f-130">Programming language support</span></span>

<span data-ttu-id="0e77f-131">Le lingue seguenti sono supportate in generale availability (GA), preview o sperimentale.</span><span class="sxs-lookup"><span data-stu-id="0e77f-131">The following languages are supported either in general availability (GA), preview, or experimental.</span></span>

|<span data-ttu-id="0e77f-132">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="0e77f-132">Language</span></span>      |<span data-ttu-id="0e77f-133">1.x</span><span class="sxs-lookup"><span data-stu-id="0e77f-133">1.x</span></span>         |<span data-ttu-id="0e77f-134">2.x</span><span class="sxs-lookup"><span data-stu-id="0e77f-134">2.x</span></span>      |
|--------------|------------|---------|
|<span data-ttu-id="0e77f-135">**C #**</span><span class="sxs-lookup"><span data-stu-id="0e77f-135">**C#**</span></span>        |<span data-ttu-id="0e77f-136">GA</span><span class="sxs-lookup"><span data-stu-id="0e77f-136">GA</span></span>          |<span data-ttu-id="0e77f-137">Anteprima</span><span class="sxs-lookup"><span data-stu-id="0e77f-137">Preview</span></span>  |
|<span data-ttu-id="0e77f-138">**Javascript**</span><span class="sxs-lookup"><span data-stu-id="0e77f-138">**JavaScript**</span></span>|<span data-ttu-id="0e77f-139">GA</span><span class="sxs-lookup"><span data-stu-id="0e77f-139">GA</span></span>          |<span data-ttu-id="0e77f-140">Anteprima</span><span class="sxs-lookup"><span data-stu-id="0e77f-140">Preview</span></span>  |
|<span data-ttu-id="0e77f-141">**F #**</span><span class="sxs-lookup"><span data-stu-id="0e77f-141">**F#**</span></span>        |<span data-ttu-id="0e77f-142">GA</span><span class="sxs-lookup"><span data-stu-id="0e77f-142">GA</span></span>          |         |
|<span data-ttu-id="0e77f-143">**Java**</span><span class="sxs-lookup"><span data-stu-id="0e77f-143">**Java**</span></span>      |            |<span data-ttu-id="0e77f-144">Anteprima</span><span class="sxs-lookup"><span data-stu-id="0e77f-144">Preview</span></span>  |
|<span data-ttu-id="0e77f-145">**Python**</span><span class="sxs-lookup"><span data-stu-id="0e77f-145">**Python**</span></span>    |<span data-ttu-id="0e77f-146">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-146">Experimental</span></span>|         |
|<span data-ttu-id="0e77f-147">**Php**</span><span class="sxs-lookup"><span data-stu-id="0e77f-147">**PHP**</span></span>       |<span data-ttu-id="0e77f-148">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-148">Experimental</span></span>|         |
|<span data-ttu-id="0e77f-149">**TypeScript**</span><span class="sxs-lookup"><span data-stu-id="0e77f-149">**TypeScript**</span></span>|<span data-ttu-id="0e77f-150">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-150">Experimental</span></span>|         |
|<span data-ttu-id="0e77f-151">**lotto**</span><span class="sxs-lookup"><span data-stu-id="0e77f-151">**Batch**</span></span>     |<span data-ttu-id="0e77f-152">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-152">Experimental</span></span>|         |
|<span data-ttu-id="0e77f-153">**Bash**</span><span class="sxs-lookup"><span data-stu-id="0e77f-153">**Bash**</span></span>      |<span data-ttu-id="0e77f-154">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-154">Experimental</span></span>|         |
|<span data-ttu-id="0e77f-155">**Powershell**</span><span class="sxs-lookup"><span data-stu-id="0e77f-155">**PowerShell**</span></span>|<span data-ttu-id="0e77f-156">Sperimentale</span><span class="sxs-lookup"><span data-stu-id="0e77f-156">Experimental</span></span>|         |

<span data-ttu-id="0e77f-157">Per altre informazioni, vedere [Linguaggi supportati](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span><span class="sxs-lookup"><span data-stu-id="0e77f-157">For more information, see [Supported languages](https://docs.microsoft.com/azure/azure-functions/supported-languages).</span></span>

## <a name="app-service-plans"></a><span data-ttu-id="0e77f-158">Piani di servizio app</span><span class="sxs-lookup"><span data-stu-id="0e77f-158">App service plans</span></span>

<span data-ttu-id="0e77f-159">Le funzioni sono supportate da un piano di *servizio app.*</span><span class="sxs-lookup"><span data-stu-id="0e77f-159">Functions are backed by an *app service plan*.</span></span> <span data-ttu-id="0e77f-160">Il piano definisce le risorse usate dall'app funzioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-160">The plan defines the resources used by the functions app.</span></span> <span data-ttu-id="0e77f-161">È possibile assegnare piani a un'area, determinare le dimensioni e il numero di macchine virtuali che verranno utilizzate e selezionare un piano tariffario.</span><span class="sxs-lookup"><span data-stu-id="0e77f-161">You can assign plans to a region, determine the size and number of virtual machines that will be used, and pick a pricing tier.</span></span> <span data-ttu-id="0e77f-162">Per un vero approccio senza server, le app per le funzioni possono usare il piano di **consumo.**</span><span class="sxs-lookup"><span data-stu-id="0e77f-162">For a true serverless approach, function apps may use the **consumption** plan.</span></span> <span data-ttu-id="0e77f-163">Il piano di consumo scalerà automaticamente il back-end in base al carico.</span><span class="sxs-lookup"><span data-stu-id="0e77f-163">The consumption plan will scale the back end automatically based on load.</span></span>

<span data-ttu-id="0e77f-164">Per altre informazioni, vedere [Piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span><span class="sxs-lookup"><span data-stu-id="0e77f-164">For more information, see [App service plans](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview).</span></span>

## <a name="create-your-first-function"></a><span data-ttu-id="0e77f-165">Creare la prima funzione</span><span class="sxs-lookup"><span data-stu-id="0e77f-165">Create your first function</span></span>

<span data-ttu-id="0e77f-166">Esistono tre modi comuni per creare app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-166">There are three common ways you can create function apps.</span></span>

- <span data-ttu-id="0e77f-167">Funzioni di script nel portale.</span><span class="sxs-lookup"><span data-stu-id="0e77f-167">Script functions in the portal.</span></span>
- <span data-ttu-id="0e77f-168">Creare le risorse necessarie usando l'interfaccia della riga di comando di Azure.Create the necessary resources using the Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="0e77f-168">Create the necessary resources using the Azure CLI.</span></span>
- <span data-ttu-id="0e77f-169">Creare funzioni in locale usando l'IDE preferito e pubblicarle in Azure.Build functions locally using your favorite IDE and publish them to Azure.</span><span class="sxs-lookup"><span data-stu-id="0e77f-169">Build functions locally using your favorite IDE and publish them to Azure.</span></span>

<span data-ttu-id="0e77f-170">Per altre informazioni sulla creazione di una funzione con script nel portale, vedere Creare la prima funzione nel portale di Azure.For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal.](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)</span><span class="sxs-lookup"><span data-stu-id="0e77f-170">For more information on creating a scripted function in the portal, see [Create your first function in the Azure portal](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function).</span></span>

<span data-ttu-id="0e77f-171">Per eseguire la compilazione dall'interfaccia della riga di comando di Azure, vedere [Creare la prima funzione usando l'interfaccia della riga di comando](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)di Azure.To build from the Azure CLI, see Create your first function using the Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="0e77f-171">To build from the Azure CLI, see [Create your first function using the Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli).</span></span>

<span data-ttu-id="0e77f-172">Per creare una funzione da Visual Studio, vedere [Creare la prima funzione utilizzando Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0e77f-172">To create a function from Visual Studio, see [Create your first function using Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio).</span></span>

## <a name="understand-triggers-and-bindings"></a><span data-ttu-id="0e77f-173">Comprendere i trigger e le associazioni</span><span class="sxs-lookup"><span data-stu-id="0e77f-173">Understand triggers and bindings</span></span>

<span data-ttu-id="0e77f-174">Le funzioni vengono richiamate da un *trigger* e possono averne esattamente uno.</span><span class="sxs-lookup"><span data-stu-id="0e77f-174">Functions are invoked by a *trigger* and can have exactly one.</span></span> <span data-ttu-id="0e77f-175">Oltre a richiamare la funzione, alcuni trigger fungono anche da associazioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-175">In addition to invoking the function, certain triggers also serve as bindings.</span></span> <span data-ttu-id="0e77f-176">È inoltre possibile definire più associazioni oltre al trigger.</span><span class="sxs-lookup"><span data-stu-id="0e77f-176">You may also define multiple bindings in addition to the trigger.</span></span> <span data-ttu-id="0e77f-177">*Le associazioni* forniscono un modo dichiarativo per connettere i dati al codice.</span><span class="sxs-lookup"><span data-stu-id="0e77f-177">*Bindings* provide a declarative way to connect data to your code.</span></span> <span data-ttu-id="0e77f-178">Possono essere passati (input) o ricevere dati (output).</span><span class="sxs-lookup"><span data-stu-id="0e77f-178">They can be passed in (input) or receive data (output).</span></span> <span data-ttu-id="0e77f-179">I trigger e le associazioni semplificano l'utilizzo delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-179">Triggers and bindings make functions easy to work with.</span></span> <span data-ttu-id="0e77f-180">Le associazioni rimuovono l'overhead della creazione manuale di connessioni al database o al file system.</span><span class="sxs-lookup"><span data-stu-id="0e77f-180">Bindings remove the overhead of manually creating database or file system connections.</span></span> <span data-ttu-id="0e77f-181">Tutte le informazioni necessarie per le associazioni sono contenute in un file *functions.json* speciale per gli script o dichiarate con attributi nel codice.</span><span class="sxs-lookup"><span data-stu-id="0e77f-181">All of the information needed for the bindings is contained in a special *functions.json* file for scripts or declared with attributes in code.</span></span>

<span data-ttu-id="0e77f-182">Alcuni trigger comuni includono:Some common triggers include:</span><span class="sxs-lookup"><span data-stu-id="0e77f-182">Some common triggers include:</span></span>

- <span data-ttu-id="0e77f-183">Archiviazione BLOB: richiamare la funzione quando un file o una cartella viene caricata o modificata nell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="0e77f-183">Blob Storage: invoke your function when a file or folder is uploaded or changed in storage.</span></span>
- <span data-ttu-id="0e77f-184">HTTP: richiamare la funzione come un'API REST.</span><span class="sxs-lookup"><span data-stu-id="0e77f-184">HTTP: invoke your function like a REST API.</span></span>
- <span data-ttu-id="0e77f-185">Coda: richiama la funzione quando gli elementi sono presenti in una coda.</span><span class="sxs-lookup"><span data-stu-id="0e77f-185">Queue: invoke your function when items exist in a queue.</span></span>
- <span data-ttu-id="0e77f-186">Timer: richiamare la funzione a cadenza regolare.</span><span class="sxs-lookup"><span data-stu-id="0e77f-186">Timer: invoke your function on a regular cadence.</span></span>

<span data-ttu-id="0e77f-187">Esempi di associazioni includono:Examples of bindings include:</span><span class="sxs-lookup"><span data-stu-id="0e77f-187">Examples of bindings include:</span></span>

- <span data-ttu-id="0e77f-188">CosmosDB: connettiti facilmente al database per caricare o salvare i file.</span><span class="sxs-lookup"><span data-stu-id="0e77f-188">CosmosDB: easily connect to the database to load or save files.</span></span>
- <span data-ttu-id="0e77f-189">Archiviazione tabelle: usare l'archiviazione con chiave/valore dall'app per le funzioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-189">Table Storage: work with key/value storage from your function app.</span></span>
- <span data-ttu-id="0e77f-190">Archiviazione delle code: recupera facilmente gli elementi da una coda o inserisci nuovi elementi nella coda.</span><span class="sxs-lookup"><span data-stu-id="0e77f-190">Queue Storage: easily retrieve items from a queue, or place new items on the queue.</span></span>

<span data-ttu-id="0e77f-191">Il file *functions.json di* esempio seguente definisce un trigger e un'associazione:The following example functions.json file defines a trigger and a binding:</span><span class="sxs-lookup"><span data-stu-id="0e77f-191">The following example *functions.json* file defines a trigger and a binding:</span></span>

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

<span data-ttu-id="0e77f-192">In questo esempio, la funzione viene attivata da `images` una modifica all'archiviazione BLOB nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="0e77f-192">In this example, the function is triggered by a change to blob storage in the `images` container.</span></span> <span data-ttu-id="0e77f-193">Le informazioni per il file vengono passate, pertanto il trigger funge anche da associazione.</span><span class="sxs-lookup"><span data-stu-id="0e77f-193">The information for the file is passed in, so the trigger also acts as a binding.</span></span> <span data-ttu-id="0e77f-194">Esiste un'altra associazione per `images`inserire informazioni in una coda denominata .</span><span class="sxs-lookup"><span data-stu-id="0e77f-194">Another binding exists to put information onto a queue named `images`.</span></span>

<span data-ttu-id="0e77f-195">Di seguito è riportato lo script di C ' per la funzione:</span><span class="sxs-lookup"><span data-stu-id="0e77f-195">Here is the C# script for the function:</span></span>

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

<span data-ttu-id="0e77f-196">L'esempio è una funzione semplice che accetta il nome del file modificato o caricato nell'archiviazione BLOB e lo inserisce in una coda per un'elaborazione successiva.</span><span class="sxs-lookup"><span data-stu-id="0e77f-196">The example is a simple function that takes the name of the file that was modified or uploaded to blob storage, and places it on a queue for later processing.</span></span>

<span data-ttu-id="0e77f-197">Per un elenco completo dei trigger e delle associazioni, vedere Concetti relativi [ai trigger e](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)alle associazioni di Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="0e77f-197">For a full list of triggers and bindings, see [Azure Functions triggers and bindings concepts](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).</span></span>

## <a name="proxies"></a><span data-ttu-id="0e77f-198">Proxy</span><span class="sxs-lookup"><span data-stu-id="0e77f-198">Proxies</span></span>

<span data-ttu-id="0e77f-199">I proxy forniscono funzionalità di reindirizzamento per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0e77f-199">Proxies provide redirect functionality for your application.</span></span> <span data-ttu-id="0e77f-200">I proxy espongono un endpoint ed eseguono il mapping di tale endpoint a un'altra risorsa.</span><span class="sxs-lookup"><span data-stu-id="0e77f-200">Proxies expose an endpoint and map that endpoint to another resource.</span></span> <span data-ttu-id="0e77f-201">Con i proxy, è possibile:</span><span class="sxs-lookup"><span data-stu-id="0e77f-201">With proxies, you can:</span></span>

- <span data-ttu-id="0e77f-202">Reindirizzare una richiesta in ingresso a un altro endpoint.</span><span class="sxs-lookup"><span data-stu-id="0e77f-202">Reroute an incoming request to another endpoint.</span></span>
- <span data-ttu-id="0e77f-203">Modificare la richiesta in ingresso prima che venga passata.</span><span class="sxs-lookup"><span data-stu-id="0e77f-203">Modify the incoming request before it's passed along.</span></span>
- <span data-ttu-id="0e77f-204">Modificare o fornire una risposta.</span><span class="sxs-lookup"><span data-stu-id="0e77f-204">Modify or provide a response.</span></span>

<span data-ttu-id="0e77f-205">I proxy vengono utilizzati per scenari quali:Proxies are used for scenarios such as:</span><span class="sxs-lookup"><span data-stu-id="0e77f-205">Proxies are used for scenarios such as:</span></span>

- <span data-ttu-id="0e77f-206">Semplificazione, accorciamento o modifica dell'URL.</span><span class="sxs-lookup"><span data-stu-id="0e77f-206">Simplifying, shortening, or changing the URL.</span></span>
- <span data-ttu-id="0e77f-207">Fornire un prefisso API coerente a più servizi back-end.</span><span class="sxs-lookup"><span data-stu-id="0e77f-207">Providing a consistent API prefix to multiple back-end services.</span></span>
- <span data-ttu-id="0e77f-208">Risposta a un endpoint in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="0e77f-208">Mocking a response to an endpoint being developed.</span></span>
- <span data-ttu-id="0e77f-209">Fornire una risposta statica a un endpoint noto.</span><span class="sxs-lookup"><span data-stu-id="0e77f-209">Providing a static response to a well-known endpoint.</span></span>
- <span data-ttu-id="0e77f-210">Mantenere coerente un endpoint API durante lo spostamento o la migrazione del back-end.</span><span class="sxs-lookup"><span data-stu-id="0e77f-210">Keeping an API endpoint consistent while the back end is moved or migrated.</span></span>

<span data-ttu-id="0e77f-211">I proxy vengono archiviati come definizioni JSON.</span><span class="sxs-lookup"><span data-stu-id="0e77f-211">Proxies are stored as JSON definitions.</span></span> <span data-ttu-id="0e77f-212">Esempio:</span><span class="sxs-lookup"><span data-stu-id="0e77f-212">Here is an example:</span></span>

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

<span data-ttu-id="0e77f-213">Il `Domain Redirect` proxy accetta una route abbreviata e ne esegue il mapping alla risorsa funzione più lunga.</span><span class="sxs-lookup"><span data-stu-id="0e77f-213">The `Domain Redirect` proxy takes a shortened route and maps it to the longer function resource.</span></span> <span data-ttu-id="0e77f-214">La trasformazione è simile alla:</span><span class="sxs-lookup"><span data-stu-id="0e77f-214">The transformation looks like:</span></span>

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

<span data-ttu-id="0e77f-215">Il `Root` proxy accetta qualsiasi elemento`https://--shorturl--/`inviato all'URL radice ( ) e lo reindirizza al sito della documentazione.</span><span class="sxs-lookup"><span data-stu-id="0e77f-215">The `Root` proxy takes anything sent to the root URL (`https://--shorturl--/`) and redirects it to the documentation site.</span></span>

<span data-ttu-id="0e77f-216">Un esempio di utilizzo dei proxy è illustrato nel video [Azure: Portare l'app nel cloud con Funzioni](https://channel9.msdn.com/events/Connect/2017/E102)di Azure senza server.</span><span class="sxs-lookup"><span data-stu-id="0e77f-216">An example of using proxies is shown in the video [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102).</span></span> <span data-ttu-id="0e77f-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span><span class="sxs-lookup"><span data-stu-id="0e77f-217">In real time, an ASP.NET Core application running on local SQL Server is migrated to the Azure Cloud.</span></span> <span data-ttu-id="0e77f-218">I proxy vengono utilizzati per facilitare il refactoring di un progetto API Web tradizionale per l'utilizzo delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="0e77f-218">Proxies are used to help refactor a traditional Web API project to use functions.</span></span>

<span data-ttu-id="0e77f-219">Per altre informazioni sui proxy, vedere Usare i proxy di Funzioni di Azure.For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span><span class="sxs-lookup"><span data-stu-id="0e77f-219">For more information about Proxies, see [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0e77f-220">[Successivo](azure-serverless-platform.md)
>[precedente](application-insights.md)</span><span class="sxs-lookup"><span data-stu-id="0e77f-220">[Previous](azure-serverless-platform.md)
[Next](application-insights.md)</span></span>
