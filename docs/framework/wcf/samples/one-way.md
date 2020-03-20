---
title: Unidirezionale
ms.date: 03/30/2017
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
ms.openlocfilehash: 3203762e05c794ed28b65d8fded6972fac1f5820
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183447"
---
# <a name="one-way"></a><span data-ttu-id="3ed19-102">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="3ed19-102">One-Way</span></span>
<span data-ttu-id="3ed19-103">Questo esempio illustra un contatto di servizio con operazioni di servizio unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="3ed19-103">This sample demonstrates a service contact with one-way service operations.</span></span> <span data-ttu-id="3ed19-104">Il client non aspetta il completamento delle operazioni del servizio per terminare le operazioni, come accade invece con le operazioni di servizio bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="3ed19-104">The client does not wait for service operations to complete as is the case with two-way service operations.</span></span> <span data-ttu-id="3ed19-105">Questo esempio è basato sulla `wsHttpBinding` [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) e usa l'associazione.</span><span class="sxs-lookup"><span data-stu-id="3ed19-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and uses the `wsHttpBinding` binding.</span></span> <span data-ttu-id="3ed19-106">Il servizio, in questo esempio, è un'applicazione console indipendente che consente di osservare il servizio che riceve ed elabora messaggi in coda.</span><span class="sxs-lookup"><span data-stu-id="3ed19-106">The service in this sample is a self-hosted console application to enable you to observe the service that receives and processes requests.</span></span> <span data-ttu-id="3ed19-107">Il client è anche un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="3ed19-107">The client is also a console application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ed19-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3ed19-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3ed19-109">Per creare un contratto di servizio unidirezionale, definire il contratto del servizio, applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni operazione e impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true`, come illustrato nel codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3ed19-109">To create a one-way service contract, define your service contract, apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, and set <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> to `true` as shown in the following sample code:</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="3ed19-110">Per dimostrare che il client non aspetta il completamento delle operazioni del servizio, il codice del servizio, in questo esempio, implementa un ritardo di cinque secondi, come mostra il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3ed19-110">To demonstrate that the client does not wait for the service operations to complete, the service code in this sample implements a five-second delay, as shown in the following sample code:</span></span>  
  
