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
# <a name="logging-with-the-azure-sdk-for-net"></a>Registrazione con Azure SDK per .NETLogging with the Azure SDK for .NET

Le librerie client di [Azure SDK](https://azure.microsoft.com/downloads/) for .NET includono la possibilità di registrare le operazioni della libreria client. In questo modo è possibile monitorare le richieste di I/O e le risposte che le librerie client stanno effettuando ai servizi di Azure.This allows you to monitor I/O requests and responses that client libraries are making to Azure services. In genere, i log vengono utilizzati per eseguire il debug o diagnosticare problemi di comunicazione. Questo articolo descrive tre approcci per abilitare la registrazione con Azure SDK per .NET:This article describes three approaches to enable logging with the Azure SDK for .NET:

- Accedere alla finestra della console
- Registra nelle tracce di diagnostica .NETLog to .NET diagnostics traces
- Configurare la registrazione personalizzata

> [!IMPORTANT]
> Questo articolo si applica alle librerie client che usano le versioni più recenti di Azure SDK per .NET. Per verificare se una libreria è supportata, fare riferimento all'elenco delle versioni più recenti di [Azure SDK.](https://azure.github.io/azure-sdk/releases/latest/index.html) Se l'applicazione usa una versione precedente delle librerie client di Azure SDK, fare riferimento a istruzioni specifiche nella documentazione del servizio applicabile.

## <a name="log-information"></a>Informazioni sui log

L'SDK registra le informazioni seguenti, sanofizzando la query dei parametri e i valori dell'intestazione per rimuovere i dati personali.

Voce del registro richieste HTTP:

- ID univoco
- Metodo HTTP
- URI
- Intestazioni delle richieste in uscita

Voce del registro risposte HTTP:

- Durata dell'operazione di I/O (tempo trascorso)
- ID richiesta
- Stato codice HTTP
- Frase motivo HTTP
- Intestazioni della risposta
- Informazioni sull'errore, se applicabile

Per il contenuto di richiesta e risposta:

- Flusso di contenuto come testo o byte a seconda dell'intestazione Content-Type.
     > [! NOTA: la registrazione del contenuto è disabilitata per impostazione predefinita. Per attivarla, `Diagnostics.IsLoggingContentEnabled` `true` impostare su in `ClientOptions`.

I registri eventi vengono restituiti in genere a uno di questi tre livelli:Event logs are output usually at one of these three levels:

- Informazioni sugli eventi di richiesta e risposta
- Avviso per gli errori
- Verbose per messaggi dettagliati e registrazione del contenuto

## <a name="enable-logging-with-built-in-methods"></a>Abilitare la registrazione con i metodi incorporatiEnable logging with built-in methods

Le librerie client di Azure SDK for .NET registrano [ `EventSource` ](/dotnet/api/system.diagnostics.tracing.eventsource)gli eventi in Event Tracing for Windows (ETW) tramite la classe , che è tipica di .NET. Le origini eventi consentono di usare la registrazione strutturata nel codice dell'applicazione con un overhead di prestazioni minimo. Per accedere a questi registri eventi, è necessario registrare i listener di eventi.

L'SDK `Azure.Core.Diagnostics.AzureEventSourceListener` include la classe (definita nel pacchetto Azure.Core NuGet), che contiene due `CreateConsoleLogger` metodi `CreateTraceLogger`statici che semplificano la registrazione completa per l'applicazione .NET: e . Questi metodi accettano un parametro facoltativo che specifica un livello di log.

### <a name="log-to-the-console-window"></a>Accedere alla finestra della console

Un principio di base delle librerie client di Azure SDK for .NET consiste nel semplificare la possibilità di visualizzare log completi in tempo reale. Il `CreateConsoleLogger` metodo consente di inviare i log alla finestra della console con una singola riga di codice:The method allows you to send logs to the console window with a single line of code:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Eseguire il log alle tracce diagnosticheLog to diagnostic traces

Se si implementano listener di `CreateTraceLogger` traccia, è possibile utilizzare il metodo[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)per registrare il meccanismo di traccia eventi .NET standard ( ). Per ulteriori informazioni sull'analisi degli eventi in .NET, vedere [Listener di traccia](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners). In questo esempio viene specificato un livello di log di livello dettagliato:This example specifies a log level of verbose:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Configurare la registrazione personalizzata

Come accennato in precedenza, è necessario registrare i listener di eventi per ricevere messaggi di log da Azure SDK per .NET. Se non si desidera implementare la registrazione completa utilizzando uno dei metodi `AzureEventSourceListener` semplificati sopra descritti, è possibile costruire un'istanza della classe e passarle una funzione di callback scritta. Questo metodo riceverà messaggi di log che è possibile elaborare in modo che sia necessario. Inoltre, quando si costruisce l'istanza, è possibile specificare i livelli di log da includere.

L'esempio seguente crea un listener di eventi che accede alla console con un messaggio personalizzato e viene filtrato in base agli eventi principali di Azure del livello dettagliato.

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

## <a name="next-steps"></a>Passaggi successivi

- [Abilitare la registrazione diagnostica per le app nel servizio app di AzureEnable diagnostics logging for apps in Azure App Service](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- Esaminare le opzioni di controllo e registrazione della sicurezza di [AzureReview Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options
- Informazioni su come usare i log della [piattaforma AzureLearn](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) how to work with Azure platform logs
- Ulteriori informazioni sulla registrazione e la traccia di [.NET Core](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)
