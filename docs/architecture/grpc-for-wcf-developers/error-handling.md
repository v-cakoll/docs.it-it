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
# <a name="error-handling"></a>Gestione degli errori

Windows Communication Foundation (WCF) utilizza <xref:System.ServiceModel.FaultException%601> e [FaultContract](xref:System.ServiceModel.FaultContractAttribute) per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard degli errori SOAP.

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

## <a name="raise-errors-in-aspnet-core-grpc"></a>Genera errori nel ASP.NET Core gRPC

Un ASP.NET Core servizio gRPC può inviare una risposta di errore generando una `RpcException`, che può essere rilevata dal client come se si trovasse nello stesso processo. Il `RpcException` deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo. I metadati possono essere utilizzati per inviare dati di supporto, in modo analogo a come `FaultContract` oggetti possono contenere dati aggiuntivi per gli errori WCF.

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

## <a name="catch-errors-in-grpc-clients"></a>Rilevare gli errori nei client gRPC

Proprio come i client WCF possono intercettare gli errori di <xref:System.ServiceModel.FaultException%601>, un client gRPC può intercettare un `RpcException` per gestire gli errori. Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi. Tuttavia, è possibile C#usare la funzionalità *filtri eccezioni* di per dichiarare blocchi di `catch` distinti per i diversi codici di stato, come illustrato nell'esempio seguente:

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
> Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le chiavi e i valori rilevanti nella documentazione dell'API o nei commenti nel file di `.proto`.

## <a name="grpc-richer-error-model"></a>modello di errore gRPC più completo

Google ha sviluppato un [modello di errore più completo](https://cloud.google.com/apis/design/errors#error_model) , più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF, ma questo modello non è C# ancora supportato. Attualmente, è disponibile solo per go, Java, Python e C++.

>[!div class="step-by-step"]
>[Precedente](metadata.md)
>[Successivo](ws-protocols.md)