```csharp
// This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="3ed19-111">Quando il client chiama il servizio, la chiamata viene restituita senza aspettare il completamento dell'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3ed19-111">When the client calls the service, the call returns without waiting for the service operation to complete.</span></span>  
  
 <span data-ttu-id="3ed19-112">Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="3ed19-112">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="3ed19-113">È possibile osservare il servizio che riceve i messaggi dal client.</span><span class="sxs-lookup"><span data-stu-id="3ed19-113">You can see the service receive messages from the client.</span></span> <span data-ttu-id="3ed19-114">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="3ed19-114">Press ENTER in each console window to shut down both the service and the client.</span></span>  
  
 <span data-ttu-id="3ed19-115">Il client termina prima del servizio, dimostrando che un client non aspetta il completamento delle operazioni unidirezionali del servizio.</span><span class="sxs-lookup"><span data-stu-id="3ed19-115">The client finishes ahead of the service, demonstrating that a client does not wait for one-way service operations to complete.</span></span> <span data-ttu-id="3ed19-116">L'output del client è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3ed19-116">The client output is as follows:</span></span>  
  
```console  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="3ed19-117">Viene mostrato l'output del servizio seguente:</span><span class="sxs-lookup"><span data-stu-id="3ed19-117">The following service output is shown:</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
> <span data-ttu-id="3ed19-118">HTTP è, per definizione, un protocollo di richiesta/risposta; quando viene effettuata una richiesta, viene restituita una risposta.</span><span class="sxs-lookup"><span data-stu-id="3ed19-118">HTTP is, by definition, a request/response protocol; when a request is made, a response is returned.</span></span> <span data-ttu-id="3ed19-119">Ciò è vero anche per un'operazione del servizio unidirezionale esposta su HTTP.</span><span class="sxs-lookup"><span data-stu-id="3ed19-119">This is true even for a one-way service operation that is exposed over HTTP.</span></span> <span data-ttu-id="3ed19-120">Quando l'operazione viene chiamata, il servizio restituisce un codice di stato HTTP 202 prima che l'operazione del servizio abbia completato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ed19-120">When the operation is called, the service returns an HTTP status code of 202 before the service operation has executed.</span></span> <span data-ttu-id="3ed19-121">Questo codice di stato significa che la richiesta è stata accettata, ma l'elaborazione non è stata ancora completata.</span><span class="sxs-lookup"><span data-stu-id="3ed19-121">This status code means that the request has been accepted for processing, but the processing has not yet been completed.</span></span> <span data-ttu-id="3ed19-122">Il client che ha chiamato l'operazione si blocca fino a che non riceve la risposta 202 dal servizio.</span><span class="sxs-lookup"><span data-stu-id="3ed19-122">The client that called the operation blocks until it receives the 202 response from the service.</span></span> <span data-ttu-id="3ed19-123">Questo può provocare alcuni comportamenti imprevisti quando più messaggi unidirezionali vengono inviati utilizzando un'associazione configurata per utilizzare sessioni.</span><span class="sxs-lookup"><span data-stu-id="3ed19-123">This can cause some unexpected behavior when multiple one-way messages are sent using a binding that is configured to use sessions.</span></span> <span data-ttu-id="3ed19-124">L'associazione `wsHttpBinding` utilizzata in questo esempio è configurata per utilizzare sessioni per impostazione predefinita e stabilire un contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3ed19-124">The `wsHttpBinding` binding used in this sample is configured to use sessions by default to establish a security context.</span></span> <span data-ttu-id="3ed19-125">Per impostazione predefinita, in una sessione, è garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="3ed19-125">By default, messages in a session are guaranteed to arrive in the order in which they are sent.</span></span> <span data-ttu-id="3ed19-126">Perciò, quando viene inviato il secondo messaggio di una sessione, non viene elaborato fino a che non è stato elaborato il primo messaggio.</span><span class="sxs-lookup"><span data-stu-id="3ed19-126">Because of this, when the second message in a session is sent, it is not processed until the first message has been processed.</span></span> <span data-ttu-id="3ed19-127">Ne risulta che il client non riceve la risposta 202 per un messaggio sino al completamento dell'elaborazione del messaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="3ed19-127">The result of this is that the client does not receive the 202 response for a message until the processing of the previous message has been completed.</span></span> <span data-ttu-id="3ed19-128">Il client sembra pertanto bloccarsi su ogni chiamata successiva dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3ed19-128">The client therefore appears to block on each subsequent operation call.</span></span> <span data-ttu-id="3ed19-129">Per evitare questo comportamento questo esempio configura il runtime in modo da inviare contemporaneamente i messaggi alle varie istanze per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3ed19-129">To avoid this behavior, this sample configures the runtime to dispatch messages concurrently to distinct instances for processing.</span></span> <span data-ttu-id="3ed19-130">Nell'esempio la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> viene impostata su `PerCall` in modo che ogni messaggio possa essere elaborato da un'istanza diversa.</span><span class="sxs-lookup"><span data-stu-id="3ed19-130">The sample sets <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> to `PerCall` so that each message can be processed by a different instance.</span></span> <span data-ttu-id="3ed19-131">La proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> viene impostata su `Multiple` per consentire l'invio contemporaneo di messaggi da parte di più thread.</span><span class="sxs-lookup"><span data-stu-id="3ed19-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to `Multiple` to allow more than one thread to dispatch messages at a time.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3ed19-132">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3ed19-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3ed19-133">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3ed19-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3ed19-134">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3ed19-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="3ed19-135">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3ed19-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ed19-136">Eseguire il servizio prima di eseguire il client e spegnere il client prima di spegnere il servizio.</span><span class="sxs-lookup"><span data-stu-id="3ed19-136">Run the service before you run the client and shut down the client before shutting down the service.</span></span> <span data-ttu-id="3ed19-137">Ciò impedisce che il client restituisca un'eccezione quando non può chiudere la sessione di sicurezza in modo pulito perché il servizio non c'è più.</span><span class="sxs-lookup"><span data-stu-id="3ed19-137">This avoids a client exception when the client cannot close the security session cleanly because the service is gone.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ed19-138">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3ed19-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3ed19-139">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3ed19-139">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3ed19-140">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3ed19-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3ed19-141">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3ed19-141">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
