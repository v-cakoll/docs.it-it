---
title: Passaggi tipici per l'utilizzo di LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3aedef610d8ad3f743b346a46059b15d917cf7ca
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Passaggi tipici per l'utilizzo di LINQ to SQL
Per implementare un'applicazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], attenersi ai passaggi descritti in questo argomento. Molti passaggi sono tuttavia facoltativi ed è molto probabile che si possa usare il modello a oggetti nello stato predefinito.  
  
 Per iniziare velocemente, usare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare il modello a oggetti e avviare la codifica delle query.  
  
## <a name="creating-the-object-model"></a>Creazione del modello a oggetti  
 Il primo passaggio consiste nel creare un modello a oggetti basato sui metadati di un database relazionale esistente. Il modello a oggetti rappresenta il database secondo il linguaggio di programmazione dello sviluppatore. Per ulteriori informazioni, vedere [LINQ al modello a oggetti SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Selezionare uno strumento per creare il modello.  
 Per la creazione del modello sono disponibili tre strumenti.  
  
-   Il tipo [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]  
  
     Questa finestra di progettazione offre un'interfaccia utente avanzata per la creazione di un modello a oggetti da un database esistente. Questo strumento fa parte dell'IDE di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] ed è più adatto per i database di piccole o medie dimensioni.  
  
-   Strumento per la generazione del codice SQLMetal  
  
     Questa utilità della riga di comando offre un set di opzioni leggermente diverso rispetto a [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Questo strumento è più adatto per la modellazione di database di grandi dimensioni. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
-   Editor di codice  
  
     È possibile scrivere codice personalizzato usando l'editor di codice [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] o un altro editor. Si sconsiglia di usare questo approccio, che può essere soggetto a errori, se si dispone già di un database ed è possibile usare [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] o lo strumento SQLMetal. L'editor di codice può tuttavia essere utile per perfezionare o modificare il codice già generato usando altri strumenti. Per ulteriori informazioni, vedere [procedura: personalizzare classi di entità utilizzando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Selezionare il tipo di codice che si desidera generare.  
  
-   File di codice sorgente C# o [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] per il mapping basato sugli attributi.  
  
     Questo file di codice verrà quindi incluso nel progetto [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]. Per ulteriori informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   File XML per il mapping esterno.  
  
     Usando questo approccio è possibile evitare di includere i metadati di mapping nel codice dell'applicazione. Per ulteriori informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    >  [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] non supporta la generazione di file di mapping esterni. Per implementare questa funzionalità è necessario usare lo strumento SQLMetal.  
  
-   File DBML che potrà essere modificato prima di generare un file di codice finale.  
  
     Si tratta di una funzionalità avanzata.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Perfezionare il file di codice in modo che rifletta le esigenze dell'applicazione.  
 A questo scopo, è possibile usare [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] o l'editor di codice.  
  
## <a name="using-the-object-model"></a>Uso del modello a oggetti  
 Nell'immagine seguente viene illustrata la relazione tra lo sviluppatore e i dati in un scenario a due livelli. Per altri scenari, vedere [a più livelli e applicazioni Remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Dopo avere creato il modello a oggetti, si procederà alla descrizione delle richieste di informazioni e alla modifica dei dati all'interno del modello. Il modello a oggetti deve essere considerato in termini di oggetti e proprietà e non di righe e colonne del database. Infatti, non si gestisce direttamente il database.  
  
 Quando si indica [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di eseguire una query che è stata fornita una descrizione o una chiamata `SubmitChanges()` sui dati modificati, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comunica con il database nella lingua del database.  
  
 Di seguito sono riportati i passaggi comuni per l'uso del modello a oggetti creato.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Creare query per recuperare informazioni dal database.  
 Per ulteriori informazioni, vedere [concetti relativi alle Query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) e [esempi di Query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Eseguire l'override dei comportamenti predefiniti per le operazioni Insert, Update e Delete.  
 Questo passaggio è facoltativo. Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Impostare le opzioni appropriate per rilevare e segnalare i conflitti di concorrenza.  
 Per gestire i conflitti di concorrenza, è possibile mantenere i valori predefiniti del modello oppure modificarli in base agli scopi del progetto. Per ulteriori informazioni, vedere [procedura: specificare che i membri vengono verificati i conflitti di concorrenza](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) e [procedura: specificare quando le eccezioni di concorrenza vengono generate](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Definire una gerarchia di ereditarietà  
 Questo passaggio è facoltativo. Per ulteriori informazioni, vedere [supporto dell'ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Fornire un'interfaccia utente adatta.  
 Questo passaggio è facoltativo e dipende dalla modalità di uso dell'applicazione.  
  
### <a name="6-debug-and-test-your-application"></a>6. Eseguire il debug e il test dell'applicazione.  
 Per ulteriori informazioni, vedere [supporto per il debug](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
