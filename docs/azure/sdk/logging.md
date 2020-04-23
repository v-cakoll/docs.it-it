---
title: Registrazione con Azure SDK per .NETLogging with the Azure SDK for .NET
description: Informazioni su come abilitare la registrazione con le librerie client di Azure SDK per .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "82071990"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="e105c-103">Registrazione con Azure SDK per .NETLogging with the Azure SDK for .NET</span><span class="sxs-lookup"><span data-stu-id="e105c-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="e105c-104">Le librerie client di [Azure SDK](https://azure.microsoft.com/downloads/) for .NET includono la possibilità di registrare le operazioni della libreria client.</span><span class="sxs-lookup"><span data-stu-id="e105c-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="e105c-105">In questo modo è possibile monitorare le richieste di I/O e le risposte che le librerie client stanno effettuando ai servizi di Azure.This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span><span class="sxs-lookup"><span data-stu-id="e105c-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="e105c-106">In genere, i log vengono utilizzati per eseguire il debug o diagnosticare problemi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e105c-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="e105c-107">Questo articolo descrive tre approcci per abilitare la registrazione con Azure SDK per .NET:This article describes three approaches to enable logging with the Azure SDK for .NET:</span><span class="sxs-lookup"><span data-stu-id="e105c-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="e105c-108">Accedere alla finestra della console</span><span class="sxs-lookup"><span data-stu-id="e105c-108">Log to the console window</span></span>
- <span data-ttu-id="e105c-109">Registra nelle tracce di diagnostica .NETLog to .NET diagnostics traces</span><span class="sxs-lookup"><span data-stu-id="e105c-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="e105c-110">Configurare la registrazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="e105c-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e105c-111">Questo articolo si applica alle librerie client che usano le versioni più recenti di Azure SDK per .NET.</span><span class="sxs-lookup"><span data-stu-id="e105c-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="e105c-112">Per verificare se una libreria è supportata, fare riferimento all'elenco delle versioni più recenti di [Azure SDK.](https://azure.github.io/azure-sdk/releases/latest/index.html)</span><span class="sxs-lookup"><span data-stu-id="e105c-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="e105c-113">Se l'applicazione usa una versione precedente delle librerie client di Azure SDK, fare riferimento a istruzioni specifiche nella documentazione del servizio applicabile.</span><span class="sxs-lookup"><span data-stu-id="e105c-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="e105c-114">Informazioni sui log</span><span class="sxs-lookup"><span data-stu-id="e105c-114">Log information</span></span>

<span data-ttu-id="e105c-115">L'SDK registra le informazioni seguenti, sanofizzando la query dei parametri e i valori dell'intestazione per rimuovere i dati personali.</span><span class="sxs-lookup"><span data-stu-id="e105c-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="e105c-116">Voce del registro richieste HTTP:</span><span class="sxs-lookup"><span data-stu-id="e105c-116">HTTP request log entry:</span></span>

- <span data-ttu-id="e105c-117">ID univoco</span><span class="sxs-lookup"><span data-stu-id="e105c-117">Unique ID</span></span>
- <span data-ttu-id="e105c-118">Metodo HTTP</span><span class="sxs-lookup"><span data-stu-id="e105c-118">HTTP method</span></span>
- <span data-ttu-id="e105c-119">URI</span><span class="sxs-lookup"><span data-stu-id="e105c-119">URI</span></span>
- <span data-ttu-id="e105c-120">Intestazioni delle richieste in uscita</span><span class="sxs-lookup"><span data-stu-id="e105c-120">Outgoing request headers</span></span>

<span data-ttu-id="e105c-121">Voce del registro risposte HTTP:</span><span class="sxs-lookup"><span data-stu-id="e105c-121">HTTP response log entry:</span></span>

- <span data-ttu-id="e105c-122">Durata dell'operazione di I/O (tempo trascorso)</span><span class="sxs-lookup"><span data-stu-id="e105c-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="e105c-123">ID richiesta</span><span class="sxs-lookup"><span data-stu-id="e105c-123">Request ID</span></span>
- <span data-ttu-id="e105c-124">Stato codice HTTP</span><span class="sxs-lookup"><span data-stu-id="e105c-124">HTTP status code</span></span>
- <span data-ttu-id="e105c-125">Frase motivo HTTP</span><span class="sxs-lookup"><span data-stu-id="e105c-125">HTTP reason phrase</span></span>
- <span data-ttu-id="e105c-126">Intestazioni della risposta</span><span class="sxs-lookup"><span data-stu-id="e105c-126">Response headers</span></span>
- <span data-ttu-id="e105c-127">Informazioni sull'errore, se applicabile</span><span class="sxs-lookup"><span data-stu-id="e105c-127">Error information, when applicable</span></span>

<span data-ttu-id="e105c-128">Per il contenuto di richiesta e risposta:</span><span class="sxs-lookup"><span data-stu-id="e105c-128">For request and response content:</span></span>

