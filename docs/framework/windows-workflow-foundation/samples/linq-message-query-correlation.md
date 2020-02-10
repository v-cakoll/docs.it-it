---
title: Correlazione di query del messaggio LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: cd91a171f3242cfd7e8ac0404e24ac065919bcce
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094618"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="2959a-102">Correlazione di query del messaggio LINQ</span><span class="sxs-lookup"><span data-stu-id="2959a-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="2959a-103">In questo esempio viene illustrato come eseguire una correlazione basata sul contenuto usando un'implementazione <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzata anziché l'oggetto <xref:System.ServiceModel.XPathMessageQuery> fornito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2959a-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2959a-104">Dimostra</span><span class="sxs-lookup"><span data-stu-id="2959a-104">Demonstrates</span></span>  
 <span data-ttu-id="2959a-105">Oggetto <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzato, correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="2959a-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2959a-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="2959a-106">Discussion</span></span>  
 <span data-ttu-id="2959a-107">In questo esempio viene illustrato come estendersi dalla classe base <xref:System.ServiceModel.Dispatcher.MessageQuery> per scopi di correlazione.</span><span class="sxs-lookup"><span data-stu-id="2959a-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="2959a-108">L'implementazione personalizzata, `LinqMessageQuery`, consente agli utenti di fornire un XName da trovare all'interno del messaggio tramite XLinq.</span><span class="sxs-lookup"><span data-stu-id="2959a-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="2959a-109">I dati recuperati dalla query vengono usati per formare la chiave di correlazione per l'invio di messaggi all'istanza del flusso di lavoro appropriata.</span><span class="sxs-lookup"><span data-stu-id="2959a-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2959a-110">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2959a-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2959a-111">In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP.</span><span class="sxs-lookup"><span data-stu-id="2959a-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="2959a-112">Per eseguire questo esempio, è necessario aggiungere gli ACL URL appropriati (per informazioni dettagliate, vedere [configurazione di http e HTTPS](../../wcf/feature-details/configuring-http-and-https.md) ), eseguendo Visual Studio come amministratore oppure eseguendo il comando seguente in un prompt con privilegi elevati per aggiungere gli ACL appropriati.</span><span class="sxs-lookup"><span data-stu-id="2959a-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="2959a-113">Assicurarsi che vengono sostituiti il dominio e il nome utente.</span><span class="sxs-lookup"><span data-stu-id="2959a-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="2959a-114">Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2959a-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="2959a-115">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="2959a-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="2959a-116">Impostare più progetti di avvio facendo clic con il pulsante destro del mouse sulla soluzione e selezionando **Imposta progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="2959a-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="2959a-117">Aggiungere il **servizio** e il **client** (in questo ordine) come più progetti di avvio.</span><span class="sxs-lookup"><span data-stu-id="2959a-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="2959a-118">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2959a-118">Run the application.</span></span> <span data-ttu-id="2959a-119">Nella console client viene illustrato un flusso di lavoro che invia un ordine, riceve l'ID dell'ordine di acquisto e conferma quindi successivamente l'ordine.</span><span class="sxs-lookup"><span data-stu-id="2959a-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="2959a-120">Nella finestra Servizio verranno visualizzate le richieste elaborate.</span><span class="sxs-lookup"><span data-stu-id="2959a-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2959a-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2959a-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2959a-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2959a-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="2959a-123">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2959a-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2959a-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2959a-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
