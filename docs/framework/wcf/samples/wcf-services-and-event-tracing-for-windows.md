---
title: Servizi WCF e traccia eventi per Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3b7b370ed6b1d9a900579ff0e6f1b0a22290c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="ead16-102">Servizi WCF e traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="ead16-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="ead16-103">In questo esempio viene descritto come usare la traccia analitica in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per generare eventi in Traccia eventi per Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="ead16-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="ead16-104">Le tracce analitiche sono eventi generati in corrispondenza di punti chiave nello stack [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che consentono risolvere i problemi relativi ai servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="ead16-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="ead16-105">La funzionalità di tracci analitica nei servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consiste in una traccia che può essere attivata in un ambiente di produzione con impatto minimo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ead16-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="ead16-106">Queste tracce vengono inviate come eventi a una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="ead16-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="ead16-107">In questo esempio è incluso un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di base in cui gli eventi vengono inviati dal servizio al registro eventi che può essere visualizzato tramite Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="ead16-108">È inoltre possibile avviare una sessione ETW dedicata che rimanga in ascolto degli eventi generati dal servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead16-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="ead16-109">Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ead16-110">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="ead16-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="ead16-111">In [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] aprire il file della soluzione EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="ead16-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ead16-112">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="ead16-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ead16-113">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ead16-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="ead16-114">Nel Web browser, fare clic su **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="ead16-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="ead16-115">L'URI del documento WSDL per il servizio viene visualizzato nel browser.</span><span class="sxs-lookup"><span data-stu-id="ead16-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="ead16-116">Copiare l'URI.</span><span class="sxs-lookup"><span data-stu-id="ead16-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="ead16-117">Per impostazione predefinita, il servizio si pone in ascolto delle richieste sulla porta 1378 (http://localhost:1378/Calculator.svc).</span><span class="sxs-lookup"><span data-stu-id="ead16-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="ead16-118">Eseguire il client di prova [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="ead16-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="ead16-119">Il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client di prova (WcfTestClient.exe) si trova nella \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] directory di installazione > \Common7\IDE\ WcfTestClient.exe (impostazione predefinita [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] è c:\Programmi\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="ead16-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="ead16-120">All'interno di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client di prova, aggiungere il servizio selezionando **File**e quindi **Aggiungi servizio**.</span><span class="sxs-lookup"><span data-stu-id="ead16-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="ead16-121">Aggiungere l'indirizzo dell'endpoint nella casella di input.</span><span class="sxs-lookup"><span data-stu-id="ead16-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="ead16-122">L'indirizzo predefinito è http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="ead16-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="ead16-123">Aprire l'applicazione Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="ead16-124">Prima di richiamare il servizio, avviare Visualizzatore eventi e verificare che il registro eventi sia in ascolto per rilevare gli eventi generati dal servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead16-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="ead16-125">Dal **avviare** dal menu **strumenti di amministrazione**e quindi **Visualizzatore eventi**.</span><span class="sxs-lookup"><span data-stu-id="ead16-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="ead16-126">Abilitare il **analitico** e **Debug** log.</span><span class="sxs-lookup"><span data-stu-id="ead16-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="ead16-127">Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ead16-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ead16-128">Fare doppio clic su **Server applicazioni-applicazioni**selezionare **vista**e quindi **Visualizza registri analitici e Debug**.</span><span class="sxs-lookup"><span data-stu-id="ead16-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="ead16-129">Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata.</span><span class="sxs-lookup"><span data-stu-id="ead16-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="ead16-130">Abilitare il **analitico** log.</span><span class="sxs-lookup"><span data-stu-id="ead16-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="ead16-131">Nella visualizzazione struttura ad albero in Visualizzatore eventi, passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ead16-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ead16-132">Fare doppio clic su **analitico** e selezionare **Attiva registro**.</span><span class="sxs-lookup"><span data-stu-id="ead16-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="ead16-133">Per eseguire il test del servizio</span><span class="sxs-lookup"><span data-stu-id="ead16-133">To test the service</span></span>  
  
1.  <span data-ttu-id="ead16-134">Tornare a client di prova [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], fare doppio clic su `Divide` e mantenere i valori predefiniti che specificano un valore per il denominatore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="ead16-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="ead16-135">Se il valore del denominatore è 0, il servizio genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="ead16-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="ead16-136">Osservare gli eventi creati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ead16-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="ead16-137">Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ead16-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="ead16-138">Fare doppio clic su **analitico** e selezionare **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="ead16-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="ead16-139">Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="ead16-140">Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.</span><span class="sxs-lookup"><span data-stu-id="ead16-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="ead16-141">Ripetere i passaggi 1 e 2 con valori di input validi.</span><span class="sxs-lookup"><span data-stu-id="ead16-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="ead16-142">Il valore del parametro `N2` deve essere un numero diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="ead16-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="ead16-143">Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.</span><span class="sxs-lookup"><span data-stu-id="ead16-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="ead16-144">Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="ead16-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="ead16-145">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ead16-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="ead16-146">Aprire Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="ead16-147">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ead16-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="ead16-148">Fare doppio clic su **analitico** e selezionare **Disattiva registro**.</span><span class="sxs-lookup"><span data-stu-id="ead16-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="ead16-149">Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="ead16-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="ead16-150">Fare doppio clic su **analitico** e selezionare **Cancella Log**.</span><span class="sxs-lookup"><span data-stu-id="ead16-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="ead16-151">Scegliere il **deselezionare** opzione per cancellare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="ead16-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ead16-152">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ead16-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ead16-153">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ead16-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ead16-154">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ead16-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ead16-155">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ead16-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="ead16-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ead16-156">See Also</span></span>  
 [<span data-ttu-id="ead16-157">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="ead16-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
