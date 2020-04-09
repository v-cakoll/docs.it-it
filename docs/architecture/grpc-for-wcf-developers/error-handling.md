---
title: Gestione degli errori - gRPC per gli sviluppatori WCFError handling - gRPC for WCF Developers
description: Argomenti relativi alla gestione degli errori in gRPC. Include una tabella dei codici di stato più comunemente utilizzati.
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988947"
---
# <a name="error-handling"></a><span data-ttu-id="47575-104">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="47575-104">Error handling</span></span>

<span data-ttu-id="47575-105">Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> e [FaultContract](xref:System.ServiceModel.FaultContractAttribute) per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard di errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="47575-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="47575-106">Sfortunatamente, la versione corrente di gRPC non dispone della sofisticazione rilevata con WCF e ha solo una gestione degli errori incorporata limitata in base a semplici codici di stato e metadati.</span><span class="sxs-lookup"><span data-stu-id="47575-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="47575-107">La tabella seguente è una guida rapida ai codici di stato più comunemente utilizzati:</span><span class="sxs-lookup"><span data-stu-id="47575-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="47575-108">Codice di stato</span><span class="sxs-lookup"><span data-stu-id="47575-108">Status code</span></span> | <span data-ttu-id="47575-109">Problema</span><span class="sxs-lookup"><span data-stu-id="47575-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="47575-110">Il metodo non è stato scritto.</span><span class="sxs-lookup"><span data-stu-id="47575-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="47575-111">Problema con l'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="47575-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="47575-112">Risposta non valida.</span><span class="sxs-lookup"><span data-stu-id="47575-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="47575-113">Problema con la codifica/decodifica.</span><span class="sxs-lookup"><span data-stu-id="47575-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="47575-114">Autenticazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="47575-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="47575-115">Autorizzazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="47575-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="47575-116">La chiamata è stata annullata, in genere dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="47575-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="47575-117">Generare errori in ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="47575-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="47575-118">Un servizio gRPC ASP.NET Core può inviare `RpcException`una risposta di errore generando un oggetto , che può essere intercettato dal client come se si trattasse nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="47575-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="47575-119">Il `RpcException` campo deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo.</span><span class="sxs-lookup"><span data-stu-id="47575-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="47575-120">I metadati possono essere utilizzati per `FaultContract` inviare dati di supporto, in modo simile a come gli oggetti possono contenere dati aggiuntivi per gli errori WCF.</span><span class="sxs-lookup"><span data-stu-id="47575-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="47575-121">Intercettare gli errori nei client gRPC</span><span class="sxs-lookup"><span data-stu-id="47575-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="47575-122">Proprio come i <xref:System.ServiceModel.FaultException%601> client WCF possono intercettare `RpcException` gli errori, un client gRPC può intercettare un per gestire gli errori.</span><span class="sxs-lookup"><span data-stu-id="47575-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="47575-123">Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi.</span><span class="sxs-lookup"><span data-stu-id="47575-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="47575-124">Ma è possibile utilizzare la funzionalità di `catch` *filtri eccezioni* di C , per dichiarare blocchi separati per codici di stato diversi, come illustrato nell'esempio seguente:But you can use C's exception filters feature to declare separate blocks for different status codes, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="47575-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="47575-125">Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le `.proto` chiavi e i valori pertinenti nella documentazione dell'API o nei commenti nel file.</span><span class="sxs-lookup"><span data-stu-id="47575-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="47575-126">modello di errore gRPC più avanzato</span><span class="sxs-lookup"><span data-stu-id="47575-126">gRPC richer error model</span></span>

<span data-ttu-id="47575-127">Google ha sviluppato un modello di [errore più ricco](https://cloud.google.com/apis/design/errors#error_model) che è più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF , ma questo modello non è ancora supportato in C .</span><span class="sxs-lookup"><span data-stu-id="47575-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="47575-128">Al momento, è disponibile solo per Go, Java, Python, e C .</span><span class="sxs-lookup"><span data-stu-id="47575-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="47575-129">[Successivo](metadata.md)
>[precedente](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="47575-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
