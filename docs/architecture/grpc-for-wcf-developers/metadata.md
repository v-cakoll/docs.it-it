---
title: Metadati-gRPC per sviluppatori WCF
description: Modalità di utilizzo dei metadati in gRPC per passare un contesto aggiuntivo tra client e server.
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628579"
---
# <a name="metadata"></a><span data-ttu-id="fb25a-103">Metadati</span><span class="sxs-lookup"><span data-stu-id="fb25a-103">Metadata</span></span>

<span data-ttu-id="fb25a-104">I *metadati* fanno riferimento a dati aggiuntivi che possono risultare utili durante l'elaborazione di richieste e risposte, ma che non fanno parte dei dati effettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fb25a-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="fb25a-105">I metadati possono includere token di autenticazione, identificatori di richiesta e tag a scopo di monitoraggio e informazioni sui dati, ad esempio il numero di record in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="fb25a-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="fb25a-106">È possibile aggiungere intestazioni chiave/valore generiche ai messaggi Windows Communication Foundation (WCF) utilizzando una <xref:System.ServiceModel.OperationContextScope> e la proprietà <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> e gestirle utilizzando <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="fb25a-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="fb25a-107">le chiamate e le risposte gRPC possono includere anche metadati simili a intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="fb25a-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="fb25a-108">Questi metadati sono principalmente invisibili per gRPC e vengono passati per essere elaborati dal codice dell'applicazione o dal middleware.</span><span class="sxs-lookup"><span data-stu-id="fb25a-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="fb25a-109">I metadati sono rappresentati come coppie chiave/valore, dove la chiave è una stringa e il valore è una stringa o dati binari.</span><span class="sxs-lookup"><span data-stu-id="fb25a-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="fb25a-110">Non è necessario specificare i metadati nel file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="fb25a-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="fb25a-111">I metadati vengono gestiti dalla classe `Metadata` del pacchetto NuGet [Grpc. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) .</span><span class="sxs-lookup"><span data-stu-id="fb25a-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="fb25a-112">Questa classe può essere utilizzata con la sintassi dell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="fb25a-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="fb25a-113">Questo esempio illustra come aggiungere metadati a una chiamata da un C# client:</span><span class="sxs-lookup"><span data-stu-id="fb25a-113">This example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="fb25a-114">i servizi gRPC possono accedere ai metadati dalla proprietà `RequestHeaders` dell'argomento `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="fb25a-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="fb25a-115">I servizi possono inviare metadati ai client usando la proprietà `ResponseTrailers` di `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="fb25a-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="fb25a-116">[Precedente](rpc-types.md)
>[Successivo](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="fb25a-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
