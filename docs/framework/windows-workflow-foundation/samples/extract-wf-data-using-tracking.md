---
title: Estrarre dati di WF utilizzando il rilevamento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bbc9d72a55bd0affdccae9b735355c7e30c5d933
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="e73a9-102">Estrarre dati di WF utilizzando il rilevamento</span><span class="sxs-lookup"><span data-stu-id="e73a9-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="e73a9-103">In questo esempio viene illustrato come usare il rilevamento del flusso di lavoro per estrarre variabili e argomenti del flusso di lavoro dalle attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="e73a9-104">Vengono inoltre illustrate l'aggiunta di annotazioni ai record di rilevamento e l'estrazione del payload di dati all'interno dei record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e73a9-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="e73a9-105">Nell'esempio viene usato il partecipante del rilevamento Traccia eventi per Windows (ETW) per estrarre i dati dal flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e73a9-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="e73a9-106">Sample Details</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="e73a9-107"> fornisce il rilevamento per ottenere visibilità nell'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-107"> provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="e73a9-108">Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="e73a9-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="e73a9-109">Insieme ai record di rilevamento del flusso di lavoro, da quest'ultimo è possibile estrarre i dati presenti nell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="e73a9-110">Nell'elenco seguente sono indicati in dettaglio i tipi di dati che possono essere estratti dai record di rilevamento:</span><span class="sxs-lookup"><span data-stu-id="e73a9-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="e73a9-111">Variabili del flusso di lavoro all'interno di un'attività e record di rilevamento durante l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="e73a9-112">Le variabili del flusso di lavoro da estrarre sono specificate in un profilo.</span><span class="sxs-lookup"><span data-stu-id="e73a9-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="e73a9-113">Le variabili da estrarre possono essere specificate solo con `ActivityStateQueries`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="e73a9-114">Nell'esempio di codice seguente viene illustrato un profilo di rilevamento usato per estrarre la variabile del flusso di lavoro da un'attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="e73a9-115">Argomenti e record di rilevamento dello stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="e73a9-116">Gli argomenti definiscono il modo in cui i dati entrano ed escono da un'attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="e73a9-117">Gli argomenti da estrarre vengono specificati usando un oggetto <xref:System.Activities.Tracking.ActivityStateQuery>. L'esempio di codice seguente è un profilo di rilevamento che estrae l'argomento `Value`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="e73a9-118">Le annotazioni sono coppie chiave/valore che possono essere aggiunte a qualsiasi record di rilevamento creato.</span><span class="sxs-lookup"><span data-stu-id="e73a9-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="e73a9-119">Le annotazioni servono come meccanismo di tag per i record di rilevamento,</span><span class="sxs-lookup"><span data-stu-id="e73a9-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="e73a9-120">vengono aggiunte ai record di rilevamento tramite un profilo di rilevamento e</span><span class="sxs-lookup"><span data-stu-id="e73a9-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="e73a9-121">possono essere aggiunte a qualsiasi tipo di query di rilevamento di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="e73a9-122">L'esempio di codice seguente è un profilo di rilevamento che mostra il modo in cui è possibile aggiungere un'annotazione a un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e73a9-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="e73a9-123">I record di rilevamento personalizzati vengono creati dalle attività definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e73a9-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="e73a9-124">I record di rilevamento personalizzati possono contenere i dati di payload definiti all'interno di questa attività.</span><span class="sxs-lookup"><span data-stu-id="e73a9-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="e73a9-125">La sottoscrizione di record di rilevamento personalizzati in un profilo di rilevamento consente l'estrazione del payload all'interno del record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="e73a9-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="e73a9-126">I record di rilevamento personalizzati possono essere estratti con un oggetto <xref:System.Activities.Tracking.TrackingQuery> personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e73a9-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="e73a9-127">L'esempio di codice seguente è un profilo di rilevamento che estrae un record di rilevamento personalizzato insieme al payload.</span><span class="sxs-lookup"><span data-stu-id="e73a9-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="e73a9-128">Nell'esempio vengono illustrate l'estrazione di variabili, argomenti, record personalizzati e l'aggiunta di annotazioni tramite un profilo specificato in un file Web.config. Il rilevamento è abilitato sul servizio flusso di lavoro di esempio aggiungendo un elemento del comportamento `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="e73a9-129">Nell'esempio di codice seguente viene abilitato il rilevamento per il profilo di rilevamento `ExtractWorkflowVariables`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e73a9-130">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="e73a9-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="e73a9-131">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WFStockPriceApplication.sln.</span><span class="sxs-lookup"><span data-stu-id="e73a9-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e73a9-132">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="e73a9-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e73a9-133">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="e73a9-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="e73a9-134">Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e73a9-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="e73a9-135">Nel browser fare clic su StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="e73a9-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="e73a9-136">Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="e73a9-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="e73a9-137">Copiare questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="e73a9-137">Copy this address.</span></span>  
  
     <span data-ttu-id="e73a9-138">Nell'esempio seguente viene mostrato un indirizzo WSDL del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="e73a9-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="e73a9-139">Prima di richiamare il servizio, avviare Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per rilevare eventi creati dal servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="e73a9-140">Dal **avviare** dal menu **strumenti di amministrazione** e quindi **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="e73a9-141">Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, e **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="e73a9-142">Fare doppio clic su **Microsoft** e selezionare **vista** e quindi **Visualizza registri analitici e Debug**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="e73a9-143">Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata.</span><span class="sxs-lookup"><span data-stu-id="e73a9-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="e73a9-144">Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="e73a9-145">Fare doppio clic su **analitico** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="e73a9-146">Usando [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], aprire il client di WCF.</span><span class="sxs-lookup"><span data-stu-id="e73a9-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="e73a9-147">Client di prova WCF (WcfTestClient.exe) si trova nella \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] cartella di installazione > \Common7\IDE\ cartella.</span><span class="sxs-lookup"><span data-stu-id="e73a9-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="e73a9-148">La cartella di installazione di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] predefinita è C:\Programmi\Microsoft Visual Studio 10.0.</span><span class="sxs-lookup"><span data-stu-id="e73a9-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="e73a9-149">Nel client di prova WCF selezionare **Aggiungi servizio** dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="e73a9-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="e73a9-150">Aggiungere l'indirizzo WSDL del servizio locale che è stato copiato precedentemente nella casella di input.</span><span class="sxs-lookup"><span data-stu-id="e73a9-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="e73a9-151">Nel client di prova WCF fare doppio clic su `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="e73a9-152">Verrà visualizzato il metodo `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="e73a9-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="e73a9-153">La richiesta accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="e73a9-153">The request accepts one parameter.</span></span> <span data-ttu-id="e73a9-154">Utilizzare il valore **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="e73a9-155">Fare clic su **richiamare**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="e73a9-156">Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**,  **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="e73a9-157">Fare doppio clic su **analitico** e selezionare **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="e73a9-158">Gli ID degli eventi flusso di lavoro sono compresi tra 100 e 199.</span><span class="sxs-lookup"><span data-stu-id="e73a9-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="e73a9-159">Gli eventi contengono annotazioni, variabili, argomenti e record di rilevamento personalizzati che possono essere visualizzati nel visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="e73a9-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="e73a9-160">Pulizia nel Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="e73a9-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="e73a9-161">Il canale analitico nel registro eventi può essere pulito nel Visualizzatore eventi eseguendo le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e73a9-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="e73a9-162">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e73a9-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="e73a9-163">Aprire Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="e73a9-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="e73a9-164">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **applicazione Applicazioni server**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="e73a9-165">Fare doppio clic su **analitico** e selezionare **Disattiva registro**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="e73a9-166">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, **applicazione Applicazioni server**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="e73a9-167">Fare doppio clic su **analitico** e selezionare **Cancella Log**.</span><span class="sxs-lookup"><span data-stu-id="e73a9-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="e73a9-168">Scegliere il **deselezionare** opzione per cancellare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="e73a9-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="e73a9-169">Problema noto</span><span class="sxs-lookup"><span data-stu-id="e73a9-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e73a9-170">Nel Visualizzatore eventi potrebbe non essere possibile decodificare gli eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="e73a9-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="e73a9-171">Si potrebbe visualizzare un messaggio di errore simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="e73a9-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="e73a9-172">Se si verifica questo errore, fare clic su **aggiornamento** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="e73a9-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="e73a9-173">La decodifica dell'evento dovrebbe ora essere eseguita in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="e73a9-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e73a9-174">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e73a9-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e73a9-175">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e73a9-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e73a9-176">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e73a9-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e73a9-177">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e73a9-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="e73a9-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e73a9-178">See Also</span></span>  
 [<span data-ttu-id="e73a9-179">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="e73a9-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
