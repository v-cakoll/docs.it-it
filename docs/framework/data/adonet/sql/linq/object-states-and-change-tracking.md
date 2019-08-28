---
title: Stati di oggetti e rilevamento di modifiche
ms.date: 03/30/2017
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
ms.openlocfilehash: a60afab5158d0d5f66d12d6913ee890abc8ca730
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043525"
---
# <a name="object-states-and-change-tracking"></a>Stati di oggetti e rilevamento di modifiche

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]gli oggetti partecipano sempre a uno *stato*. Ad esempio, quando in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene creato un nuovo oggetto, lo stato dell'oggetto è `Unchanged`. Un nuovo oggetto creato è sconosciuto a <xref:System.Data.Linq.DataContext> e si trova nello `Untracked` stato. Dopo la corretta esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, tutti gli oggetti riconosciuti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono nello stato `Unchanged`. La sola eccezione è rappresentata dagli oggetti eliminati dal database che sono nello stato `Deleted` e di conseguenza inutilizzabili in quell'istanza di <xref:System.Data.Linq.DataContext>.

## <a name="object-states"></a>Stati degli oggetti

Nella tabella riportata di seguito sono elencati gli stati possibili per gli oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

|Stato|Descrizione|
|-----------|-----------------|
|`Untracked`|Un oggetto non registrato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Di seguito vengono forniti alcuni esempi:<br /><br /> -Oggetto non sottoposto a query tramite l' <xref:System.Data.Linq.DataContext> oggetto corrente, ad esempio un oggetto appena creato.<br />: Oggetto creato tramite la deserializzazione.<br />-Oggetto su cui è stata eseguita una <xref:System.Data.Linq.DataContext>query tramite un oggetto diverso.|
|`Unchanged`|Un oggetto recuperato usando l'istanza corrente di <xref:System.Data.Linq.DataContext> e che non risulta modificato da quando è stato creato.|
|`PossiblyModified`|Oggetto *associato* a un <xref:System.Data.Linq.DataContext>oggetto. Per ulteriori informazioni, vedere [recupero di dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|
|`ToBeInserted`|Un oggetto non recuperato usando l'istanza corrente di <xref:System.Data.Linq.DataContext>. In questo caso viene eseguita un'operazione `INSERT` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeUpdated`|Un oggetto che risulta modificato da quando è stato recuperato. In questo caso viene eseguita un'operazione `UPDATE` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeDeleted`|Un oggetto contrassegnato per l'eliminazione, che causa un'operazione `DELETE` in un database durante l'esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`Deleted`|Un oggetto eliminato nel database. Questo stato è finale e non consente transizioni aggiuntive.|

## <a name="inserting-objects"></a>Inserimento di oggetti

È possibile richiedere `Inserts` usando <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> in modo esplicito. In alternativa, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] può dedurre `Inserts` individuando gli oggetti connessi a uno degli oggetti noti che devono essere aggiornati. Se ad esempio si `Untracked` aggiunge un oggetto a un <xref:System.Data.Linq.EntitySet%601> oggetto o si imposta <xref:System.Data.Linq.EntityRef%601> un oggetto `Untracked` su un oggetto, l' `Untracked` oggetto viene reso raggiungibile tramite oggetti rilevati nel grafico. Durante l' <xref:System.Data.Linq.DataContext.SubmitChanges%2A>elaborazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , attraversa gli oggetti rilevati e individua tutti gli oggetti persistenti raggiungibili che non vengono rilevati. Tali oggetti sono candidati per l'inserimento nel database.

Per le classi in una gerarchia di <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>ereditarietà`o`, () imposta anche il valore del membro designato come discriminatore in modo che corrisponda al `o`tipo dell'oggetto. Qualora un tipo dovesse corrispondere al valore discriminante predefinito, questa azione causerà la sovrascrittura del valore discriminante con il valore predefinito. Per ulteriori informazioni, vedere [supporto](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)per l'ereditarietà.

> [!IMPORTANT]
> Un oggetto aggiunto a un oggetto `Table` non si trova nella cache delle identità, che riflette solo gli oggetti recuperati dal database. Dopo una chiamata a <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, l'entità aggiunta non viene visualizzata nelle query eseguite sul database finché non si completerà <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

## <a name="deleting-objects"></a>Eliminazione di oggetti

