---
title: Raggruppamento di messaggi in coda in una sessione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 66f51267f20f8cdad8feeedf37435ccfa733146e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597358"
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="2ed2c-102">Raggruppamento di messaggi in coda in una sessione</span><span class="sxs-lookup"><span data-stu-id="2ed2c-102">Grouping Queued Messages in a Session</span></span>
<span data-ttu-id="2ed2c-103">Windows Communication Foundation (WCF) fornisce una sessione che consente di raggruppare un set di messaggi correlati per l'elaborazione da un'unica applicazione ricevente.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="2ed2c-104">I messaggi appartenenti a una sessione devono appartenere alla stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="2ed2c-105">Poiché tutti i messaggi appartengono alla stessa transazione, se l'elaborazione di un messaggio non riesce viene eseguito il rollback dell'intera sessione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="2ed2c-106">Le sessioni presentano comportamenti simili relativamente alle code di messaggi non recapitabili e alle code di messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="2ed2c-107">La proprietà di durata (TTL, Time To Live) impostata in un'associazione in coda configurata per una determinata sessione viene applicata all'intera sessione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="2ed2c-108">Se allo scadere del TTL è stata inviata solo una parte dei messaggi, l'intera sessione viene inserita nella coda di messaggi non recapitabili.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="2ed2c-109">Analogamente, quando risulta impossibile inviare a un'applicazione alcuni messaggi di una sessione contenuti nella coda dell'applicazione, l'intera sessione viene inserita nella coda di messaggi non elaborabili (se disponibile).</span><span class="sxs-lookup"><span data-stu-id="2ed2c-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="2ed2c-110">Esempio di raggruppamento di messaggi</span><span class="sxs-lookup"><span data-stu-id="2ed2c-110">Message Grouping Example</span></span>  
 <span data-ttu-id="2ed2c-111">Un esempio in cui il raggruppamento di messaggi è utile quando si implementa un'applicazione di elaborazione degli ordini come servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="2ed2c-112">Si supponga ad esempio che un client invii a questa applicazione un ordine contenente alcuni elementi.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="2ed2c-113">Per ogni elemento il client effettua una chiamata al servizio. Ciò comporta l'invio di un messaggio a parte per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="2ed2c-114">È possibile che il server A riceva il primo elemento e il server B riceva il secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="2ed2c-115">Ogni volta che viene aggiunto un elemento, il server che lo sta elaborando deve individuare l'ordine associato e quindi aggiungervi tale elemento. Ciò risulta particolarmente inefficiente.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="2ed2c-116">Gli stessi problemi di inefficienza si presentano anche utilizzando un unico server che gestisce tutte le richieste. Infatti, tale server deve tenere traccia di tutti gli ordini correntemente in elaborazione e determinare a quale di essi appartiene il nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="2ed2c-117">Il raggruppamento di tutte le richieste relative a un determinato ordine consente di semplificare notevolmente l'implementazione dell'applicazione descritta.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="2ed2c-118">L'applicazione client invia in una sessione tutti gli elementi relativi a un determinato ordine. Pertanto, quando il servizio elabora l'ordine, elabora l'intera sessione in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="2ed2c-119">Procedure</span><span class="sxs-lookup"><span data-stu-id="2ed2c-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="2ed2c-120">Per configurare l'utilizzo di sessioni in un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="2ed2c-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="2ed2c-121">Definire un contratto di servizio che richieda una sessione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="2ed2c-122">Eseguire questa operazione con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo specificando:</span><span class="sxs-lookup"><span data-stu-id="2ed2c-122">Do this with the <xref:System.ServiceModel.ServiceContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="2ed2c-123">Poiché questi metodi non restituiscono alcun dato, contrassegnare le operazioni del contratto come unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="2ed2c-124">Questa operazione viene eseguita con l' <xref:System.ServiceModel.OperationContractAttribute> attributo specificando:</span><span class="sxs-lookup"><span data-stu-id="2ed2c-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="2ed2c-125">Implementare il contratto di servizio e specificare la modalità <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode><xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-125">Implement the service contract and specify an <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ed2c-126">Ciò comporta la creazione di un'unica istanza del servizio per ogni sessione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-126">This instantiates the service only once for each session.</span></span>  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="2ed2c-127">Per ogni operazione del servizio è necessario specificare una transazione.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="2ed2c-128">A tale scopo, utilizzare l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="2ed2c-129">L'operazione che completa la transazione deve inoltre impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-129">The operation that completes the transaction should also set <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> to `true`.</span></span>  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. <span data-ttu-id="2ed2c-130">Configurare un endpoint che utilizza l'associazione `NetMsmqBinding` fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="2ed2c-131">Creare una coda transazionale utilizzando lo spazio dei nomi <xref:System.Messaging>.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="2ed2c-132">Tale coda può anche essere creata tramite il sistema di accodamento dei messaggi (MSMQ) o la console MMC.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="2ed2c-133">In tal caso, creare una coda transazionale.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="2ed2c-134">Creare un host del servizio mediante la classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="2ed2c-135">Aprire l'host del servizio per rendere disponibile il servizio.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="2ed2c-136">Chiudere l'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="2ed2c-137">Per configurare un client</span><span class="sxs-lookup"><span data-stu-id="2ed2c-137">To set up a client</span></span>  
  
1. <span data-ttu-id="2ed2c-138">Creare un ambito di transazione per scrivere nella coda transazionale.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="2ed2c-139">Creare il client WCF utilizzando lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="2ed2c-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="2ed2c-140">Inviare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-140">Place the order.</span></span>  
  
4. <span data-ttu-id="2ed2c-141">Chiudere il client WCF.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ed2c-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ed2c-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2ed2c-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ed2c-143">Description</span></span>  
 <span data-ttu-id="2ed2c-144">Nell'esempio seguente viene riportato il codice del servizio `IProcessOrder` e di un client che utilizza tale servizio.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="2ed2c-145">Viene illustrato come WCF utilizza le sessioni in coda per fornire il comportamento di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="2ed2c-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="2ed2c-146">Codice del servizio</span><span class="sxs-lookup"><span data-stu-id="2ed2c-146">Code for the Service</span></span>  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="2ed2c-147">Codice del client</span><span class="sxs-lookup"><span data-stu-id="2ed2c-147">Code for the Client</span></span>  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="2ed2c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ed2c-148">See also</span></span>

- [<span data-ttu-id="2ed2c-149">Sessioni e code</span><span class="sxs-lookup"><span data-stu-id="2ed2c-149">Sessions and Queues</span></span>](../samples/sessions-and-queues.md)
- [<span data-ttu-id="2ed2c-150">Panoramica delle code</span><span class="sxs-lookup"><span data-stu-id="2ed2c-150">Queues Overview</span></span>](queues-overview.md)
