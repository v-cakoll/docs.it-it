---
title: Commit di una transazione in monofase e multifase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2891313c15b4003db5d50f2e9f2d461de9397dfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="63d0b-102">Commit di una transazione in monofase e multifase</span><span class="sxs-lookup"><span data-stu-id="63d0b-102">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="63d0b-103">Ogni risorsa utilizzata in una transazione viene gestita dalla gestione risorse (in seguito indicato con la sigla GR), le cui azioni vengono coordinate dalla gestione transazioni (in seguito indicato con la sigla GT).</span><span class="sxs-lookup"><span data-stu-id="63d0b-103">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="63d0b-104">Il [l'integrazione di risorse come partecipanti in una transazione](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) argomento viene illustrato come una risorsa (o più risorse) possono essere integrate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="63d0b-104">The [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="63d0b-105">Questo argomento descrive invece come coordinare il commit di una transazione fra le risorse integrate.</span><span class="sxs-lookup"><span data-stu-id="63d0b-105">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="63d0b-106">Al termine della transazione, l'applicazione richiede che venga eseguito il commit o il rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="63d0b-106">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="63d0b-107">La gestione transazioni deve eliminare qualsiasi possibilità che si verifichino situazioni di incoerenza, come ad esempio nel caso di una transazione per cui alcuni gestori di risorse votano a favore del commit mentre altri votano a favore del rollback.</span><span class="sxs-lookup"><span data-stu-id="63d0b-107">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="63d0b-108">Se la transazione interessa più di una risorsa, è necessario eseguire un commit a due fasi.</span><span class="sxs-lookup"><span data-stu-id="63d0b-108">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="63d0b-109">Il protocollo di commit a due fasi, che prevede una fase di preparazione e una fase di commit, garantisce che al termine della transazione venga eseguito coerentemente il commit oppure il rollback di tutte le modifiche apportate alle risorse.</span><span class="sxs-lookup"><span data-stu-id="63d0b-109">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="63d0b-110">Tutti i partecipanti vengono quindi informati in merito al risultato finale.</span><span class="sxs-lookup"><span data-stu-id="63d0b-110">All the participants are then informed of the final result.</span></span> <span data-ttu-id="63d0b-111">Per una descrizione dettagliata del protocollo commit in due fasi, consultare il manuale "*l'elaborazione delle transazioni: concetti e tecniche (Series Morgan Kaufmann nei sistemi di gestione di dati) ISBN:1558601902*" da Jim Gray.</span><span class="sxs-lookup"><span data-stu-id="63d0b-111">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="63d0b-112">Le prestazioni delle transazioni possono anche essere ottimizzate tramite il protocollo di commit monofase.</span><span class="sxs-lookup"><span data-stu-id="63d0b-112">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="63d0b-113">Per ulteriori informazioni, vedere [ottimizzazione utilizzando il Commit a fase singola e Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="63d0b-113">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="63d0b-114">Se si desidera soltanto ricevere informazioni sul risultato di una transazione senza partecipare alla votazione, è necessario essere registrati all'evento <xref:System.Transactions.Transaction.TransactionCompleted>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-114">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="63d0b-115">Protocollo 2PC</span><span class="sxs-lookup"><span data-stu-id="63d0b-115">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="63d0b-116">Nella prima fase della transazione, la gestione transazioni esegue una query su ogni risorsa allo scopo di determinare se eseguire il commit o il rollback di una transazione.</span><span class="sxs-lookup"><span data-stu-id="63d0b-116">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="63d0b-117">Nella seconda fase della transazione, la gestione transazioni informa ogni risorsa in merito al risultato delle query eseguite, consentendo l'esecuzione delle operazioni di pulizia eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="63d0b-117">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="63d0b-118">Per poter partecipare a questo tipo di transazione, un gestore di risorse deve implementare l'interfaccia <xref:System.Transactions.IEnlistmentNotification>, che fornisce i metodi chiamati dal GT per l'invio delle notifiche durante un commit a due fasi.</span><span class="sxs-lookup"><span data-stu-id="63d0b-118">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="63d0b-119">Di seguito è riportato un esempio di questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="63d0b-119">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="63d0b-120">Fase di preparazione (fase 1)</span><span class="sxs-lookup"><span data-stu-id="63d0b-120">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="63d0b-121">Quando riceve dall'applicazione una richiesta di commit tramite una chiamata al metodo <xref:System.Transactions.CommittableTransaction.Commit%2A>, la gestione transazioni avvia la fase di preparazione di tutti i partecipanti integrati. A tale scopo, chiama il metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> su ogni risorsa integrata al fine di determinare per ognuna di esse il voto espresso in merito alla transazione.</span><span class="sxs-lookup"><span data-stu-id="63d0b-121">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="63d0b-122">Come illustrato nel semplice esempio seguente, il gestore di risorse che implementa l'interfaccia <xref:System.Transactions.IEnlistmentNotification> deve prima implementare il metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-122">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```  
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="63d0b-123">Quando il gestore di risorse durevole riceve questa chiamata, deve registrare le informazioni per il ripristino della transazione (disponibili tramite il recupero della proprietà <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>) nonché qualsiasi informazione necessaria al completamento della transazione in caso di commit.</span><span class="sxs-lookup"><span data-stu-id="63d0b-123">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="63d0b-124">Non è necessario eseguire questa operazione all'interno del metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>, in quanto il GR può eseguirla mediante un thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="63d0b-124">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="63d0b-125">Dopo aver completato la fase di preparazione, il GR deve votare il commit o il rollback della transazione chiamando rispettivamente il metodo <xref:System.Transactions.PreparingEnlistment.Prepared%2A> o il metodo <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-125">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="63d0b-126">Si noti che la classe <xref:System.Transactions.PreparingEnlistment> eredita un metodo <xref:System.Transactions.Enlistment.Done%2A> dalla classe <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-126">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="63d0b-127">Se si chiama questo metodo sul callback <xref:System.Transactions.PreparingEnlistment> durante la fase di preparazione, il GT riceve una notifica in cui si indica che l'integrazione è di sola lettura (ovvero, i gestori di risorse possono leggere ma non aggiornare i dati protetti dalle transazioni) e il GT non informa più il GR in merito al risultato della transazione nella fase 2.</span><span class="sxs-lookup"><span data-stu-id="63d0b-127">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="63d0b-128">L'applicazione riceve informazioni sull'esito positivo del commit della transazione dopo che tutti i gestori di risorse votano tramite il metodo <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-128">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="63d0b-129">Fase di commit (fase 2)</span><span class="sxs-lookup"><span data-stu-id="63d0b-129">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="63d0b-130">Nella seconda fase della transazione, se tutti i GR inviano al GT una conferma di esito positivo relativamente alla fase 1, ovvero se tutti i GR hanno richiamato il metodo <xref:System.Transactions.PreparingEnlistment.Prepared%2A> al termine della fase di preparazione, il GT richiama il metodo <xref:System.Transactions.IEnlistmentNotification.Commit%2A> per ogni gestore di risorse.</span><span class="sxs-lookup"><span data-stu-id="63d0b-130">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="63d0b-131">I gestori di risorse possono quindi rendere definitive le modifiche e completare il commit.</span><span class="sxs-lookup"><span data-stu-id="63d0b-131">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="63d0b-132">Se almeno uno dei gestori di risorse invia una conferma di esito negativo relativamente alla fase 1, la gestione transazioni richiama il metodo <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> per ogni gestore di risorse e segnala all'applicazione la non riuscita del commit.</span><span class="sxs-lookup"><span data-stu-id="63d0b-132">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="63d0b-133">Ne consegue che il gestore di risorse deve implementare i metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="63d0b-133">Thus, your resource manager should implement the following methods.</span></span>  
  
```  
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment    
     enlistment.Done();    
}  
```  
  
 <span data-ttu-id="63d0b-134">Il GR deve eseguire tutte le operazioni necessarie per completare la transazione in base al tipo di notifica e quindi informare il GT in merito chiamando il metodo <xref:System.Transactions.Enlistment.Done%2A> sul parametro <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="63d0b-134">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="63d0b-135">Queste operazioni possono essere eseguite su un thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="63d0b-135">This work can be done on a worker thread.</span></span> <span data-ttu-id="63d0b-136">Si osservi che nella fase 2 le notifiche possono presentarsi inline nello stesso thread che ha chiamato il metodo <xref:System.Transactions.PreparingEnlistment.Prepared%2A> nella fase 1.</span><span class="sxs-lookup"><span data-stu-id="63d0b-136">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="63d0b-137">Ne consegue che, dopo la chiamata al metodo  <xref:System.Transactions.PreparingEnlistment.Prepared%2A>, non occorre eseguire alcuna operazione (ad esempio il rilascio dei blocchi) che si prevede sia stata completata prima di ricevere le notifiche della fase 2.</span><span class="sxs-lookup"><span data-stu-id="63d0b-137">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="63d0b-138">Implementazione di InDoubt</span><span class="sxs-lookup"><span data-stu-id="63d0b-138">Implementing InDoubt</span></span>  
 <span data-ttu-id="63d0b-139">Infine, è necessario implementare il metodo <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> per il gestore di risorse volatile.</span><span class="sxs-lookup"><span data-stu-id="63d0b-139">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="63d0b-140">Questo metodo viene chiamato se la gestione transazioni perde il contatto con uno o più partecipanti, il cui stato risulta pertanto sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="63d0b-140">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="63d0b-141">In questo caso è necessario registrare questo problema in modo che in un secondo momento sia possibile verificare se uno o più partecipanti della transazione sono rimasti in uno stato incoerente.</span><span class="sxs-lookup"><span data-stu-id="63d0b-141">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```  
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="63d0b-142">Ottimizzazione mediante commit monofase</span><span class="sxs-lookup"><span data-stu-id="63d0b-142">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="63d0b-143">Il protocollo di commit monofase è più efficiente in fase di esecuzione, poiché tutti gli aggiornamenti vengono eseguiti senza alcuna coordinazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="63d0b-143">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="63d0b-144">Per ulteriori informazioni su questo protocollo, vedere [ottimizzazione utilizzando il Commit a fase singola e Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="63d0b-144">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d0b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d0b-145">See Also</span></span>  
 [<span data-ttu-id="63d0b-146">Ottimizzazione mediante commit monofase e notifica monofase promuovibile</span><span class="sxs-lookup"><span data-stu-id="63d0b-146">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
 [<span data-ttu-id="63d0b-147">Integrazione di risorse come partecipanti a una transazione</span><span class="sxs-lookup"><span data-stu-id="63d0b-147">Enlisting Resources as Participants in a Transaction</span></span>](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)
