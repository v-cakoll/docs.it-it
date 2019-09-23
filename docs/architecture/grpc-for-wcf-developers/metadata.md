---
title: Metadati-gRPC per sviluppatori WCF
description: Modalità di utilizzo dei metadati in gRPC per passare un contesto aggiuntivo tra client e server
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1a2131fa3ee3112eaa3c3e7f7c97017fea6b1004
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184330"
---
# <a name="metadata"></a>Metadati

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

"Metadata" si riferisce a dati aggiuntivi che possono risultare utili durante l'elaborazione di richieste e risposte, ma che non fanno parte dei dati effettivi dell'applicazione. I metadati possono includere token di autenticazione, identificatori di richiesta e tag a scopo di monitoraggio o informazioni sui dati come il numero di record in un set di dati.

È possibile aggiungere intestazioni chiave/valore generiche ai messaggi WCF usando un oggetto <xref:System.ServiceModel.OperationContextScope> e la <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> proprietà e gestirli usando <xref:System.ServiceModel.Channels.MessageProperties>.

le chiamate e le risposte gRPC possono includere anche metadati simili alle intestazioni HTTP. Sono principalmente invisibili per gRPC e vengono passati per essere elaborati dal codice dell'applicazione o dal middleware. I metadati sono rappresentati come coppie chiave/valore in cui la chiave è una stringa e il valore è una stringa o dati binari. Non è necessario specificare i `.proto` metadati nel file.

I metadati vengono gestiti usando `Metadata` la classe del pacchetto NuGet [Grpc. Core](https://www.nuget.org/packages/Grpc.Core/) . Questa classe può essere utilizzata con la sintassi dell'inizializzatore di raccolta.

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

i servizi gRPC possono accedere ai metadati `ServerCallContext` dalla `RequestHeaders` proprietà dell'argomento:

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

I servizi possono inviare metadati ai client usando `ResponseTrailers` la proprietà `ServerCallContext`di:

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
