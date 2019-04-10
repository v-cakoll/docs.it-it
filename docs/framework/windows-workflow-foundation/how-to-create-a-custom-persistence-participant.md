---
title: 'Procedura: Creare un partecipante di persistenza personalizzato'
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 1de2abb8ababd794cd644733b6e4ab0ed42b1810
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321458"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Procedura: Creare un partecipante di persistenza personalizzato
Nella procedura riportata di seguito sono illustrati i passaggi per creare un partecipante di persistenza. Vedere le [che fanno parte di persistenza](https://go.microsoft.com/fwlink/?LinkID=177735) campione e [Store estendibilità](store-extensibility.md) argomento per le implementazioni di esempio dei partecipanti di persistenza.  
  
1. Creare una classe che deriva dalla classe <xref:System.Activities.Persistence.PersistenceParticipant> o <xref:System.Activities.Persistence.PersistenceIOParticipant>. La classe PersistenceIOParticipant offre gli stessi punti di estendibilità della classe PersistenceParticipant oltre a poter partecipare alle operazioni dei / o. Attenersi ad almeno uno dei passaggi seguenti.  
  
2. Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. Il **CollectValues** metodo ha due parametri di dizionario, uno per l'archiviazione dei valori di lettura/scrittura e l'altro per l'archiviazione dei valori di sola scrittura (usati in un secondo momento nella query). In tale metodo, è necessario popolare questi dizionari con i dati specifici di un partecipante di persistenza. Ogni dizionario contiene il nome del valore come chiave e il valore stesso come oggetto <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
     I valori del dizionario readWriteValues vengono impacchettati come **InstanceValue** oggetti. I valori nel dizionario di sola scrittura vengono impacchettati come **InstanceValue** oggetti con set InstanceValueOptions.Optional e Instancevalueoption. Ciascuna **InstanceValue** forniti dalle **CollectValues** implementazioni in tutti i partecipanti di persistenza devono avere un nome univoco.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3. Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. Il **MapValues** metodo accetta due parametri che sono simili ai parametri che le **CollectValues** metodo riceve. Tutti i valori raccolti nella **CollectValues** fase vengono passati tramite questi parametri di dizionario. I nuovi valori aggiunti per il **MapValues** fase vengono aggiunti ai valori di sola scrittura.  Il dizionario di sola scrittura viene usato per fornire dati a un'origine esterna non direttamente associata ai valori dell'istanza. Ogni valore fornito dalle implementazioni del **MapValues** metodo in tutti i partecipanti di persistenza deve avere un nome univoco.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> fornisce la funzionalità che non è offerta da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, nel senso che consente di usare una dipendenza da un altro valore fornito da un altro partecipante di persistenza che non è stato ancora elaborato da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4. Implementare il **PublishValues** (metodo). Il **PublishValues** metodo riceve un dizionario contenente tutti i valori caricati dall'archivio di persistenza.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5. Implementare il **BeginOnSave** metodo se il partecipante è un partecipante di persistenza i/o. Questo metodo viene chiamato durante un'operazione di salvataggio. In questo metodo, è consigliabile eseguire complemento dei / o di mantenere (le istanze del flusso di lavoro salvataggio).  Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current.  Inoltre, l'oggetto PersistenceIOParticipants può annunciare un requisito di coerenza transazionale e, in tal caso, l'host crea una transazione per l'episodio di persistenza, qualora non venisse altrimenti usata.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6. Implementare il **BeginOnLoad** metodo se il partecipante è un partecipante di persistenza i/o. Questo metodo viene chiamato durante un'operazione di caricamento. In questo metodo, è consigliabile eseguire complemento dei / o il caricamento delle istanze del flusso di lavoro. Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current. Inoltre, i partecipanti di persistenza dei / o possono annunciare un requisito di coerenza delle transazioni, in tal caso l'host crea una transazione per l'episodio di persistenza se sarebbe non in caso contrario, è possibile utilizzare.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
