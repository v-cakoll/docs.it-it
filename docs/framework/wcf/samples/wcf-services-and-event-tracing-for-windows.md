---
title: Servizi WCF e traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183205"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="76eb3-102">Servizi WCF e traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="76eb3-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="76eb3-103">In questo esempio viene illustrato come utilizzare la traccia analitica in Windows Communication Foundation (WCF) per generare eventi in Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="76eb3-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="76eb3-104">Le tracce analitiche sono eventi generati in punti chiave nello stack WCF che consentono la risoluzione dei problemi dei servizi WCF nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="76eb3-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="76eb3-105">La traccia analitica nei servizi WCF è la traccia che può essere attivata in un ambiente di produzione con un impatto minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="76eb3-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="76eb3-106">Queste tracce vengono inviate come eventi a una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="76eb3-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="76eb3-107">Questo esempio include un servizio WCF di base in cui gli eventi vengono generati dal servizio al registro eventi, che può essere visualizzato tramite il Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="76eb3-108">È anche possibile avviare una sessione ETW dedicata in ascolto di eventi dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="76eb3-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="76eb3-109">Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="76eb3-110">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="76eb3-110">To use this sample</span></span>

1. <span data-ttu-id="76eb3-111">Utilizzando Visual Studio 2012, aprire il file di soluzione EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="76eb3-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="76eb3-112">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="76eb3-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="76eb3-113">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="76eb3-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="76eb3-114">Nel browser Web fare clic su **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="76eb3-115">L'URI del documento WSDL per il servizio viene visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="76eb3-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="76eb3-116">Copiare l'URI.</span><span class="sxs-lookup"><span data-stu-id="76eb3-116">Copy that URI.</span></span>

     <span data-ttu-id="76eb3-117">Per impostazione predefinita, il servizio avvia l'ascolto delle richieste sulla porta 1378 `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="76eb3-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="76eb3-118">Eseguire il client di test WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="76eb3-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="76eb3-119">Il client di test WCF (WcfTestClient.exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="76eb3-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="76eb3-120">Il dir di installazione di Visual `C:\Program Files\Microsoft Visual Studio 10.0`Studio 2012 predefinito è .</span><span class="sxs-lookup"><span data-stu-id="76eb3-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="76eb3-121">All'interno del client di test WCF aggiungere il servizio selezionando **File**, quindi **Aggiungi servizio**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="76eb3-122">Aggiungere l'indirizzo dell'endpoint nella casella di input.</span><span class="sxs-lookup"><span data-stu-id="76eb3-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="76eb3-123">Il valore predefinito è `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="76eb3-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="76eb3-124">Aprire l'applicazione Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="76eb3-125">Prima di richiamare il servizio, avviare il Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per tenere traccia degli eventi generati dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="76eb3-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="76eb3-126">Dal menu **Start** selezionare **Strumenti di amministrazione**, quindi **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="76eb3-127">Abilitare i registri **analitici** e **di debug.**</span><span class="sxs-lookup"><span data-stu-id="76eb3-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="76eb3-128">Nella visualizzazione struttura nel Visualizzatore eventi passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e infine Applicazioni **server applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="76eb3-129">Fare clic con il pulsante destro del mouse su **Applicazioni server applicazioni**, scegliere **Visualizza**, quindi Mostra **registri analitici e**di debug .</span><span class="sxs-lookup"><span data-stu-id="76eb3-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="76eb3-130">Verificare che l'opzione **Mostra registri analitici e** di debug sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="76eb3-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="76eb3-131">Abilitare il registro **analitico.**</span><span class="sxs-lookup"><span data-stu-id="76eb3-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="76eb3-132">Nella visualizzazione struttura nel Visualizzatore eventi passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e infine Applicazioni **server applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="76eb3-133">Fare clic con il pulsante destro del mouse su **Analitica** e selezionare **Abilita registro**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="76eb3-134">Per eseguire il test del servizio</span><span class="sxs-lookup"><span data-stu-id="76eb3-134">To test the service</span></span>

1. <span data-ttu-id="76eb3-135">Tornare al client di test `Divide` WCF e fare doppio clic e mantenere i valori predefiniti, che specificano un denominatore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="76eb3-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="76eb3-136">Se il valore del denominatore è 0, il servizio genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="76eb3-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="76eb3-137">Osservare gli eventi creati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="76eb3-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="76eb3-138">Tornare al Visualizzatore eventi e passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi Applicazioni **server applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="76eb3-139">Fare clic con il pulsante destro del mouse su **Analitica** e scegliere **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="76eb3-140">Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="76eb3-141">Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.</span><span class="sxs-lookup"><span data-stu-id="76eb3-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="76eb3-142">Ripetere i passaggi 1 e 2 con valori di input validi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="76eb3-143">Il valore del parametro `N2` deve essere un numero diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="76eb3-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="76eb3-144">Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.</span><span class="sxs-lookup"><span data-stu-id="76eb3-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="76eb3-145">Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="76eb3-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="76eb3-146">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="76eb3-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="76eb3-147">Aprire Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="76eb3-148">Passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Applicazioni-Server-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="76eb3-149">Fare clic con il pulsante destro del mouse su **Analisi** e selezionare **Disattiva registro**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="76eb3-150">Passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Applicazioni-Server-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="76eb3-151">Fare clic con il pulsante destro del mouse su **Analitica** e selezionare **Cancella registro**.</span><span class="sxs-lookup"><span data-stu-id="76eb3-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="76eb3-152">Scegliere l'opzione **Cancella** per cancellare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="76eb3-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76eb3-153">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="76eb3-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="76eb3-154">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="76eb3-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="76eb3-155">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="76eb3-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="76eb3-156">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="76eb3-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="76eb3-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76eb3-157">See also</span></span>

- <span data-ttu-id="76eb3-158">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="76eb3-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
