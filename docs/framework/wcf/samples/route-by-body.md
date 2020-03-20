---
title: Routing in base al corpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: c3f4b19e646a6a9716d2264a3969b339208c60a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144188"
---
# <a name="route-by-body"></a><span data-ttu-id="55503-102">Routing in base al corpo</span><span class="sxs-lookup"><span data-stu-id="55503-102">Route by Body</span></span>
<span data-ttu-id="55503-103">In questo esempio viene illustrato come implementare un servizio che accetta oggetti di messaggi con qualsiasi azione SOAP.</span><span class="sxs-lookup"><span data-stu-id="55503-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="55503-104">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="55503-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="55503-105">Il servizio implementa una sola operazione `Calculate` che accetta un parametro di richiesta <xref:System.ServiceModel.Channels.Message> e restituisce una risposta <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="55503-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="55503-106">In questo esempio il client è un'applicazione console (con estensione exe) e il servizio è ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="55503-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55503-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="55503-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="55503-108">Nell'esempio viene illustrata la distribuzione dei messaggi in base al contenuto del corpo.</span><span class="sxs-lookup"><span data-stu-id="55503-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="55503-109">Il meccanismo di invio dei messaggi del modello di servizio Windows Communication Foundation (WCF) incorporato è basato sulle azioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="55503-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="55503-110">Tuttavia, molti servizi Web esistenti definiscono tutte le relative operazioni con Action="".</span><span class="sxs-lookup"><span data-stu-id="55503-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="55503-111">È impossibile compilare un servizio basato su WSDL che continua a distribuire messaggi di richiesta in base alle informazioni dell'azione.</span><span class="sxs-lookup"><span data-stu-id="55503-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="55503-112">In questo esempio viene mostrato un contratto di servizio basato su WSDL (WSDL è contenuto nel file Service.wsdl incluso con l'esempio).</span><span class="sxs-lookup"><span data-stu-id="55503-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="55503-113">Il contratto di servizio è Calcolatrice, simile a quello utilizzato in [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="55503-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="55503-114">Tuttavia `[OperationContract]` specifica `Action=""` per tutte le operazioni.</span><span class="sxs-lookup"><span data-stu-id="55503-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```csharp  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="55503-115">Se dispone di un contratto, un servizio richiede un comportamento di distribuzione `DispatchByBodyBehavior` personalizzato per consentire la distribuzione dei messaggi tra le operazioni.</span><span class="sxs-lookup"><span data-stu-id="55503-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="55503-116">Questo comportamento dispatch `DispatchByBodyElementOperationSelector` inizializza il selettore dell'operazione personalizzata con una tabella dei nomi delle operazioni con chiave da QName dei rispettivi elementi wrapper.</span><span class="sxs-lookup"><span data-stu-id="55503-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="55503-117">`DispatchByBodyElementOperationSelector` analizza il tag iniziale del primo elemento figlio del corpo e seleziona l'operazione utilizzando la tabella menzionata.</span><span class="sxs-lookup"><span data-stu-id="55503-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="55503-118">Il client utilizza un proxy generato automaticamente dal file WSDL esportato dal servizio mediante lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="55503-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="55503-119">Se le azioni di tutte le operazioni sono vuote non si verifica alcun impatto sul codice client, eccetto che per i parametri Action nel proxy generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55503-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="55503-120">Il codice client esegue molti calcoli.</span><span class="sxs-lookup"><span data-stu-id="55503-120">The client code performs several calculations.</span></span> <span data-ttu-id="55503-121">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="55503-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="55503-122">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="55503-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="55503-123">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="55503-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="55503-124">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55503-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="55503-125">Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55503-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="55503-126">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="55503-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="55503-127">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="55503-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="55503-128">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="55503-128">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="55503-129">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="55503-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="55503-130">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="55503-130">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
