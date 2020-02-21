---
title: Gestione degli errori-gRPC per sviluppatori WCF
description: Argomenti relativi alla gestione degli errori in gRPC. Include una tabella dei codici di stato usati più di frequente.
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542793"
---
# <a name="error-handling"></a><span data-ttu-id="226bc-104">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="226bc-104">Error handling</span></span>

<span data-ttu-id="226bc-105">Windows Communication Foundation (WCF) utilizza <xref:System.ServiceModel.FaultException%601> e [FaultContract](xref:System.ServiceModel.FaultContractAttribute) per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard degli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="226bc-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="226bc-106">Sfortunatamente, la versione corrente di gRPC non dispone della sofisticazione trovata con WCF e prevede una gestione degli errori incorporata limitata basata su semplici codici di stato e metadati.</span><span class="sxs-lookup"><span data-stu-id="226bc-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="226bc-107">La tabella seguente è una guida rapida ai codici di stato usati più di frequente:</span><span class="sxs-lookup"><span data-stu-id="226bc-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="226bc-108">Codice di stato</span><span class="sxs-lookup"><span data-stu-id="226bc-108">Status code</span></span> | <span data-ttu-id="226bc-109">Problema</span><span class="sxs-lookup"><span data-stu-id="226bc-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="226bc-110">Il metodo non è stato scritto.</span><span class="sxs-lookup"><span data-stu-id="226bc-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="226bc-111">Problema con l'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="226bc-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="226bc-112">Risposta non valida.</span><span class="sxs-lookup"><span data-stu-id="226bc-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="226bc-113">Problemi di codifica/decodifica.</span><span class="sxs-lookup"><span data-stu-id="226bc-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="226bc-114">Autenticazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="226bc-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="226bc-115">Autorizzazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="226bc-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="226bc-116">La chiamata è stata annullata, in genere dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="226bc-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="226bc-117">Genera errori nel ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="226bc-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="226bc-118">Un ASP.NET Core servizio gRPC può inviare una risposta di errore generando una `RpcException`, che può essere rilevata dal client come se si trovasse nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="226bc-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="226bc-119">Il `RpcException` deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo.</span><span class="sxs-lookup"><span data-stu-id="226bc-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="226bc-120">I metadati possono essere utilizzati per inviare dati di supporto, in modo analogo a come `FaultContract` oggetti possono contenere dati aggiuntivi per gli errori WCF.</span><span class="sxs-lookup"><span data-stu-id="226bc-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="226bc-121">Rilevare gli errori nei client gRPC</span><span class="sxs-lookup"><span data-stu-id="226bc-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="226bc-122">Proprio come i client WCF possono intercettare gli errori di <xref:System.ServiceModel.FaultException%601>, un client gRPC può intercettare un `RpcException` per gestire gli errori.</span><span class="sxs-lookup"><span data-stu-id="226bc-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="226bc-123">Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi.</span><span class="sxs-lookup"><span data-stu-id="226bc-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="226bc-124">Tuttavia, è possibile C#usare la funzionalità *filtri eccezioni* di per dichiarare blocchi di `catch` distinti per i diversi codici di stato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="226bc-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="226bc-125">Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le chiavi e i valori rilevanti nella documentazione dell'API o nei commenti nel file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="226bc-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="226bc-126">modello di errore gRPC più completo</span><span class="sxs-lookup"><span data-stu-id="226bc-126">gRPC richer error model</span></span>

<span data-ttu-id="226bc-127">Google ha sviluppato un [modello di errore più completo](https://cloud.google.com/apis/design/errors#error_model) , più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF, ma questo modello non è C# ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="226bc-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="226bc-128">Attualmente, è disponibile solo per go, Java, Python e C++.</span><span class="sxs-lookup"><span data-stu-id="226bc-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="226bc-129">[Precedente](metadata.md)
>[Successivo](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="226bc-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
