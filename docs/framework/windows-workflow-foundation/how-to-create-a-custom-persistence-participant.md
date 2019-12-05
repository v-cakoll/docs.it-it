---
title: 'Procedura: creare un partecipante di persistenza personalizzato'
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 0e61395cb59a7d162668445d23241e3ff562d67b
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802544"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Procedura: creare un partecipante di persistenza personalizzato
Nella procedura riportata di seguito sono illustrati i passaggi per creare un partecipante di persistenza. Per le implementazioni di esempio dei partecipanti di persistenza, vedere l'argomento relativo all'esempio di [persistenza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100)) e [archiviazione](store-extensibility.md) .  
  
1. Creare una classe che deriva dalla classe <xref:System.Activities.Persistence.PersistenceParticipant> o <xref:System.Activities.Persistence.PersistenceIOParticipant>. La classe PersistenceIOParticipant offre gli stessi punti di estendibilità della classe PersistenceParticipant, oltre alla possibilità di partecipare alle operazioni di I/O. Attenersi ad almeno uno dei passaggi seguenti.  
  
2. Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. Il metodo **CollectValues** ha due parametri del dizionario, uno per l'archiviazione di valori di lettura/scrittura e l'altro per l'archiviazione di valori di sola scrittura (usati più avanti nelle query). In tale metodo, è necessario popolare questi dizionari con i dati specifici di un partecipante di persistenza. Ogni dizionario contiene il nome del valore come chiave e il valore stesso come oggetto <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
    I valori nel dizionario readWriteValues sono inclusi nel pacchetto come oggetti **InstanceValue** . I valori nel dizionario di sola scrittura vengono inclusi nel pacchetto come oggetti **InstanceValue** con InstanceValueOptions. optional e InstanceValueOption. WriteOnly impostati. Ogni **InstanceValue** fornito dalle implementazioni di **CollectValues** in tutti i partecipanti di persistenza deve avere un nome univoco.
  
    ```csharp  
    protected virtual void CollectValues(out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
3. Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. Il metodo **MapValues** accetta due parametri simili ai parametri ricevuti dal metodo **CollectValues** . Tutti i valori raccolti nella fase **CollectValues** vengono passati attraverso questi parametri del dizionario. I nuovi valori aggiunti dalla fase **MapValues** vengono aggiunti ai valori di sola scrittura.  Il dizionario di sola scrittura viene usato per fornire dati a un'origine esterna non direttamente associata ai valori dell'istanza. Ogni valore fornito dalle implementazioni del metodo **MapValues** in tutti i partecipanti di persistenza deve avere un nome univoco.  
  
    ```csharp  
    protected virtual IDictionary<XName,Object> MapValues(IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
     Il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> fornisce la funzionalità che non è offerta da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, nel senso che consente di usare una dipendenza da un altro valore fornito da un altro partecipante di persistenza che non è stato ancora elaborato da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4. Implementare il metodo **PublishValues** . Il metodo **PublishValues** riceve un dizionario contenente tutti i valori caricati dall'archivio di persistenza.  
  
    ```csharp  
    protected virtual void PublishValues(IDictionary<XName,Object> readWriteValues)
    {
    }
    ```  
  
5. Implementare il metodo **BeginOnSave** se il partecipante è un partecipante di i/O di persistenza. Questo metodo viene chiamato durante un'operazione di salvataggio. In questo metodo, è necessario eseguire l'aggiunta di I/O alle istanze del flusso di lavoro di salvataggio permanente.  Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current.  Inoltre, l'oggetto PersistenceIOParticipants può annunciare un requisito di coerenza transazionale e, in tal caso, l'host crea una transazione per l'episodio di persistenza, qualora non venisse altrimenti usata.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnSave(IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```  
  
6. Implementare il metodo **BeginOnLoad** se il partecipante è un partecipante di i/O di persistenza. Questo metodo viene chiamato durante un'operazione di caricamento. In questo metodo, è necessario eseguire l'aggiunta di I/O al caricamento delle istanze del flusso di lavoro. Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current. Inoltre, i partecipanti di I/O di persistenza possono annunciare un requisito di coerenza transazionale, nel qual caso l'host crea una transazione per l'episodio di persistenza, se non ne verrebbe altrimenti usato uno.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnLoad(IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```
