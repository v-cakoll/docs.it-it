---
title: 'Concorrenza ottimistica: Panoramica'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: 8f3bd35cc1391339d99d5aa0a4021e29fa81756c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767488"
---
# <a name="optimistic-concurrency-overview"></a>Concorrenza ottimistica: Panoramica
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è supportato il controllo della concorrenza ottimistica. Nella tabella seguente vengono descritti i termini applicabili alla concorrenza ottimistica in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione:  
  
|Termini|Descrizione|  
|-----------|-----------------|  
|concorrenza|Situazione in cui due o più utenti tentano contemporaneamente di aggiornare la stessa riga del database.|  
|conflitto di concorrenza|Situazione in cui due o più utenti tentano contemporaneamente di inviare valori in conflitto a una o più colonne di una riga.|  
|controllo della concorrenza|Tecnica usata per risolvere i conflitti di concorrenza.|  
|controllo di concorrenza ottimistica|Tecnica che consente di esaminare se i valori presenti in una riga in altre transazioni sono stati modificati prima di consentire l'invio di modifiche.<br /><br /> Si differenzia *controllo della concorrenza pessimistica*, che blocca il record per evitare conflitti di concorrenza.<br /><br /> *Ottimistica* controllo viene così definito perché considera la possibilità di una transazione interferisca con un'altra improbabile.|  
|risoluzione dei conflitti|Processo di aggiornamento di un elemento in conflitto mediante la riesecuzione di una query sul database e la risoluzione delle differenze.<br /><br /> Quando un oggetto viene aggiornato, la funzionalità di ricerca delle modifiche di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] conserva i dati seguenti:<br /><br /> -Controllare i valori originariamente eseguita dal database e usato per l'aggiornamento.<br />-I nuovi valori di database dalla query successiva.<br /><br /> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina quindi se l'oggetto è in conflitto, ovvero se uno o più valori del membro sono stati modificati. Se l'oggetto è in conflitto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] successivamente determina quale dei relativi membri sono in conflitto.<br /><br /> Qualsiasi conflitto fra membri individuato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene aggiunto a un elenco di conflitti.|  
  
 Nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti, un' *conflitto di concorrenza ottimistica* si verifica quando vengono soddisfatte entrambe le condizioni seguenti:  
  
- Il client tenta di inviare modifiche al database.  
  
- Uno o più valori di controllo degli aggiornamenti sono stati aggiornati nel database dall'ultima lettura effettuata dal client.  
  
 Per risolvere questo conflitto, è necessario individuare i membri dell'oggetto in conflitto, quindi decidere come procedere.  
  
> [!NOTE]
>  Solo i membri di cui è stato eseguito il mapping come <xref:System.Data.Linq.Mapping.UpdateCheck.Always> o <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> fanno parte dei controlli di concorrenza ottimistica. Per i membri contrassegnati come <xref:System.Data.Linq.Mapping.UpdateCheck.Never> non viene eseguito alcun controllo. Per altre informazioni, vedere <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## <a name="example"></a>Esempio  
 Nel seguente scenario, ad esempio, User1 prepara un aggiornamento mediante l'esecuzione di una query su una riga del database. User1 riceve una riga con i valori Alfreds, Maria e Sales.  
  
 User1 desidera modificare il valore della colonna Manager in Alfred e il valore della colonna Department in Marketing. Prima che User1 possa inviare le modifiche, User2 ha già inviato le proprie modifiche al database. Ora il valore della colonna Assistant è stato modificato in Mary e il valore della colonna Department è cambiato in Service.  
  
 Quando User1 tenta di inviare le modifiche, l'invio non viene completato e viene generata un'eccezione <xref:System.Data.Linq.ChangeConflictException>. Questo risultato si verifica perché i valori del database per le colonna Assistant e Department non sono quelli previsti. I membri che rappresentano le colonne Assistant e Department sono in conflitto. Nella tabella seguente è riepilogata questa situazione:  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Stato originale|Alfreds|Maria|Sales|  
|Utente1|Alfred||Marketing|  
|User2||Mary|Service|  
  
 È possibile risolvere questo tipo di conflitti in diversi modi. Per altre informazioni, vedere [Procedura: Gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## <a name="conflict-detection-and-resolution-checklist"></a>Elenco di controllo per il rilevamento e la risoluzione dei conflitti  
 È possibile rilevare e risolvere i conflitti a qualsiasi livello di dettaglio. Da una parte è possibile risolvere tutti i conflitti usando una delle tre modalità disponibili (vedere <xref:System.Data.Linq.RefreshMode>) senza ulteriori considerazioni. Dall'altra è possibile definire un'azione specifica per ogni tipo di conflitto e per ogni membro in conflitto.  
  
- Specificare o modificare le opzioni per <xref:System.Data.Linq.Mapping.UpdateCheck> nel modello a oggetti.  
  
     Per altre informazioni, vedere [Procedura: Specificare quali membri sono verificati conflitti di concorrenza](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
- Nel blocco try/catch della chiamata a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> specificare a che punto dovranno essere generate eccezioni.  
  
     Per altre informazioni, vedere [Procedura: Specificare le eccezioni di concorrenza quando vengono generate](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
- Determinare la quantità di dettagli sul conflitto da recuperare, quindi includere nel blocco try/catch il codice necessario.  
  
     Per altre informazioni, vedere [Procedura: Recuperare informazioni sui conflitti di entità](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md) e [come: Recuperare informazioni sui conflitti di concorrenza](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md).  
  
- Includere nelle `try` / `catch` codice come si desidera risolvere i diversi conflitti individuati.  
  
     Per altre informazioni, vedere [Procedura: Risolvere i conflitti mantenendo valori di Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md), [come: Risolvere i conflitti sovrascrivendo i valori del Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md), e [come: Risolvere i conflitti mediante l'unione con valori di Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md).  
  
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

- [Procedura: Gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
