---
title: 'Procedura dettagliata: Modello a oggetti e query semplici (C#)'
description: Seguire questa procedura dettagliata per creare una classe di entità per la modellazione di una tabella in un database di esempio. Creare quindi una semplice query per elencare i clienti in una determinata posizione.
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: 4637fabecc1726d8fec12857a667073912cfbed5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286301"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a>Procedura dettagliata: Modello a oggetti e query semplici (C#)

In questa procedura dettagliata viene descritto uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base con minime complessità. Verranno create una classe di entità per la modellazione della tabella Customers nel database Northwind di esempio, quindi una semplice query per elencare i clienti residenti nell'area londinese.

Questa procedura dettagliata è basata sul codice in fase di progettazione per illustrare i concetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. In genere, è possibile utilizzare il Object Relational Designer per creare il modello a oggetti.

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.

## <a name="prerequisites"></a>Prerequisiti

- Per i file usati nella procedura dettagliata viene usata una cartella dedicata ("c:\linqtest5"). Creare la cartella prima di avviare la procedura.

- Per questa procedura dettagliata è richiesto il database di esempio Northwind. Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft. Per istruzioni, vedere [download di database di esempio](downloading-sample-databases.md). Dopo avere scaricato il database, copiare il file nella cartella c:\linqtest5.

## <a name="overview"></a>Panoramica

La procedura dettagliata è costituita da sei attività principali:

- Creazione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di una soluzione in Visual Studio.

- Mapping di una classe a una tabella del database.

- Definizione di proprietà nella classe per rappresentare colonne del database.

- Definizione della connessione al database Northwind.

- Creazione di una semplice query da eseguire sul database.

- Esecuzione della query e analisi dei risultati.

## <a name="creating-a-linq-to-sql-solution"></a>Creazione di una soluzione LINQ to SQL

In questa prima attività viene creata una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.

### <a name="to-create-a-linq-to-sql-solution"></a>Per creare una soluzione LINQ to SQL

1. Scegliere **nuovo**dal menu **file** di Visual Studio, quindi fare clic su **progetto**.

2. Nel riquadro **Tipi progetto** della finestra di dialogo **nuovo progetto** fare clic su **Visual C#**.

3. Nel riquadro **Modelli** fare clic su **Applicazione console**.

4. Nella casella **nome** digitare **LinqConsoleApp**.

5. Nella casella **percorso** , verificare dove si desidera archiviare i file di progetto.

6. Fare clic su **OK**.

## <a name="adding-linq-references-and-directives"></a>Aggiunta di riferimenti e direttive LINQ

In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto. Se System. Data. Linq non è elencato come riferimento nel progetto (espandere il nodo **riferimenti** in **Esplora soluzioni**), aggiungerlo, come illustrato nei passaggi seguenti.

### <a name="to-add-systemdatalinq"></a>Per aggiungere System.Data.Linq

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **riferimenti**, quindi scegliere **Aggiungi riferimento**.

2. Nella finestra di dialogo **Aggiungi riferimento** fare clic su **.NET**, selezionare l'assembly System. Data. Linq, quindi fare clic su **OK**.

     L'assembly verrà aggiunto al progetto.

3. Aggiungere le direttive seguenti all'inizio di **Program.cs**:

     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]

## <a name="mapping-a-class-to-a-database-table"></a>Mapping di una classe a una tabella del database

In questo passaggio verrà creata una classe ed eseguito il mapping della classe a una tabella di database. Tale classe viene definita una classe di *entità*. Notare che il mapping viene eseguito semplicemente aggiungendo l'attributo <xref:System.Data.Linq.Mapping.TableAttribute>. La proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> consente di specificare il nome della tabella nel database.

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a>Per creare una classe di entità ed eseguire il mapping della classe a una tabella di database

- Digitare o incollare il codice seguente in Program.cs immediatamente sopra la dichiarazione della classe `Program`:

     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a>Definizione di proprietà nella classe per rappresentare colonne del database

In questo passaggio si completeranno diverse attività.

