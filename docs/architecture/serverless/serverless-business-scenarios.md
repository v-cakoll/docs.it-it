---
title: Scenari aziendali di esempio e casi d'uso per le app senza server
description: Impara a usare senza server un approccio pratico accedendo ad esempi che variano dall'elaborazione di immagini al supporto per dispositivi mobili e alle pipeline ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158450"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="e6ef4-103">Scenari di business serverless e casi d'uso</span><span class="sxs-lookup"><span data-stu-id="e6ef4-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="e6ef4-104">Esistono molti casi d'uso e scenari per le applicazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="e6ef4-105">Questo capitolo include esempi che illustrano i diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="e6ef4-106">Gli scenari includono collegamenti alla documentazione correlata e ai repository di codice sorgente pubblico.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="e6ef4-107">Gli esempi in questo capitolo consentono di iniziare a creare e implementare soluzioni senza server.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="big-data-processing"></a><span data-ttu-id="e6ef4-108">Elaborazione di Big Data</span><span class="sxs-lookup"><span data-stu-id="e6ef4-108">Big data processing</span></span>

![Diagramma di mapping/riduzione](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

<span data-ttu-id="e6ef4-110">Questo esempio USA senza server per eseguire un'operazione di mapping/riduzione su un set di Big Data.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-110">This example uses serverless to do a map/reduce operation on a big data set.</span></span> <span data-ttu-id="e6ef4-111">Determina la velocità media delle corse dei taxi gialli di New York al giorno nel 2017.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-111">It determines the average speed of New York Yellow taxi trips per day in 2017.</span></span>

[<span data-ttu-id="e6ef4-112">Elaborazione di Big Data: MapReduce senza server in Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-112">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a><span data-ttu-id="e6ef4-113">Creare applicazioni senza server: Lab pratico</span><span class="sxs-lookup"><span data-stu-id="e6ef4-113">Create serverless applications: hands-on lab</span></span>

<span data-ttu-id="e6ef4-114">Informazioni su come usare le funzioni per eseguire la logica sul lato server e creare architetture senza server.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-114">Learn how to use functions to execute server-side logic and build serverless architectures.</span></span>

- <span data-ttu-id="e6ef4-115">Scelta del migliore servizio di Azure per la tua azienda</span><span class="sxs-lookup"><span data-stu-id="e6ef4-115">Choosing the best Azure service for your business</span></span>
- <span data-ttu-id="e6ef4-116">Creazione di funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-116">Creating Azure Functions</span></span>
- <span data-ttu-id="e6ef4-117">Trigger</span><span class="sxs-lookup"><span data-stu-id="e6ef4-117">Using triggers</span></span>
- <span data-ttu-id="e6ef4-118">Funzioni di concatenamento</span><span class="sxs-lookup"><span data-stu-id="e6ef4-118">Chaining functions</span></span>
- <span data-ttu-id="e6ef4-119">Flussi di lavoro a esecuzione prolungata</span><span class="sxs-lookup"><span data-stu-id="e6ef4-119">Long-running workflows</span></span>
- <span data-ttu-id="e6ef4-120">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="e6ef4-120">Monitoring</span></span>
- <span data-ttu-id="e6ef4-121">Sviluppo, test e distribuzione</span><span class="sxs-lookup"><span data-stu-id="e6ef4-121">Development, testing, and deployment</span></span>

[<span data-ttu-id="e6ef4-122">Crea applicazioni senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-122">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a><span data-ttu-id="e6ef4-123">Recensioni dei clienti</span><span class="sxs-lookup"><span data-stu-id="e6ef4-123">Customer reviews</span></span>

<span data-ttu-id="e6ef4-124">Questo esempio mostra i nuovi strumenti di funzioni di Azure per le librerie di classi C# in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-124">This sample showcases the new Azure Functions tooling for C# Class Libraries in Visual Studio.</span></span> <span data-ttu-id="e6ef4-125">Creare un sito Web in cui i clienti inviano recensioni di prodotti archiviate in BLOB di archiviazione di Azure e CosmosDB.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-125">Create a website where customers submit product reviews that are stored in Azure storage blobs and CosmosDB.</span></span> <span data-ttu-id="e6ef4-126">Aggiungere una funzione di Azure per eseguire la moderazione automatica delle revisioni dei clienti usando servizi cognitivi di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-126">Add an Azure Function to perform automated moderation of the customer reviews using Azure Cognitive Services.</span></span> <span data-ttu-id="e6ef4-127">Usare una coda di archiviazione di Azure per separare il sito Web dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-127">Use an Azure storage queue to decouple the website from the function.</span></span>

[<span data-ttu-id="e6ef4-128">App Customer revisioni con servizi cognitivi</span><span class="sxs-lookup"><span data-stu-id="e6ef4-128">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a><span data-ttu-id="e6ef4-129">Supporto per immagini Linux Docker</span><span class="sxs-lookup"><span data-stu-id="e6ef4-129">Docker Linux image support</span></span>

<span data-ttu-id="e6ef4-130">Questo esempio illustra come creare un `Dockerfile` per compilare ed eseguire funzioni di Azure in un contenitore Docker Linux.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-130">This sample demonstrates how to create a `Dockerfile` to build and run Azure Functions on a Linux Docker container.</span></span>

[<span data-ttu-id="e6ef4-131">Funzioni di Azure in Linux</span><span class="sxs-lookup"><span data-stu-id="e6ef4-131">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a><span data-ttu-id="e6ef4-132">Elaborazione e convalida di file</span><span class="sxs-lookup"><span data-stu-id="e6ef4-132">File processing and validation</span></span>

<span data-ttu-id="e6ef4-133">In questo esempio viene analizzato un set di file CSV da clienti ipotetici.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-133">This example parses a set of CSV files from hypothetical customers.</span></span> <span data-ttu-id="e6ef4-134">Garantisce che tutti i file necessari per un "batch" del cliente siano pronti, quindi convalida la struttura di ogni file.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-134">It ensures that all files required for a customer "batch" are ready, then validates the structure of each file.</span></span> <span data-ttu-id="e6ef4-135">Vengono presentate diverse soluzioni usando funzioni di Azure, app per la logica e Durable Functions.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-135">Different solutions are presented using Azure Functions, Logic Apps, and Durable Functions.</span></span>

[<span data-ttu-id="e6ef4-136">Elaborazione e convalida di file con funzioni di Azure, app per la logica e Durable Functions</span><span class="sxs-lookup"><span data-stu-id="e6ef4-136">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a><span data-ttu-id="e6ef4-137">Visualizzazione dei dati del gioco</span><span class="sxs-lookup"><span data-stu-id="e6ef4-137">Game data visualization</span></span>

![Telemetria del gioco](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

<span data-ttu-id="e6ef4-139">Un esempio di come uno sviluppatore può implementare una soluzione di visualizzazione dati nell'editor per il gioco.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-139">An example of how a developer could implement an in-editor data visualization solution for their game.</span></span> <span data-ttu-id="e6ef4-140">In realtà, un plug-in Unreal Engine 4 e un plug-in Unity sono stati sviluppati usando questo esempio come back-end.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-140">In fact, an Unreal Engine 4 Plugin and Unity Plugin were developed using this sample as its backend.</span></span> <span data-ttu-id="e6ef4-141">Il componente del servizio è indipendente dal motore di gioco.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-141">The service component is game engine agnostic.</span></span>

[<span data-ttu-id="e6ef4-142">Visualizzazione telemetria del gioco in-Editor</span><span class="sxs-lookup"><span data-stu-id="e6ef4-142">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a><span data-ttu-id="e6ef4-143">GraphQL</span><span class="sxs-lookup"><span data-stu-id="e6ef4-143">GraphQL</span></span>

<span data-ttu-id="e6ef4-144">Creare una funzione senza server che espone un'API GraphQL.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-144">Create a serverless function that exposes a GraphQL API.</span></span>

[<span data-ttu-id="e6ef4-145">Funzioni senza server per GraphQL</span><span class="sxs-lookup"><span data-stu-id="e6ef4-145">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a><span data-ttu-id="e6ef4-146">Inoltro Reliable Edge di Internet delle cose</span><span class="sxs-lookup"><span data-stu-id="e6ef4-146">Internet of Things (IoT) reliable edge relay</span></span>

![Architettura dell'it](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

<span data-ttu-id="e6ef4-148">Questo esempio implementa un nuovo protocollo di comunicazione per consentire la comunicazione upstream affidabile dai dispositivi Internet.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-148">This sample implements a new communication protocol to enable reliable upstream communication from IoT devices.</span></span> <span data-ttu-id="e6ef4-149">Automatizza il rilevamento e il recupero del gap di dati.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-149">It automates data gap detection and backfill.</span></span>

[<span data-ttu-id="e6ef4-150">Inoltro Reliable Edge</span><span class="sxs-lookup"><span data-stu-id="e6ef4-150">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a><span data-ttu-id="e6ef4-151">Architettura di riferimento per i microservizi</span><span class="sxs-lookup"><span data-stu-id="e6ef4-151">Microservices reference architecture</span></span>

![Architettura di riferimento](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

<span data-ttu-id="e6ef4-153">Un'architettura di riferimento che illustra il processo decisionale necessario per la progettazione, lo sviluppo e la distribuzione dell'applicazione rideshare by Relecloud (una società fittizia).</span><span class="sxs-lookup"><span data-stu-id="e6ef4-153">A reference architecture that walks you through the decision-making process involved in designing, developing, and delivering the Rideshare by Relecloud application (a fictitious company).</span></span> <span data-ttu-id="e6ef4-154">Sono incluse istruzioni pratiche per la configurazione e la distribuzione di tutti i componenti dell'architettura.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-154">It includes hands-on instructions for configuring and deploying all of the architecture's components.</span></span>

[<span data-ttu-id="e6ef4-155">Architettura di riferimento per microservizi senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-155">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a><span data-ttu-id="e6ef4-156">Esegui la migrazione delle app console a senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-156">Migrate console apps to serverless</span></span>

<span data-ttu-id="e6ef4-157">Questo esempio è una funzione generica`.csx` (file) che può essere usata per convertire qualsiasi applicazione console in un servizio Web http in funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-157">This sample is a generic function (`.csx` file) that can be used to convert any console application to an HTTP web service in Azure Functions.</span></span> <span data-ttu-id="e6ef4-158">È sufficiente modificare un file di configurazione e specificare i `.exe`parametri di input che verranno passati come argomenti a.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-158">All you have to do is edit a configuration file and specify what input parameters will be passed as arguments to the `.exe`.</span></span>

[<span data-ttu-id="e6ef4-159">Eseguire app console in funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-159">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a><span data-ttu-id="e6ef4-160">Senza server per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="e6ef4-160">Serverless for mobile</span></span>

<span data-ttu-id="e6ef4-161">Funzioni di Azure è facile da implementare e gestire e accessibile tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-161">Azure Functions are easy to implement and maintain, and accessible through HTTP.</span></span> <span data-ttu-id="e6ef4-162">Sono un ottimo modo per implementare un'API per un'applicazione per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-162">They are a great way to implement an API for a mobile application.</span></span> <span data-ttu-id="e6ef4-163">Microsoft offre ottimi strumenti multipiattaforma per iOS, Android e Windows con Novell.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-163">Microsoft offers great cross-platform tools for iOS, Android, and Windows with Xamarin.</span></span> <span data-ttu-id="e6ef4-164">Di conseguenza, Novell e funzioni di Azure operano insieme.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-164">As such, Xamarin and Azure Functions are working great together.</span></span> <span data-ttu-id="e6ef4-165">Questo articolo illustra come implementare una funzione di Azure nella portale di Azure o in Visual Studio inizialmente e creare un client multipiattaforma con Novell. Forms in esecuzione in Android, iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-165">This article shows how to implement an Azure Function in the Azure portal or in Visual Studio at first, and build a cross-platform client with Xamarin.Forms running on Android, iOS, and Windows.</span></span>

[<span data-ttu-id="e6ef4-166">Implementazione di una semplice funzione di Azure con un client Novell. Forms</span><span class="sxs-lookup"><span data-stu-id="e6ef4-166">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a><span data-ttu-id="e6ef4-167">Messaggistica senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-167">Serverless messaging</span></span>

<span data-ttu-id="e6ef4-168">Questo esempio illustra come usare il modello di fan-out di Durable Functions per caricare un numero arbitrario di messaggi in un numero qualsiasi di sessioni/partizioni.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-168">This sample shows how to utilize Durable Functions' fan-out pattern to load an arbitrary number of messages across any number of sessions/partitions.</span></span> <span data-ttu-id="e6ef4-169">È destinato a bus di servizio, Hub eventi o code di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-169">It targets Service Bus, Event Hubs, or Storage Queues.</span></span> <span data-ttu-id="e6ef4-170">L'esempio aggiunge anche la possibilità di utilizzare tali messaggi con un'altra funzione di Azure e di caricare i dati temporali risultanti in un altro hub eventi.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-170">The sample also adds the ability to consume those messages with another Azure Function and load the resulting timing data in to another Event Hub.</span></span> <span data-ttu-id="e6ef4-171">I dati vengono quindi inseriti in servizi di analisi come Azure Esplora dati.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-171">The data is then ingested into analytics services like Azure Data Explorer.</span></span>

[<span data-ttu-id="e6ef4-172">Produrre e utilizzare messaggi tramite il bus di servizio, Hub eventi e le code di archiviazione con funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-172">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a><span data-ttu-id="e6ef4-173">Risorse consigliate</span><span class="sxs-lookup"><span data-stu-id="e6ef4-173">Recommended resources</span></span>

- [<span data-ttu-id="e6ef4-174">Funzioni di Azure in Linux</span><span class="sxs-lookup"><span data-stu-id="e6ef4-174">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [<span data-ttu-id="e6ef4-175">Elaborazione di Big Data: MapReduce senza server in Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-175">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [<span data-ttu-id="e6ef4-176">Crea applicazioni senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-176">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [<span data-ttu-id="e6ef4-177">App Customer revisioni con servizi cognitivi</span><span class="sxs-lookup"><span data-stu-id="e6ef4-177">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [<span data-ttu-id="e6ef4-178">Elaborazione e convalida di file con funzioni di Azure, app per la logica e Durable Functions</span><span class="sxs-lookup"><span data-stu-id="e6ef4-178">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [<span data-ttu-id="e6ef4-179">Implementazione di una semplice funzione di Azure con un client Novell. Forms</span><span class="sxs-lookup"><span data-stu-id="e6ef4-179">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [<span data-ttu-id="e6ef4-180">Visualizzazione telemetria del gioco in-Editor</span><span class="sxs-lookup"><span data-stu-id="e6ef4-180">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [<span data-ttu-id="e6ef4-181">Inoltro Reliable Edge</span><span class="sxs-lookup"><span data-stu-id="e6ef4-181">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [<span data-ttu-id="e6ef4-182">Produrre e utilizzare messaggi tramite il bus di servizio, Hub eventi e le code di archiviazione con funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-182">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [<span data-ttu-id="e6ef4-183">Eseguire app console in funzioni di Azure</span><span class="sxs-lookup"><span data-stu-id="e6ef4-183">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [<span data-ttu-id="e6ef4-184">Funzioni senza server per GraphQL</span><span class="sxs-lookup"><span data-stu-id="e6ef4-184">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [<span data-ttu-id="e6ef4-185">Architettura di riferimento per microservizi senza server</span><span class="sxs-lookup"><span data-stu-id="e6ef4-185">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
><span data-ttu-id="e6ef4-186">[Precedente](orchestration-patterns.md)
>[successivo](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="e6ef4-186">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
