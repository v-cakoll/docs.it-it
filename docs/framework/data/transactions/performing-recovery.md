---
title: Esecuzione del ripristino
description: Eseguire il ripristino in .NET. Resource Manager consente di risolvere gli elenchi durevoli delle transazioni riintegrando il partecipante alla transazione dopo un errore di risorsa.
ms.date: 03/30/2017
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
ms.openlocfilehash: bb00d2f574cc2651b733f3308cf2ffc6b430cc31
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141965"
---
# <a name="performing-recovery"></a>Esecuzione del ripristino
In caso di errore delle risorse, la gestione risorse consente di ripristinare le integrazioni durevoli di una transazione mediante la reintegrazione dei partecipanti della transazione.  
  
## <a name="the-recovery-process"></a>Descrizione del processo di ripristino  
 Per eseguire l'integrazione durevole di una risorsa (definita da un'implementazione dell'interfaccia <xref:System.Transactions.IEnlistmentNotification>) che in seguito può essere ripristinata, è necessario chiamare il metodo <xref:System.Transactions.Transaction.EnlistDurable%2A>. È inoltre necessario fornire al metodo <xref:System.Transactions.Transaction.EnlistDurable%2A> un identificatore del gestore di risorse (ovvero un oggetto <xref:System.Guid>), che viene utilizzato per identificare in modo coerente il partecipante della transazione in caso di errore delle risorse. Per questo motivo, la proprietà <xref:System.Guid> fornita alla chiamata di integrazione iniziale deve essere identica al parametro *resourceManagerIdentifier* nella <xref:System.Transactions.TransactionManager.Reenlist%2A> chiamata durante il ripristino. In caso contrario, viene generata un'eccezione <xref:System.Transactions.TransactionException>. Per ulteriori informazioni sulle integrazioni durevoli, vedere [integrazione di risorse come partecipanti in una transazione](enlisting-resources-as-participants-in-a-transaction.md) .  
  
 Nella fase di preparazione (fase 1) del protocollo 2PC, l'implementazione del gestore di risorse durevole deve registrare il proprio record di preparazione non appena riceve la notifica di preparazione tramite il metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>. Il record deve contenere tutte le informazioni necessarie a completare la transazione in caso di commit. Il record di preparazione può essere eseguito in un secondo momento durante il ripristino recuperando la <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> proprietà del callback *preparingEnlistment* . Non è necessario eseguire la registrazione del record all'interno del metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>, in quanto il gestore di risorse può eseguire questa operazione in un thread di lavoro.  
  
 Il processo di ripristino è costituito dai due passaggi seguenti:  
  
### <a name="step-1---reenlist"></a>Passaggio 1: reintegrazione  
 Il gestore di risorse esamina le informazioni contenute nel record di preparazione di ogni integrazione incerta, ovvero nello stato InDoubt. A tale scopo, esamina la proprietà <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> del callback <xref:System.Transactions.PreparingEnlistment> passata durante la fase 1 al gestore di risorse nella notifica basata sul metodo <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>.  
  
 Per ogni integrazione di questo tipo, il gestore di risorse richiama il metodo <xref:System.Transactions.TransactionManager.Reenlist%2A> sulla gestione transazioni. Questo metodo passa una matrice di byte contenente l'identificatore univoco <xref:System.Guid> del gestore di risorse nonché le informazioni relative all'integrazione. Viene quindi restituito un nuovo oggetto <xref:System.Transactions.Enlistment>. Se la reintegrazione non riesce e viene generata un'eccezione, il gestore di risorse deve provare in seguito a eseguire nuovamente questo passaggio.  
  
 Il metodo <xref:System.Transactions.TransactionManager.Reenlist%2A> deve essere chiamato soltanto quando un gestore delle risorse viene riavviato dopo un errore. Inoltre, la reintegrazione deve riguardare esclusivamente le transazioni non ripristinate registrate da un gestore di risorse durante la fase iniziale di preparazione di un commit a due fasi. Qualsiasi tentativo di chiamata a questo metodo in casi non validi può produrre risultati imprevisti.  
  
 Dopo aver utilizzato questo metodo per reintegrare un partecipante, il sistema chiama il metodo della fase 2 dell'interfaccia <xref:System.Transactions.IEnlistmentNotification> corrispondente al risultato della transazione (ovvero <xref:System.Transactions.IEnlistmentNotification.Commit%2A>, <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> o <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>).  
  
### <a name="step-2---completing-the-recovery"></a>Passaggio 2: completamento del ripristino  
 Al termine di tutte le reintegrazioni, il gestore di risorse chiama il metodo <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>. Questo metodo consente di completare il ripristino e di comunicare alla gestione transazioni che il gestore di risorse non presenta più alcuna transazione incerta. Ciò consente al gestore di risorse di garantire che non richiamerà più il metodo <xref:System.Transactions.TransactionManager.Reenlist%2A>.  
  
 Un gestore di risorse può integrarsi in altre transazioni anche se non ha ancora risolto tutte le transazioni incerte. Il primo passaggio può essere eseguito in qualsiasi momento dopo che Gestione risorse ha stabilito una relazione con la gestione transazioni, ma dopo che <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> è stato richiamato (passaggio 2); non è possibile eseguire di nuovo il passaggio 1. Il passaggio 2 può essere ripetuto più volte senza che ciò influisca sul risultato delle transazioni.
