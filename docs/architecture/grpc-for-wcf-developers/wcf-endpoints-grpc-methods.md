---
title: Endpoint WCF e metodi gRPC-gRPC per sviluppatori WCF
description: Confronto tra gli endpoint WCF dichiarati con gli attributi ServiceContract e OperationContract e i metodi gRPC dichiarati in protobuf
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503424"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>Endpoint WCF e metodi gRPC

In Windows Communication Foundation (WCF), quando si scrive il codice dell'applicazione, usare uno dei metodi seguenti:

- È possibile scrivere il codice dell'applicazione in una classe e decorare i metodi con l'attributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .
- Si dichiara un'interfaccia per il servizio e si aggiungono gli attributi [OperationContract](xref:System.ServiceModel.OperationContractAttribute) all'interfaccia.

Ad esempio, l'equivalente WCF del servizio `greet.proto` greeter potrebbe essere scritto come segue:

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

Il capitolo 3 ha mostrato che le definizioni dei messaggi protobuf vengono usate per generare le classi di dati. Le dichiarazioni di servizio e di metodo vengono utilizzate per generare classi base ereditate da per implementare il servizio. È sufficiente dichiarare i metodi da implementare nel file di `.proto` e il compilatore genera una classe base con i metodi virtuali di cui è necessario eseguire l'override.

## <a name="operationcontract-properties"></a>Proprietà di OperationContract

L'attributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) dispone di proprietà per controllare o ridefinire il funzionamento. i metodi gRPC non offrono questo tipo di controllo. Nella tabella seguente sono elencate le proprietà di `OperationContract` e viene descritto il modo in cui la funzionalità specificata non viene gestita in gRPC:

| Proprietà `OperationContract` | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | URI che identifica l'operazione. gRPC usa il nome di `package`, `service`e `rpc` dal file `.proto`. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Tutti i metodi del servizio gRPC restituiscono oggetti `Task`. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Vedere il paragrafo dopo questa tabella. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | I metodi gRPC unidirezionali restituiscono `Empty` risultati o utilizzano lo streaming client. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Vedere il paragrafo dopo questa tabella. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Questa proprietà è associata a SOAP e non ha significato in gRPC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Non è presente alcuna crittografia dei messaggi. La crittografia di rete viene gestita a livello di trasporto (TLS su HTTP/2). |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Questa proprietà è associata a SOAP e non ha significato in gRPC. |

La proprietà `IsInitiating` consente di indicare che un metodo all'interno di [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) non può essere il primo metodo chiamato come parte di una sessione. La proprietà `IsTerminating` determina la chiusura della sessione da parte del server dopo la chiamata di un'operazione o il client, se la proprietà viene utilizzata in un client di callback. In gRPC i flussi vengono creati da singoli metodi e chiusi in modo esplicito. Vedere [gRPC streaming](rpc-types.md#grpc-streaming).

Per ulteriori informazioni sulla sicurezza e la crittografia di gRPC, vedere il [capitolo 6](security.md).

>[!div class="step-by-step"]
>[Precedente](wcf-services-to-grpc-comparison.md)
>[Successivo](wcf-bindings.md)
