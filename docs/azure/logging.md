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
# <a name="logging-with-the-azure-sdk-for-net"></a>Registrazione con Azure SDK per .NET

Le librerie client di [Azure SDK](https://azure.microsoft.com/downloads/) per .NET includono la possibilità di registrare le operazioni della libreria client. In questo modo è possibile monitorare le richieste di I/O e le risposte effettuate dalle librerie client ai servizi di Azure. I log vengono in genere usati per eseguire il debug o diagnosticare i problemi di comunicazione. Questo articolo descrive tre approcci per abilitare la registrazione con Azure SDK per .NET:

- Accedi alla finestra della console
- Accedi alle tracce di diagnostica .NET
- Configurare la registrazione personalizzata

> [!IMPORTANT]
> Questo articolo si applica alle librerie client che usano le versioni più recenti di Azure SDK per .NET. Per verificare se una libreria è supportata, vedere l'elenco delle [versioni più recenti di Azure SDK](https://azure.github.io/azure-sdk/releases/latest/index.html). Se l'applicazione usa una versione precedente delle librerie client di Azure SDK, fare riferimento a istruzioni specifiche nella documentazione del servizio applicabile.

## <a name="log-information"></a>Informazioni sui log

L'SDK registra le informazioni seguenti, purificando i valori delle intestazioni e delle query dei parametri per rimuovere i dati personali.

Voce di log richiesta HTTP:

- ID univoco
- Metodo HTTP
- URI
- Intestazioni delle richieste in uscita

Voce di log della risposta HTTP:

- Durata dell'operazione di I/O (tempo trascorso)
- ID richiesta
- Codice di stato HTTP
- Frase del motivo HTTP
- Intestazioni di risposta
- Informazioni sull'errore, quando applicabile

Per il contenuto della richiesta e della risposta:

- Flusso di contenuto come testo o byte in base all'intestazione Content-Type.
     > [! Nota} la registrazione del contenuto è disabilitata per impostazione predefinita. Per abilitarla, impostare `Diagnostics.IsLoggingContentEnabled` su `true` in `ClientOptions` .

I registri eventi vengono in genere restituiti in uno dei tre livelli seguenti:

- Informazioni per eventi di richiesta e risposta
- Avviso per errori
- Dettagliato per i messaggi dettagliati e la registrazione del contenuto

## <a name="enable-logging-with-built-in-methods"></a>Abilitare la registrazione con i metodi predefiniti

Le librerie client di Azure SDK per .NET registrano gli eventi Event Tracing for Windows (ETW) tramite la [ `EventSource` classe](/dotnet/api/system.diagnostics.tracing.eventsource), che è tipica per .NET. Le origini eventi consentono di usare la registrazione strutturata nel codice dell'applicazione con un overhead minimo sulle prestazioni. Per ottenere l'accesso a questi registri eventi, è necessario registrare i listener di eventi.

L'SDK include la `Azure.Core.Diagnostics.AzureEventSourceListener` classe (definita nel pacchetto NuGet di Azure. Core), che contiene due metodi statici che semplificano la registrazione completa per l'applicazione .NET: `CreateConsoleLogger` e `CreateTraceLogger` . Questi metodi accettano un parametro facoltativo che specifica un livello di registrazione.

### <a name="log-to-the-console-window"></a>Accedi alla finestra della console

Un principio fondamentale delle librerie client di Azure SDK per .NET consiste nel semplificare la possibilità di visualizzare i log completi in tempo reale. Il `CreateConsoleLogger` metodo consente di inviare i log alla finestra della console con una sola riga di codice:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a>Accedi alle tracce di diagnostica

Se si implementano i listener di traccia, è possibile usare il `CreateTraceLogger` metodo per accedere al meccanismo di traccia eventi .NET standard ( [`System.Diagnostics.Tracing`](/dotnet/api/system.diagnostics.tracing) ). Per ulteriori informazioni sull'analisi degli eventi in .NET, vedere [listener di traccia](../framework/debug-trace-profile/trace-listeners.md). Questo esempio specifica un livello di log dettagliato:

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a>Configurare la registrazione personalizzata

Come indicato in precedenza, è necessario registrare i listener di eventi per ricevere i messaggi di log da Azure SDK per .NET. Se non si desidera implementare la registrazione completa utilizzando uno dei metodi semplificati descritti in precedenza, è possibile creare un'istanza della `AzureEventSourceListener` classe e passargli una funzione di callback che si scrive. Questo metodo riceverà i messaggi di log che è possibile elaborare, tuttavia è necessario. Inoltre, quando si crea l'istanza di, è possibile specificare i livelli di registrazione da includere.

Nell'esempio seguente viene creato un listener di eventi che accede alla console con un messaggio personalizzato e viene filtrato in base agli eventi di Azure core del livello dettagliato.

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

- [Abilitare la registrazione diagnostica per le app nel servizio app Azure](/azure/app-service/troubleshoot-diagnostic-logs)
- Esaminare [le opzioni di controllo e registrazione sicurezza di Azure](/azure/security/fundamentals/log-audit)
- Informazioni su come usare i [log della piattaforma Azure](/azure/azure-monitor/platform/platform-logs-overview)
- Scopri di più sulla [registrazione e la traccia di .NET Core](../core/diagnostics/logging-tracing.md)
