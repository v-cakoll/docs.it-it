---
title: 'Procedura: creare un partecipante di persistenza personalizzato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebc83f100b4303b73ba2e6d3dc41d0f82e8f2c22
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Procedura: creare un partecipante di persistenza personalizzato
Nella procedura riportata di seguito sono illustrati i passaggi per creare un partecipante di persistenza. Vedere il [che fanno parte di persistenza](http://go.microsoft.com/fwlink/?LinkID=177735) esempio e [archivio estendibilità](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) argomento per le implementazioni di esempio partecipanti di persistenza.  
  
1.  Creare una classe che deriva dalla classe <xref:System.Activities.Persistence.PersistenceParticipant> o <xref:System.Activities.Persistence.PersistenceIOParticipant>. Oltre alla possibilità di partecipare alle operazioni di IO, la classe PersistenceIOParticipant dispone degli stessi punti di estensibilità della classe PersistenceParticipant. Attenersi ad almeno uno dei passaggi seguenti.  
  
2.  Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. Il **CollectValues** metodo presenta due parametri di dizionario, uno per l'archiviazione dei valori di lettura/scrittura e l'altro per l'archiviazione dei valori di sola scrittura (usati di seguito nelle query). In tale metodo, è necessario popolare questi dizionari con i dati specifici di un partecipante di persistenza. Ogni dizionario contiene il nome del valore come chiave e il valore stesso come oggetto <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
     I valori del dizionario readWriteValues vengono impacchettati come **InstanceValue** oggetti. I valori nel dizionario di sola scrittura vengono impacchettati come **InstanceValue** oggetti con set InstanceValueOptions.Optional e Instancevalueoption. Ogni **InstanceValue** fornito dal **CollectValues** implementazioni in tutti i partecipanti di persistenza devono avere un nome univoco.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  Implementare il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. Il **MapValues** metodo accetta due parametri che sono simili ai parametri che il **CollectValues** metodo riceve. Tutti i valori raccolti nella **CollectValues** fase vengono passati tramite questi parametri di dizionario. I nuovi valori aggiunti per il **MapValues** fase vengono aggiunti ai valori di sola scrittura.  Il dizionario di sola scrittura viene usato per fornire dati a un'origine esterna non direttamente associata ai valori dell'istanza. Ogni valore fornito dalle implementazioni del **MapValues** metodo in tutti i partecipanti di persistenza deve avere un nome univoco.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Il metodo <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> fornisce la funzionalità che non è offerta da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, nel senso che consente di usare una dipendenza da un altro valore fornito da un altro partecipante di persistenza che non è stato ancora elaborato da <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4.  Implementare il **PublishValues** metodo. Il **PublishValues** metodo riceve un dizionario contenente tutti i valori caricati dall'archivio di persistenza.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  Implementare il **BeginOnSave** metodo se il partecipante è un partecipante di IO di persistenza. Questo metodo viene chiamato durante un'operazione di salvataggio. In questo metodo, è necessario eseguire l'aggiunta di IO alla persistenza delle istanze del flusso di lavoro (salvataggio).  Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current.  Inoltre, l'oggetto PersistenceIOParticipants può annunciare un requisito di coerenza transazionale e, in tal caso, l'host crea una transazione per l'episodio di persistenza, qualora non venisse altrimenti usata.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Implementare il **BeginOnLoad** metodo se il partecipante è un partecipante di IO di persistenza. Questo metodo viene chiamato durante un'operazione di caricamento. In questo metodo, è necessario eseguire l'aggiunta di IO al caricamento delle istanze del flusso di lavoro. Se l'host sta usando una transazione per il comando di persistenza corrispondente, la stessa transazione viene fornita in Transaction.Current. Inoltre, i partecipanti di IO di persistenza possono annunciare un requisito di coerenza transazionale e, in tal caso, l'host crea una transazione per l'episodio di persistenza, qualora non venisse altrimenti usata.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
