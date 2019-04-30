---
title: Usare Chiudi e Interrompi per rilasciare risorse client WCF
description: Dispose può avere esito negativo e generano eccezioni quando si verifica un errore di rete. Che può causare comportamenti indesiderati. Invece utilizzare Chiudi e Interrompi per rilasciare le risorse del client quando la rete non è riuscita.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 58f828d9cd85806f5f04c349a7de18828ab5f6f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007573"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a><span data-ttu-id="f7548-105">Chiusura e interruzione rilasciare le risorse in modo sicuro quando le connessioni di rete sono stato eliminato</span><span class="sxs-lookup"><span data-stu-id="f7548-105">Close and Abort release resources safely when network connections have dropped</span></span>

<span data-ttu-id="f7548-106">In questo esempio viene illustrato come utilizzare il `Close` e `Abort` metodi per pulire le risorse quando si usa un client tipizzato.</span><span class="sxs-lookup"><span data-stu-id="f7548-106">This sample demonstrates using the `Close` and `Abort` methods to clean up resources when using a typed client.</span></span> <span data-ttu-id="f7548-107">Il `using` istruzione genera eccezioni quando la connessione di rete non è affidabile.</span><span class="sxs-lookup"><span data-stu-id="f7548-107">The `using` statement causes exceptions when the network connection is not robust.</span></span> <span data-ttu-id="f7548-108">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="f7548-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="f7548-109">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f7548-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="f7548-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f7548-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="f7548-111">In questo esempio vengono illustrati due dei problemi comuni che si verificano in caso di utilizzo dell'istruzione "using" di C# con i client tipizzati e il codice che pulisce correttamente le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f7548-111">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>

<span data-ttu-id="f7548-112">L'istruzione "using" di C# genera una chiamata a `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="f7548-112">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="f7548-113">Questo corrisponde a `Close`(), che può generare eccezioni quando si verifica un errore di rete.</span><span class="sxs-lookup"><span data-stu-id="f7548-113">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="f7548-114">Poiché la chiamata a `Dispose`() si verifica implicitamente alla parentesi graffa di chiusura del blocco "using", è probabile che l'origine delle eccezioni non venga rilevata da chi scrive il codice e da chi lo legge.</span><span class="sxs-lookup"><span data-stu-id="f7548-114">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="f7548-115">Questa situazione può causare errori dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f7548-115">This represents a potential source of application errors.</span></span>

<span data-ttu-id="f7548-116">Il primo problema, illustrato nel metodo `DemonstrateProblemUsingCanThrow` è che la parentesi graffa di chiusura genera un'eccezione e il codice dopo che la parentesi graffa di chiusura non viene eseguito:</span><span class="sxs-lookup"><span data-stu-id="f7548-116">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

<span data-ttu-id="f7548-117">Anche se non vengono generate eccezioni nel blocco "using" o se tutte le eccezioni all'interno del blocco "using" vengono rilevate, `Console.WriteLine` potrebbe non verificarsi visto che la chiamata `Dispose`() implicita potrebbe generare un'eccezione alla parentesi graffa di chiusura.</span><span class="sxs-lookup"><span data-stu-id="f7548-117">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.WriteLine` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>

<span data-ttu-id="f7548-118">Il secondo problema, illustrato nel metodo `DemonstrateProblemUsingCanThrowAndMask` deriva da un'altra implicazione della parentesi graffa di chiusura che genera un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="f7548-118">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

<span data-ttu-id="f7548-119">Poiché `Dispose`() si verifica in un blocco "finally", `ApplicationException` non viene mai visualizzato al di fuori del blocco "using" se si verifica un errore in `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="f7548-119">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="f7548-120">Se il codice esterno deve essere in grado di rilevare quando si verifica `ApplicationException`, si potrebbero verificare problemi se il costrutto "using" maschera questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="f7548-120">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>

<span data-ttu-id="f7548-121">Nell'esempio viene infine illustrato come pulire correttamente le eccezioni che si verificano in `DemonstrateCleanupWithExceptions`.</span><span class="sxs-lookup"><span data-stu-id="f7548-121">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="f7548-122">Questa operazione utilizza un blocco try/catch per segnalare gli errori e chiamare `Abort`.</span><span class="sxs-lookup"><span data-stu-id="f7548-122">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="f7548-123">Vedere le [eccezioni previsto](../../../../docs/framework/wcf/samples/expected-exceptions.md) esempio per ulteriori informazioni sul rilevamento delle eccezioni da chiamate del client.</span><span class="sxs-lookup"><span data-stu-id="f7548-123">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> <span data-ttu-id="f7548-124">L'istruzione using e ServiceHost: Molte applicazioni self-hosting poco più di ospitare un servizio e ServiceHost. Close raramente genera un'eccezione, in modo che tali applicazioni possono utilizzare in modo sicuro l'utilizzo dell'istruzione ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="f7548-124">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="f7548-125">Tuttavia, è consigliabile prendere in considerazione che ServiceHost.Close può generare un'eccezione `CommunicationException`, pertanto se l'applicazione è ancora in esecuzione dopo avere chiuso ServiceHost, è necessario evitare di usare l'istruzione using e seguire il modello fornito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f7548-125">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>

<span data-ttu-id="f7548-126">Quando si esegue l'esempio, le risposte e le eccezioni dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="f7548-126">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>

<span data-ttu-id="f7548-127">Il processo client esegue tre scenari, ognuno dei quali tenta di chiamare `Divide`.</span><span class="sxs-lookup"><span data-stu-id="f7548-127">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="f7548-128">Nel primo scenario viene descritto il codice ignorato a causa di un'eccezione da `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="f7548-128">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="f7548-129">Nel secondo scenario viene illustrata un'eccezione importante mascherata a causa di un'eccezione da `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="f7548-129">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="f7548-130">Nel terzo scenario viene illustrato come eseguire correttamente la pulizia.</span><span class="sxs-lookup"><span data-stu-id="f7548-130">The third scenario demonstrates correct clean up.</span></span>

<span data-ttu-id="f7548-131">L'output previsto dal processo client è:</span><span class="sxs-lookup"><span data-stu-id="f7548-131">The expected output from the client process is:</span></span>

```
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f7548-132">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f7548-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f7548-133">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f7548-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f7548-134">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f7548-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="f7548-135">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f7548-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7548-136">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f7548-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f7548-137">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f7548-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f7548-138">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f7548-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f7548-139">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f7548-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`
