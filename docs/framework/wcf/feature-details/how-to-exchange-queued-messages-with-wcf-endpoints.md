---
title: 'Procedura: Lo scambio di messaggi in coda con endpoint WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 11435dc6f941a566427c0e0cb797e84f33dd66a2
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303647"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="08d19-102">Procedura: Lo scambio di messaggi in coda con endpoint WCF</span><span class="sxs-lookup"><span data-stu-id="08d19-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="08d19-103">Le code garantiscono che la messaggistica affidabile può verificarsi tra un client e un servizio Windows Communication Foundation (WCF), anche se il servizio non è disponibile al momento della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="08d19-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="08d19-104">Le procedure seguenti illustrano come assicurare una comunicazione durevole tra un client e un servizio utilizzando lo standard di associazione in coda quando si implementa il servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="08d19-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="08d19-105">In questa sezione illustra come usare <xref:System.ServiceModel.NetMsmqBinding> per la comunicazione in coda tra un client WCF e un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="08d19-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="08d19-106">Per utilizzare l'accodamento in un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="08d19-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="08d19-107">Definire un contratto di servizio utilizzando un'interfaccia contrassegnata con <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="08d19-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="08d19-108">Contrassegnare con <xref:System.ServiceModel.OperationContractAttribute> le operazioni che nell'interfaccia fanno parte del contratto di servizio e specificare che sono unidirezionali dal momento che non viene restituita alcuna risposta al metodo.</span><span class="sxs-lookup"><span data-stu-id="08d19-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="08d19-109">Nel codice seguente sono contenuti un esempio di contratto di servizio semplice e la relativa definizione di operazione.</span><span class="sxs-lookup"><span data-stu-id="08d19-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="08d19-110">Quando il contratto di servizio passa tipi definiti dall'utente, è necessario definire contratti dati per tali tipi.</span><span class="sxs-lookup"><span data-stu-id="08d19-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="08d19-111">Nel codice seguente vengono illustrati due contratti dati, `PurchaseOrder` e `PurchaseOrderLineItem`.</span><span class="sxs-lookup"><span data-stu-id="08d19-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="08d19-112">Questi due tipi definiscono i dati inviati al servizio.</span><span class="sxs-lookup"><span data-stu-id="08d19-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="08d19-113">Si noti che le classi che definiscono questo contratto dati definiscono anche un certo numero di metodi.</span><span class="sxs-lookup"><span data-stu-id="08d19-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="08d19-114">Questi non vengono considerati parte del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="08d19-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="08d19-115">Solo i membri che sono dichiarati con l'attributo `DataMember` fanno parte del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="08d19-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="08d19-116">Implementare i metodi del contratto di servizio definiti nell'interfaccia in una classe.</span><span class="sxs-lookup"><span data-stu-id="08d19-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="08d19-117">Si noti <xref:System.ServiceModel.OperationBehaviorAttribute> sul metodo `SubmitPurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="08d19-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="08d19-118">In tal modo viene specificato che questa operazione deve essere chiamata all'interno di una transazione e che la transazione viene completata automaticamente quando il metodo è stato completato.</span><span class="sxs-lookup"><span data-stu-id="08d19-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="08d19-119">Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="08d19-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="08d19-120">È possibile scegliere di creare la coda mediante la console MMC (Microsoft Management Console) MSMQ.</span><span class="sxs-lookup"><span data-stu-id="08d19-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="08d19-121">In tal caso, avere cura di creare una coda transazionale.</span><span class="sxs-lookup"><span data-stu-id="08d19-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="08d19-122">Definire un oggetto <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo del servizio e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard.</span><span class="sxs-lookup"><span data-stu-id="08d19-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="08d19-123">Per altre informazioni sull'uso di configurazione WCF, vedere [servizi di configurazione WCF](../configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="08d19-123">For more information about using WCF configuration, see [Configuring WCF services](../configuring-services.md).</span></span>  
  
  
  
6.  <span data-ttu-id="08d19-124">Creare un host per il servizio `OrderProcessing` utilizzando l'elemento <xref:System.ServiceModel.ServiceHost> che legge i messaggi dalla coda e li elabora.</span><span class="sxs-lookup"><span data-stu-id="08d19-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="08d19-125">Aprire l'host del servizio per rendere disponibile il servizio.</span><span class="sxs-lookup"><span data-stu-id="08d19-125">Open the service host to make the service available.</span></span> <span data-ttu-id="08d19-126">Visualizzare un messaggio che indichi all'utente di premere un tasto qualsiasi per terminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="08d19-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="08d19-127">Chiamare `ReadLine` per attendere che il tasto venga premuto, quindi chiudere il servizio.</span><span class="sxs-lookup"><span data-stu-id="08d19-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="08d19-128">Per creare un client per il servizio in coda</span><span class="sxs-lookup"><span data-stu-id="08d19-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="08d19-129">Nell'esempio seguente viene illustrato come eseguire l'applicazione host e utilizzare lo strumento Svcutil.exe per creare il client WCF.</span><span class="sxs-lookup"><span data-stu-id="08d19-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="08d19-130">Definire un <xref:System.ServiceModel.Description.ServiceEndpoint> nella configurazione che specifichi l'indirizzo e utilizzi l'associazione <xref:System.ServiceModel.NetMsmqBinding> standard, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="08d19-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="08d19-131">Creare un ambito di transazione da scrivere nella coda transazionale, chiamata di `SubmitPurchaseOrder` operazione e chiudere il client WCF, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="08d19-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="08d19-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="08d19-132">Example</span></span>  
 <span data-ttu-id="08d19-133">Negli esempi seguenti vengono illustrati il codice di servizio, l'applicazione host, il file App.config e il codice client inclusi per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="08d19-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="08d19-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08d19-134">See also</span></span>
- <xref:System.ServiceModel.NetMsmqBinding>
- [<span data-ttu-id="08d19-135">Associazioni MSMQ transazionali</span><span class="sxs-lookup"><span data-stu-id="08d19-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)
- [<span data-ttu-id="08d19-136">Accodamento in WCF</span><span class="sxs-lookup"><span data-stu-id="08d19-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [<span data-ttu-id="08d19-137">Procedura: Scambiare messaggi con endpoint WCF e le applicazioni di Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="08d19-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [<span data-ttu-id="08d19-138">Da Windows Communication Foundation a Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="08d19-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="08d19-139">Installazione accodamento messaggi (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="08d19-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="08d19-140">Accodamento messaggi in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="08d19-140">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="08d19-141">Sicurezza dei messaggi nell'accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="08d19-141">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
