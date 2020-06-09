---
title: Routing in base al corpo
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: 146baf806f4922f5e3ddd92a762772786e61d443
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594595"
---
# <a name="route-by-body"></a><span data-ttu-id="14aed-102">Routing in base al corpo</span><span class="sxs-lookup"><span data-stu-id="14aed-102">Route by Body</span></span>
<span data-ttu-id="14aed-103">In questo esempio viene illustrato come implementare un servizio che accetta oggetti di messaggi con qualsiasi azione SOAP.</span><span class="sxs-lookup"><span data-stu-id="14aed-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="14aed-104">Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="14aed-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="14aed-105">Il servizio implementa una sola operazione `Calculate` che accetta un parametro di richiesta <xref:System.ServiceModel.Channels.Message> e restituisce una risposta <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="14aed-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="14aed-106">In questo esempio il client è un'applicazione console (con estensione exe) e il servizio è ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="14aed-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14aed-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="14aed-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="14aed-108">Nell'esempio viene illustrata la distribuzione dei messaggi in base al contenuto del corpo.</span><span class="sxs-lookup"><span data-stu-id="14aed-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="14aed-109">Il meccanismo di invio dei messaggi del modello di servizio Windows Communication Foundation (WCF) incorporato è basato sulle azioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="14aed-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="14aed-110">Tuttavia, molti servizi Web esistenti definiscono tutte le relative operazioni con Action="".</span><span class="sxs-lookup"><span data-stu-id="14aed-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="14aed-111">È impossibile compilare un servizio basato su WSDL che continua a distribuire messaggi di richiesta in base alle informazioni dell'azione.</span><span class="sxs-lookup"><span data-stu-id="14aed-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="14aed-112">In questo esempio viene mostrato un contratto di servizio basato su WSDL (WSDL è contenuto nel file Service.wsdl incluso con l'esempio).</span><span class="sxs-lookup"><span data-stu-id="14aed-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="14aed-113">Il contratto di servizio è Calculator, simile a quello usato in [Introduzione](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="14aed-113">The service contract is Calculator, similar to the one used in [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="14aed-114">Tuttavia `[OperationContract]` specifica `Action=""` per tutte le operazioni.</span><span class="sxs-lookup"><span data-stu-id="14aed-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
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
  
 <span data-ttu-id="14aed-115">Se dispone di un contratto, un servizio richiede un comportamento di distribuzione `DispatchByBodyBehavior` personalizzato per consentire la distribuzione dei messaggi tra le operazioni.</span><span class="sxs-lookup"><span data-stu-id="14aed-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="14aed-116">Questo comportamento di distribuzione Inizializza il `DispatchByBodyElementOperationSelector` selettore dell'operazione personalizzato con una tabella dei nomi delle operazioni con chiave da QName dei rispettivi elementi wrapper.</span><span class="sxs-lookup"><span data-stu-id="14aed-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="14aed-117">`DispatchByBodyElementOperationSelector` analizza il tag iniziale del primo elemento figlio del corpo e seleziona l'operazione utilizzando la tabella menzionata.</span><span class="sxs-lookup"><span data-stu-id="14aed-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="14aed-118">Il client utilizza un proxy generato automaticamente da WSDL esportato dal servizio utilizzando [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="14aed-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```console  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="14aed-119">Se le azioni di tutte le operazioni sono vuote non si verifica alcun impatto sul codice client, eccetto che per i parametri Action nel proxy generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="14aed-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="14aed-120">Il codice client esegue molti calcoli.</span><span class="sxs-lookup"><span data-stu-id="14aed-120">The client code performs several calculations.</span></span> <span data-ttu-id="14aed-121">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="14aed-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="14aed-122">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="14aed-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="14aed-123">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="14aed-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="14aed-124">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14aed-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="14aed-125">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14aed-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="14aed-126">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="14aed-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14aed-127">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="14aed-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="14aed-128">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="14aed-128">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="14aed-129">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="14aed-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="14aed-130">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="14aed-130">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
