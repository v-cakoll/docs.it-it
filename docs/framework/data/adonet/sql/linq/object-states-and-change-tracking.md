---
title: Stati di oggetti e rilevamento di modifiche
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f7eb1a8afe87caece18432c66a8d8a268ce9fbd2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="object-states-and-change-tracking"></a>Stati di oggetti e rilevamento di modifiche
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]oggetti sempre associato uno *stato*. Ad esempio, quando in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene creato un nuovo oggetto, lo stato dell'oggetto è `Unchanged`. Un nuovo oggetto creato dall'utente è noto il <xref:System.Data.Linq.DataContext> e `Untracked` dello stato. Dopo la corretta esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, tutti gli oggetti riconosciuti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono nello stato `Unchanged`. La sola eccezione è rappresentata dagli oggetti eliminati dal database che sono nello stato `Deleted` e di conseguenza inutilizzabili in quell'istanza di <xref:System.Data.Linq.DataContext>.  
  
## <a name="object-states"></a>Stati degli oggetti  
 Nella tabella riportata di seguito sono elencati gli stati possibili per gli oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Stato|Descrizione|  
|-----------|-----------------|  
|`Untracked`|Un oggetto non registrato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Di seguito vengono forniti alcuni esempi:<br /><br /> -Un oggetto non query tramite l'istanza corrente <xref:System.Data.Linq.DataContext> (ad esempio un oggetto appena creato).<br />-Un oggetto creato tramite deserializzazione<br />-Un oggetto di cui eseguire una query tramite una diversa <xref:System.Data.Linq.DataContext>.|  
|`Unchanged`|Un oggetto recuperato usando l'istanza corrente di <xref:System.Data.Linq.DataContext> e che non risulta modificato da quando è stato creato.|  
|`PossiblyModified`|Un oggetto che è *collegati* per un <xref:System.Data.Linq.DataContext>. Per ulteriori informazioni, vedere [il recupero dei dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|  
|`ToBeInserted`|Un oggetto non recuperato usando l'istanza corrente di <xref:System.Data.Linq.DataContext>. In questo caso viene eseguita un'operazione `INSERT` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeUpdated`|Un oggetto che risulta modificato da quando è stato recuperato. In questo caso viene eseguita un'operazione `UPDATE` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeDeleted`|Un oggetto contrassegnato per l'eliminazione, che causa un'operazione `DELETE` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`Deleted`|Un oggetto eliminato nel database. Questo stato è finale e non consente transizioni aggiuntive.|  
  
## <a name="inserting-objects"></a>Inserimento di oggetti  
 È possibile richiedere `Inserts` usando <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> in modo esplicito. In alternativa, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in grado di dedurre `Inserts` mediante la ricerca di oggetti collegati a uno degli oggetti conosciuti che devono essere aggiornati. Ad esempio, se si aggiunge un `Untracked` l'oggetto in un <xref:System.Data.Linq.EntitySet%601> o impostare un <xref:System.Data.Linq.EntityRef%601> per un `Untracked` dell'oggetto, si apportano le `Untracked` oggetto raggiungibile mediante gli oggetti rilevati nel grafico. Durante l'elaborazione <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consente di scorrere gli oggetti rilevati e individuato qualsiasi oggetto persistente raggiungibile di cui non vengono rilevate. Tali oggetti sono candidati per l'inserimento nel database.  
  
 Per le classi in una gerarchia di ereditarietà, <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>(`o`) imposta inoltre il valore del membro definito come il *discriminatore* corrispondere al tipo dell'oggetto `o`. Qualora un tipo dovesse corrispondere al valore discriminante predefinito, questa azione causerà la sovrascrittura del valore discriminante con il valore predefinito. Per ulteriori informazioni, vedere [supporto dell'ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
> [!IMPORTANT]
>  Un oggetto aggiunto a un oggetto `Table` non si trova nella cache delle identità, che riflette solo gli oggetti recuperati dal database. Dopo una chiamata a <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, l'entità aggiunta non viene visualizzata nelle query eseguite sul database finché non si completerà <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="deleting-objects"></a>Eliminazione di oggetti  
 Per contrassegnare per l'eliminazione un oggetto `o` rilevato, chiamare <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>(o) sull'oggetto <xref:System.Data.Linq.Table%601> appropriato. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]la rimozione di un oggetto da un <xref:System.Data.Linq.EntitySet%601> come aggiornamento operazione e il valore di chiave esterna corrispondente viene impostato su null. La destinazione dell'operazione (`o`) non viene eliminata dalla relativa tabella. Ad esempio, `cust.Orders.DeleteOnSubmit(ord)` indica un aggiornamento in cui la relazione tra `cust` e `ord` viene interrotta mediante l'impostazione della chiave esterna `ord.CustomerID` su null. Non causa l'eliminazione della riga che corrisponde a `ord`.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]esegue l'elaborazione seguente quando viene eliminato un oggetto (<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>) rispetto alla relativa tabella:  
  
