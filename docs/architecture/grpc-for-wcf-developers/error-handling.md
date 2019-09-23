---
title: Gestione degli errori-gRPC per sviluppatori WCF
description: DA SCRIVERE
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 3535a00aad49f532eb5f5f778116454a12bfd639
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184456"
---
# <a name="error-handling"></a>Gestione degli errori

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

WCF utilizza `FaultException<T>` e `FaultContract` per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard di errore SOAP.

Sfortunatamente, la versione corrente di gRPC non dispone della sofisticazione trovata con WCF e prevede una gestione degli errori incorporata limitata basata su semplici codici di stato e metadati. La tabella seguente è una guida rapida ai codici di stato usati più di frequente:

| Codice di stato | Problema |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Il metodo non è stato scritto. |
| `GRPC_STATUS_UNAVAILABLE` | Problema con l'intero servizio. |
| `GRPC_STATUS_UNKNOWN` | Risposta non valida. |
| `GRPC_STATUS_INTERNAL` | Problemi di codifica/decodifica. |
| `GRPC_STATUS_UNAUTHENTICATED` | Autenticazione non riuscita. |
| `GRPC_STATUS_PERMISSION_DENIED` | Autorizzazione non riuscita. |
| `GRPC_STATUS_CANCELLED` | La chiamata è stata annullata, in genere dal chiamante. |

## <a name="raising-errors-in-aspnet-core-grpc"></a>Generazione di errori nel ASP.NET Core gRPC

Un ASP.NET Core servizio gRPC può inviare una risposta di errore generando `RpcException`un'eccezione, che può essere rilevata dal client come se si trovasse nello stesso processo. `RpcException` Deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo. I metadati possono essere utilizzati per inviare dati di supporto, in modo `FaultContract` analogo a come gli oggetti possono includere dati aggiuntivi per gli errori WCF.

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

## <a name="catching-errors-in-grpc-clients"></a>Rilevamento di errori nei client gRPC

Proprio come i client WCF possono <xref:System.ServiceModel.FaultException%601> rilevare errori, un client gRPC può intercettare un `RpcException` per gestire gli errori. Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi, C#ma è possibile usare la funzionalità relativa `catch` ai *filtri eccezioni* per dichiarare blocchi distinti per i diversi codici di stato, come illustrato di seguito. esempio

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
> Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le chiavi e i valori rilevanti nella documentazione dell'API o nei commenti del `.proto` file.

## <a name="grpc-richer-error-model"></a>Modello di errore gRPC più completo

In C# futuro, Google ha sviluppato un [modello di errore più completo](https://cloud.google.com/apis/design/errors#error_model) , più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF, ma non è ancora supportato. Attualmente, è disponibile solo per go, Java, Python e C++, ma il supporto per C# è previsto per il prossimo anno.

>[!div class="step-by-step"]
>[Precedente](metadata.md)
>[Successivo](ws-protocols.md)
