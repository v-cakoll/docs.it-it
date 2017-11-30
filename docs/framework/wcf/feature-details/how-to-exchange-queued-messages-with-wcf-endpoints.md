---
title: 'Procedura: scambiare messaggi in coda con endpoint WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4b52fe96bc88f09b807640dedcc54a8468dc26e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="82ec3-102">Procedura: scambiare messaggi in coda con endpoint WCF</span><span class="sxs-lookup"><span data-stu-id="82ec3-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="82ec3-103">Le code garantiscono una messaggistica affidabile tra un client e un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], anche se il servizio non è disponibile al momento della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="82ec3-103">Queues ensure that reliable messaging can occur between a client and a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="82ec3-104">Nelle procedure seguenti viene spiegato come assicurare una comunicazione durevole tra un client e un servizio utilizzando l'associazione in coda standard in caso di implementazione del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ec3-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="82ec3-105">Contenuto della sezione viene spiegato come utilizzare <xref:System.ServiceModel.NetMsmqBinding> per la comunicazione in coda tra un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ec3-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="82ec3-106">Per utilizzare l'accodamento in un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="82ec3-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="82ec3-107">Definire un contratto di servizio utilizzando un'interfaccia contrassegnata con <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="82ec3-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="82ec3-108">Contrassegnare con <xref:System.ServiceModel.OperationContractAttribute> le operazioni che nell'interfaccia fanno parte del contratto di servizio e specificare che sono unidirezionali dal momento che non viene restituita alcuna risposta al metodo.</span><span class="sxs-lookup"><span data-stu-id="82ec3-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="82ec3-109">Nel codice seguente sono contenuti un esempio di contratto di servizio semplice e la relativa definizione di operazione.</span><span class="sxs-lookup"><span data-stu-id="82ec3-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="82ec3-110">Quando il contratto di servizio passa tipi definiti dall'utente, è necessario definire contratti dati per tali tipi.</span><span class="sxs-lookup"><span data-stu-id="82ec3-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="82ec3-111">Nel codice seguente vengono illustrati due contratti dati, `PurchaseOrder` e `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="82ec3-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="82ec3-112">Questi due tipi definiscono i dati inviati al servizio.</span><span class="sxs-lookup"><span data-stu-id="82ec3-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="82ec3-113">Si noti che le classi che definiscono questo contratto dati definiscono anche un certo numero di metodi.</span><span class="sxs-lookup"><span data-stu-id="82ec3-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="82ec3-114">Questi non vengono considerati parte del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="82ec3-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="82ec3-115">Solo i membri che sono dichiarati con l'attributo `DataMember` fanno parte del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="82ec3-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="82ec3-116">Implementare i metodi del contratto di servizio definiti nell'interfaccia in una classe.</span><span class="sxs-lookup"><span data-stu-id="82ec3-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="82ec3-117">Si noti <xref:System.ServiceModel.OperationBehaviorAttribute> sul metodo `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="82ec3-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="82ec3-118">In tal modo viene specificato che questa operazione deve essere chiamata all'interno di una transazione e che la transazione viene completata automaticamente quando il metodo è stato completato.</span><span class="sxs-lookup"><span data-stu-id="82ec3-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="82ec3-119">Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="82ec3-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="82ec3-120">È possibile scegliere di creare la coda mediante la console MMC (Microsoft Management Console) MSMQ.</span><span class="sxs-lookup"><span data-stu-id="82ec3-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="82ec3-121">In tal caso, avere cura di creare una coda transazionale.</span><span class="sxs-lookup"><span data-stu-id="82ec3-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="82ec3-122">Definire un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo del servizio e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard.</span><span class="sxs-lookup"><span data-stu-id="82ec3-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="82ec3-123">utilizzando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configurazione, vedere [la configurazione di applicazioni di Windows Communication Foundation](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span><span class="sxs-lookup"><span data-stu-id="82ec3-123"> using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="82ec3-124">Creare un host per il servizio `OrderProcessing` utilizzando l'elemento <xref:System.ServiceModel.ServiceHost> che legge i messaggi dalla coda e li elabora.</span><span class="sxs-lookup"><span data-stu-id="82ec3-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="82ec3-125">Aprire l'host del servizio per rendere disponibile il servizio.</span><span class="sxs-lookup"><span data-stu-id="82ec3-125">Open the service host to make the service available.</span></span> <span data-ttu-id="82ec3-126">Visualizzare un messaggio che indichi all'utente di premere un tasto qualsiasi per terminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="82ec3-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="82ec3-127">Chiamare `ReadLine` per attendere che il tasto venga premuto, quindi chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="82ec3-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="82ec3-128">Per creare un client per il servizio in coda</span><span class="sxs-lookup"><span data-stu-id="82ec3-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="82ec3-129">Nell'esempio di codice riportato di seguito viene illustrato come eseguire l'applicazione host e utilizzare lo strumento Svcutil.exe per creare il client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ec3-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="82ec3-130">Definire un <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="82ec3-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="82ec3-131">Creare un ambito di transazione da scrivere nella coda transazionale, chiamare l'operazione `SubmitPurchaseOrder` e chiudere il client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="82ec3-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="82ec3-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="82ec3-132">Example</span></span>  
 <span data-ttu-id="82ec3-133">Negli esempi seguenti vengono illustrati il codice di servizio, l'applicazione host, il file App.config e il codice client inclusi per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="82ec3-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="82ec3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82ec3-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="82ec3-135">Associazioni MSMQ transazionali</span><span class="sxs-lookup"><span data-stu-id="82ec3-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="82ec3-136">Accodamento messaggi in WCF</span><span class="sxs-lookup"><span data-stu-id="82ec3-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="82ec3-137">Procedura: scambiare messaggi con endpoint WCF e applicazioni di accodamento dei messaggi</span><span class="sxs-lookup"><span data-stu-id="82ec3-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="82ec3-138">Windows Communication Foundation a Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="82ec3-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="82ec3-139">Installazione di Accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="82ec3-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="82ec3-140">Esempi di associazione di integrazione di Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="82ec3-140">Message Queuing Integration Binding Samples</span></span>](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="82ec3-141">Accodamento messaggi di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="82ec3-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="82ec3-142">Sicurezza del messaggio su Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="82ec3-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