-   Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, per quell'oggetto viene eseguita un'operazione `DELETE`.  
  
-   La rimozione non viene propagata agli oggetti correlati, indipendentemente dallo stato di caricamento. In particolare, gli oggetti correlati non vengono caricati per aggiornare la proprietà della relazione.  
  
-   Dopo la corretta esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, gli oggetti vengono impostati sullo stato `Deleted`. Di conseguenza non sarà possibile usare l'oggetto o il relativo `id` in un'istanza di <xref:System.Data.Linq.DataContext>. La cache interna gestita da un'istanza di <xref:System.Data.Linq.DataContext> non elimina gli oggetti recuperati o aggiunti come nuovi, anche dopo che sono stati eliminati nel database.  
  
 È possibile chiamare <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> solo su un oggetto registrato da <xref:System.Data.Linq.DataContext>. Per un oggetto `Untracked` è necessario chiamare <xref:System.Data.Linq.Table%601.Attach%2A> prima di <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>. Chiamando <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> su un oggetto`Untracked`, verrà generata un'eccezione.  
  
> [!NOTE]
>  La rimozione di un oggetto da una tabella indica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per generare un database SQL corrispondente `DELETE` comando al momento della <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Questa azione non rimuove l'oggetto dalla cache, né propaga l'eliminazione agli oggetti correlati.  
>   
>  Per recuperare l'`id` di un oggetto eliminato, usare una nuova istanza di <xref:System.Data.Linq.DataContext>. Per la pulizia degli oggetti correlati, è possibile utilizzare il *eliminazione a catena* funzionalità del database, altrimenti manualmente eliminare gli oggetti correlati.  
>   
>  Non è necessario, a differenza del database, eliminare gli oggetti correlati in un ordine particolare.  
  
## <a name="updating-objects"></a>Aggiornamento di oggetti  
 È possibile rilevare l'esecuzione di `Updates` osservando le notifiche delle modifiche, che vengono fornite tramite l'evento <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> nei metodi per l'impostazione delle proprietà. Quando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] riceve una notifica della prima modifica a un oggetto, crea una copia dell'oggetto e lo considera candidato per la generazione di un'istruzione `Update`.  
  
 Per gli oggetti che non implementano <xref:System.ComponentModel.INotifyPropertyChanging>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mantiene una copia dei valori degli oggetti quando prima materializzazione. Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] confronta i valori originali e correnti per stabilire se l'oggetto è stato modificato.  
  
 Per gli aggiornamenti delle relazioni, il riferimento dal figlio al padre, ovvero il riferimento che corrisponde alla chiave esterna, viene considerato autorevole. Il riferimento nella direzione inversa, ovvero da padre a figlio, è facoltativo. Le classi di relazione (<xref:System.Data.Linq.EntitySet%601> e <xref:System.Data.Linq.EntityRef%601>) assicurano che i riferimenti bidirezionali siano coerenti per le relazioni uno-a-molti e uno-a-uno. Se il modello a oggetti non usa <xref:System.Data.Linq.EntitySet%601> o <xref:System.Data.Linq.EntityRef%601> e se è presente il riferimento inverso, sarà necessario mantenerlo coerente con il riferimento in avanti quando viene aggiornata la relazione.  
  
 Se si aggiornano sia il riferimento obbligatorio che la chiave esterna corrispondente, è necessario assicurarsi che corrispondano. Se non sono entrambi sincronizzati quando si chiama <xref:System.InvalidOperationException>, verrà generata un'eccezione <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Anche se le modifiche dei valori della chiave esterna sono sufficienti per interessare un aggiornamento della riga sottostante, è necessario modificare il riferimento per mantenere la connettività dell'oggetto grafico e la coerenza bidirezionale delle relazioni.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)
