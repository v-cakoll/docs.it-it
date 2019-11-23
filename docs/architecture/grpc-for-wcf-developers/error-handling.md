---
title: Gestione degli errori-gRPC per sviluppatori WCF
description: DA SCRIVERE
ms.date: 09/02/2019
ms.openlocfilehash: 2c44bd9264c877a7c7a86c115b6da9f759006016
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967785"
---
# <a name="error-handling"></a><span data-ttu-id="e9237-103">Gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="e9237-103">Error handling</span></span>

<span data-ttu-id="e9237-104">WCF utilizza `FaultException<T>` e `FaultContract` per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard degli errori SOAP.</span><span class="sxs-lookup"><span data-stu-id="e9237-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="e9237-105">Sfortunatamente, la versione corrente di gRPC non dispone della sofisticazione trovata con WCF e prevede una gestione degli errori incorporata limitata basata su semplici codici di stato e metadati.</span><span class="sxs-lookup"><span data-stu-id="e9237-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="e9237-106">La tabella seguente è una guida rapida ai codici di stato usati più di frequente:</span><span class="sxs-lookup"><span data-stu-id="e9237-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="e9237-107">Codice di stato</span><span class="sxs-lookup"><span data-stu-id="e9237-107">Status Code</span></span> | <span data-ttu-id="e9237-108">Problema</span><span class="sxs-lookup"><span data-stu-id="e9237-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="e9237-109">Il metodo non è stato scritto.</span><span class="sxs-lookup"><span data-stu-id="e9237-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="e9237-110">Problema con l'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="e9237-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="e9237-111">Risposta non valida.</span><span class="sxs-lookup"><span data-stu-id="e9237-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="e9237-112">Problemi di codifica/decodifica.</span><span class="sxs-lookup"><span data-stu-id="e9237-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="e9237-113">Autenticazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e9237-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="e9237-114">Autorizzazione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="e9237-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="e9237-115">La chiamata è stata annullata, in genere dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="e9237-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="e9237-116">Generazione di errori nel ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e9237-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="e9237-117">Un ASP.NET Core servizio gRPC può inviare una risposta di errore generando una `RpcException`, che può essere rilevata dal client come se si trovasse nello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="e9237-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="e9237-118">Il `RpcException` deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo.</span><span class="sxs-lookup"><span data-stu-id="e9237-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="e9237-119">I metadati possono essere utilizzati per inviare dati di supporto, in modo analogo a come `FaultContract` oggetti possono contenere dati aggiuntivi per gli errori WCF.</span><span class="sxs-lookup"><span data-stu-id="e9237-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="e9237-120">Rilevamento di errori nei client gRPC</span><span class="sxs-lookup"><span data-stu-id="e9237-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="e9237-121">Proprio come i client WCF possono intercettare gli errori di <xref:System.ServiceModel.FaultException%601>, un client gRPC può intercettare un `RpcException` per gestire gli errori.</span><span class="sxs-lookup"><span data-stu-id="e9237-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="e9237-122">Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi, C#ma è possibile usare la funzionalità *filtri eccezioni* per dichiarare blocchi di `catch` separati per i diversi codici di stato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e9237-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="e9237-123">Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le chiavi e i valori rilevanti nella documentazione dell'API o nei commenti nel file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="e9237-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="e9237-124">Modello di errore gRPC più completo</span><span class="sxs-lookup"><span data-stu-id="e9237-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="e9237-125">In C# futuro, Google ha sviluppato un [modello di errore più completo](https://cloud.google.com/apis/design/errors#error_model) , più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF, ma non è ancora supportato.</span><span class="sxs-lookup"><span data-stu-id="e9237-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="e9237-126">Attualmente, è disponibile solo per go, Java, Python e C++, ma il supporto per C# è previsto per il prossimo anno.</span><span class="sxs-lookup"><span data-stu-id="e9237-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e9237-127">[Precedente](metadata.md)
>[Successivo](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="e9237-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
