---
title: Servizi WCF e traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 5bf965ad6a9997ec0603325f246679cf42662a52
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094813"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="a4e22-102">Servizi WCF e traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="a4e22-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="a4e22-103">In questo esempio viene illustrato come utilizzare la traccia analitica in Windows Communication Foundation (WCF) per generare eventi in Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="a4e22-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="a4e22-104">Le tracce analitiche sono eventi generati in punti chiave dello stack WCF che consentono la risoluzione dei problemi relativi ai servizi WCF nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="a4e22-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="a4e22-105">Traccia analitica nei servizi WCF è la traccia che può essere attivata in un ambiente di produzione con un impatto minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a4e22-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="a4e22-106">Queste tracce vengono inviate come eventi a una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="a4e22-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="a4e22-107">Questo esempio include un servizio WCF di base in cui gli eventi vengono generati dal servizio nel registro eventi, che possono essere visualizzati utilizzando Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="a4e22-108">È inoltre possibile avviare una sessione ETW dedicata che rimane in ascolto degli eventi del servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="a4e22-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="a4e22-109">Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a4e22-110">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a4e22-110">To use this sample</span></span>

1. <span data-ttu-id="a4e22-111">Con Visual Studio 2012 aprire il file della soluzione EtwAnalyticTraceSample. sln.</span><span class="sxs-lookup"><span data-stu-id="a4e22-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="a4e22-112">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="a4e22-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="a4e22-113">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a4e22-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="a4e22-114">Nella Web browser fare clic su **Calculator. svc**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="a4e22-115">L'URI del documento WSDL per il servizio viene visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="a4e22-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="a4e22-116">Copiare l'URI.</span><span class="sxs-lookup"><span data-stu-id="a4e22-116">Copy that URI.</span></span>

     <span data-ttu-id="a4e22-117">Per impostazione predefinita, il servizio inizia l'ascolto delle richieste sulla porta 1378 `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="a4e22-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="a4e22-118">Eseguire il client di prova WCF (WcfTestClient. exe).</span><span class="sxs-lookup"><span data-stu-id="a4e22-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="a4e22-119">Il client di prova WCF (WcfTestClient. exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="a4e22-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="a4e22-120">La directory di installazione predefinita di Visual Studio 2012 è `C:\Program Files\Microsoft Visual Studio 10.0`.</span><span class="sxs-lookup"><span data-stu-id="a4e22-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="a4e22-121">Nel client di prova WCF aggiungere il servizio selezionando **file**e quindi **Aggiungi servizio**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="a4e22-122">Aggiungere l'indirizzo dell'endpoint nella casella di input.</span><span class="sxs-lookup"><span data-stu-id="a4e22-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="a4e22-123">Il valore predefinito è `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="a4e22-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="a4e22-124">Aprire l'applicazione Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="a4e22-125">Prima di richiamare il servizio, avviare Visualizzatore eventi e verificare che il registro eventi sia in ascolto di eventi di rilevamento generati dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="a4e22-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="a4e22-126">Dal menu **Start** , selezionare **strumenti di amministrazione**, quindi **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="a4e22-127">Abilitare i log **analitici** e di **debug** .</span><span class="sxs-lookup"><span data-stu-id="a4e22-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="a4e22-128">Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a4e22-129">Fare clic con il pulsante destro del mouse su **server applicazioni-applicazioni**, selezionare **Visualizza**, quindi **Visualizza registri analitici e di debug**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="a4e22-130">Verificare che l'opzione **Mostra log analitici e di debug** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="a4e22-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="a4e22-131">Abilitare il registro **analitico** .</span><span class="sxs-lookup"><span data-stu-id="a4e22-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="a4e22-132">Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a4e22-133">Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Abilita log**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="a4e22-134">Per eseguire il test del servizio</span><span class="sxs-lookup"><span data-stu-id="a4e22-134">To test the service</span></span>

1. <span data-ttu-id="a4e22-135">Tornare al client di prova WCF, fare doppio clic su `Divide` e mantengono i valori predefiniti, che specificano un denominatore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="a4e22-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="a4e22-136">Se il valore del denominatore è 0, il servizio genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="a4e22-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="a4e22-137">Osservare gli eventi creati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="a4e22-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="a4e22-138">Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi Server applicazioni **-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a4e22-139">Fare clic con il pulsante destro del mouse su **Analytics** e selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="a4e22-140">Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="a4e22-141">Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.</span><span class="sxs-lookup"><span data-stu-id="a4e22-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="a4e22-142">Ripetere i passaggi 1 e 2 con valori di input validi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="a4e22-143">Il valore del parametro `N2` deve essere un numero diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="a4e22-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="a4e22-144">Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.</span><span class="sxs-lookup"><span data-stu-id="a4e22-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="a4e22-145">Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="a4e22-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="a4e22-146">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a4e22-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="a4e22-147">Aprire Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="a4e22-148">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **Application-Server-** Applications.</span><span class="sxs-lookup"><span data-stu-id="a4e22-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a4e22-149">Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Disattiva log**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="a4e22-150">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **Application-Server-** Applications.</span><span class="sxs-lookup"><span data-stu-id="a4e22-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a4e22-151">Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Cancella log**.</span><span class="sxs-lookup"><span data-stu-id="a4e22-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="a4e22-152">Scegliere l'opzione **Cancella** per cancellare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e22-153">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a4e22-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a4e22-154">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a4e22-154">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a4e22-155">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="a4e22-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4e22-156">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a4e22-156">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="a4e22-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4e22-157">See also</span></span>

- <span data-ttu-id="a4e22-158">[Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a4e22-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
