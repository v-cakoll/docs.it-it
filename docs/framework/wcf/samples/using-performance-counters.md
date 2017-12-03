---
title: Utilizzo dei contatori delle prestazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5963a1b2600066020562c1d17b0d2d2eb6eb67c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-performance-counters"></a><span data-ttu-id="9a7fe-102">Utilizzo dei contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="9a7fe-102">Using Performance Counters</span></span>
<span data-ttu-id="9a7fe-103">In questo esempio viene illustrato come accedere ai contatori delle prestazioni di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e come creare contatori delle prestazioni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-103">This sample demonstrates how to access [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="9a7fe-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9a7fe-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a7fe-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9a7fe-106">In questo esempio, il client chiama i quattro metodi del servizio `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="9a7fe-107">Questa procedura continua fino a quando il client viene interrotto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="9a7fe-108">Il servizio rimane inalterato.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="9a7fe-109">I contatori delle prestazioni vengono abilitati nella sezione di diagnostica del file Web.config per il servizio, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="9a7fe-110">Questa attività può essere eseguita anche utilizzando la [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9a7fe-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="9a7fe-111">Quando i contatori delle prestazioni vengono abilitati, l'intera suite di contatori delle prestazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene abilitata per il servizio.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-111">When performance counters are enabled, the entire suite of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters is enabled for the service.</span></span> <span data-ttu-id="9a7fe-112">.NET Framework gestisce automaticamente i dati relativi alle prestazioni a tre livelli: `ServiceModelService`, `ServiceModelEndpoint` e `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="9a7fe-113">Per ognuno di questi livelli sono presenti dei contatori delle prestazioni, ad esempio "Chiamate", "Chiamate al secondo" e "Chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="9a7fe-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9a7fe-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9a7fe-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9a7fe-115">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9a7fe-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9a7fe-116">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9a7fe-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9a7fe-117">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9a7fe-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="9a7fe-118">Per visualizzare i dati relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="9a7fe-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="9a7fe-119">Avviare lo strumento Performance Monitor facendo **avviare**, **Esegui...** , immettere `perfmon` e fare clic su **OK,** oppure dal Pannello di controllo, selezionare **strumenti di amministrazione** fare doppio clic su **prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a7fe-120">Non è possibile aggiungere contatori mentre il codice di esempio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="9a7fe-121">Rimuovere i contatori delle prestazioni elencati selezionandoli e premendo CANC.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="9a7fe-122">Aggiungi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contatori il pulsante destro del riquadro del grafico e selezionando **Aggiungi contatori**.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="9a7fe-123">Nel **Aggiungi contatori** nella finestra di dialogo **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 o ServiceModelService 3.0.0.0** nell'oggetto prestazione casella a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="9a7fe-124">Selezionare i contatori che si desidera visualizzare nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a7fe-125">Se nel computer non è in esecuzione alcun servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], non sono disponibili contatori delle prestazioni di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a7fe-125">There are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters for a service if there are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="9a7fe-126">Per utilizzare l'editor di configurazione per abilitare i contatori</span><span class="sxs-lookup"><span data-stu-id="9a7fe-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="9a7fe-127">Aprire un'istanza di SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="9a7fe-128">Dal menu File, fare clic su **aprire** e quindi fare clic su **file di configurazione...** .</span><span class="sxs-lookup"><span data-stu-id="9a7fe-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="9a7fe-129">Passare alla cartella del servizio dell'applicazione di esempio e aprire il file Web.config.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="9a7fe-130">Fare clic su **diagnostica** nell'albero configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="9a7fe-131">Attiva/disattiva **contatore delle prestazioni** nel **diagnostica** finestra per visualizzare "All".</span><span class="sxs-lookup"><span data-stu-id="9a7fe-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="9a7fe-132">Salvare il file di configurazione e uscire dall'editor.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a7fe-133">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9a7fe-134">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a7fe-135">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a7fe-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a7fe-136">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9a7fe-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="9a7fe-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a7fe-137">See Also</span></span>  
 [<span data-ttu-id="9a7fe-138">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="9a7fe-138">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
