---
title: Eccezioni previste
ms.date: 03/30/2017
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
ms.openlocfilehash: ea2043826291e77a59d61077d92b59baf129af90
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425873"
---
# <a name="expected-exceptions"></a><span data-ttu-id="45bec-102">Eccezioni previste</span><span class="sxs-lookup"><span data-stu-id="45bec-102">Expected Exceptions</span></span>
<span data-ttu-id="45bec-103">In questo esempio viene illustrato come rilevare le eccezioni previste quando si utilizza un client tipizzato.</span><span class="sxs-lookup"><span data-stu-id="45bec-103">This sample demonstrates how to catch expected exceptions when using a typed client.</span></span> <span data-ttu-id="45bec-104">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="45bec-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="45bec-105">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="45bec-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45bec-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="45bec-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="45bec-107">In questo esempio viene illustrata l'intercettazione e la gestione di due tipi di eccezione previsti che devono essere gestiti da programmi specifici, ovvero `TimeoutException` e `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-107">This sample demonstrates catching and handling the two expected exception types that correct programs must handle: `TimeoutException` and `CommunicationException`.</span></span>  
  
 <span data-ttu-id="45bec-108">Le eccezioni generate dai metodi di comunicazione in un client Windows Communication Foundation (WCF) possono essere previste o impreviste.</span><span class="sxs-lookup"><span data-stu-id="45bec-108">Exceptions that are thrown from communication methods on a Windows Communication Foundation (WCF) client are either expected or unexpected.</span></span> <span data-ttu-id="45bec-109">Le eccezioni impreviste includono gli errori irreversibili come `OutOfMemoryException` e gli errori di programmazione come `ArgumentNullException` o `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-109">Unexpected exceptions include catastrophic failures like `OutOfMemoryException` and programming errors like `ArgumentNullException` or `InvalidOperationException`.</span></span> <span data-ttu-id="45bec-110">In genere non è possibile utili per gestire gli errori imprevisti, in genere che è necessario non intercettare tali quando si chiama un metodo di comunicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="45bec-110">Typically there is no useful way to handle unexpected errors, so typically you should not catch them when calling a WCF client communication method.</span></span>  
  
 <span data-ttu-id="45bec-111">Previsto includono le eccezioni dai metodi di comunicazione in un client WCF `TimeoutException`, `CommunicationException`, e qualsiasi classe derivata da `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-111">Expected exceptions from communication methods on a WCF client include `TimeoutException`, `CommunicationException`, and any derived class of `CommunicationException`.</span></span> <span data-ttu-id="45bec-112">Queste informazioni indicano un problema durante la comunicazione che può essere gestita in modo sicuro da interrompere il client WCF e la segnalazione di un errore di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="45bec-112">These indicate a problem during communication that can be safely handled by aborting the WCF client and reporting a communication failure.</span></span> <span data-ttu-id="45bec-113">Perché fattori esterni possono provocare questi errori in qualsiasi applicazione, le eccezioni devono essere rilevate da applicazioni specifiche e deve essere eseguito il ripristino quando si verificano.</span><span class="sxs-lookup"><span data-stu-id="45bec-113">Because external factors can cause these errors in any application, correct applications must catch these exceptions and recover when they occur.</span></span>  
  
 <span data-ttu-id="45bec-114">Un client può generare numerose classi derivate di `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-114">There are several derived classes of `CommunicationException` that a client can throw.</span></span> <span data-ttu-id="45bec-115">In alcuni casi, le applicazioni rilevano anche alcune di queste eccezioni per una gestione speciale, ma lasciano che le altre vengano gestite come `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-115">In some cases, applications also catch some of these to do special handling, but let the others be handled as a `CommunicationException`.</span></span> <span data-ttu-id="45bec-116">Questo processo può essere portato a termine rilevando prima il tipo di eccezione più specifico e quindi `CommunicationException` in una clausola di rilevamento successiva.</span><span class="sxs-lookup"><span data-stu-id="45bec-116">This can be accomplished by catching the more specific exception type first and then catching `CommunicationException` in a later catch-clause.</span></span>  
  
 <span data-ttu-id="45bec-117">Il codice che chiama un metodo di comunicazione client deve rilevare `TimeoutException` e `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="45bec-117">Code that calls a client communication method must catch the `TimeoutException` and `CommunicationException`.</span></span> <span data-ttu-id="45bec-118">Un modo per gestire tali errori consiste nell'interrompere il client e riportare l'errore di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="45bec-118">One way to handle such errors is to abort the client and report the communication failure.</span></span>  
  
```csharp   
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="45bec-119">In seguito a un'eccezione prevista, il client può essere utilizzabile o non esserlo.</span><span class="sxs-lookup"><span data-stu-id="45bec-119">If an expected exception occurs, the client may or may not be usable afterwards.</span></span> <span data-ttu-id="45bec-120">Per determinare se il client può ancora essere utilizzato, verificare che la proprietà `State` sia impostata su `CommunicationState`.Opened.</span><span class="sxs-lookup"><span data-stu-id="45bec-120">To determine if the client is still usable, check that the `State` property is `CommunicationState`.Opened.</span></span> <span data-ttu-id="45bec-121">Se è aperto, può essere ancora utilizzato.</span><span class="sxs-lookup"><span data-stu-id="45bec-121">If it is still opened, then it is still usable.</span></span> <span data-ttu-id="45bec-122">In caso contrario è necessario interrompere il client e rilasciare tutti i riferimenti attinenti.</span><span class="sxs-lookup"><span data-stu-id="45bec-122">Otherwise you should abort the client and release all references to it.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="45bec-123">È possibile osservare che i client che dispongono di una sessione spesso possono più essere utilizzati dopo un'eccezione, mentre i client privi di una sessione spesso possono ancora essere utilizzati dopo un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="45bec-123">You may observe that clients that have a session are often no longer usable after an exception, and clients that do not have a session are often still usable after an exception.</span></span> <span data-ttu-id="45bec-124">Tuttavia, nessuno di questi comportamenti è garantito, pertanto se si desidera continuare a utilizzare il client dopo un'eccezione, l'applicazione dovere controllare la proprietà `State` per verificare che il client sia ancora aperto.</span><span class="sxs-lookup"><span data-stu-id="45bec-124">However, neither of these is guaranteed, so if you want to try to continue using the client after an exception your application should check the `State` property to verify the client is still opened.</span></span>  
  
 <span data-ttu-id="45bec-125">Quando si esegue l'esempio, le risposte e le eccezioni dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="45bec-125">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="45bec-126">Il processo client esegue due scenari, ognuno dei quali tenta di chiamare `Add` seguito da `Divide`.</span><span class="sxs-lookup"><span data-stu-id="45bec-126">The client process runs two scenarios, each of which attempts to call `Add` followed by `Divide`.</span></span> <span data-ttu-id="45bec-127">Il primo scenario simula un problema di rete interrompendo il client prima di effettuare la chiamata a `Divide`.</span><span class="sxs-lookup"><span data-stu-id="45bec-127">The first scenario simulates a network issue by aborting the client before making the call to `Divide`.</span></span> <span data-ttu-id="45bec-128">Il secondo scenario provoca una condizione di timeout impostando un valore di timeout troppo breve per consentire il completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="45bec-128">The second scenario causes a timeout condition by setting the timeout too short for the method to complete.</span></span> <span data-ttu-id="45bec-129">L'output previsto dal processo client è:</span><span class="sxs-lookup"><span data-stu-id="45bec-129">The expected output from the client process is:</span></span>  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="45bec-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="45bec-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="45bec-131">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="45bec-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="45bec-132">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="45bec-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="45bec-133">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="45bec-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="45bec-134">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="45bec-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="45bec-135">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="45bec-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="45bec-136">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="45bec-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="45bec-137">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="45bec-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
## <a name="see-also"></a><span data-ttu-id="45bec-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bec-138">See Also</span></span>
