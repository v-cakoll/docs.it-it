---
title: Rilevamento tramite un file di testo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1d4b3f319d86dd463dabc8b71be7c76c7fef41f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="8ad2d-102">Rilevamento tramite un file di testo</span><span class="sxs-lookup"><span data-stu-id="8ad2d-102">Tracking Using a Text File</span></span>
<span data-ttu-id="8ad2d-103">In questo esempio viene illustrato come estendere il rilevamento in [!INCLUDE[wf](../../../../includes/wf-md.md)] creando un partecipante di rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-103">This sample demonstrates how to extend tracking in [!INCLUDE[wf](../../../../includes/wf-md.md)] by creating a custom tracking participant.</span></span> <span data-ttu-id="8ad2d-104">I partecipanti di rilevamento sono classi .NET Framework che ricevono record di rilevamento dal runtime man mano che vengono generati.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="8ad2d-105">È possibile creare un partecipante di rilevamento per trasportare gli eventi di rilevamento a qualunque destinazione necessaria per lo specifico scenario.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="8ad2d-106">Ad esempio, il partecipante di rilevamento Analisi eventi per Windows (ETW) viene fornito come parte di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ad2d-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="8ad2d-107">Il partecipante di rilevamento in questo esempio scrive i record in formato XML in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="8ad2d-108">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="8ad2d-108">Sample details</span></span>  
 <span data-ttu-id="8ad2d-109">Per ottimizzare l'utilità e l'affidabilità del partecipante di rilevamento, è necessario completare alcuni passaggi aggiuntivi per collegare correttamente il partecipante di rilevamento al runtime.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="8ad2d-110">Nella tabella seguente vengono descritte le classi usate in questo esempio per creare un partecipante di rilevamento conforme alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="8ad2d-111">Classe</span><span class="sxs-lookup"><span data-stu-id="8ad2d-111">Class</span></span>|<span data-ttu-id="8ad2d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ad2d-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="8ad2d-113"><xref:System.ServiceModel.Configuration.BehaviorExtensionElement> consente di definire la sezione di configurazione usata per configurare il partecipante di rilevamento del file di testo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="8ad2d-114">Gli utenti possono specificare la destinazione del file di log usando file di configurazione standard di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="8ad2d-115">I comportamenti disponibili in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consentono agli utenti di inserire estensioni nel runtime.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-115">Behaviors in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="8ad2d-116">Tramite questo comportamento il partecipante di rilevamento viene aggiunto al servizio all'avvio di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="8ad2d-117">Il partecipante di rilevamento riceve i partecipanti di rilevamento in fase di esecuzione e li archivia in un file di log come XML.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="8ad2d-118">Configurazione degli elementi estensione di comportamento</span><span class="sxs-lookup"><span data-stu-id="8ad2d-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="8ad2d-119">Per poter usare l'elemento estensione di comportamento descritto in precedenza usando file di configurazione di .NET Framework, è necessario un ulteriore passaggio.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="8ad2d-120">La configurazione seguente deve essere inserita nei file di configurazione in cui verrà usata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="8ad2d-121">Vedere il file Web.config incluso nell'esempio per un completo esempio di utilizzo della configurazione di elementi estensione di comportamento.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="8ad2d-122">Record di rilevamento personalizzati</span><span class="sxs-lookup"><span data-stu-id="8ad2d-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="8ad2d-123">Il file GetStockPrices.cs illustra come creare record di rilevamento personalizzati dall'interno di <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="8ad2d-124">Quando si esegue l'esempio, cercare questo record.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8ad2d-125">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="8ad2d-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="8ad2d-126">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WFStockPriceApplication.sln.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="8ad2d-127">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="8ad2d-128">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="8ad2d-129">Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="8ad2d-130">Nel browser fare clic su StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="8ad2d-131">Nel browser viene visualizzata la **StockPriceService** pagina, che contiene l'indirizzo wsdl del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="8ad2d-132">Copiare questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-132">Copy this address.</span></span>  
  
     <span data-ttu-id="8ad2d-133">L'indirizzo wsdl del servizio locale è, ad esempio, http://localhost:53797/StockPriceService.xamlx?wsdl.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="8ad2d-134">Da [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] passare alla cartella [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (la cartella di installazione predefinita è %SystemDrive%\Programmi\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="8ad2d-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="8ad2d-135">Individuare quindi la sottocartella Common7\IDE\.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="8ad2d-136">Fare doppio clic sul file WcfTestClient.exe per avviare il client di prova WCF.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="8ad2d-137">Nel Client di prova WCF, selezionare **Aggiungi servizio...**</span><span class="sxs-lookup"><span data-stu-id="8ad2d-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="8ad2d-138">dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="8ad2d-139">Incollare l'URL appena copiato nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="8ad2d-140">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="8ad2d-141">Testare il servizio usando il client di prova WCF.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="8ad2d-142">Nel Client di prova WCF fare doppio clic su **getstockprice ()** sotto il **IStockPriceService** nodo.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="8ad2d-143">Il **getstockprice ()** metodo verrà visualizzato nel riquadro di destra, con un parametro.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="8ad2d-144">Digitare Contoso come valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="8ad2d-145">Fare clic su **richiamare**.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="8ad2d-146">Vedere gli eventi rilevati nel file di log presente nella directory dei dati dell'applicazione in %APPDATA%\trackingRecords.log.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ad2d-147">% APPDATA % è una variabile di ambiente che viene risolta in %SystemDrive%\Users\\< nome utente\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], o Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ad2d-148">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8ad2d-149">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8ad2d-150">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ad2d-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ad2d-151">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8ad2d-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="8ad2d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ad2d-152">See Also</span></span>  
 [<span data-ttu-id="8ad2d-153">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="8ad2d-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
