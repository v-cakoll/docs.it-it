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
# <a name="error-handling"></a>Gestione degli errori

Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> e [FaultContract](xref:System.ServiceModel.FaultContractAttribute) per fornire informazioni dettagliate sull'errore, incluso il supporto dello standard di errore SOAP.

Sfortunatamente, la versione corrente di gRPC non dispone della sofisticazione rilevata con WCF e ha solo una gestione degli errori incorporata limitata in base a semplici codici di stato e metadati. La tabella seguente è una guida rapida ai codici di stato più comunemente utilizzati:

| Codice di stato | Problema |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Il metodo non è stato scritto. |
| `GRPC_STATUS_UNAVAILABLE` | Problema con l'intero servizio. |
| `GRPC_STATUS_UNKNOWN` | Risposta non valida. |
| `GRPC_STATUS_INTERNAL` | Problema con la codifica/decodifica. |
| `GRPC_STATUS_UNAUTHENTICATED` | Autenticazione non riuscita. |
| `GRPC_STATUS_PERMISSION_DENIED` | Autorizzazione non riuscita. |
| `GRPC_STATUS_CANCELLED` | La chiamata è stata annullata, in genere dal chiamante. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Generare errori in ASP.NET Core gRPC

Un servizio gRPC ASP.NET Core può inviare `RpcException`una risposta di errore generando un oggetto , che può essere intercettato dal client come se si trattasse nello stesso processo. Il `RpcException` campo deve includere un codice di stato e una descrizione e può includere facoltativamente metadati e un messaggio di eccezione più lungo. I metadati possono essere utilizzati per `FaultContract` inviare dati di supporto, in modo simile a come gli oggetti possono contenere dati aggiuntivi per gli errori WCF.

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

## <a name="catch-errors-in-grpc-clients"></a>Intercettare gli errori nei client gRPC

Proprio come i <xref:System.ServiceModel.FaultException%601> client WCF possono intercettare `RpcException` gli errori, un client gRPC può intercettare un per gestire gli errori. Poiché `RpcException` non è un tipo generico, non è possibile intercettare tipi di errore diversi in blocchi diversi. Ma è possibile utilizzare la funzionalità di `catch` *filtri eccezioni* di C , per dichiarare blocchi separati per codici di stato diversi, come illustrato nell'esempio seguente:But you can use C's exception filters feature to declare separate blocks for different status codes, as shown in the following example:

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
> Quando si forniscono metadati aggiuntivi per gli errori, assicurarsi di documentare le `.proto` chiavi e i valori pertinenti nella documentazione dell'API o nei commenti nel file.

## <a name="grpc-richer-error-model"></a>modello di errore gRPC più avanzato

Google ha sviluppato un modello di [errore più ricco](https://cloud.google.com/apis/design/errors#error_model) che è più simile a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)di WCF , ma questo modello non è ancora supportato in C . Al momento, è disponibile solo per Go, Java, Python, e C .

>[!div class="step-by-step"]
>[Successivo](metadata.md)
>[precedente](ws-protocols.md)
