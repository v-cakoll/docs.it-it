---
title: Comportamento predefinito del servizio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
ms.openlocfilehash: 4da3deff69930dba7249e0651f820b448b837862
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592450"
---
# <a name="default-service-behavior"></a><span data-ttu-id="9fc2c-102">Comportamento predefinito del servizio</span><span class="sxs-lookup"><span data-stu-id="9fc2c-102">Default Service Behavior</span></span>
<span data-ttu-id="9fc2c-103">In questo esempio viene illustrato come configurare le impostazioni del comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-103">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="9fc2c-104">L'esempio è basato sulla [Introduzione](getting-started-sample.md), che implementa il `ICalculator` contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-104">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="9fc2c-105">In questo esempio vengono definiti in modo esplicito i comportamenti del servizio e i comportamenti dell'operazione utilizzando gli attributi <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-105">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="9fc2c-106">È possibile configurare i comportamenti nei file di configurazione oppure in modo imperativo nel codice, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-106">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="9fc2c-107">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="9fc2c-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fc2c-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9fc2c-109">La classe del servizio specifica i comportamenti con <xref:System.ServiceModel.ServiceBehaviorAttribute> e <xref:System.ServiceModel.OperationBehaviorAttribute>, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-109">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="9fc2c-110">Tutti i valori specificati sono le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-110">All values specified are the defaults.</span></span>  
  
```csharp
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="9fc2c-111">I comportamenti del servizio vengono specificati con l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-111">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="9fc2c-112">Nella tabella seguente sono descritti alcuni di tali comportamenti.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-112">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="9fc2c-113">Comportamento del servizio</span><span class="sxs-lookup"><span data-stu-id="9fc2c-113">Service behavior</span></span>|<span data-ttu-id="9fc2c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fc2c-114">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="9fc2c-115">Arresta automaticamente una sessione alla richiesta del client.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-115">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="9fc2c-116">Specifica la modalità di concorrenza per ogni istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-116">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="9fc2c-117">Specifica la modalità di contesto dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-117">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="9fc2c-118">Determina se utilizzare il contesto di sincronizzazione fornito, se impostato.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-118">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="9fc2c-119">Usare questa proprietà quando si desidera controllare se usare un `WindowsFormsSynchronizationContext` in applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-119">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="9fc2c-120">Determina se le eccezioni di esecuzione generali non gestite devono essere convertite in una `Fault<string>` e inviate come messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-120">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="9fc2c-121">Specifica il livello di isolamento per le transazioni.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-121">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="9fc2c-122">Determina se intestazioni impreviste del messaggio provocano una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-122">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="9fc2c-123">I comportamenti dell'operazione vengono specificati utilizzando l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-123">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="9fc2c-124">Nella tabella seguente sono descritti alcuni di tali comportamenti.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-124">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="9fc2c-125">Comportamento dell'operazione</span><span class="sxs-lookup"><span data-stu-id="9fc2c-125">Operation Behavior</span></span>|<span data-ttu-id="9fc2c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fc2c-126">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="9fc2c-127">Determina se il completamento dell'operazione del servizio esegue il commit della transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-127">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="9fc2c-128">Determina se l'operazione del servizio si integra in una transazione propagata dal client.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-128">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="9fc2c-129">Determina se l'operazione del servizio rappresenta l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-129">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="9fc2c-130">Determina se le istanze del servizio vengono riciclate all'inizio o alla fine della chiamata dell'operazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-130">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="9fc2c-131">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-131">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9fc2c-132">Il ritardo tra le chiamate è il risultato delle chiamate a `System.Threading.Thread.Sleep()` eseguite nelle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-132">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="9fc2c-133">Gli altri esempi di comportamento illustrano questi comportamenti in maggiore dettaglio.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-133">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="9fc2c-134">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-134">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9fc2c-135">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9fc2c-135">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9fc2c-136">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9fc2c-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9fc2c-137">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9fc2c-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9fc2c-138">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9fc2c-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9fc2c-139">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9fc2c-140">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-140">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="9fc2c-141">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9fc2c-142">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9fc2c-142">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
