---
title: Integrazione di risorse come partecipanti a una transazione
description: Integrare le risorse come partecipanti in una transazione .NET. Ogni risorsa in una transazione viene gestita da un gestore di risorse, coordinata da una gestione transazioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 786a12c2-d530-49f4-9c59-5c973e15a11d
ms.openlocfilehash: c3c777593750b3a4f05ae97ed6e26e19f58e4d72
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141875"
---
# <a name="enlisting-resources-as-participants-in-a-transaction"></a>Integrazione di risorse come partecipanti a una transazione

Ogni risorsa che partecipa a una transazione viene gestita dalla gestione risorse, le cui azioni vengono coordinate dalla gestione transazioni. La coordinazione si basa sull'invio di notifiche ai partecipanti che hanno utilizzato la gestione transazioni per integrarsi nella transazione.

Questo argomento descrive come integrare una o più risorse in una transazione, nonché i vari tipi di integrazione. Il [commit di una transazione in un argomento a fase singola e multifase](committing-a-transaction-in-single-phase-and-multi-phase.md) descrive il modo in cui l'impegno delle transazioni può essere coordinato tra le risorse integrate.

## <a name="enlisting-resources-in-a-transaction"></a>Integrazione di risorse in una transazione

Per poter partecipare a una determinata transazione, una risorsa deve integrarsi in essa. La <xref:System.Transactions.Transaction> classe definisce un set di metodi i cui nomi iniziano con **integrazione** che forniscono questa funzionalità. I diversi **metodi di integrazione corrispondono** ai diversi tipi di integrazione che può avere un gestore di risorse. In particolare, i metodi <xref:System.Transactions.Transaction.EnlistVolatile%2A> vengono utilizzati per le risorse volatili, mentre i metodi <xref:System.Transactions.Transaction.EnlistDurable%2A> vengono utilizzati per le risorse durevoli. La durabilità (o la volatilità) di un gestore di risorse ne indica la capacità (o la non capacità) di ripristino in caso di errore. I gestori di risorse che supportano il ripristino in caso di errore salvano i dati in modo permanente in un archivio durevole durante la fase 1, ovvero la fase di preparazione. In questo modo, se il gestore di risorse diventa non disponibile, può reintegrarsi nella transazione non appena viene ripristinato e quindi eseguire le azioni appropriate in base alle notifiche ricevute dalla gestione transazioni. In generale, i gestori di risorse volatili gestiscono risorse volatili, come nel caso di una struttura di dati in memoria (ad esempio, una tabella hash transazionale in memoria), laddove i gestori di risorse durevoli gestiscono risorse che presentano un archivio di backup permanente, come nel caso di un database con archivio di backup su disco.

Per semplicità, dopo aver deciso se utilizzare il metodo <xref:System.Transactions.Transaction.EnlistDurable%2A> o il metodo <xref:System.Transactions.Transaction.EnlistVolatile%2A> a seconda del supporto di durabilità della risorsa utilizzata, è necessario integrare la risorsa nel protocollo 2PC (2-Phase Commit, commit a due fasi) implementando nel gestore di risorse l'interfaccia <xref:System.Transactions.IEnlistmentNotification>. Per altre informazioni su 2PC, vedere [commit di una transazione in un'unica fase e in più fasi](committing-a-transaction-in-single-phase-and-multi-phase.md).

Un determinato partecipante può integrarsi in uno o più di questi protocolli chiamando più volte i metodi <xref:System.Transactions.Transaction.EnlistDurable%2A> e <xref:System.Transactions.Transaction.EnlistVolatile%2A>.

### <a name="durable-enlistment"></a>Integrazione durevole

I metodi <xref:System.Transactions.Transaction.EnlistDurable%2A> consentono di integrare un gestore di risorse affinché partecipi alla transazione come risorsa durevole.  Un gestore di risorse durevoli è in grado di eseguire il ripristino anche se diventa non disponibile durante l'esecuzione di una transazione. Non appena diventa nuovamente disponibile, il gestore di risorse esegue il ripristino reintegrandosi (tramite il metodo <xref:System.Transactions.TransactionManager.Reenlist%2A>) in tutte le transazioni a cui partecipava e per cui non è stato in grado di completare la fase 2. Al termine delle operazioni di ripristino, il gestore di risorse chiama il metodo <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>. Per ulteriori informazioni sul ripristino, vedere [esecuzione del ripristino](performing-recovery.md).

Tutti i metodi <xref:System.Transactions.Transaction.EnlistDurable%2A> accettano come primo parametro un oggetto <xref:System.Guid>. L'oggetto <xref:System.Guid> viene utilizzato dalla gestione transazioni per associare un'integrazione durevole a un determinato gestore di risorse. È pertanto estremamente importante che, quando riavviato, un gestore di risorse utilizzi in modo coerente lo stesso oggetto <xref:System.Guid> per identificarsi anche presso più gestori di risorse. In caso contrario, è possibile che la procedura di ripristino abbia esito negativo.

