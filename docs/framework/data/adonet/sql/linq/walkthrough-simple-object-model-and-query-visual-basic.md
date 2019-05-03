---
title: 'Procedura dettagliata: Modello a oggetti e query semplici (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: 326caf550e8b138b4b968f0021a7fc475dc58c8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037011"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a>Procedura dettagliata: Modello a oggetti e query semplici (Visual Basic)
In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base con minime complessità. Verranno create una classe di entità per la modellazione della tabella Customers nel database Northwind di esempio, quindi una semplice query per elencare i clienti residenti nell'area londinese.  
  
 Questa procedura dettagliata è basata sul codice in fase di progettazione per illustrare i concetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Normalmente per creare il modello a oggetti si usa [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.  
  
## <a name="prerequisites"></a>Prerequisiti  
  
- Per i file usati nella procedura dettagliata viene usata una cartella dedicata ("c:\linqtest"). Creare la cartella prima di avviare la procedura.  
  
- Per questa procedura dettagliata è richiesto il database di esempio Northwind. Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file nella cartella c:\linqtest.  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da sei attività principali:  
  
- Creazione di un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.  
  
- Mapping di una classe a una tabella del database.  
  
- Definizione di proprietà nella classe per rappresentare colonne del database.  
  
- Definizione della connessione al database Northwind.  
  
- Creazione di una semplice query da eseguire sul database.  
  
- Esecuzione della query e analisi dei risultati.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL  
 In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL  
  
1. Scegliere **Nuovo progetto** dal menu **File**.  
  
2. Nel **tipi di progetto** riquadro della finestra di **nuovo progetto** nella finestra di dialogo fare clic su **Visual Basic**.  
  
3. Nel riquadro **Modelli** fare clic su **Applicazione console**.  
  
4. Nel **Name** , digitare **LinqConsoleApp**.  
  
5. Fare clic su **OK**.  
  
## <a name="adding-linq-references-and-directives"></a>Aggiunta di riferimenti e direttive LINQ  
 In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto. Se `System.Data.Linq` non è elencato come riferimento nel progetto (fare clic su **Mostra tutti i file** nelle **Esplora soluzioni** ed espandere la **riferimenti** nodo), aggiungerlo come spiegato nella la procedura seguente.  
  
#### <a name="to-add-systemdatalinq"></a>Per aggiungere System.Data.Linq  
  
1. Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.  
  
2. Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.  
  
     L'assembly verrà aggiunto al progetto.  
  
3. Anche nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, scorrere fino alla e fare clic su Forms e quindi fare clic su **OK**.  
  
     Questo assembly, che supporta la finestra di messaggio nella procedura dettagliata, viene aggiunto al progetto.  
  
4. Aggiungere la seguente direttiva sopra a `Module1`:  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a>Mapping di una classe a una tabella del database  
 In questo passaggio verrà creata una classe ed eseguito il mapping della classe a una tabella di database. Tale classe è detta un' *classe di entità*. Notare che il mapping viene eseguito semplicemente aggiungendo l'attributo <xref:System.Data.Linq.Mapping.TableAttribute>. La proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> consente di specificare il nome della tabella nel database.  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a>Per creare una classe di entità ed eseguire il mapping della classe a una tabella di database  
  
- Digitare o incollare il codice seguente in Module1.vb immediatamente sopra `Sub Main`:  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a>Definizione di proprietà nella classe per rappresentare colonne del database  
 In questo passaggio si completeranno diverse attività.  
  
- Usare l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> per definire le proprietà `CustomerID` e `City` nella classe di entità in modo che rappresentino colonne nella tabella del database.  
  
- Definire la proprietà `CustomerID` in modo che rappresenti una colonna di chiave primaria nel database.  
  
- Definire i campi `_CustomerID` e `_City` per l'archiviazione privata. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sarà quindi in grado di archiviare e recuperare direttamente i valori, anziché usare funzioni di accesso pubbliche che potrebbero includere la logica di business.  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a>Per rappresentare caratteristiche di due colonne del database  
  
- Digitare o incollare il codice seguente in Module1.vb subito prima di `End Class`:  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a>Definizione della connessione al database Northwind  
 In questo passaggio viene usato un oggetto <xref:System.Data.Linq.DataContext> per stabilire una connessione tra le strutture di dati basate sul codice e il database stesso. <xref:System.Data.Linq.DataContext> è il canale principale tramite il quale vengono recuperati oggetti dal database e vengono inviate modifiche.  
  
 Viene inoltre dichiarato un oggetto `Table(Of Customer)` che fungerà da tabella tipizzata logica per le query sulla tabella Customers nel database. Tali query verranno quindi create ed eseguite nei passaggi successivi.  
  
#### <a name="to-specify-the-database-connection"></a>Per specificare la connessione al database  
  
- Digitare o incollare il codice seguente nel metodo `Sub Main`:  
  
     Si presuppone che il file `northwnd.mdf` si trovi nella cartella linqtest. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## <a name="creating-a-simple-query"></a>Creazione di una query semplice  
 In questo passaggio viene creata una query per cercare i clienti nella tabella di database Customers residenti nell'area londinese. Il codice della query in questo passaggio descrive semplicemente la query, ma non la esegue. Questo approccio è noto come *un'esecuzione posticipata*. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Verrà anche prodotto un output del log per mostrare i comandi SQL generati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Questa funzionalità di registrazione, che usa <xref:System.Data.Linq.DataContext.Log%2A>, è utile per eseguire il debug e per determinare che i comandi inviati al database rappresentano accuratamente la query.  
  
#### <a name="to-create-a-simple-query"></a>Per creare una query semplice  
  
- Digitare o incollare il codice seguente nel metodo `Sub Main` dopo la dichiarazione `Table(Of Customer)`:  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## <a name="executing-the-query"></a>Esecuzione della query  
 In questo passaggio verrà effettivamente eseguita la query. Le espressioni di query create nei passaggi precedenti non vengono valutate finché i risultati non saranno necessari. Quando si inizia l'iterazione `For Each`, viene eseguito un comando SQL sul database e gli oggetti vengono materializzati.  
  
#### <a name="to-execute-the-query"></a>Per eseguire la query  
  
1. Digitare o incollare il codice seguente alla fine del metodo `Sub Main` dopo la descrizione della query:  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2. ‎Premere F5 per eseguire il debug dell'applicazione.  
  
    > [!NOTE]
    >  Se l'applicazione genera un errore di run-time, vedere la sezione Risoluzione dei problemi dei [apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
     Nella finestra di messaggio viene visualizzato un elenco di sei clienti. Nella finestra della console verrà visualizzato il codice SQL generato.  
  
3. Fare clic su **OK** per chiudere la finestra del messaggio.  
  
     L'applicazione verrà chiusa.  
  
4. Nel menu **File** fare clic su **Salva tutto**.  
  
     Questa applicazione sarà necessaria se si continua con la successiva procedura dettagliata.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Il [procedura dettagliata: Esecuzione di query tra relazioni (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) argomento continua in cui termina questa procedura dettagliata. La procedura dettagliata l'esecuzione di query tra relazioni illustra la modalità [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eseguire query tra tabelle, simile a *join* in un database relazionale.  
  
 Se si desidera eseguire la procedura dettagliata relativa all'esecuzione di query tra relazioni, è indispensabile salvare la soluzione per la procedura dettagliata appena completata.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
