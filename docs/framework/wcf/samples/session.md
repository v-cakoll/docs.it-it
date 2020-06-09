---
title: Sessione
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: 283c8b9641dcce8b0207d3be0024b57369d125ff
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591449"
---
# <a name="session"></a><span data-ttu-id="898df-102">Sessione</span><span class="sxs-lookup"><span data-stu-id="898df-102">Session</span></span>
<span data-ttu-id="898df-103">Nell'esempio della sessione viene illustrato come implementare un contratto che richiede una sessione.</span><span class="sxs-lookup"><span data-stu-id="898df-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="898df-104">Una sessione fornisce il contesto per l'esecuzione di più operazioni.</span><span class="sxs-lookup"><span data-stu-id="898df-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="898df-105">Ciò consente a un servizio di associare lo stato a una sessione specifica, in modo che le operazioni successive possano utilizzare lo stato di un'operazione precedente.</span><span class="sxs-lookup"><span data-stu-id="898df-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="898df-106">Questo esempio è basato sul [Introduzione](getting-started-sample.md), che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="898df-106">This sample is based on the [Getting Started](getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="898df-107">Il contratto `ICalculator` è stato modificato per consentire l'esecuzione di un insieme di operazioni aritmetiche, mantenendo il risultato parziale.</span><span class="sxs-lookup"><span data-stu-id="898df-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="898df-108">Questa funzionalità è definita dal contratto `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="898df-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="898df-109">Il servizio gestisce lo stato di un client mentre vengono chiamate più operazioni del servizio per eseguire un calcolo.</span><span class="sxs-lookup"><span data-stu-id="898df-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="898df-110">Il client può recuperare il risultato corrente chiamando `Result()` e azzerare il risultato chiamando `Clear()`.</span><span class="sxs-lookup"><span data-stu-id="898df-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="898df-111">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="898df-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="898df-112">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="898df-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="898df-113">L'impostazione di <xref:System.ServiceModel.SessionMode> del contratto su `Required` assicura che, quando il contratto viene esposto su una particolare associazione, l'associazione supporti le sessioni.</span><span class="sxs-lookup"><span data-stu-id="898df-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="898df-114">Se l'associazione non supporta le sessioni viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="898df-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="898df-115">L'interfaccia `ICalculatorSession` è definita in modo che possono essere chiamate una o più operazioni, aspetto che modifica un risultato parziale, come illustrato dal codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="898df-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="898df-116">Il servizio utilizza un <xref:System.ServiceModel.InstanceContextMode> di <xref:System.ServiceModel.InstanceContextMode.PerSession> per associare un determinato contesto dell'istanza del servizio a ogni sessione in ingresso.</span><span class="sxs-lookup"><span data-stu-id="898df-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="898df-117">Questo consente al servizio di gestire il risultato parziale per ogni sessione in una variabile membro locale.</span><span class="sxs-lookup"><span data-stu-id="898df-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="898df-118">Quando si esegue l'esempio, il client esegue molte richieste al server e richiede il risultato, che viene quindi visualizzato nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="898df-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="898df-119">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="898df-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="898df-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="898df-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="898df-121">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="898df-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="898df-122">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="898df-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="898df-123">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="898df-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="898df-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="898df-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="898df-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="898df-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="898df-126">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="898df-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="898df-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="898df-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
