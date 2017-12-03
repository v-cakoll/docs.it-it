---
title: "Compatibilità con ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c8cf38e65bbc917720b1a1c5b604d81ca536c14
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="b28c0-102">Compatibilità con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b28c0-102">ASP.NET Compatibility</span></span>
<span data-ttu-id="b28c0-103">In questo esempio viene illustrato come abilitare la modalità di compatibilità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b28c0-103">This sample demonstrates how to enable [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="b28c0-104">I servizi in esecuzione nella modalità di compatibilità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] si integrano pienamente nella pipeline dell'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e possono avvalersi delle funzionalità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], ad esempio l'autorizzazione file/URL, lo stato della sessione e la classe <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="b28c0-104">Services running in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode participate fully in the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application pipeline and can make use of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="b28c0-105">La classe <xref:System.Web.HttpContext> consente di accedere ai cookie, alle sessioni e ad altre funzionalità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b28c0-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features.</span></span> <span data-ttu-id="b28c0-106">Questa modalità richiede che le associazioni usino il trasporto HTTP e che il servizio stesso debba essere ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="b28c0-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>  
  
 <span data-ttu-id="b28c0-107">In questo esempio, il client è un'applicazione console (un file eseguibile) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b28c0-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b28c0-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b28c0-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b28c0-109">Per eseguire questo esempio è necessario un pool di applicazioni di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b28c0-109">This sample requires a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] application pool in order to run.</span></span> <span data-ttu-id="b28c0-110">Per creare un nuovo pool di applicazioni o modificare il pool di applicazioni predefinito, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b28c0-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>  
>   
>  1.  <span data-ttu-id="b28c0-111">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="b28c0-111">Open **Control Panel**.</span></span>  <span data-ttu-id="b28c0-112">Aprire il **strumenti di amministrazione** applet sotto il **sistema e sicurezza** intestazione.</span><span class="sxs-lookup"><span data-stu-id="b28c0-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="b28c0-113">Aprire il **Gestione Internet Information Services (IIS)** applet.</span><span class="sxs-lookup"><span data-stu-id="b28c0-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>  
> 2.  <span data-ttu-id="b28c0-114">Espandere il treeview nel **connessioni** riquadro.</span><span class="sxs-lookup"><span data-stu-id="b28c0-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="b28c0-115">Selezionare il **pool di applicazioni** nodo.</span><span class="sxs-lookup"><span data-stu-id="b28c0-115">Select the **Application Pools** node.</span></span>  
> 3.  <span data-ttu-id="b28c0-116">Per impostare il pool di applicazioni predefinito da utilizzare [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (che potrebbe causare problemi di incompatibilità con i siti esistenti), fare doppio clic su di **DefaultAppPool** voce di elenco e selezionare **impostazioni di base...** .</span><span class="sxs-lookup"><span data-stu-id="b28c0-116">To set the default application pool to use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="b28c0-117">Impostare il **.Net Framework versione** pull-down **.Net Framework v 4.0.30128** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="b28c0-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>  
> 4.  <span data-ttu-id="b28c0-118">Per creare un nuovo pool di applicazioni che utilizza [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (per mantenere la compatibilità per le altre applicazioni), fare doppio clic su di **pool di applicazioni** nodo e selezionare **Aggiungi Pool di applicazioni...** .</span><span class="sxs-lookup"><span data-stu-id="b28c0-118">To create a new application pool that uses [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="b28c0-119">Denominare il nuovo pool di applicazioni e impostare il **.Net Framework versione** pull-down **.Net Framework v 4.0.30128** (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="b28c0-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="b28c0-120">Dopo che è in esecuzione il programma di installazione di passaggi inferiore, destro la **ServiceModelSamples** dell'applicazione e selezionare **Gestione applicazione**, **impostazioni avanzate...** .</span><span class="sxs-lookup"><span data-stu-id="b28c0-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="b28c0-121">Impostare il **Pool di applicazioni** per il nuovo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b28c0-121">Set the **Application Pool** to the new application pool.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b28c0-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b28c0-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b28c0-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b28c0-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b28c0-124">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b28c0-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b28c0-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b28c0-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 <span data-ttu-id="b28c0-126">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="b28c0-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="b28c0-127">Il contratto `ICalculator` è stato modificato al contratto `ICalculatorSession` per consentire l'esecuzione di un set di operazioni mantenendo il risultato della sessione.</span><span class="sxs-lookup"><span data-stu-id="b28c0-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="b28c0-128">Usando questa funzionalità il servizio mantiene lo stato di ogni client, mentre vengono chiamate più operazioni del servizio per eseguire un calcolo.</span><span class="sxs-lookup"><span data-stu-id="b28c0-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="b28c0-129">Il client può recuperare il risultato corrente chiamando `Result` e può azzerare il risultato chiamando `Clear`.</span><span class="sxs-lookup"><span data-stu-id="b28c0-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>  
  
 <span data-ttu-id="b28c0-130">Il servizio usa la sessione di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] per archiviare il risultato per ogni sessione client.</span><span class="sxs-lookup"><span data-stu-id="b28c0-130">The service uses the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session to store the result for each client session.</span></span> <span data-ttu-id="b28c0-131">Questo consente al servizio di mantenere il risultato della sessione per ogni client, su più chiamate al servizio.</span><span class="sxs-lookup"><span data-stu-id="b28c0-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b28c0-132">Lo stato della sessione di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e delle sessioni di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono molto diversi.</span><span class="sxs-lookup"><span data-stu-id="b28c0-132">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session state and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions are very different things.</span></span>  <span data-ttu-id="b28c0-133">Vedere il [sessione](../../../../docs/framework/wcf/samples/session.md) per informazioni dettagliate su [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessioni.</span><span class="sxs-lookup"><span data-stu-id="b28c0-133">See the [Session](../../../../docs/framework/wcf/samples/session.md) for details on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions.</span></span>  
  
 <span data-ttu-id="b28c0-134">Il servizio ha una dipendenza stretta con lo stato della sessione di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e richiede che la modalità di compatibilità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="b28c0-134">The service has an intimate dependency on [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session state and requires [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compatibility mode to function correctly.</span></span> <span data-ttu-id="b28c0-135">Questi requisiti vengono espressi in modo dichiarativo applicando l'attributo `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="b28c0-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 <span data-ttu-id="b28c0-136">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="b28c0-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b28c0-137">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="b28c0-137">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b28c0-138">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b28c0-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b28c0-139">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b28c0-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b28c0-140">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b28c0-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b28c0-141">Dopo aver compilato la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b28c0-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="b28c0-142">La directory ServiceModelSamples verrà ora visualizzata come applicazione [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b28c0-142">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="b28c0-143">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b28c0-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28c0-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b28c0-144">See Also</span></span>  
 [<span data-ttu-id="b28c0-145">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="b28c0-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
