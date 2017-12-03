---
title: Intestazioni di indirizzo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d46dac29157455f736e30515f4bc6b277b63694
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="address-headers"></a><span data-ttu-id="e0886-102">Intestazioni di indirizzo</span><span class="sxs-lookup"><span data-stu-id="e0886-102">Address Headers</span></span>
<span data-ttu-id="e0886-103">Nell'esempio delle intestazioni di indirizzo viene illustrato come i client possano passare parametri di riferimento a un servizio utilizzando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0886-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0886-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e0886-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e0886-105">La specifica WS-Addressing definisce la nozione di un riferimento dell'endpoint come un modo di indirizzare un particolare endpoint servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e0886-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="e0886-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], i riferimenti all'endpoint vengono modellati utilizzando la classe `EndpointAddress`: `EndpointAddress` è il tipo del campo Indirizzo della classe `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="e0886-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>  
  
 <span data-ttu-id="e0886-107">Parte del modello di riferimento all'endpoint è che ogni riferimento può portare alcuni parametri di riferimento che aggiungono informazioni di identificazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e0886-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="e0886-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], questi parametri di riferimento vengono modellati come istanze della classe `AddressHeader`.</span><span class="sxs-lookup"><span data-stu-id="e0886-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], these reference parameters are modeled as instances of `AddressHeader` class.</span></span>  
  
 <span data-ttu-id="e0886-109">In questo esempio, il client aggiunge un parametro di riferimento a `EndpointAddress` dell'endpoint client.</span><span class="sxs-lookup"><span data-stu-id="e0886-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="e0886-110">Il servizio cerca questo parametro di riferimento e ne utilizza il valore nella logica dell'operazione del servizio "Hello".</span><span class="sxs-lookup"><span data-stu-id="e0886-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>  
  
## <a name="client"></a><span data-ttu-id="e0886-111">Client</span><span class="sxs-lookup"><span data-stu-id="e0886-111">Client</span></span>  
 <span data-ttu-id="e0886-112">Il client deve aggiungere un `AddressHeader` al `EndpointAddress` del `ServiceEndpoint` per inviare un parametro di riferimento.</span><span class="sxs-lookup"><span data-stu-id="e0886-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="e0886-113">Poiché la classe `EndpointAddress` è immutabile, è necessario modificare l'indirizzo endpoint utilizzando la classe `EndpointAddressBuilder`.</span><span class="sxs-lookup"><span data-stu-id="e0886-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="e0886-114">Nel codice seguente il client viene inizializzato per inviare un parametro di riferimento come parte del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e0886-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 <span data-ttu-id="e0886-115">Il codice crea un `EndpointAddressBuilder` utilizzando il `EndpointAddress` originale come valore iniziale.</span><span class="sxs-lookup"><span data-stu-id="e0886-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="e0886-116">Viene quindi aggiunta una nuova intestazione di indirizzo. La chiamata a `CreateAddressHeadercreates` crea un'intestazione con un nome, uno spazio dei nomi e un valore specifici.</span><span class="sxs-lookup"><span data-stu-id="e0886-116">It then adds a newly created address header; the call to `CreateAddressHeadercreates` a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="e0886-117">In questo esempio il valore è "John."</span><span class="sxs-lookup"><span data-stu-id="e0886-117">Here the value is "John".</span></span> <span data-ttu-id="e0886-118">Una volta aggiunta l'intestazione al generatore, il metodo `ToEndpointAddress()` converte nuovamente il generatore (mutevole) in un indirizzo endpoint (immutabile), il quale viene assegnato di nuovo al campo Indirizzo dell'endpoint client.</span><span class="sxs-lookup"><span data-stu-id="e0886-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>  
  
 <span data-ttu-id="e0886-119">Quando il client chiama `Console.WriteLine(client.Hello());`, il servizio è in grado di ottenere il valore di questo parametro di indirizzo, come si può vedere nell'output risultante del client.</span><span class="sxs-lookup"><span data-stu-id="e0886-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>  
  
 `Hello, John`  
  
## <a name="server"></a><span data-ttu-id="e0886-120">Server</span><span class="sxs-lookup"><span data-stu-id="e0886-120">Server</span></span>  
 <span data-ttu-id="e0886-121">L'implementazione dell'operazione del servizio `Hello()` utilizza il `OperationContext` corrente per controllare i valori delle intestazioni nel messaggio in arrivo.</span><span class="sxs-lookup"><span data-stu-id="e0886-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 <span data-ttu-id="e0886-122">Il codice scorre tutte le intestazioni nel messaggio in arrivo, cercando intestazioni che sono parametri di riferimento dotati del nome particolare.</span><span class="sxs-lookup"><span data-stu-id="e0886-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="e0886-123">Una volta individuato il parametro, il codice legge il valore del parametro e lo archivia nella variabile "id".</span><span class="sxs-lookup"><span data-stu-id="e0886-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e0886-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e0886-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e0886-125">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0886-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e0886-126">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0886-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e0886-127">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e0886-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0886-128">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e0886-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e0886-129">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e0886-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e0886-130">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0886-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0886-131">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e0886-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a><span data-ttu-id="e0886-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0886-132">See Also</span></span>
