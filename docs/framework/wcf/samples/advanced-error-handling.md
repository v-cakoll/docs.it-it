---
title: Gestione avanzata degli errori
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77034a1948b7fc6dd383c9bdb5456917c6082687
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-error-handling"></a><span data-ttu-id="a6fb7-102">Gestione avanzata degli errori</span><span class="sxs-lookup"><span data-stu-id="a6fb7-102">Advanced Error Handling</span></span>
<span data-ttu-id="a6fb7-103">Nell'esempio viene descritto il servizio di routing [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6fb7-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="a6fb7-104">Il servizio di routing è un componente di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che semplifica l'aggiunta nell'applicazione di un router basato sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="a6fb7-105">Nell'esempio viene illustrata la modalità di ripristino intelligente del servizio di routing in caso di errore mediante l'uso di transazioni e altri concetti di messaggistica più complessi, ad esempio il multicasting.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a6fb7-106">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a6fb7-107">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a6fb7-108">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6fb7-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a6fb7-109">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="a6fb7-110">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="a6fb7-110">Sample Details</span></span>  
 <span data-ttu-id="a6fb7-111">In questo esempio il servizio di routing è configurato per leggere un messaggio da una coda MSMQ ed eseguirne il multicasting a due elenchi di code.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="a6fb7-112">Un elenco viene usato per le code dei servizi e un altro per le code di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="a6fb7-113">Poiché per impostazione predefinita l'associazione MSMQ per il cui uso è configurato il servizio di routing supporta l'uso di transazioni, il servizio di routing verifica che il messaggio sia transazionale e che sia stato ricevuto da almeno una coda in ogni elenco prima della segnalazione alla coda in ingresso (`InQ`) a cui il messaggio è stato indirizzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="a6fb7-114">Pertanto, nel caso in cui non siano disponibili entrambe le code dei servizi o entrambe le code di registrazione, il servizio di routing segnalerà l'impossibilità di indirizzare il messaggio e la coda in ingresso dovrà intraprendere un'azione.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="a6fb7-115">Questa azione consiste nello spostamento del messaggio alla coda di messaggi non recapitabili di sistema.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a6fb7-116">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="a6fb7-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="a6fb7-117">Installare MSMQ prima di eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="a6fb7-118">Se MSMQ non è installato, nel momento in cui l'esempio viene eseguito verrà restituito un messaggio di eccezione.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="a6fb7-119">È possibile trovare istruzioni per l'installazione di MSMQ in [l'installazione di Accodamento messaggi (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="a6fb7-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="a6fb7-120">Aprire AdvancedErrorHandling.sln usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6fb7-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="a6fb7-121">Premere **F5** o **CTRL + MAIUSC + B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6fb7-121">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="a6fb7-122">Se l'applicazione viene compilata con CTRL+MAIUSC+B, sarà necessario avviare l'applicazione in ./RoutingService/bin/debug/RoutingService.exe.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="a6fb7-123">Nella finestra della console premere INVIO per avviare il client.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="a6fb7-124">Il client restituirà statistiche diverse relativamente alle code per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="a6fb7-125">Di seguito è riportato l'output restituito per il caso 1 (nessun errore).</span><span class="sxs-lookup"><span data-stu-id="a6fb7-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="a6fb7-126">Di seguito è riportato l'output restituito per il caso 3 (coda dei servizi primaria e di registrazione con errori).</span><span class="sxs-lookup"><span data-stu-id="a6fb7-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="a6fb7-127">Di seguito è riportato l'output restituito per il caso 4 (coda dei servizi primaria e coda di registrazione primaria e di backup con errori).</span><span class="sxs-lookup"><span data-stu-id="a6fb7-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="a6fb7-128">Di seguito è riportato l'output restituito per il caso 2 (coda dei servizi primaria con errori).</span><span class="sxs-lookup"><span data-stu-id="a6fb7-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="a6fb7-129">Configurabile tramite codice o App.config</span><span class="sxs-lookup"><span data-stu-id="a6fb7-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="a6fb7-130">L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="a6fb7-131">È inoltre possibile modificare il nome del file RoutingService\App.config affinché non venga riconosciuto e modificare il valore del campo `configDriven` in RoutingService\Program.cs su `false` per usare la configurazione definita nel codice.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="a6fb7-132">Entrambi i metodi restituiscono lo stesso comportamento da parte del router.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="a6fb7-133">Scenario</span><span class="sxs-lookup"><span data-stu-id="a6fb7-133">Scenario</span></span>  
 <span data-ttu-id="a6fb7-134">In questo esempio viene illustrato come il servizio di routing sia in grado di gestire funzionalità di messaggistica avanzate, ad esempio transazioni e contesto di ricezione, e possa usare tali funzionalità come parte della gestione corretta di scenari di errore.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="a6fb7-135">Scenario reale</span><span class="sxs-lookup"><span data-stu-id="a6fb7-135">Real World Scenario</span></span>  
 <span data-ttu-id="a6fb7-136">Contoso desidera usare ricezioni transazionali tramite il servizio di routing per garantire che tutti i servizi necessari ricevano le informazioni anche durante le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="a6fb7-137">Desidera inoltre che gli errori vengano gestiti correttamente e automaticamente e che i problemi vengano segnalati nel caso in cui un messaggio non sia recapitabile anche quando viene usata la logica di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="a6fb7-138">Per questo scopo, il servizio di routing viene configurato per il failover di endpoint specifici come previsto. Tale servizio gestisce inoltre le situazioni di errore, inclusi la creazione, il completamento, il rollback o l'interruzione di transazioni/contesti di ricezione in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="a6fb7-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fb7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6fb7-139">See Also</span></span>  
 [<span data-ttu-id="a6fb7-140">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="a6fb7-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
