---
title: Correlazione di query del messaggio LINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1207f371da5b447903e2846229860fd8c214a46e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="3d6a2-102">Correlazione di query del messaggio LINQ</span><span class="sxs-lookup"><span data-stu-id="3d6a2-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="3d6a2-103">In questo esempio viene illustrato come eseguire una correlazione basata sul contenuto usando un'implementazione <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzata anziché l'oggetto <xref:System.ServiceModel.XPathMessageQuery> fornito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3d6a2-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="3d6a2-104">Demonstrates</span></span>  
 <span data-ttu-id="3d6a2-105">Oggetto <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzato, correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3d6a2-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="3d6a2-106">Discussion</span></span>  
 <span data-ttu-id="3d6a2-107">In questo esempio viene illustrato come estendersi dalla classe base <xref:System.ServiceModel.Dispatcher.MessageQuery> per scopi di correlazione.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="3d6a2-108">L'implementazione personalizzata, `LinqMessageQuery`, consente agli utenti di fornire un XName da trovare all'interno del messaggio tramite XLinq.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="3d6a2-109">I dati recuperati dalla query vengono usati per formare la chiave di correlazione per l'invio di messaggi all'istanza del flusso di lavoro appropriata.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3d6a2-110">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3d6a2-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3d6a2-111">In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="3d6a2-112">Eseguire questa procedura elenchi ACL di URL di esempio, appropriata deve essere aggiunto (vedere [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate), eseguendo Visual Studio come amministratore o eseguendo il comando seguente in un prompt dei comandi con privilegi elevati per aggiungere gli ACL appropriati.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="3d6a2-113">Assicurarsi che vengono sostituiti il dominio e il nome utente.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="3d6a2-114">Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="3d6a2-115">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-115">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="3d6a2-116">Impostare più progetti di avvio facendo clic sulla soluzione e selezionando **Imposta progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="3d6a2-117">Aggiungere **servizio** e **Client** (in tale ordine) come più progetti di avvio.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3.  <span data-ttu-id="3d6a2-118">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-118">Run the application.</span></span> <span data-ttu-id="3d6a2-119">Nella console client viene illustrato un flusso di lavoro che invia un ordine, riceve l'ID dell'ordine di acquisto e conferma quindi successivamente l'ordine.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="3d6a2-120">Nella finestra Servizio verranno visualizzate le richieste elaborate.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d6a2-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3d6a2-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3d6a2-123">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d6a2-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3d6a2-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3d6a2-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
