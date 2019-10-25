---
title: Endpoint WCF e metodi gRPC-gRPC per sviluppatori WCF
description: Confronto tra gli endpoint WCF dichiarati con gli attributi ServiceContract e OperationContract e i metodi gRPC dichiarati in protobuf
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846060"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>Endpoint WCF e metodi gRPC

In WCF, quando si scrive il codice dell'applicazione, usare uno dei metodi seguenti:

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

L'attributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) dispone di proprietà per controllare o ridefinire il funzionamento. i metodi gRPC non offrono questo tipo di controllo. Nella tabella seguente vengono illustrate le proprietà `OperationContract` e il modo in cui la funzionalità specificata viene o non è gestita in gRPC:

| Proprietà`OperationContract` | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | URI che identifica l'operazione. gRPC usa il nome del `package`, `service` e `rpc` dal file `.proto`. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Tutti i metodi del servizio gRPC restituiscono oggetti `Task`. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Vedere la nota seguente. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | I metodi gRPC unidirezionali restituiscono `Empty` risultati o utilizzano lo streaming client. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Vedere la nota seguente. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Correlato a SOAP, nessun significato in gRPC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Nessuna crittografia del messaggio; crittografia di rete gestita a livello di trasporto (TLS su HTTP/2). |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Correlato a SOAP, nessun significato in gRPC. |

La proprietà `IsInitiating` consente di indicare che un metodo all'interno di un [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) non può essere il primo metodo chiamato come parte di una sessione. La proprietà `IsTerminating` fa in modo che il server chiuda la sessione dopo la chiamata di un'operazione o il client, se usato in un client di callback. In gRPC i flussi vengono creati da singoli metodi e chiusi in modo esplicito. Vedere [gRPC streaming](rpc-types.md#grpc-streaming).

Per ulteriori informazioni sulla sicurezza e la crittografia di gRPC, vedere il [capitolo 6](security.md).

>[!div class="step-by-step"]
>[Precedente](wcf-services-to-grpc-comparison.md)
>[Successivo](wcf-bindings.md)
