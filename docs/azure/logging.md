---
title: Registrazione con Azure SDK per .NET
description: Informazioni su come abilitare la registrazione con le librerie client di Azure SDK per .NET
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: 0b255713bc9c13e0cbdaeb25a3d0fe46e91e815d
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416032"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="3ba21-103">Registrazione con Azure SDK per .NET</span><span class="sxs-lookup"><span data-stu-id="3ba21-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="3ba21-104">Le librerie client di [Azure SDK](https://azure.microsoft.com/downloads/) per .NET includono la possibilità di registrare le operazioni della libreria client.</span><span class="sxs-lookup"><span data-stu-id="3ba21-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="3ba21-105">In questo modo è possibile monitorare le richieste di I/O e le risposte effettuate dalle librerie client ai servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="3ba21-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="3ba21-106">I log vengono in genere usati per eseguire il debug o diagnosticare i problemi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="3ba21-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="3ba21-107">Questo articolo descrive tre approcci per abilitare la registrazione con Azure SDK per .NET:</span><span class="sxs-lookup"><span data-stu-id="3ba21-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="3ba21-108">Accedi alla finestra della console</span><span class="sxs-lookup"><span data-stu-id="3ba21-108">Log to the console window</span></span>
- <span data-ttu-id="3ba21-109">Accedi alle tracce di diagnostica .NET</span><span class="sxs-lookup"><span data-stu-id="3ba21-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="3ba21-110">Configurare la registrazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3ba21-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ba21-111">Questo articolo si applica alle librerie client che usano le versioni più recenti di Azure SDK per .NET.</span><span class="sxs-lookup"><span data-stu-id="3ba21-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="3ba21-112">Per verificare se una libreria è supportata, vedere l'elenco delle [versioni più recenti di Azure SDK](https://azure.github.io/azure-sdk/releases/latest/index.html).</span><span class="sxs-lookup"><span data-stu-id="3ba21-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="3ba21-113">Se l'applicazione usa una versione precedente delle librerie client di Azure SDK, fare riferimento a istruzioni specifiche nella documentazione del servizio applicabile.</span><span class="sxs-lookup"><span data-stu-id="3ba21-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="3ba21-114">Informazioni sui log</span><span class="sxs-lookup"><span data-stu-id="3ba21-114">Log information</span></span>

<span data-ttu-id="3ba21-115">L'SDK registra le informazioni seguenti, purificando i valori delle intestazioni e delle query dei parametri per rimuovere i dati personali.</span><span class="sxs-lookup"><span data-stu-id="3ba21-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="3ba21-116">Voce di log richiesta HTTP:</span><span class="sxs-lookup"><span data-stu-id="3ba21-116">HTTP request log entry:</span></span>

- <span data-ttu-id="3ba21-117">ID univoco</span><span class="sxs-lookup"><span data-stu-id="3ba21-117">Unique ID</span></span>
- <span data-ttu-id="3ba21-118">Metodo HTTP</span><span class="sxs-lookup"><span data-stu-id="3ba21-118">HTTP method</span></span>
- <span data-ttu-id="3ba21-119">URI</span><span class="sxs-lookup"><span data-stu-id="3ba21-119">URI</span></span>
- <span data-ttu-id="3ba21-120">Intestazioni delle richieste in uscita</span><span class="sxs-lookup"><span data-stu-id="3ba21-120">Outgoing request headers</span></span>

<span data-ttu-id="3ba21-121">Voce di log della risposta HTTP:</span><span class="sxs-lookup"><span data-stu-id="3ba21-121">HTTP response log entry:</span></span>

- <span data-ttu-id="3ba21-122">Durata dell'operazione di I/O (tempo trascorso)</span><span class="sxs-lookup"><span data-stu-id="3ba21-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="3ba21-123">ID richiesta</span><span class="sxs-lookup"><span data-stu-id="3ba21-123">Request ID</span></span>
- <span data-ttu-id="3ba21-124">Codice di stato HTTP</span><span class="sxs-lookup"><span data-stu-id="3ba21-124">HTTP status code</span></span>
- <span data-ttu-id="3ba21-125">Frase del motivo HTTP</span><span class="sxs-lookup"><span data-stu-id="3ba21-125">HTTP reason phrase</span></span>
- <span data-ttu-id="3ba21-126">Intestazioni di risposta</span><span class="sxs-lookup"><span data-stu-id="3ba21-126">Response headers</span></span>
- <span data-ttu-id="3ba21-127">Informazioni sull'errore, quando applicabile</span><span class="sxs-lookup"><span data-stu-id="3ba21-127">Error information, when applicable</span></span>

<span data-ttu-id="3ba21-128">Per il contenuto della richiesta e della risposta:</span><span class="sxs-lookup"><span data-stu-id="3ba21-128">For request and response content:</span></span>

- <span data-ttu-id="3ba21-129">Flusso di contenuto come testo o byte in base all'intestazione Content-Type.</span><span class="sxs-lookup"><span data-stu-id="3ba21-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="3ba21-130">[! Nota} la registrazione del contenuto è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ba21-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="3ba21-131">Per abilitarla, impostare `Diagnostics.IsLoggingContentEnabled` su `true` in `ClientOptions` .</span><span class="sxs-lookup"><span data-stu-id="3ba21-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="3ba21-132">I registri eventi vengono in genere restituiti in uno dei tre livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ba21-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="3ba21-133">Informazioni per eventi di richiesta e risposta</span><span class="sxs-lookup"><span data-stu-id="3ba21-133">Informational for request and response events</span></span>
- <span data-ttu-id="3ba21-134">Avviso per errori</span><span class="sxs-lookup"><span data-stu-id="3ba21-134">Warning for errors</span></span>
- <span data-ttu-id="3ba21-135">Dettagliato per i messaggi dettagliati e la registrazione del contenuto</span><span class="sxs-lookup"><span data-stu-id="3ba21-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="3ba21-136">Abilitare la registrazione con i metodi predefiniti</span><span class="sxs-lookup"><span data-stu-id="3ba21-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="3ba21-137">Le librerie client di Azure SDK per .NET registrano gli eventi Event Tracing for Windows (ETW) tramite la [ `EventSource` classe](/dotnet/api/system.diagnostics.tracing.eventsource), che è tipica per .NET.</span><span class="sxs-lookup"><span data-stu-id="3ba21-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="3ba21-138">Le origini eventi consentono di usare la registrazione strutturata nel codice dell'applicazione con un overhead minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3ba21-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="3ba21-139">Per ottenere l'accesso a questi registri eventi, è necessario registrare i listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="3ba21-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="3ba21-140">L'SDK include la `Azure.Core.Diagnostics.AzureEventSourceListener` classe (definita nel pacchetto NuGet di Azure. Core), che contiene due metodi statici che semplificano la registrazione completa per l'applicazione .NET: `CreateConsoleLogger` e `CreateTraceLogger` .</span><span class="sxs-lookup"><span data-stu-id="3ba21-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="3ba21-141">Questi metodi accettano un parametro facoltativo che specifica un livello di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3ba21-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="3ba21-142">Accedi alla finestra della console</span><span class="sxs-lookup"><span data-stu-id="3ba21-142">Log to the console window</span></span>

<span data-ttu-id="3ba21-143">Un principio fondamentale delle librerie client di Azure SDK per .NET consiste nel semplificare la possibilità di visualizzare i log completi in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="3ba21-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="3ba21-144">Il `CreateConsoleLogger` metodo consente di inviare i log alla finestra della console con una sola riga di codice:</span><span class="sxs-lookup"><span data-stu-id="3ba21-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="3ba21-145">Accedi alle tracce di diagnostica</span><span class="sxs-lookup"><span data-stu-id="3ba21-145">Log to diagnostic traces</span></span>

<span data-ttu-id="3ba21-146">Se si implementano i listener di traccia, è possibile usare il `CreateTraceLogger` metodo per accedere al meccanismo di traccia eventi .NET standard ( [`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing) ).</span><span class="sxs-lookup"><span data-stu-id="3ba21-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="3ba21-147">Per ulteriori informazioni sull'analisi degli eventi in .NET, vedere [listener di traccia](../framework/debug-trace-profile/trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="3ba21-147">For more information on event tracing in .NET, see [Trace Listeners](../framework/debug-trace-profile/trace-listeners.md).</span></span> <span data-ttu-id="3ba21-148">Questo esempio specifica un livello di log dettagliato:</span><span class="sxs-lookup"><span data-stu-id="3ba21-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="3ba21-149">Configurare la registrazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3ba21-149">Configure custom logging</span></span>

<span data-ttu-id="3ba21-150">Come indicato in precedenza, è necessario registrare i listener di eventi per ricevere i messaggi di log da Azure SDK per .NET.</span><span class="sxs-lookup"><span data-stu-id="3ba21-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="3ba21-151">Se non si desidera implementare la registrazione completa utilizzando uno dei metodi semplificati descritti in precedenza, è possibile creare un'istanza della `AzureEventSourceListener` classe e passargli una funzione di callback che si scrive.</span><span class="sxs-lookup"><span data-stu-id="3ba21-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="3ba21-152">Questo metodo riceverà i messaggi di log che è possibile elaborare, tuttavia è necessario.</span><span class="sxs-lookup"><span data-stu-id="3ba21-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="3ba21-153">Inoltre, quando si crea l'istanza di, è possibile specificare i livelli di registrazione da includere.</span><span class="sxs-lookup"><span data-stu-id="3ba21-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="3ba21-154">Nell'esempio seguente viene creato un listener di eventi che accede alla console con un messaggio personalizzato e viene filtrato in base agli eventi di Azure core del livello dettagliato.</span><span class="sxs-lookup"><span data-stu-id="3ba21-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="3ba21-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3ba21-155">Next steps</span></span>

- [<span data-ttu-id="3ba21-156">Abilitare la registrazione diagnostica per le app nel servizio app Azure</span><span class="sxs-lookup"><span data-stu-id="3ba21-156">Enable diagnostics logging for apps in Azure App Service</span></span>](/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="3ba21-157">Esaminare [le opzioni di controllo e registrazione sicurezza di Azure](/azure/security/fundamentals/log-audit)</span><span class="sxs-lookup"><span data-stu-id="3ba21-157">Review [Azure security logging and auditing](/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="3ba21-158">Informazioni su come usare i [log della piattaforma Azure](/azure/azure-monitor/platform/platform-logs-overview)</span><span class="sxs-lookup"><span data-stu-id="3ba21-158">Learn how to work with [Azure platform logs](/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="3ba21-159">Scopri di più sulla [registrazione e la traccia di .NET Core](../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="3ba21-159">Read more about [.NET Core logging and tracing](../core/diagnostics/logging-tracing.md)</span></span>
