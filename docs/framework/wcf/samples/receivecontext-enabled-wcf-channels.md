---
title: Canali WCF abilitati per ReceiveContext
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442746"
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="dff52-102">Canali WCF abilitati per ReceiveContext</span><span class="sxs-lookup"><span data-stu-id="dff52-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="dff52-103">In questo esempio viene illustrata l'utilità dei canali WCF abilitati per <xref:System.ServiceModel.Channels.ReceiveContext>.</span><span class="sxs-lookup"><span data-stu-id="dff52-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="dff52-104">In questo esempio viene implementato un servizio per trovare il prodotto di due numeri usando un canale NetMSMQ.</span><span class="sxs-lookup"><span data-stu-id="dff52-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="dff52-105">La classe <xref:System.ServiceModel.Channels.ReceiveContext> consente a un'applicazione di scegliere se accedere al messaggio o lasciarlo nella coda per l'ulteriore elaborazione, anche dopo il controllo del contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="dff52-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="dff52-106">In questo esempio un client invia integer casuali a una coda transazionale.</span><span class="sxs-lookup"><span data-stu-id="dff52-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="dff52-107">Il servizio `ProductCalculator` riceve i messaggi e controlla il contenuto dei messaggi, costituito da integer, per determinare se è possibile calcolare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="dff52-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="dff52-108">Se l'operazione del servizio non determina il calcolo del prodotto, il messaggio viene inserito di nuovo nella coda e può essere ricevuto nuovamente dal servizio in ascolto sulla coda.</span><span class="sxs-lookup"><span data-stu-id="dff52-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dff52-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dff52-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dff52-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dff52-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dff52-111">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="dff52-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dff52-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dff52-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dff52-113">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="dff52-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="dff52-114">Verificare che Accodamento messaggi Microsoft (MSMQ) sia installato.</span><span class="sxs-lookup"><span data-stu-id="dff52-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="dff52-115">Per installare MSMQ in [!INCLUDE[lserver](../../../../includes/lserver-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff52-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="dff52-116">Nelle **Server Manager**, fare clic su **funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="dff52-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="dff52-117">Nel riquadro destro sotto **Riepilogo funzionalità**, fare clic su **Aggiungi funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="dff52-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="dff52-118">Nella finestra risulta, espandere **Accodamento messaggi**.</span><span class="sxs-lookup"><span data-stu-id="dff52-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="dff52-119">Espandere **servizi di accodamento dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="dff52-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="dff52-120">Fare clic su **integrazione servizi Directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto HTTP**.</span><span class="sxs-lookup"><span data-stu-id="dff52-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="dff52-121">Fare clic su **successivo**, quindi fare clic su **installare**.</span><span class="sxs-lookup"><span data-stu-id="dff52-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="dff52-122">Per installare MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff52-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="dff52-123">Aprire il **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="dff52-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="dff52-124">Fare clic su **i programmi** e quindi selezionare **programmi e funzionalità**, fare clic su **Attiva funzionalità Windows attivare e disattivare**.</span><span class="sxs-lookup"><span data-stu-id="dff52-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="dff52-125">Espandere **Microsoft Message Queue (MSMQ) Server**, espandere **Microsoft Message Queue (MSMQ) Server Core**e quindi selezionare le caselle di controllo per le seguenti funzionalità installare Accodamento messaggi:</span><span class="sxs-lookup"><span data-stu-id="dff52-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="dff52-126">Message Queuing Server</span><span class="sxs-lookup"><span data-stu-id="dff52-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="dff52-127">Integrazione dei Servizi di dominio Active Directory MSMQ (per i computer aggiunti a un dominio).</span><span class="sxs-lookup"><span data-stu-id="dff52-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="dff52-128">Supporto HTTP MSMQ</span><span class="sxs-lookup"><span data-stu-id="dff52-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="dff52-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dff52-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="dff52-130">Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dff52-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="dff52-131">Verificare che [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] sia installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="dff52-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="dff52-132">Usare [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] per aprire il file della soluzione ReceiveContextProductGenerator.sln.</span><span class="sxs-lookup"><span data-stu-id="dff52-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="dff52-133">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="dff52-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="dff52-134">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="dff52-134">To run the solution, press CTRL+F5.</span></span>
