---
title: Metadati-gRPC per sviluppatori WCF
description: Modalità di utilizzo dei metadati in gRPC per passare un contesto aggiuntivo tra client e server
ms.date: 09/02/2019
ms.openlocfilehash: 723d877bfbf0c2b0785949ff15939aedbac4d4e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971981"
---
# <a name="metadata"></a>Metadati

"Metadata" si riferisce a dati aggiuntivi che possono risultare utili durante l'elaborazione di richieste e risposte, ma che non fanno parte dei dati effettivi dell'applicazione. I metadati possono includere token di autenticazione, identificatori di richiesta e tag a scopo di monitoraggio o informazioni sui dati come il numero di record in un set di dati.

È possibile aggiungere intestazioni chiave/valore generiche ai messaggi WCF utilizzando un <xref:System.ServiceModel.OperationContextScope> e la proprietà <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> e gestirle utilizzando <xref:System.ServiceModel.Channels.MessageProperties>.

le chiamate e le risposte gRPC possono includere anche metadati simili alle intestazioni HTTP. Sono principalmente invisibili per gRPC e vengono passati per essere elaborati dal codice dell'applicazione o dal middleware. I metadati sono rappresentati come coppie chiave/valore in cui la chiave è una stringa e il valore è una stringa o dati binari. Non è necessario specificare i metadati nel file di `.proto`.

I metadati vengono gestiti usando la classe `Metadata` dal pacchetto NuGet [Grpc. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) . Questa classe può essere utilizzata con la sintassi dell'inizializzatore di raccolta.

Nell'esempio seguente viene illustrato come aggiungere metadati a una chiamata da un C# client:

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

i servizi gRPC possono accedere ai metadati dalla proprietà `RequestHeaders` dell'argomento `ServerCallContext`:

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

I servizi possono inviare metadati ai client usando la proprietà `ResponseTrailers` di `ServerCallContext`:

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
>[Precedente](rpc-types.md)
>[Successivo](error-handling.md)
