---
title: Correlazione basata sul contenuto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5fea83ff6ac73fc26c419d9f7d5e8c5fe571135
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="content-based-correlation"></a><span data-ttu-id="11d49-102">Correlazione basata sul contenuto</span><span class="sxs-lookup"><span data-stu-id="11d49-102">Content-Based Correlation</span></span>
<span data-ttu-id="11d49-103">In questo esempio viene illustrato come è possibile usare le attività di messaggistica (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>e <xref:System.ServiceModel.Activities.ReceiveReply>) con una e con più correlazioni basate sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="11d49-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="11d49-104">In questo scenario una correlazione viene prima inizializzata in base a un ID dell'ordine di acquisto, quindi in un secondo momento viene creata l'altra correlazione in base all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="11d49-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="11d49-105">Illustra come un'attività <xref:System.ServiceModel.Activities.Receive> possa seguire una correlazione esistente e inizializzarne una nuova in base allo stesso messaggio in arrivo.</span><span class="sxs-lookup"><span data-stu-id="11d49-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="11d49-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="11d49-106">Demonstrates</span></span>  
 <span data-ttu-id="11d49-107">Attività di messaggistica e correlazione basata sul contenuto</span><span class="sxs-lookup"><span data-stu-id="11d49-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="11d49-108">Discussione</span><span class="sxs-lookup"><span data-stu-id="11d49-108">Discussion</span></span>  
 <span data-ttu-id="11d49-109">In questo esempio viene illustrato come usare più correlazioni basate sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="11d49-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="11d49-110">In questo scenario una correlazione viene prima inizializzata in base a un ID dell'ordine di acquisto, quindi in un secondo momento viene creata l'altra correlazione in base all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="11d49-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="11d49-111">Le correlazioni vengono sovrapposte usando un'attività <xref:System.ServiceModel.Activities.Receive> che segue una correlazione esistente (PurchaseOrderId) e inizializza una nuova correlazione (CustomerID) in base allo stesso messaggio in arrivo.</span><span class="sxs-lookup"><span data-stu-id="11d49-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="11d49-112">Per eseguire questa operazione, nell'attività <xref:System.ServiceModel.Activities.Receive> vengono usate le proprietà <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> e <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.</span><span class="sxs-lookup"><span data-stu-id="11d49-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="11d49-113">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="11d49-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="11d49-114">Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="11d49-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="11d49-115">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CascadingCorrelation.sln.</span><span class="sxs-lookup"><span data-stu-id="11d49-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="11d49-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="11d49-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="11d49-117">Per eseguire il server, premere F5.</span><span class="sxs-lookup"><span data-stu-id="11d49-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="11d49-118">Una volta che servizio è pronto e in attesa dei messaggi, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Client ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="11d49-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11d49-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="11d49-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="11d49-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="11d49-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="11d49-121">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11d49-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="11d49-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="11d49-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`