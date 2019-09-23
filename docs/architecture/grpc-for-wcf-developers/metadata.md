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
# <a name="metadata"></a><span data-ttu-id="3fc61-103">Metadati</span><span class="sxs-lookup"><span data-stu-id="3fc61-103">Metadata</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="3fc61-104">"Metadata" si riferisce a dati aggiuntivi che possono risultare utili durante l'elaborazione di richieste e risposte, ma che non fanno parte dei dati effettivi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3fc61-104">"Metadata" refers to additional data that may be useful while processing requests and responses but is not part of the actual application data.</span></span> <span data-ttu-id="3fc61-105">I metadati possono includere token di autenticazione, identificatori di richiesta e tag a scopo di monitoraggio o informazioni sui dati come il numero di record in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="3fc61-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, or information about the data like the number of records in a dataset.</span></span>

<span data-ttu-id="3fc61-106">È possibile aggiungere intestazioni chiave/valore generiche ai messaggi WCF usando un oggetto <xref:System.ServiceModel.OperationContextScope> e la <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> proprietà e gestirli usando <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="3fc61-106">It's possible to add generic key/value headers to WCF messages using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property, and handle them using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="3fc61-107">le chiamate e le risposte gRPC possono includere anche metadati simili alle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="3fc61-107">gRPC calls and responses can also include metadata similar to HTTP headers.</span></span> <span data-ttu-id="3fc61-108">Sono principalmente invisibili per gRPC e vengono passati per essere elaborati dal codice dell'applicazione o dal middleware.</span><span class="sxs-lookup"><span data-stu-id="3fc61-108">These are mostly invisible to gRPC itself and are passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="3fc61-109">I metadati sono rappresentati come coppie chiave/valore in cui la chiave è una stringa e il valore è una stringa o dati binari.</span><span class="sxs-lookup"><span data-stu-id="3fc61-109">Metadata is represented as key/value pairs where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="3fc61-110">Non è necessario specificare i `.proto` metadati nel file.</span><span class="sxs-lookup"><span data-stu-id="3fc61-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="3fc61-111">I metadati vengono gestiti usando `Metadata` la classe del pacchetto NuGet [Grpc. Core](https://www.nuget.org/packages/Grpc.Core/) .</span><span class="sxs-lookup"><span data-stu-id="3fc61-111">Metadata is handled using the `Metadata` class from the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core/) NuGet package.</span></span> <span data-ttu-id="3fc61-112">Questa classe può essere utilizzata con la sintassi dell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="3fc61-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="3fc61-113">Nell'esempio seguente viene illustrato come aggiungere metadati a una chiamata da un C# client:</span><span class="sxs-lookup"><span data-stu-id="3fc61-113">The following example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="3fc61-114">i servizi gRPC possono accedere ai metadati `ServerCallContext` dalla `RequestHeaders` proprietà dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="3fc61-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="3fc61-115">I servizi possono inviare metadati ai client usando `ResponseTrailers` la proprietà `ServerCallContext`di:</span><span class="sxs-lookup"><span data-stu-id="3fc61-115">Services can send metadata to clients using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="3fc61-116">[Precedente](rpc-types.md)
>[Successivo](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="3fc61-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
