---
title: Passaggi tipici per l'utilizzo di LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: c7964c821a838e027302cddce704d86cc6a34f66
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792336"
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Passaggi tipici per l'utilizzo di LINQ to SQL
Per implementare un'applicazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], attenersi ai passaggi descritti in questo argomento. Molti passaggi sono tuttavia facoltativi ed è molto probabile che si possa usare il modello a oggetti nello stato predefinito.  
  
 Per iniziare rapidamente, utilizzare il Object Relational Designer per creare il modello a oggetti e avviare la codifica delle query.  
  
## <a name="creating-the-object-model"></a>Creazione del modello a oggetti  
 Il primo passaggio consiste nel creare un modello a oggetti basato sui metadati di un database relazionale esistente. Il modello a oggetti rappresenta il database secondo il linguaggio di programmazione dello sviluppatore. Per ulteriori informazioni, vedere [il modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Selezionare uno strumento per creare il modello.  
 Per la creazione del modello sono disponibili tre strumenti.  
  
- Object Relational Designer  
  
     Questa finestra di progettazione offre un'interfaccia utente avanzata per la creazione di un modello a oggetti da un database esistente. Questo strumento fa parte dell'IDE di Visual Studio ed è più adatto ai database di piccole o medie dimensioni.  
  
- Strumento per la generazione del codice SQLMetal  
  
     Questa utilità della riga di comando fornisce un set di opzioni leggermente diverso da O/R Designer. Questo strumento è più adatto per la modellazione di database di grandi dimensioni. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
- Editor di codice  
  
     È possibile scrivere il proprio codice usando l'editor di codice di Visual Studio o un altro editor. Questo approccio non è consigliato, che può essere soggetto a errori, quando si dispone di un database esistente e può utilizzare o/R Designer o lo strumento SQLMetal. L'editor di codice può tuttavia essere utile per perfezionare o modificare il codice già generato usando altri strumenti. Per altre informazioni, vedere [Procedura: Personalizzare le classi di entità tramite l'editor](how-to-customize-entity-classes-by-using-the-code-editor.md)di codice.  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Selezionare il tipo di codice che si desidera generare.  
  
- Oggetto C# o Visual Basic file di codice sorgente per il mapping basato su attributi.  
  
     Il file di codice verrà quindi incluso nel progetto di Visual Studio. Per altre informazioni, vedere [mapping basato su attributi](attribute-based-mapping.md).  
  
- File XML per il mapping esterno.  
  
     Usando questo approccio è possibile evitare di includere i metadati di mapping nel codice dell'applicazione. Per ulteriori informazioni, vedere [mapping esterno](external-mapping.md).  
  
    > [!NOTE]
    > La finestra di progettazione di O/R non supporta la generazione di file di mapping esterni. Per implementare questa funzionalità è necessario usare lo strumento SQLMetal.  
  
- File DBML che potrà essere modificato prima di generare un file di codice finale.  
  
     Si tratta di una funzionalità avanzata.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Perfezionare il file di codice in modo che rifletta le esigenze dell'applicazione.  
 A questo scopo, è possibile usare o/R Designer o l'editor di codice.  
  
## <a name="using-the-object-model"></a>Uso del modello a oggetti  
 Nell'immagine seguente viene illustrata la relazione tra lo sviluppatore e i dati in un scenario a due livelli. Per altri scenari, vedere [applicazioni a più livelli e remote con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![Screenshot che mostra il modello a oggetti LINQ.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 Dopo avere creato il modello a oggetti, si procederà alla descrizione delle richieste di informazioni e alla modifica dei dati all'interno del modello. Il modello a oggetti deve essere considerato in termini di oggetti e proprietà e non di righe e colonne del database. Infatti, non si gestisce direttamente il database.  
  
 Quando si indica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a di eseguire una query descritta dall'utente o di chiamare `SubmitChanges()` i dati che sono stati modificati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comunica con il database nella lingua del database.  
  
 Di seguito sono riportati i passaggi comuni per l'uso del modello a oggetti creato.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Creare query per recuperare informazioni dal database.  
 Per altre informazioni, vedere [concetti relativi a query](query-concepts.md) ed [esempi di query](query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Eseguire l'override dei comportamenti predefiniti per le operazioni Insert, Update e Delete.  
 Questo passaggio è facoltativo. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Impostare le opzioni appropriate per rilevare e segnalare i conflitti di concorrenza.  
 Per gestire i conflitti di concorrenza, è possibile mantenere i valori predefiniti del modello oppure modificarli in base agli scopi del progetto. Per altre informazioni, vedere [Procedura: Specificare i membri sottoposti a test per i](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) conflitti [di concorrenza e procedura: Consente di specificare quando vengono generate](how-to-specify-when-concurrency-exceptions-are-thrown.md)eccezioni di concorrenza.  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Definire una gerarchia di ereditarietà  
 Questo passaggio è facoltativo. Per ulteriori informazioni, vedere [supporto](inheritance-support.md)per l'ereditarietà.  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Fornire un'interfaccia utente adatta.  
 Questo passaggio è facoltativo e dipende dalla modalità di uso dell'applicazione.  
  
### <a name="6-debug-and-test-your-application"></a>6. Eseguire il debug e il test dell'applicazione.  
 Per ulteriori informazioni, vedere [supporto](debugging-support.md)per il debug.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](getting-started.md)
- [Creazione del modello a oggetti](creating-the-object-model.md)
- [stored procedure](stored-procedures.md)