- <span data-ttu-id="e105c-129">Flusso di contenuto come testo o byte a seconda dell'intestazione Content-Type.</span><span class="sxs-lookup"><span data-stu-id="e105c-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="e105c-130">[! NOTA: la registrazione del contenuto è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e105c-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="e105c-131">Per attivarla, `Diagnostics.IsLoggingContentEnabled` `true` impostare su in `ClientOptions`.</span><span class="sxs-lookup"><span data-stu-id="e105c-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="e105c-132">I registri eventi vengono restituiti in genere a uno di questi tre livelli:Event logs are output usually at one of these three levels:</span><span class="sxs-lookup"><span data-stu-id="e105c-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="e105c-133">Informazioni sugli eventi di richiesta e risposta</span><span class="sxs-lookup"><span data-stu-id="e105c-133">Informational for request and response events</span></span>
- <span data-ttu-id="e105c-134">Avviso per gli errori</span><span class="sxs-lookup"><span data-stu-id="e105c-134">Warning for errors</span></span>
- <span data-ttu-id="e105c-135">Verbose per messaggi dettagliati e registrazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="e105c-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="e105c-136">Abilitare la registrazione con i metodi incorporatiEnable logging with built-in methods</span><span class="sxs-lookup"><span data-stu-id="e105c-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="e105c-137">Le librerie client di Azure SDK for .NET registrano [ `EventSource` ](/dotnet/api/system.diagnostics.tracing.eventsource)gli eventi in Event Tracing for Windows (ETW) tramite la classe , che è tipica di .NET.</span><span class="sxs-lookup"><span data-stu-id="e105c-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="e105c-138">Le origini eventi consentono di usare la registrazione strutturata nel codice dell'applicazione con un overhead di prestazioni minimo.</span><span class="sxs-lookup"><span data-stu-id="e105c-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="e105c-139">Per accedere a questi registri eventi, è necessario registrare i listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="e105c-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="e105c-140">L'SDK `Azure.Core.Diagnostics.AzureEventSourceListener` include la classe (definita nel pacchetto Azure.Core NuGet), che contiene due `CreateConsoleLogger` metodi `CreateTraceLogger`statici che semplificano la registrazione completa per l'applicazione .NET: e .</span><span class="sxs-lookup"><span data-stu-id="e105c-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="e105c-141">Questi metodi accettano un parametro facoltativo che specifica un livello di log.</span><span class="sxs-lookup"><span data-stu-id="e105c-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="e105c-142">Accedere alla finestra della console</span><span class="sxs-lookup"><span data-stu-id="e105c-142">Log to the console window</span></span>

<span data-ttu-id="e105c-143">Un principio di base delle librerie client di Azure SDK for .NET consiste nel semplificare la possibilità di visualizzare log completi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="e105c-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="e105c-144">Il `CreateConsoleLogger` metodo consente di inviare i log alla finestra della console con una singola riga di codice:The method allows you to send logs to the console window with a single line of code:</span><span class="sxs-lookup"><span data-stu-id="e105c-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="e105c-145">Eseguire il log alle tracce diagnosticheLog to diagnostic traces</span><span class="sxs-lookup"><span data-stu-id="e105c-145">Log to diagnostic traces</span></span>

<span data-ttu-id="e105c-146">Se si implementano listener di `CreateTraceLogger` traccia, è possibile utilizzare il metodo[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)per registrare il meccanismo di traccia eventi .NET standard ( ).</span><span class="sxs-lookup"><span data-stu-id="e105c-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="e105c-147">Per ulteriori informazioni sull'analisi degli eventi in .NET, vedere [Listener di traccia](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span><span class="sxs-lookup"><span data-stu-id="e105c-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="e105c-148">In questo esempio viene specificato un livello di log di livello dettagliato:This example specifies a log level of verbose:</span><span class="sxs-lookup"><span data-stu-id="e105c-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="e105c-149">Configurare la registrazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="e105c-149">Configure custom logging</span></span>

<span data-ttu-id="e105c-150">Come accennato in precedenza, è necessario registrare i listener di eventi per ricevere messaggi di log da Azure SDK per .NET.</span><span class="sxs-lookup"><span data-stu-id="e105c-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="e105c-151">Se non si desidera implementare la registrazione completa utilizzando uno dei metodi `AzureEventSourceListener` semplificati sopra descritti, è possibile costruire un'istanza della classe e passarle una funzione di callback scritta.</span><span class="sxs-lookup"><span data-stu-id="e105c-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="e105c-152">Questo metodo riceverà messaggi di log che è possibile elaborare in modo che sia necessario.</span><span class="sxs-lookup"><span data-stu-id="e105c-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="e105c-153">Inoltre, quando si costruisce l'istanza, è possibile specificare i livelli di log da includere.</span><span class="sxs-lookup"><span data-stu-id="e105c-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="e105c-154">L'esempio seguente crea un listener di eventi che accede alla console con un messaggio personalizzato e viene filtrato in base agli eventi principali di Azure del livello dettagliato.</span><span class="sxs-lookup"><span data-stu-id="e105c-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a><span data-ttu-id="e105c-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e105c-155">Next steps</span></span>

- [<span data-ttu-id="e105c-156">Abilitare la registrazione diagnostica per le app nel servizio app di AzureEnable diagnostics logging for apps in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="e105c-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="e105c-157">Esaminare le opzioni di controllo e registrazione della sicurezza di [AzureReview Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span><span class="sxs-lookup"><span data-stu-id="e105c-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="e105c-158">Informazioni su come usare i log della [piattaforma AzureLearn](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) how to work with Azure platform logs</span><span class="sxs-lookup"><span data-stu-id="e105c-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="e105c-159">Ulteriori informazioni sulla registrazione e la traccia di [.NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span><span class="sxs-lookup"><span data-stu-id="e105c-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
