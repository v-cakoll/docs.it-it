---
title: 'Concorrenza ottimistica: Panoramica'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: a61d4c5b35f3797539fe845045b8a959b0351350
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938622"
---
# <a name="optimistic-concurrency-overview"></a>Concorrenza ottimistica: Panoramica
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è supportato il controllo della concorrenza ottimistica. Nella tabella seguente vengono descritte le condizioni che si applicano alla concorrenza [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ottimistica nella documentazione di:  
  
|Termini|Descrizione|  
|-----------|-----------------|  
|concurrency|Situazione in cui due o più utenti tentano contemporaneamente di aggiornare la stessa riga del database.|  
|conflitto di concorrenza|Situazione in cui due o più utenti tentano contemporaneamente di inviare valori in conflitto a una o più colonne di una riga.|  
|controllo della concorrenza|Tecnica usata per risolvere i conflitti di concorrenza.|  
|controllo di concorrenza ottimistica|Tecnica che consente di esaminare se i valori presenti in una riga in altre transazioni sono stati modificati prima di consentire l'invio di modifiche.<br /><br /> Si differenzia dal *controllo della concorrenza pessimistica*, che blocca il record per evitare conflitti di concorrenza.<br /><br /> Il controllo ottimistico è così definito poiché considera improbabile che una transazione interferisca con un'altra.|  
|risoluzione dei conflitti|Processo di aggiornamento di un elemento in conflitto mediante la riesecuzione di una query sul database e la risoluzione delle differenze.<br /><br /> Quando un oggetto viene aggiornato, la funzionalità di ricerca delle modifiche di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] conserva i dati seguenti:<br /><br /> : I valori originariamente ricavati dal database e usati per il controllo degli aggiornamenti.<br />-I nuovi valori del database della query successiva.<br /><br /> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina quindi se l'oggetto è in conflitto, ovvero se uno o più valori del membro sono stati modificati. Se l'oggetto è in conflitto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina quindi quale dei suoi membri sono in conflitto.<br /><br /> Qualsiasi conflitto fra membri individuato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene aggiunto a un elenco di conflitti.|  
  
 Nel modello a oggetti,siverificaunconflittodiconcorrenzaottimisticaquandosonosoddisfatteentrambelecondizioni[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] seguenti:  
  
- Il client tenta di inviare modifiche al database.  
  
- Uno o più valori di controllo degli aggiornamenti sono stati aggiornati nel database dall'ultima lettura effettuata dal client.  
  
 Per risolvere questo conflitto, è necessario individuare i membri dell'oggetto in conflitto, quindi decidere come procedere.  
  
> [!NOTE]
> Solo i membri di cui è stato eseguito il mapping come <xref:System.Data.Linq.Mapping.UpdateCheck.Always> o <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> fanno parte dei controlli di concorrenza ottimistica. Per i membri contrassegnati come <xref:System.Data.Linq.Mapping.UpdateCheck.Never> non viene eseguito alcun controllo. Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## <a name="example"></a>Esempio  
 Nel seguente scenario, ad esempio, User1 prepara un aggiornamento mediante l'esecuzione di una query su una riga del database. User1 riceve una riga con i valori Alfreds, Maria e Sales.  
  
 User1 desidera modificare il valore della colonna Manager in Alfred e il valore della colonna Department in Marketing. Prima che User1 possa inviare le modifiche, User2 ha già inviato le proprie modifiche al database. Ora il valore della colonna Assistant è stato modificato in Mary e il valore della colonna Department è cambiato in Service.  
  
 Quando User1 tenta di inviare le modifiche, l'invio non viene completato e viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException>. Questo risultato si verifica perché i valori del database per le colonna Assistant e Department non sono quelli previsti. I membri che rappresentano le colonne Assistant e Department sono in conflitto. Nella tabella seguente è riepilogata questa situazione:  
  
||Manager|Assistant|department|  
|------|-------------|---------------|----------------|  
|Stato originale|Alfreds|Maria|Sales|  
|Utente1|Alfred||Marketing|  
|User2||Mary|Service|  
  
 È possibile risolvere questo tipo di conflitti in diversi modi. Per altre informazioni, vedere [Procedura: Gestire i conflitti](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)di modifica.  
  
## <a name="conflict-detection-and-resolution-checklist"></a>Elenco di controllo per il rilevamento e la risoluzione dei conflitti  
 È possibile rilevare e risolvere i conflitti a qualsiasi livello di dettaglio. Da una parte è possibile risolvere tutti i conflitti usando una delle tre modalità disponibili (vedere <xref:System.Data.Linq.RefreshMode>) senza ulteriori considerazioni. Dall'altra è possibile definire un'azione specifica per ogni tipo di conflitto e per ogni membro in conflitto.  
  
- Specificare o modificare le opzioni per <xref:System.Data.Linq.Mapping.UpdateCheck> nel modello a oggetti.  
  
     Per altre informazioni, vedere [Procedura: Specificare i membri sottoposti a test per i](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)conflitti di concorrenza.  
  
- Nel blocco try/catch della chiamata a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> specificare a che punto dovranno essere generate eccezioni.  
  
     Per altre informazioni, vedere [Procedura: Consente di specificare quando vengono generate](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)eccezioni di concorrenza.  
  
- Determinare la quantità di dettagli sul conflitto da recuperare, quindi includere nel blocco try/catch il codice necessario.  
  
     Per altre informazioni, vedere [Procedura: Recuperare informazioni sui](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md) conflitti di [entità e procedura: Recuperare le informazioni sui](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)conflitti dei membri.  
  
- Includere nel `try` / codice comesidesiderarisolvereidiversiconflittiindividuati.`catch`  
  
     Per altre informazioni, vedere [Procedura: Risolvere i conflitti mantenendo i valori](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)del database, [procedura: Risolvere i conflitti sovrascrivendo i](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)valori del [database e procedura: Risolvere i conflitti mediante l'Unione con](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)i valori del database.  
  
## <a name="linq-to-sql-types-that-support-conflict-discovery-and-resolution"></a>Tipi LINQ to SQL che supportano l'individuazione e la risoluzione dei conflitti  
 Di seguito sono elencate le classi e le funzionalità di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] che supportano la risoluzione di conflitti nella concorrenza ottimistica:  
  
- <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.MemberChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictException?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.RefreshMode?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