- Usare l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> per definire le proprietà `CustomerID` e `City` nella classe di entità in modo che rappresentino colonne nella tabella del database.

- Definire la proprietà `CustomerID` in modo che rappresenti una colonna di chiave primaria nel database.

- Definire i campi `_CustomerID` e `_City` per l'archiviazione privata. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sarà quindi in grado di archiviare e recuperare direttamente i valori, anziché usare funzioni di accesso pubbliche che potrebbero includere la logica di business.

### <a name="to-represent-characteristics-of-two-database-columns"></a>Per rappresentare caratteristiche di due colonne del database

- Digitare o incollare il codice seguente in Program.cs all'interno delle parentesi graffe della classe `Customer`:

     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a>Definizione della connessione al database Northwind

In questo passaggio viene usato un oggetto <xref:System.Data.Linq.DataContext> per stabilire una connessione tra le strutture di dati basate sul codice e il database stesso. <xref:System.Data.Linq.DataContext> è il canale principale tramite il quale vengono recuperati oggetti dal database e vengono inviate modifiche.

Viene inoltre dichiarato un oggetto `Table<Customer>` che fungerà da tabella tipizzata logica per le query sulla tabella Customers nel database. Tali query verranno quindi create ed eseguite nei passaggi successivi.

### <a name="to-specify-the-database-connection"></a>Per specificare la connessione al database

- Digitare o incollare il codice seguente nel metodo `Main`:

     Si presuppone che il file `northwnd.mdf` si trovi nella cartella linqtest5. Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.

     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]

## <a name="creating-a-simple-query"></a>Creazione di una query semplice

In questo passaggio viene creata una query per cercare i clienti nella tabella di database Customers residenti nell'area londinese. Il codice della query in questo passaggio descrive semplicemente la query, ma non la esegue. Questo approccio è noto come *esecuzione posticipata*. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).

Verrà anche prodotto un output del log per mostrare i comandi SQL generati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Questa funzionalità di registrazione, che usa <xref:System.Data.Linq.DataContext.Log%2A>, è utile per eseguire il debug e per determinare che i comandi inviati al database rappresentano accuratamente la query.

### <a name="to-create-a-simple-query"></a>Per creare una query semplice

- Digitare o incollare il codice seguente nel metodo `Main` dopo la dichiarazione `Table<Customer>`.

     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]

## <a name="executing-the-query"></a>Esecuzione della query

In questo passaggio verrà effettivamente eseguita la query. Le espressioni di query create nei passaggi precedenti non vengono valutate finché i risultati non saranno necessari. Quando si inizia l'iterazione `foreach`, viene eseguito un comando SQL sul database e gli oggetti vengono materializzati.

### <a name="to-execute-the-query"></a>Per eseguire la query

1. Digitare o incollare il codice seguente alla fine del metodo `Main` dopo la descrizione della query.

     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]

2. ‎Premere F5 per eseguire il debug dell'applicazione.

    > [!NOTE]
    > Se l'applicazione genera un errore di run-time, vedere la sezione relativa alla risoluzione dei problemi di [apprendimento per procedure dettagliate](learning-by-walkthroughs.md).

     I risultati della query nella finestra della console dovrebbero avere il seguente aspetto:

     `ID=AROUT, City=London`

     `ID=BSBEV, City=London`

     `ID=CONSH, City=London`

     `ID=EASTC, City=London`

     `ID=NORTS, City=London`

     `ID=SEVES, City=London`

3. Premere INVIO nella finestra della console per chiudere l'applicazione.

## <a name="next-steps"></a>Passaggi successivi

L'argomento [procedura dettagliata: esecuzione di query tra relazioni (C#)](walkthrough-querying-across-relationships-csharp.md) continua dove termina questa procedura dettagliata. Nella procedura dettagliata relativa alla query tra relazioni viene illustrato come è [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] possibile eseguire query tra tabelle, in modo analogo ai *join* in un database relazionale.

Se si desidera eseguire la procedura dettagliata relativa all'esecuzione di query tra relazioni, è indispensabile salvare la soluzione per la procedura dettagliata appena completata.

## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](learning-by-walkthroughs.md)
