---
title: Hello World con il servizio di routing
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 52b5c3b167cbbfb032d8e6104a118c5c9384938e
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845775"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="9f502-102">Hello World con il servizio di routing</span><span class="sxs-lookup"><span data-stu-id="9f502-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="9f502-103">Questo esempio viene illustrato il servizio di Routing di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9f502-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="9f502-104">Il servizio di Routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f502-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="9f502-105">In questo esempio si adatta l'esempio di calcolatrice standard di WCF per comunicare con il servizio di Routing.</span><span class="sxs-lookup"><span data-stu-id="9f502-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="9f502-106">In questo esempio, il client calcolatrice è configurato per inviare messaggi a un endpoint esposto dal router.</span><span class="sxs-lookup"><span data-stu-id="9f502-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="9f502-107">Il servizio di routing è configurato per accettare tutti i messaggi ad esso inviati e per inoltrarli a un endpoint che corrisponde al servizio di calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="9f502-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="9f502-108">I messaggi inviati dal client vengono pertanto ricevuti dal router e reindirizzati al servizio di calcolatrice effettivo.</span><span class="sxs-lookup"><span data-stu-id="9f502-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="9f502-109">I messaggi provenienti dal servizio di calcolatrice di backup vengono inviati nuovamente al router del servizio, che a sua volta li inoltra al client calcolatrice.</span><span class="sxs-lookup"><span data-stu-id="9f502-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="9f502-110">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="9f502-110">To use this sample</span></span>

1.  <span data-ttu-id="9f502-111">Se si utilizza Visual Studio 2012, aprire Helloroutingservice.</span><span class="sxs-lookup"><span data-stu-id="9f502-111">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2.  <span data-ttu-id="9f502-112">Premere F5 o CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="9f502-112">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9f502-113">Se si preme F5, il client calcolatrice viene avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f502-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="9f502-114">Se si preme CTRL+MAIUSC+B (compilazione), è necessario avviare le applicazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9f502-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1.  <span data-ttu-id="9f502-115">Client calcolatrice (./CalculatorClient/bin/client.exe</span><span class="sxs-lookup"><span data-stu-id="9f502-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2.  <span data-ttu-id="9f502-116">Servizio di calcolatrice (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="9f502-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3.  <span data-ttu-id="9f502-117">Servizio di routing (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="9f502-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3.  <span data-ttu-id="9f502-118">Premere INVIO per avviare il client.</span><span class="sxs-lookup"><span data-stu-id="9f502-118">Press ENTER to start the client.</span></span>

     <span data-ttu-id="9f502-119">È necessario visualizzare il seguente output:</span><span class="sxs-lookup"><span data-stu-id="9f502-119">You should see the following output:</span></span>

     <span data-ttu-id="9f502-120">Add(100,15.99) = 115.99</span><span class="sxs-lookup"><span data-stu-id="9f502-120">Add(100,15.99) = 115.99</span></span>

     <span data-ttu-id="9f502-121">Subtract(145,76.54) = 68.46</span><span class="sxs-lookup"><span data-stu-id="9f502-121">Subtract(145,76.54) = 68.46</span></span>

     <span data-ttu-id="9f502-122">Multiply(9,81.25) = 731.25</span><span class="sxs-lookup"><span data-stu-id="9f502-122">Multiply(9,81.25) = 731.25</span></span>

     <span data-ttu-id="9f502-123">Divide(22,7) = 3.14285714285714</span><span class="sxs-lookup"><span data-stu-id="9f502-123">Divide(22,7) = 3.14285714285714</span></span>

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="9f502-124">Configurabile tramite codice o App.Config</span><span class="sxs-lookup"><span data-stu-id="9f502-124">Configurable via Code or App.Config</span></span>
 <span data-ttu-id="9f502-125">L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router.</span><span class="sxs-lookup"><span data-stu-id="9f502-125">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="9f502-126">È inoltre possibile modificare il nome del file App.config affinché non venga riconosciuto e rimuovere i commenti dalla chiamata al metodo in ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="9f502-126">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="9f502-127">Entrambi i metodi restituiscono lo stesso comportamento da parte del router.</span><span class="sxs-lookup"><span data-stu-id="9f502-127">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="9f502-128">Scenario</span><span class="sxs-lookup"><span data-stu-id="9f502-128">Scenario</span></span>
 <span data-ttu-id="9f502-129">Questo esempio descrive l'utilizzo del router come message pump di base.</span><span class="sxs-lookup"><span data-stu-id="9f502-129">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="9f502-130">Il servizio di routing viene utilizzato come nodo proxy trasparente configurato per inoltrare direttamente messaggi a un set preconfigurato di endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9f502-130">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="9f502-131">Scenario reale</span><span class="sxs-lookup"><span data-stu-id="9f502-131">Real World Scenario</span></span>
 <span data-ttu-id="9f502-132">Contoso desidera incrementare la flessibilità relativa a denominazione, indirizzamento, configurazione e sicurezza dei propri servizi.</span><span class="sxs-lookup"><span data-stu-id="9f502-132">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="9f502-133">A tale scopo, una message pump di base viene posizionata di fronte ai servizi per essere utilizzata come endpoint rivolto al pubblico.</span><span class="sxs-lookup"><span data-stu-id="9f502-133">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="9f502-134">Ciò consente di posizionare sicurezza aggiuntiva davanti ai servizi effettivi e di semplificare l'implementazione di soluzioni di scalabilità o di controllo delle versioni del servizio in una data successiva.</span><span class="sxs-lookup"><span data-stu-id="9f502-134">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9f502-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9f502-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9f502-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9f502-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9f502-137">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9f502-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9f502-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9f502-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="9f502-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f502-139">See Also</span></span>  
 [<span data-ttu-id="9f502-140">Hosting di AppFabric e salvataggio permanente</span><span class="sxs-lookup"><span data-stu-id="9f502-140">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