Il secondo parametro del metodo <xref:System.Transactions.Transaction.EnlistDurable%2A> è un riferimento all'oggetto che il gestore di risorse implementa per ricevere notifiche transazionali. L'overload utilizzato consente di comunicare alla gestione transazioni se il gestore di risorse supporta l'ottimizzazione mediante SPC (Single-Phase Commit, commit monofase). La maggior parte delle volte si implementerebbe l'interfaccia <xref:System.Transactions.IEnlistmentNotification> per consentire la partecipazione al commit a due fasi. Tuttavia, se si desidera ottimizzare il processo di commit, è possibile implementare l'interfaccia <xref:System.Transactions.ISinglePhaseNotification> per il commit monofase. Per ulteriori informazioni su SPC, vedere [commit di una transazione in un'unica fase e multifase](committing-a-transaction-in-single-phase-and-multi-phase.md) e [Ottimizzazione mediante commit a fase singola e notifica a singola fase promuovibile](optimization-spc-and-promotable-spn.md).

Il terzo parametro è un'enumerazione <xref:System.Transactions.EnlistmentOptions> il cui valore può essere <xref:System.Transactions.EnlistmentOptions.None> o <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>. Se il valore è impostato su <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>, l'integrazione può coinvolgere gestori di risorse aggiuntivi non appena viene ricevuta la notifica di preparazione inviata dalla gestione transazioni. Si noti tuttavia che per questo tipo di integrazione non è possibile utilizzare l'ottimizzazione mediante SPC.

### <a name="volatile-enlistment"></a>Integrazione volatile

I partecipanti che gestiscono risorse volatili, ad esempio una cache, devono integrarsi mediante i metodi <xref:System.Transactions.Transaction.EnlistVolatile%2A>. Tali oggetti potrebbero non essere in grado di conoscere il risultato di una transazione o ripristinare lo stato delle transazioni a cui partecipano a seguito di un errore di sistema.

Come già descritto, i gestori di risorse eseguono un'integrazione volatile solo se gestiscono una risorsa in memoria volatile. Uno dei vantaggi dell'utilizzo del metodo <xref:System.Transactions.Transaction.EnlistVolatile%2A> è che consente di evitare le escalation non necessarie delle transazioni. Per ulteriori informazioni sull'escalation delle transazioni, vedere l'argomento relativo all' [escalation della gestione delle transazioni](transaction-management-escalation.md) . L'integrazione della volatilità implica una differenza nel modo in cui l'integrazione viene gestita dal gestore transazioni, oltre a quanto previsto dal gestore delle transazioni. Ciò è dovuto al fatto che il gestore di risorse volatile non esegue alcuna procedura di ripristino. Ciò a sua volta comporta che i gestori di risorse volatili non chiamano alcun metodo <xref:System.Transactions.Transaction.EnlistVolatile%2A> a cui passare un oggetto <xref:System.Guid>. Ne consegue che i metodi <xref:System.Transactions.TransactionManager.Reenlist%2A> non accettano alcun parametro <xref:System.Guid>.

Analogamente alle integrazioni durevoli, la gestione transazioni è in grado di stabilire se il gestore di risorse supporta l'ottimizzazione mediante il protocollo SPC a partire dal metodo di overload utilizzato per eseguire l'integrazione. Poiché i gestori delle risorse volatili non eseguono alcuna procedura di ripristino, la fase di preparazione dell'integrazione volatile non prevede alcuna scrittura di informazioni di ripristino. Se pertanto si chiama il metodo <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>, il sistema genera un'eccezione <xref:System.InvalidOperationException>.

Nell'esempio seguente viene mostrato come utilizzare il metodo <xref:System.Transactions.Transaction.EnlistVolatile%2A> per integrare un oggetto come partecipante a una transazione.

[!code-csharp[Tx_Enlist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#1)]
[!code-vb[Tx_Enlist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#1)]

### <a name="optimizing-performance"></a>Ottimizzazione delle prestazioni

La classe <xref:System.Transactions.Transaction> fornisce inoltre il metodo <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> per eseguire l'integrazione PSPE (Promotable Single Phase Enlistment). Grazie a questo meccanismo, un gestore di risorse durevoli può ospitare e "possedere" una transazione di cui in seguito può eseguire l'escalation in modo che venga gestita dal gestore MSDTC, se necessario. Per altre informazioni, vedere [ottimizzazione tramite commit a fase singola e notifica a singola fase promuovibile](optimization-spc-and-promotable-spn.md).

## <a name="see-also"></a>Vedere anche

- [Ottimizzazione mediante commit monofase e notifica monofase promuovibile](optimization-spc-and-promotable-spn.md)
- [Commit di una transazione in monofase e multifase](committing-a-transaction-in-single-phase-and-multi-phase.md)