Per contrassegnare per l'eliminazione un oggetto `o` rilevato, chiamare <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>(o) sull'oggetto <xref:System.Data.Linq.Table%601> appropriato. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Considera la rimozione di un oggetto da un <xref:System.Data.Linq.EntitySet%601> oggetto come operazione di aggiornamento e il valore di chiave esterna corrispondente è impostato su null. La destinazione dell'operazione (`o`) non viene eliminata dalla relativa tabella. Ad esempio, `cust.Orders.DeleteOnSubmit(ord)` indica un aggiornamento in cui la relazione tra `cust` e `ord` viene interrotta mediante l'impostazione della chiave esterna `ord.CustomerID` su null. Non causa l'eliminazione della riga che corrisponde a `ord`.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]esegue l'elaborazione seguente quando un oggetto viene eliminato (<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>) dalla tabella:

- Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, per quell'oggetto viene eseguita un'operazione `DELETE`.

- La rimozione non viene propagata agli oggetti correlati, indipendentemente dallo stato di caricamento. In particolare, gli oggetti correlati non vengono caricati per aggiornare la proprietà della relazione.

- Dopo la corretta esecuzione di <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, gli oggetti vengono impostati sullo stato `Deleted`. Di conseguenza non sarà possibile usare l'oggetto o il relativo `id` in un'istanza di <xref:System.Data.Linq.DataContext>. La cache interna gestita da un'istanza di <xref:System.Data.Linq.DataContext> non elimina gli oggetti recuperati o aggiunti come nuovi, anche dopo che sono stati eliminati nel database.

È possibile chiamare <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> solo su un oggetto registrato da <xref:System.Data.Linq.DataContext>. Per un oggetto `Untracked` è necessario chiamare <xref:System.Data.Linq.Table%601.Attach%2A> prima di <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>. Chiamando <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> su un oggetto`Untracked`, verrà generata un'eccezione.

> [!NOTE]
> La rimozione di un oggetto da una [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tabella indica a di generare `DELETE` un comando SQL corrispondente al <xref:System.Data.Linq.DataContext.SubmitChanges%2A>momento della. Questa azione non rimuove l'oggetto dalla cache, né propaga l'eliminazione agli oggetti correlati.
>
> Per recuperare l'`id` di un oggetto eliminato, usare una nuova istanza di <xref:System.Data.Linq.DataContext>. Per la pulizia di oggetti correlati, è possibile utilizzare la funzionalità di *eliminazione a catena* del database, altrimenti eliminare manualmente gli oggetti correlati.
>
> Non è necessario, a differenza del database, eliminare gli oggetti correlati in un ordine particolare.

## <a name="updating-objects"></a>Aggiornamento di oggetti

È possibile rilevare l'esecuzione di `Updates` osservando le notifiche delle modifiche, che vengono fornite tramite l'evento <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> nei metodi per l'impostazione delle proprietà. Quando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] riceve una notifica della prima modifica a un oggetto, crea una copia dell'oggetto e lo considera candidato per la generazione di un'istruzione `Update`.

Per gli oggetti che non <xref:System.ComponentModel.INotifyPropertyChanging>implementano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , in viene mantenuta una copia dei valori utilizzati dagli oggetti quando sono stati materializzati per la prima volta. Quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Confronta i valori correnti e originali per decidere se l'oggetto è stato modificato.

Per gli aggiornamenti delle relazioni, il riferimento dal figlio al padre, ovvero il riferimento che corrisponde alla chiave esterna, viene considerato autorevole. Il riferimento nella direzione inversa, ovvero da padre a figlio, è facoltativo. Le classi di relazione (<xref:System.Data.Linq.EntitySet%601> e <xref:System.Data.Linq.EntityRef%601>) assicurano che i riferimenti bidirezionali siano coerenti per le relazioni uno-a-molti e uno-a-uno. Se il modello a oggetti non usa <xref:System.Data.Linq.EntitySet%601> o <xref:System.Data.Linq.EntityRef%601> e se è presente il riferimento inverso, sarà necessario mantenerlo coerente con il riferimento in avanti quando viene aggiornata la relazione.

Se si aggiornano sia il riferimento obbligatorio che la chiave esterna corrispondente, è necessario assicurarsi che corrispondano. Se non sono entrambi sincronizzati quando si chiama <xref:System.InvalidOperationException>, verrà generata un'eccezione <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Anche se le modifiche dei valori della chiave esterna sono sufficienti per interessare un aggiornamento della riga sottostante, è necessario modificare il riferimento per mantenere la connettività dell'oggetto grafico e la coerenza bidirezionale delle relazioni.

## <a name="see-also"></a>Vedere anche

- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)
