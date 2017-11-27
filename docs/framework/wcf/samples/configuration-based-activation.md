---
title: Attivazione basata sulla configurazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: db67447ce262949c9ad302a37420fc7023264bd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-based-activation"></a><span data-ttu-id="d696d-102">Attivazione basata sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="d696d-102">Configuration-Based Activation</span></span>
<span data-ttu-id="d696d-103">In questo esempio viene descritto come attivare servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] senza richiedere un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d696d-103">This sample demonstrates how to activate [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d696d-104">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d696d-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d696d-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d696d-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d696d-106">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d696d-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d696d-107">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d696d-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="d696d-108">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d696d-108">Sample Details</span></span>  
 <span data-ttu-id="d696d-109">In questo esempio il client è il client di prova [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e il servizio è ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="d696d-109">In this sample, the client is the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d696d-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d696d-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="d696d-111">Attivazione di servizi senza richiedere un file con estensione svc</span><span class="sxs-lookup"><span data-stu-id="d696d-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="d696d-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], per l'attivazione di un servizio è richiesto un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d696d-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="d696d-113">Ciò causa un ulteriore sovraccarico di gestione, perché insieme all'applicazione, è necessario distribuire e gestire un file aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="d696d-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="d696d-114">Con la versione di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], è possibile configurare i componenti di attivazione utilizzando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d696d-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="d696d-115"> introduce un nuovo elemento di configurazione (<xref:System.ServiceModel.Configuration.ServiceActivationElement>) nella sezione <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d696d-115"> introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="d696d-116">La raccolta <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> accetta una raccolta di servizi da attivare, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d696d-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="d696d-117">È importante notare che la configurazione ha un aspetto molto simile alla configurazione di file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d696d-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="d696d-118">Un attributo aggiuntivo introdotto è `relativeAddress`, che fornisce l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="d696d-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="d696d-119">L'indirizzo relativo è anche il percorso virtuale per il servizio.</span><span class="sxs-lookup"><span data-stu-id="d696d-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="d696d-120">L'host recupera il file Web.config del file dal percorso `virtualPath`, se presente; in caso contrario, l'host esegue ricerche in modo ricorsivo nella cartella padre.</span><span class="sxs-lookup"><span data-stu-id="d696d-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d696d-121">Per il funzionamento di questo esempio, è necessario l'hosting in IIS.</span><span class="sxs-lookup"><span data-stu-id="d696d-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d696d-122">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="d696d-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="d696d-123">Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire il file Service.csproj.</span><span class="sxs-lookup"><span data-stu-id="d696d-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="d696d-124">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d696d-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d696d-125">Eseguire il test del servizio eseguendo WCFTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="d696d-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="d696d-126">Utilizzando [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], passare alla cartella %SystemDrive%\Programmi\Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="d696d-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="d696d-127">Eseguire WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="d696d-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="d696d-128">Impostare l'indirizzo MEX del servizio.</span><span class="sxs-lookup"><span data-stu-id="d696d-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="d696d-129">Premere CTRL+SHIFT+A per impostare l'indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="d696d-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="d696d-130">Impostare l'indirizzo su http://localhost/ServiceModelSamples/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="d696d-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="d696d-131">Eseguire l'operazione `Add`.</span><span class="sxs-lookup"><span data-stu-id="d696d-131">Perform the `Add` operation.</span></span> <span data-ttu-id="d696d-132">Impostare il valore nel parametro `n1` su 10 e il valore nel parametro `n2` su 15.</span><span class="sxs-lookup"><span data-stu-id="d696d-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="d696d-133">Premere **richiamare**.</span><span class="sxs-lookup"><span data-stu-id="d696d-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="d696d-134">Il risultato previsto è 25.</span><span class="sxs-lookup"><span data-stu-id="d696d-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d696d-135">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d696d-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d696d-136">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d696d-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d696d-137">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d696d-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d696d-138">Una volta compilata la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in IIS.</span><span class="sxs-lookup"><span data-stu-id="d696d-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="d696d-139">La directory ServiceModelSamples deve essere visualizzata come applicazione IIS.</span><span class="sxs-lookup"><span data-stu-id="d696d-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="d696d-140">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d696d-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d696d-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d696d-141">See Also</span></span>  
 [<span data-ttu-id="d696d-142">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="d696d-142">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
