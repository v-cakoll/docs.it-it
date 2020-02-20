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
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="479a7-103">Endpoint WCF e metodi gRPC</span><span class="sxs-lookup"><span data-stu-id="479a7-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="479a7-104">In Windows Communication Foundation (WCF), quando si scrive il codice dell'applicazione, usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="479a7-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="479a7-105">È possibile scrivere il codice dell'applicazione in una classe e decorare i metodi con l'attributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="479a7-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="479a7-106">Si dichiara un'interfaccia per il servizio e si aggiungono gli attributi [OperationContract](xref:System.ServiceModel.OperationContractAttribute) all'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="479a7-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="479a7-107">Ad esempio, l'equivalente WCF del servizio `greet.proto` greeter potrebbe essere scritto come segue:</span><span class="sxs-lookup"><span data-stu-id="479a7-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="479a7-108">Il capitolo 3 ha mostrato che le definizioni dei messaggi protobuf vengono usate per generare le classi di dati.</span><span class="sxs-lookup"><span data-stu-id="479a7-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="479a7-109">Le dichiarazioni di servizio e di metodo vengono utilizzate per generare classi base ereditate da per implementare il servizio.</span><span class="sxs-lookup"><span data-stu-id="479a7-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="479a7-110">È sufficiente dichiarare i metodi da implementare nel file di `.proto` e il compilatore genera una classe base con i metodi virtuali di cui è necessario eseguire l'override.</span><span class="sxs-lookup"><span data-stu-id="479a7-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="479a7-111">Proprietà di OperationContract</span><span class="sxs-lookup"><span data-stu-id="479a7-111">OperationContract properties</span></span>

<span data-ttu-id="479a7-112">L'attributo [OperationContract](xref:System.ServiceModel.OperationContractAttribute) dispone di proprietà per controllare o ridefinire il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="479a7-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="479a7-113">i metodi gRPC non offrono questo tipo di controllo.</span><span class="sxs-lookup"><span data-stu-id="479a7-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="479a7-114">Nella tabella seguente sono elencate le proprietà di `OperationContract` e viene descritto il modo in cui la funzionalità specificata non viene gestita in gRPC:</span><span class="sxs-lookup"><span data-stu-id="479a7-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="479a7-115">Proprietà `OperationContract`</span><span class="sxs-lookup"><span data-stu-id="479a7-115">`OperationContract` property</span></span> | <span data-ttu-id="479a7-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="479a7-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="479a7-117">URI che identifica l'operazione.</span><span class="sxs-lookup"><span data-stu-id="479a7-117">A URI identifies the operation.</span></span> <span data-ttu-id="479a7-118">gRPC usa il nome di `package`, `service`e `rpc` dal file `.proto`.</span><span class="sxs-lookup"><span data-stu-id="479a7-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="479a7-119">Tutti i metodi del servizio gRPC restituiscono oggetti `Task`.</span><span class="sxs-lookup"><span data-stu-id="479a7-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="479a7-120">Vedere il paragrafo dopo questa tabella.</span><span class="sxs-lookup"><span data-stu-id="479a7-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="479a7-121">I metodi gRPC unidirezionali restituiscono `Empty` risultati o utilizzano lo streaming client.</span><span class="sxs-lookup"><span data-stu-id="479a7-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="479a7-122">Vedere il paragrafo dopo questa tabella.</span><span class="sxs-lookup"><span data-stu-id="479a7-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="479a7-123">Questa proprietà è associata a SOAP e non ha significato in gRPC.</span><span class="sxs-lookup"><span data-stu-id="479a7-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="479a7-124">Non è presente alcuna crittografia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="479a7-124">There's no message encryption.</span></span> <span data-ttu-id="479a7-125">La crittografia di rete viene gestita a livello di trasporto (TLS su HTTP/2).</span><span class="sxs-lookup"><span data-stu-id="479a7-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="479a7-126">Questa proprietà è associata a SOAP e non ha significato in gRPC.</span><span class="sxs-lookup"><span data-stu-id="479a7-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="479a7-127">La proprietà `IsInitiating` consente di indicare che un metodo all'interno di [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) non può essere il primo metodo chiamato come parte di una sessione.</span><span class="sxs-lookup"><span data-stu-id="479a7-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="479a7-128">La proprietà `IsTerminating` determina la chiusura della sessione da parte del server dopo la chiamata di un'operazione o il client, se la proprietà viene utilizzata in un client di callback.</span><span class="sxs-lookup"><span data-stu-id="479a7-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="479a7-129">In gRPC i flussi vengono creati da singoli metodi e chiusi in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="479a7-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="479a7-130">Vedere [gRPC streaming](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="479a7-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="479a7-131">Per ulteriori informazioni sulla sicurezza e la crittografia di gRPC, vedere il [capitolo 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="479a7-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="479a7-132">[Precedente](wcf-services-to-grpc-comparison.md)
>[Successivo](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="479a7-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
