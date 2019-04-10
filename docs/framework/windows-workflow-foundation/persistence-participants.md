---
title: Partecipanti di persistenza
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: 18614962708eafa192d8163638fce2b8154d6106
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316362"
---
# <a name="persistence-participants"></a>Partecipanti di persistenza
Un partecipante di persistenza può far parte di un'operazione di persistenza (Save o Load) attivata da un'applicazione host. Il [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] viene fornito con due classi astratte **PersistenceParticipant** e **PersistenceIOParticipant**, che è possibile usare per creare un partecipante di persistenza. Un partecipante di persistenza deriva da una di queste classi, implementa i metodi di interesse, quindi aggiunge un'istanza della classe alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> nell'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>. L'applicazione host può cercare tali estensioni del flusso di lavoro quando rende persistente un'istanza del flusso di lavoro e richiamare metodi appropriati sui partecipanti di persistenza in momenti appropriati.  
  
 Nell'elenco seguente vengono descritte le attività eseguite dal sottosistema di persistenza in fasi diverse dell'operazione Persist (Save). I partecipanti di persistenza vengono usati nella terza e quarta fase. Se il partecipante è un partecipante dei / o (un partecipante di persistenza che fa parte anche nelle operazioni dei / o), il partecipante viene usato anche nella sesta fase.  
  
1. Raccoglie i valori predefiniti, inclusi lo stato del flusso di lavoro, i segnalibri, le variabili mappate e il timestamp.  
  
2. Raccoglie tutti i partecipanti di persistenza aggiunti alla raccolta di estensioni associata all'istanza del flusso di lavoro.  
  
3. Richiama il metodo <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> implementato da tutti i partecipanti di persistenza.  
  
4. Richiama il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> implementato da tutti i partecipanti di persistenza.  
  
5. Rende persistente o salva il flusso di lavoro nell'archivio di persistenza.  
  
6. Richiama il <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> metodo su tutti i partecipanti di persistenza i/o. Se il partecipante non è un partecipante dei / o, questa attività viene ignorata. Se l'episodio di persistenza è transazionale, la transazione viene fornita nella proprietà Transaction.Current.  
  
7. Attende il completamento di tutti i partecipanti di persistenza. Se tutti i partecipanti riescono a rendere persistenti i dati dell'istanza, esegue il commit della transazione.  
  
 Un partecipante di persistenza deriva dal **PersistenceParticipant** classe e può implementare il **CollectValues** e **MapValues** metodi. Un partecipante di persistenza i/o deriva dal **PersistenceIOParticipant** classe e può implementare il **BeginOnSave** metodo oltre all'implementazione di **CollectValues**e **MapValues** metodi.  
  
 Ogni fase viene completata prima dell'inizio della fase successiva. Ad esempio, i valori vengono raccolti dal **tutti** partecipanti di persistenza nella prima fase. Quindi tutti i valori raccolti nella prima fase vengono forniti a tutti i partecipanti di persistenza nella seconda fase per il mapping. Successivamente tutti i valori raccolti e mappati nella prima e seconda fase vengono forniti al provider di persistenza nella terza fase e così via.  
  
 Nell'elenco seguente vengono descritte le attività eseguite dal sottosistema di persistenza in fasi diverse dell'operazione Load. I partecipanti di persistenza vengono usati nella quarta fase. I partecipanti dei / o di persistenza (partecipanti di persistenza che fanno parte anche nelle operazioni dei / o) vengono inoltre usati nella terza fase.  
  
1. Raccoglie tutti i partecipanti di persistenza aggiunti alla raccolta di estensioni associata all'istanza del flusso di lavoro.  
  
2. Carica il flusso di lavoro dall'archivio di persistenza.  
  
3. Richiama il <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> su tutti i partecipanti di persistenza i/o e attende che tutti i partecipanti di persistenza per il completamento. Se l'episodio di persistenza è transazionale, la transazione viene fornita nell'oggetto Transaction.Current.  
  
4. Carica l'istanza del flusso di lavoro in memoria in base ai dati recuperati dall'archivio di persistenza.  
  
5. Richiama il metodo <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> su ogni partecipante di persistenza.  
  
 Un partecipante di persistenza deriva dal **PersistenceParticipant** classe e può implementare il **PublishValues** (metodo). Un partecipante di persistenza i/o deriva dal **PersistenceIOParticipant** classe e può implementare il **BeginOnLoad** metodo oltre all'implementazione di **PublishValues**metodo.  
  
 Quando si carica un'istanza del flusso di lavoro, il provider di persistenza crea un blocco su tale istanza. In questo modo l'istanza non può essere caricata da più di un host in uno scenario che presenta molteplici nodi. Se si tenta di caricare un'istanza del flusso di lavoro è stata bloccata è verrà restituita un'eccezione simile alla seguente: L'eccezione "InstanceLockException: Non è riuscito a completare l'operazione richiesta perché il blocco, ad esempio ' 00000000-0000-0000-0000-000000000000' non è stato possibile acquisire ". Generalmente questo errore si verifica in presenza di una delle seguenti condizioni:  
  
-   In uno scenario a molteplici nodi l'istanza viene caricata da un altro host.  Esistono alcuni modi per risolvere questi tipi di conflitti: inoltrare l'elaborazione al nodo proprietario del blocco e tentare o forzare il caricamento, che impedirà all'altro host di salvare il lavoro.  
  
-   In uno scenario a nodo singolo l'host si è arrestato in modo anomalo.  Quando un host viene riavviato (riciclo di un processo o creando una nuova factory del provider di persistenza), il nuovo host tenta di caricare un'istanza che però è ancora bloccata dall'host precedente poiché il blocco non è ancora scaduto.  
  
-   In uno scenario a nodo singolo, l'istanza in questione è stata interrotta a un certo punto e viene creata una nuova istanza del provider di persistenza con un ID host differente.  
  
 Il valore di timeout del blocco predefinito è 5 minuti; è possibile specificare un valore di timeout diverso quando viene chiamato il metodo <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.  
  
## <a name="in-this-section"></a>In questa sezione  
  
-   [Procedura: Creare un partecipante di persistenza personalizzato](how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Vedere anche

- [Estensibilità dell'archivio](store-extensibility.md)
