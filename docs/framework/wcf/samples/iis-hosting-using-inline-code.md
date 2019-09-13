---
title: Hosting IIS mediante il codice inline
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 7713c8ca690570ee80721329a7857e6111c93e2f
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893209"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="6bc35-102">Hosting IIS mediante il codice inline</span><span class="sxs-lookup"><span data-stu-id="6bc35-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="6bc35-103">In questo esempio viene illustrato come implementare un servizio ospitato da Internet Information Services (IIS), in cui il codice del servizio è contenuto inline in un file con estensione svc e viene compilato su richiesta.</span><span class="sxs-lookup"><span data-stu-id="6bc35-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="6bc35-104">Il codice del servizio può anche essere implementato direttamente nei file del codice sorgente presenti nella directory \App_Code dell'applicazione, oppure essere compilato in assembly distribuiti in \bin.</span><span class="sxs-lookup"><span data-stu-id="6bc35-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="6bc35-105">In questo esempio non vengono illustrate tali tecniche.</span><span class="sxs-lookup"><span data-stu-id="6bc35-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="6bc35-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6bc35-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bc35-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6bc35-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6bc35-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6bc35-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6bc35-109">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="6bc35-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6bc35-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6bc35-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="6bc35-111">Nell'esempio viene illustrato un servizio tipico che implementa un contratto in cui viene definito un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="6bc35-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="6bc35-112">Il servizio è ospitato in IIS e il codice del servizio è interamente contenuto nel file Service.svc.</span><span class="sxs-lookup"><span data-stu-id="6bc35-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="6bc35-113">Il servizio viene attivato dall'host e compilato su richiesta dal primo messaggio inviato al servizio.</span><span class="sxs-lookup"><span data-stu-id="6bc35-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="6bc35-114">Non è necessaria la precompilazione.</span><span class="sxs-lookup"><span data-stu-id="6bc35-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="6bc35-115">Il servizio implementa un contratto `ICalculator`, come definito nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6bc35-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="6bc35-116">L'implementazione del servizio calcola e restituisce il risultato appropriato.</span><span class="sxs-lookup"><span data-stu-id="6bc35-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="6bc35-117">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="6bc35-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6bc35-118">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="6bc35-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6bc35-119">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6bc35-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="6bc35-120">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6bc35-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="6bc35-121">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6bc35-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="6bc35-122">Una volta compilata la soluzione, eseguire Setup. bat per configurare l'applicazione ServiceModelSamples in IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="6bc35-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="6bc35-123">La directory ServiceModelSamples dovrebbe ora essere visualizzata come applicazione IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="6bc35-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="6bc35-124">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6bc35-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="6bc35-125">Per un esempio su come creare un'applicazione client in grado di chiamare questo servizio, vedere [procedura: Creazione di un](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)client.</span><span class="sxs-lookup"><span data-stu-id="6bc35-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc35-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bc35-126">See also</span></span>

- [<span data-ttu-id="6bc35-127">Esempi di persistenza e hosting di AppFabric</span><span class="sxs-lookup"><span data-stu-id="6bc35-127">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
