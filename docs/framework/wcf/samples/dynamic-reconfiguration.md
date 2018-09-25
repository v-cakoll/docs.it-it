---
title: Riconfigurazione dinamica
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157142"
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="9fe07-102">Riconfigurazione dinamica</span><span class="sxs-lookup"><span data-stu-id="9fe07-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="9fe07-103">Questo esempio viene illustrato il servizio di routing di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9fe07-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="9fe07-104">Il servizio di routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9fe07-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="9fe07-105">In questo esempio si adatta l'esempio di calcolatrice standard di WCF per comunicare con il servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="9fe07-105">This sample adapts the standard WCF Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="9fe07-106">In questo esempio viene illustrato come è possibile riconfigurare il servizio di routing dinamicamente durante il runtime.</span><span class="sxs-lookup"><span data-stu-id="9fe07-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fe07-107">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9fe07-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9fe07-108">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9fe07-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9fe07-109">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9fe07-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9fe07-110">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9fe07-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="9fe07-111">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="9fe07-111">Sample Details</span></span>  
 <span data-ttu-id="9fe07-112">Per riconfigurare dinamicamente il servizio di routing durante il runtime, questo esempio genera un timer ogni cinque secondi che determina la creazione e l'applicazione di un nuovo oggetto <xref:System.ServiceModel.Routing.RoutingConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="9fe07-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="9fe07-113">Questa configurazione fa riferimento al normale endpoint del servizio di calcolo o all'endpoint del servizio di calcolo che esegue l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="9fe07-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="9fe07-114">L'applicazione client calcolatrice riceve i messaggi da uno dei due servizi, a seconda del servizio di routing configurato per l'indirizzamento in quel momento specifico.</span><span class="sxs-lookup"><span data-stu-id="9fe07-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="9fe07-115">Vengono utilizzate le funzionalità del servizio di routing per la riconfigurazione dinamica tramite un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9fe07-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="9fe07-116">In base a tale comportamento personalizzato viene allegata un'estensione del servizio contenente un semplice thread che genera il timer ogni cinque secondi, comportando un callback al metodo `UpdateRules`.</span><span class="sxs-lookup"><span data-stu-id="9fe07-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="9fe07-117">Questo callback crea e applica la nuova configurazione del routing.</span><span class="sxs-lookup"><span data-stu-id="9fe07-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="9fe07-118">In una distribuzione effettiva questo callback verrebbe probabilmente eseguito in risposta ad altri tipi di evento, ad esempio una notifica di evento SQL o un annuncio di individuazione WS.</span><span class="sxs-lookup"><span data-stu-id="9fe07-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9fe07-119">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="9fe07-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="9fe07-120">Aprire DynamicReconfiguration.sln utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fe07-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="9fe07-121">Per aprire **Esplora soluzioni**, selezionare **Esplora soluzioni** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="9fe07-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="9fe07-122">Premere **F5** oppure **CTRL + MAIUSC + B** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9fe07-122">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="9fe07-123">Se si desidera avviare automaticamente i progetti necessari quando si preme **F5**, la soluzione e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9fe07-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="9fe07-124">Selezionare il **progetto di avvio** nodo **proprietà comuni** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="9fe07-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="9fe07-125">Selezionare il **progetti di avvio multipli** pulsante di opzione e impostare tutti i progetti affinché le **avviare** azione.</span><span class="sxs-lookup"><span data-stu-id="9fe07-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="9fe07-126">Se si compila il progetto con **CTRL + MAIUSC + B**, è necessario avviare le applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fe07-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="9fe07-127">Client calcolatrice (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="9fe07-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="9fe07-128">Servizio di calcolatrice (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="9fe07-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="9fe07-129">Servizio di routing relativo alla calcolatrice (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="9fe07-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="9fe07-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="9fe07-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="9fe07-131">Nella finestra della console del client calcolatrice premere INVIO per avviare il client e per chiamare le operazioni del servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="9fe07-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="9fe07-132">Il servizio di routing indirizza i messaggi in modo alternativo e dinamico al servizio di calcolo che esegue l'arrotondamento e al normale servizio di calcolatrice a mano a mano che la configurazione del routing viene modificata dinamicamente ogni cinque secondi.</span><span class="sxs-lookup"><span data-stu-id="9fe07-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="9fe07-133">A seconda dell'endpoint configurato per l'invio dei messaggi da parte del servizio routing, nella finestra della console client verranno visualizzati risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="9fe07-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="9fe07-134">Continuare a premere INVIO ripetutamente per più di cinque secondi e osservare le modifiche nei risultati generati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9fe07-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="9fe07-135">Di seguito è riportato l'output restituito quando il servizio router è configurato per indirizzare messaggi al servizio di calcolo che esegue l'arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="9fe07-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="9fe07-136">Di seguito è riportato l'output restituito quando il servizio di routing è configurato per indirizzare messaggi al normale servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="9fe07-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="9fe07-137">Il servizio di calcolatrice e il servizio di calcolo che esegue l'arrotondamento stamperanno inoltre un log delle operazioni richiamate nelle rispettive finestre della console.</span><span class="sxs-lookup"><span data-stu-id="9fe07-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="9fe07-138">Nella finestra della console client, digitare "quit" e premere INVIO per uscire.</span><span class="sxs-lookup"><span data-stu-id="9fe07-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="9fe07-139">Premere INVIO nelle finestre della console dei servizi per terminare i servizi.</span><span class="sxs-lookup"><span data-stu-id="9fe07-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="9fe07-140">Scenario</span><span class="sxs-lookup"><span data-stu-id="9fe07-140">Scenario</span></span>  
 <span data-ttu-id="9fe07-141">In questo esempio il router agisce come router basato sul contenuto consentendo a più tipi o implementazioni di servizi di essere esposti mediante un endpoint.</span><span class="sxs-lookup"><span data-stu-id="9fe07-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="9fe07-142">Scenario reale</span><span class="sxs-lookup"><span data-stu-id="9fe07-142">Real World Scenario</span></span>  
 <span data-ttu-id="9fe07-143">Contoso desidera virtualizzare i propri servizi per esporre pubblicamente solo un endpoint tramite il quale viene offerto l'accesso a più tipi diversi di servizi.</span><span class="sxs-lookup"><span data-stu-id="9fe07-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="9fe07-144">In questo caso, le funzionalità di routing basate sul contenuto del servizio di routing vengono utilizzate per determinare dove devono essere inviate le richieste in entrata.</span><span class="sxs-lookup"><span data-stu-id="9fe07-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe07-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fe07-145">See Also</span></span>  
 [<span data-ttu-id="9fe07-146">Hosting di AppFabric e salvataggio permanente</span><span class="sxs-lookup"><span data-stu-id="9fe07-146">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
