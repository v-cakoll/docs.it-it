---
title: 'Procedura dettagliata: Accesso a un database SQL tramite provider di tipi (F#)'
description: 'Informazioni su come utilizzare il provider di tipi SqlDataConnection (LINQ to SQL) in F # 3.0 per generare i tipi per un database SQL quando si dispone di una connessione di database attivo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>Procedura dettagliata: Accesso a un database SQL tramite provider di tipi

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](http://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questa procedura dettagliata viene illustrato come utilizzare il provider di tipi SqlDataConnection (LINQ to SQL) che è disponibile in F # 3.0 per generare i tipi per i dati in un database SQL quando si dispone di una connessione in tempo reale a un database. Se non è una connessione in tempo reale a un database, ma è un LINQ al file di schema SQL (file. DBML), vedere [procedura dettagliata: generazione di tipi F # da un File DBML](generating-fsharp-types-from-dbml.md).

In questa procedura dettagliata vengono illustrate le attività seguenti. In quest'ordine perché la procedura abbia esito positivo, è necessario effettuare queste attività:


- Preparazione di un database di test

- Creazione del progetto

- Impostazione di un provider di tipi

- Esecuzione di una query sui dati

- Utilizzo dei campi che ammettono valori null

- Chiamata di una stored procedure

- Aggiornamento del database

- L'esecuzione del codice Transact-SQL

- Utilizzando il contesto dei dati completo

- L'eliminazione dei dati

- Creare un database di prova (in base alle esigenze)

## <a name="preparing-a-test-database"></a>Preparazione di un Database di Test
In un server che esegue SQL Server, creare un database a scopo di test. È possibile utilizzare il database creare script nella parte inferiore della pagina nella sezione [la creazione di un database di prova](#creating-a-test-database) per eseguire questa operazione.


#### <a name="to-prepare-a-test-database"></a>Per preparare un database di test

Per eseguire lo Script di creazione MyDatabase, aprire il **vista** menu, quindi scegliere **Esplora oggetti di SQL Server** oppure scegliere Ctrl +\, tasti Ctrl + S. In **Esplora oggetti di SQL Server** finestra, aprire il menu di scelta rapida per l'istanza appropriata, scegliere **nuova Query**, copiare lo script nella parte inferiore della pagina e quindi incollare lo script nell'editor. Per eseguire lo script SQL, scegliere l'icona della barra degli strumenti con il simbolo triangolare oppure premere i tasti Ctrl + Q. Per ulteriori informazioni su **Esplora oggetti di SQL Server**, vedere [sviluppo del Database connesso](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).


## <a name="creating-the-project"></a>Creazione del progetto
Successivamente, si crea un progetto di applicazione di F #.


#### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto

1. Creare un nuovo progetto di applicazione F #.

2. Aggiungere riferimenti a [Typeproviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), così come `System.Data`, e `System.Data.Linq`.

3. Aprire gli spazi dei nomi appropriato aggiungendo le righe di codice seguente all'inizio dei file di codice F # FS.

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. Come con molti altri programmi F #, è possibile eseguire il codice in questa procedura dettagliata di un programma compilato, o è possibile eseguirlo in modo interattivo come script. Se si preferisce utilizzare gli script, aprire il menu di scelta rapida per il nodo del progetto, seleziona **Aggiungi nuovo elemento**, aggiungere un file di script F # e aggiungere il codice in ogni passaggio allo script. È necessario aggiungere le righe seguenti all'inizio del file da caricare i riferimenti all'assembly.

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  È quindi possibile selezionare ogni blocco di codice, aggiungerlo e premere Alt + INVIO per eseguirlo in F # Interactive.

## <a name="setting-up-a-type-provider"></a>Impostazione di un provider di tipi
In questo passaggio viene creato un provider di tipi per lo schema del database.


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>Per configurare il provider di tipi da una connessione diretta del database

Esistono due righe critiche del codice necessarie per creare i tipi che è possibile utilizzare per un database SQL tramite il provider di tipi di query. Innanzitutto, creare un'istanza del provider di tipi. A tale scopo, creare l'aspetto seguente abbreviazione di tipo per un `SqlDataConnection` con un parametro generico statico. `SqlDataConnection`è un provider di tipi SQL e non deve essere confuso con `SqlConnection` tipo che è utilizzato nella programmazione di ADO.NET. Se si dispone di un database che si desidera connettersi e dispone di una stringa di connessione, usare il codice seguente per richiamare il provider di tipi. Sostituire con la propria stringa di connessione per la stringa di esempio specificata. Ad esempio, se il server MYSERVER e l'istanza del database è l'istanza, il nome del database è MyDatabase e si desidera utilizzare l'autenticazione di Windows per accedere al database, quindi la stringa di connessione sarebbe quello specificato nell'esempio di codice seguente.

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

Ora è un tipo, `dbSchema`, che è un tipo padre che contiene tutti i tipi generati che rappresentano le tabelle del database. È anche un oggetto, `db`, che abbia come membri di tutte le tabelle nel database. I nomi di tabella sono di proprietà e il tipo di queste proprietà viene generato dal compilatore F #. Degli stessi tipi vengono visualizzati come i tipi annidati in `dbSchema.ServiceTypes`. Di conseguenza, i dati recuperati per le righe delle tabelle è un'istanza del tipo appropriato che è stato generato per la tabella. Il nome del tipo è `ServiceTypes.Table1`.

Per acquisire familiarità con modalità di interpretazione delle query in query SQL linguaggio F #, esaminare la riga che imposta il `Log` proprietà nel contesto dati.

Per esplorare ulteriormente i tipi creati mediante il provider di tipi, aggiungere il codice seguente.

```fsharp
let table1 = db.Table1
```

Passare il mouse su `table1` per visualizzare il relativo tipo. Il tipo è `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` e l'argomento generico implica che il tipo di ogni riga è il tipo generato, `dbSchema.ServiceTypes.Table1`. Il compilatore crea un tipo simile per ogni tabella nel database.

## <a name="querying-the-data"></a>Esecuzione di una query sui dati
In questo passaggio, scrivere una query utilizzando espressioni di query F #.


#### <a name="to-query-the-data"></a>Per eseguire una query sui dati

1. Ora è possibile creare una query per la tabella nel database. Aggiungere il codice seguente.

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  L'aspetto della parola `query` indica che si tratta di un'espressione di query, un tipo di espressione di calcolo che genera una raccolta di risultati simile di una query sul database tipico. Se si posiziona sulla query, si noterà che è un'istanza di [classe LINQ. querybuilder](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), un tipo che definisce l'espressione di calcolo di query. Se si passa il mouse `query1`, si noterà che è un'istanza di `System.Linq.IQueryable`. Come suggerisce il nome, `System.Linq.IQueryable` rappresenta i dati che possono essere eseguita una query, non il risultato di una query. Una query è soggetta alla valutazione differita, che significa che il database è solo di eseguire una query quando viene valutata la query. La riga finale passa la query tramite `Seq.iter`. Le query enumerabile e possono essere Iterate come sequenze. Per ulteriori informazioni, vedere [espressioni di Query](../../language-reference/query-expressions.md).

2. Ora è possibile aggiungere un operatore di query alla query. Esistono un numero di operatori di query disponibili che è possibile utilizzare per costruire query più complesse. Questo esempio mostra anche che è possibile eliminare la variabile di query e utilizzare invece un operatore pipeline.

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. Aggiungere una query più complessa con un join di due tabelle.

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. Nel codice del mondo reale, i parametri nella query sono in genere valori o le variabili, costanti non in fase di compilazione. Aggiungere il codice seguente che esegue il wrapping di una query in una funzione che accetta un parametro e quindi chiama tale funzione con il valore 10.

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>Utilizzo dei campi che ammettono valori null
Nei database, spesso i campi consentono valori null. Nel sistema di tipi .NET, è possibile utilizzare i tipi di dati numerici normali per i dati che ammette valori null, perché non dispone di tali tipi null come un possibile valore. Di conseguenza, questi valori sono rappresentati da istanze di `System.Nullable` tipo. Anziché il valore di tali campi direttamente con il nome del campo, è necessario eseguire alcuni passaggi aggiuntivi. È possibile utilizzare il `System.Nullable.Value` proprietà per accedere al valore sottostante di un tipo nullable. Il `System.Nullable.Value` proprietà genera un'eccezione se l'oggetto è null anziché un valore. È possibile utilizzare il `System.Nullable.HasValue` metodo booleano per determinare se esiste un valore oppure utilizzare `System.Nullable.GetValueOrDefault()` per assicurarsi di avere un valore effettivo in tutti i casi. Se si utilizza `System.Nullable.GetValueOrDefault()` è un valore null nel database, quindi viene sostituito con un valore, ad esempio una stringa vuota per i tipi string, 0 per i tipi integrali o 0,0 per Mobile tipi di punti.

Quando è necessario eseguire i test di uguaglianza o confronti tra valori ammette valori null in un `where` clausola in una query, è possibile utilizzare gli operatori che ammette valori null, vedere il [modulo Linq. nullableoperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d). Si tratta ad esempio gli operatori di confronto regolare `=`, `>`, `<=`e così via, ad eccezione del fatto che un punto interrogativo viene visualizzata a sinistra o destra dell'operatore di valori nullable. Ad esempio, l'operatore `>?` è maggiore-operatore con un valore nullable a destra. Il funzionamento di questi operatori è che se entrambi i lati dell'espressione sono null, l'espressione restituisce `false`. In un `where` clausola, in genere significa che le righe che contengono campi null non sono è selezionate e non è state restituite nei risultati della query.


#### <a name="to-work-with-nullable-fields"></a>Per funzionare con i campi che ammettono valori null

Il codice seguente illustra l'uso dei valori ammette valori null. Si supponga che **TestData1** è un campo di tipo integer che ammette valori null.

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a>Chiamata di una stored procedure
Le stored procedure nel database possono essere chiamate da F #. È necessario impostare il parametro static `StoredProcedures` per `true` nell'istanza del provider di tipo. Il provider di tipi `SqlDataConnection` contiene diversi metodi statici che è possibile utilizzare per configurare i tipi generati. Per una descrizione completa di questi, vedere [Provider di tipi SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d). Viene generato un metodo nel tipo di contesto dati per ogni stored procedure.


#### <a name="to-call-a-stored-procedure"></a>Per chiamare una stored procedure

Se le stored procedure accetta parametri che ammettono valori null, è necessario passare un oggetto appropriato `System.Nullable` valore. Il valore restituito di un metodo di stored procedure che restituisce un valore scalare o una tabella è `System.Data.Linq.ISingleResult`, che contiene le proprietà che consentono di accedere ai dati restituiti. L'argomento tipo per `System.Data.Linq.ISingleResult` dipende la procedura specifica e viene anche uno dei tipi generati dal provider di tipo. Per una stored procedure denominata `Procedure1`, il tipo è `Procedure1Result`. Il tipo `Procedure1Result` contiene i nomi delle colonne in una tabella restituita, o, per una stored procedure che restituisce un valore scalare, che rappresenta il valore restituito.

Il codice seguente si presuppone che esista una stored procedure `Procedure1` sul database che accetta due numeri interi che ammette valori null come parametri, viene eseguita una query che restituisce una colonna denominata `TestData1`e restituisce un intero.

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>Aggiornamento del database
Il tipo DataContext LINQ contiene metodi che rendono più semplice eseguire gli aggiornamenti di database transazionali in modo completamente tipizzato con i tipi generati.


#### <a name="to-update-the-database"></a>Per aggiornare il database

1. Nel codice seguente, più righe vengono aggiunte al database. Se si aggiunge solo una riga, è possibile utilizzare `System.Data.Linq.Table.InsertOnSubmit()` per specificare la nuova riga da aggiungere. Se si inseriscono più righe, è consigliabile posizionare in una raccolta e chiamare `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`. Quando si chiama uno di questi metodi, il database non viene modificato immediatamente. È necessario chiamare `System.Data.Linq.DataContext.SubmitChanges` per eseguire il commit delle modifiche. Per impostazione predefinita, tutte le operazioni eseguite prima di chiamare `System.Data.Linq.DataContext.SubmitChanges` in modo implicito fa parte della stessa transazione.

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. Ora di pulire le righe chiamando un'operazione di eliminazione.

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>L'esecuzione del codice Transact-SQL
È inoltre possibile specificare Transact-SQL direttamente tramite il `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` metodo la `DataContext` classe.


#### <a name="to-execute-custom-sql-commands"></a>Per eseguire comandi SQL personalizzati

Il codice seguente viene illustrato come inviare comandi SQL per inserire un record in una tabella ed eliminare un record da una tabella.

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>Utilizzando il contesto dei dati completo
Negli esempi precedenti, il `GetDataContext` metodo è stato utilizzato per ottenere ciò che viene chiamato il *contesto dati semplificato* per lo schema del database. Il contesto dati semplificato è più facile da utilizzare durante la creazione di query perché non sono disponibili tutti i membri. Pertanto, quando si esplorano le proprietà in IntelliSense, è possibile concentrarsi sulla struttura di database, ad esempio le tabelle e stored procedure. Tuttavia, vi è un limite a cosa si può fare con il contesto dati semplificato. Un contesto dei dati completo che offre la possibilità di eseguire altre azioni. è inoltre disponibile il file si trova nel `ServiceTypes` e ha il nome del *DataContext* parametro statico se è stato specificato. Se non è stato fornito, il nome del tipo di contesto dati viene generato automaticamente da SqlMetal.exe in base all'input di altri. Eredita il contesto dei dati completo `System.Data.Linq.DataContext` ed espone i membri della relativa classe base, inclusi i riferimenti ai tipi di dati ADO.NET, ad esempio il `Connection` oggetti, metodi, ad esempio `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` e `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` che è possibile utilizzare per scrivere query in SQL, e inoltre un modo per utilizzare le transazioni in modo esplicito.


#### <a name="to-use-the-full-data-context"></a>Utilizzare il contesto dati completa

Il codice seguente viene illustrato il recupero di un oggetto di contesto dati completa e utilizzarlo per eseguire comandi direttamente sul database. In questo caso, due comandi vengono eseguiti come parte della stessa transazione.

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>L'eliminazione dei dati
Questo passaggio illustra come eliminare righe da una tabella dati.


#### <a name="to-delete-rows-from-the-database"></a>Per eliminare righe dal database

A questo punto, pulizia backup di tutte le righe aggiunte scrivendo una funzione che elimina le righe da una tabella specificata, un'istanza del `System.Data.Linq.Table` classe. Scrivere una query per trovare tutte le righe che si desidera eliminare, quindi inviare tramite pipe i risultati della query nel `deleteRows` (funzione). Questo codice consente di sfruttare la possibilità di fornire applicazione parziale degli argomenti della funzione.

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>Creazione di un database di test
In questa sezione viene illustrato come configurare il database di test da utilizzare in questa procedura dettagliata.

Si noti che se si modifica il database in qualche modo, sarà necessario reimpostare il provider di tipi. Per reimpostare il provider di tipi, ricostruire o pulire il progetto che contiene il tipo provider.


#### <a name="to-create-the-test-database"></a>Per creare il database di test

1. In **Esplora Server**, aprire il menu di scelta rapida per il **connessioni dati** nodo e scegliere **Aggiungi connessione**. Il **Aggiungi connessione** viene visualizzata la finestra di dialogo.

2. Nel **nome Server** casella, specificare il nome di un'istanza di SQL Server che si hanno accesso amministrativo a o se non si dispone di accesso a un server, specificare (localdb\v11.0). SQL Express LocalDB fornisce un server di database semplice per lo sviluppo e test nel computer. Viene creato un nuovo nodo **Esplora Server** in **connessioni dati**. Per ulteriori informazioni su LocalDB, vedere [procedura dettagliata: creazione di un File di Database locale in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).

3. Aprire il menu di scelta rapida per il nuovo nodo di connessione e selezionare **nuova Query**.

4. Copiare lo script SQL seguente, incollarlo nell'editor di query e quindi scegliere il **Execute** sulla barra degli strumenti o premere i tasti Ctrl + Maiusc + A.

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>Vedere anche
[Provider di tipi](index.md)

[Provider di tipi SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[Procedura dettagliata: Generazione di tipi F # da un File DBML](generating-fsharp-types-from-dbml.md)

[Espressioni di query](../../language-reference/query-expressions.md)

[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)

[SqlMetal.exe &#40; Lo strumento di generazione di codice &#41;](https://msdn.microsoft.com/library/bb386987)
