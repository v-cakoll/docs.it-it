---
title: Sessione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01c1bc2d202080349db32452adfe549d7a6dd3cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="session"></a><span data-ttu-id="91d8d-102">Sessione</span><span class="sxs-lookup"><span data-stu-id="91d8d-102">Session</span></span>
<span data-ttu-id="91d8d-103">Nell'esempio della sessione viene illustrato come implementare un contratto che richiede una sessione.</span><span class="sxs-lookup"><span data-stu-id="91d8d-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="91d8d-104">Una sessione fornisce il contesto per l'esecuzione di più operazioni.</span><span class="sxs-lookup"><span data-stu-id="91d8d-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="91d8d-105">Ciò consente a un servizio di associare lo stato a una sessione specifica, in modo che le operazioni successive possano utilizzare lo stato di un'operazione precedente.</span><span class="sxs-lookup"><span data-stu-id="91d8d-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="91d8d-106">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="91d8d-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="91d8d-107">Il contratto `ICalculator` è stato modificato per consentire l'esecuzione di un insieme di operazioni aritmetiche, mantenendo il risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="91d8d-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="91d8d-108">Questa funzionalità è definita dal contratto `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="91d8d-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="91d8d-109">Il servizio gestisce lo stato di un client mentre vengono chiamate più operazioni del servizio per eseguire un calcolo.</span><span class="sxs-lookup"><span data-stu-id="91d8d-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="91d8d-110">Il client può recuperare il risultato corrente chiamando `Result()` e azzerare il risultato chiamando `Clear()`.</span><span class="sxs-lookup"><span data-stu-id="91d8d-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="91d8d-111">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="91d8d-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91d8d-112">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="91d8d-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="91d8d-113">L'impostazione di <xref:System.ServiceModel.SessionMode> del contratto su `Required` assicura che, quando il contratto viene esposto su una particolare associazione, l'associazione supporti le sessioni.</span><span class="sxs-lookup"><span data-stu-id="91d8d-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="91d8d-114">Se l'associazione non supporta le sessioni viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="91d8d-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="91d8d-115">L'interfaccia `ICalculatorSession` è definita in modo che possono essere chiamate una o più operazioni, aspetto che modifica un risultato parziale, come illustrato dal codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="91d8d-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="91d8d-116">Il servizio utilizza un <xref:System.ServiceModel.InstanceContextMode> di <xref:System.ServiceModel.InstanceContextMode.PerSession> per associare un determinato contesto dell'istanza del servizio a ogni sessione in ingresso.</span><span class="sxs-lookup"><span data-stu-id="91d8d-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="91d8d-117">Questo consente al servizio di gestire il risultato parziale per ogni sessione in una variabile membro locale.</span><span class="sxs-lookup"><span data-stu-id="91d8d-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 <span data-ttu-id="91d8d-118">Quando si esegue l'esempio, il client esegue molte richieste al server e richiede il risultato, che viene quindi visualizzato nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="91d8d-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="91d8d-119">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="91d8d-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="91d8d-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="91d8d-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="91d8d-121">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="91d8d-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="91d8d-122">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="91d8d-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="91d8d-123">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="91d8d-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91d8d-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="91d8d-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91d8d-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="91d8d-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="91d8d-126">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91d8d-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91d8d-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="91d8d-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## <a name="see-also"></a><span data-ttu-id="91d8d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91d8d-128">See Also</span></span>
