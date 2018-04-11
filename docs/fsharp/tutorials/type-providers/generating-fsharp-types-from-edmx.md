---
title: 'Procedura dettagliata: generazione di tipi F# da un file di schema EDMX (F#)'
description: "Informazioni su come creare tipi F # per dati rappresentati da Entity Data Model (EDM) in F # 3.0, in cui lo schema è specificato in un file con estensione edmx."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>Procedura dettagliata: generazione di tipi F# da un file di schema EDMX

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questa procedura dettagliata per F# 3.0 spiega come creare tipi per dati rappresentati da Entity Data Model (EDM), lo schema per il quale è specificato in un file .edmx. Questa procedura dettagliata illustra inoltre come utilizzare il provider di tipi EdmxFile. Prima di iniziare, considerare se un provider di tipi SqlEntityConnection sia un'opzione più appropriata. Il provider di tipi SqlEntityConnection è ideale per scenari in cui si ha un database attivo che è possibile connettere durante la fase di sviluppo del progetto e non ci si ricorda di specificare la stringa di connessione in fase di compilazione. Tuttavia, questo provider di tipi è limitato in quanto non espone così tante funzionalità di database come il provider di tipi EdmxFile. Inoltre, se non si dispone di una connessione attiva per un progetto di database che utilizza Entity Data Model, è possibile utilizzare il file .edmx per scrivere codice rispetto al database. Quando si utilizza il provider di tipi EdmxFile, il compilatore F# esegue EdmGen.exe per generare i tipi che fornisce.

In questa procedura dettagliata vengono illustrate le seguenti attività, che è necessario eseguire in quest'ordine perché la procedura abbia esito positivo:


- Creazione di un file EDMX
<br />

- Creazione del progetto
<br />

- Ricerca o creazione di una stringa di connessione per Entity Data Model
<br />

- Configurazione del provider di tipi
<br />

- Esecuzione di una query sui dati
<br />

- Chiamata di una stored procedure
<br />


## <a name="prerequisites"></a>Prerequisiti

## <a name="creating-an-edmx-file"></a>Creazione di un file EDMX
Se si dispone già di un file EDMX, è possibile ignorare questo passaggio.


#### <a name="to-create-an-edmx-file"></a>Per creare un file EDMX

- Se si dispone già di un file EDMX, è possibile seguire le istruzioni alla fine di questa procedura dettagliata nel passaggio [la configurazione di Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).
<br />

## <a name="creating-the-project"></a>Creazione del progetto
In questo passaggio viene creato un progetto e vengono aggiunti i riferimenti appropriati per utilizzare il provider di tipi EDMX.


#### <a name="to-create-and-set-up-an-f-project"></a>Per creare e configurare un progetto F#

1. Chiudere il progetto precedente, creare un altro progetto e denominarlo SchoolEDM.
<br />

2. In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.
<br />

3. Nel **assembly** area, scegliere il **Framework** nodo.
<br />

4. Nell'elenco di assembly disponibili, scegliere il **System.Data.Entity** e **LINQ** assembly, quindi scegliere il **Aggiungi** pulsante per aggiungere i riferimenti a queste assembly al progetto.
<br />

5. Nel **assembly** area, selezionare il **estensioni** nodo.
<br />

6. Nell'elenco delle estensioni disponibili aggiungere un riferimento all'assembly FSharp.Data.TypeProviders.
<br />

7. Aggiungere il codice seguente per aprire gli spazi dei nomi appropriati.
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>Ricerca o creazione della stringa di connessione per Entity Data Model
La stringa di connessione per Entity Data Model (stringa di connessione EDMX) non include solo la stringa di connessione per il provider del database ma anche informazioni aggiuntive. Ad esempio, la stringa di connessione EDMX per un semplice database SQL Server è simile al seguente codice.

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

Per ulteriori informazioni sulle stringhe di connessione EDMX, vedere [le stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>Per trovare o creare la stringa di connessione per Entity Data Model

1. Le stringhe di connessione EDMX possono essere difficili da generare manualmente, pertanto è possibile risparmiare tempo generandola a livello di programmazione. Se si conosce la stringa di connessione EDMX, è possibile ignorare questo passaggio e utilizzare semplicemente tale stringa nel passaggio successivo. In caso contrario, utilizzare il codice seguente per generare la stringa di connessione EDMX da una stringa di connessione del database fornito.
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a>Configurazione del provider di tipi
In questo passaggio viene creato e configurato il provider di tipi con la stringa di connessione EDMX e vengono generati i tipi per lo schema definito nel file .edmx.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Per configurare il provider di tipi e generare i tipi

1. Copiare il file .edmx, che è stato generato nel primo passaggio di questa procedura guidata, nella cartella del progetto.
<br />

2. Aprire il menu di scelta rapida per il nodo del progetto nel progetto F #, scegliere **Aggiungi elemento esistente**, quindi scegliere il file. edmx per aggiungerlo al progetto.
<br />

3. Digitare il codice seguente per attivare il provider di tipi per il file .edmx. Sostituire *Server*\*istanza * con il nome del server che esegue SQL Server e il nome dell'istanza e utilizzare il nome del file con estensione edmx dal primo passaggio in questa procedura dettagliata.
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>Esecuzione di una query sui dati
In questo passaggio utilizzare le espressioni di query F# per eseguire una query sul database.


#### <a name="to-query-the-data"></a>Per eseguire una query sui dati

- Digitare il codice seguente per eseguire una query sui dati in Entity Data Model.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a>Chiamata di una stored procedure
È possibile chiamare stored procedure usando il provider di tipi EDMX. Nella procedura seguente, il database School contiene una stored procedure, **UpdatePerson**, che aggiorna un record, specificando i nuovi valori per le colonne. È possibile seguire questa stored procedure in quanto è esposta come metodo sul tipo DataContext.


#### <a name="to-call-a-stored-procedure"></a>Per chiamare una stored procedure

- Aggiungere il seguente codice per aggiornare i record.
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

Il risultato è 1 se si ha esito positivo. Si noti che **exactlyOne** viene utilizzato nell'espressione di query per garantire che un solo risultato sia restituito; in caso contrario, viene generata un'eccezione. Inoltre, per utilizzare valori nullable più facilmente, è possibile utilizzare la semplice **nullable** funzione definita in questo codice per creare un valore nullable da un valore comune.

<br />

## <a name="configuring-the-entity-data-model"></a>Configurazione di Entity Data Model
È consigliabile completare questa procedura solo se si desidera sapere come generare un Entity Data Model completo da un database e non si dispone di un database con il quale testarlo.


#### <a name="to-configure-the-entity-data-model"></a>Per configurare Entity Data Model

1. Nella barra dei menu, scegliere **SQL**, **Editor Transact-SQL**, **nuova Query** per creare un database. Se richiesto, specificare il server di database e l'istanza.
<br />

2. Copiare e incollare il contenuto dello script del database viene creato il database di studenti, come descritto nel [documentazione di Entity Framework](https://msdn.microsoft.com/data/JJ614587.aspx) nel centro per sviluppatori di dati.
<br />

3. Eseguire lo script SQL scegliendo il pulsante della barra degli strumenti con il simbolo del triangolo o i tasti Ctrl + Q.
<br />

4. In **Esplora Server**, aprire il menu di scelta rapida per **connessioni dati**, scegliere **Aggiungi connessione**e quindi immettere il nome del server di database, il nome del nome dell'istanza e il database School.
<br />

5. Creare un progetto c# o applicazione Console Visual Basic, aprire il menu di scelta rapida, scegli **Aggiungi nuovo elemento**, quindi scegliere **ADO.NET Entity Data Model**.
<br />  Verrà aperta la Procedura guidata Entity Data Model. Utilizzando questa procedura guidata è possibile scegliere la modalità di creazione di Entity Data Model.
<br />

6. In **Scegli contenuto Model**, selezionare il **genera da database** casella di controllo.
<br />

7. Nella pagina successiva scegliere il database School appena creato come connessione dati.
<br />  Questa connessione dovrebbe essere simile  **&lt;servername&gt;.&lt; InstanceName&gt;. School.dbo**.
<br />

8. Copiare la stringa di connessione a entità negli Appunti perché tale stringa potrebbe essere importante successivamente.
<br />

9. Verificare che la casella di controllo per salvare la stringa di connessione di entità per il **app** file sia selezionata e prendere nota del valore stringa nella casella di testo, che consentono di individuare la stringa di connessione in un secondo momento, se necessario.
<br />

10. Nella pagina successiva, scegliere **tabelle** e **Stored procedure e funzioni**.
<br />  Scegliendo questi nodi di primo livello, si scelgono tutte le tabelle, le stored procedure e le funzioni. È anche possibile selezionarle individualmente, se lo si desidera.
<br />

11. Verificare che le caselle di controllo per le altre impostazioni siano selezionate.
<br />  Il primo **Rendi plurali o singolari i nomi degli oggetti generati** casella di controllo indica se modificare le forme singolari in plurale per soddisfare le convenzioni di denominazione degli oggetti che rappresentano le tabelle del database. Il **Includi colonne chiavi esterne nel modello** casella di controllo determina se includere i campi il cui scopo è di unirsi ad altri campi nei tipi di oggetti che vengono generati per lo schema del database. La terza casella di controllo indica se includere stored procedure e funzioni nel modello.
<br />

12. Selezionare il **fine** pulsante per generare un file con estensione edmx contenente un Entity Data Model basato sul database School.
<br />  Un file, **Model1**, viene aggiunto al progetto e verrà visualizzato un diagramma di database.
<br />

13. Nella barra dei menu, scegliere **vista**, **altre finestre**, **Browser Entity Data Model** per visualizzare tutti i dettagli del modello o **Dettagli Mapping Entity Data Model**  per aprire una finestra che mostra come il modello a oggetti generato esegue il mapping nelle colonne e tabelle di database.
<br />


## <a name="next-steps"></a>Passaggi successivi
Esplorare altre query esaminando gli operatori di query disponibili elencate in [espressioni di Query](../../language-reference/query-expressions.md).


## <a name="see-also"></a>Vedere anche
[Provider di tipi](index.md)

[Provider di tipi EdmxFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[Walkthrough: Accessing a SQL Database by Using Type Providers and Entities](accessing-a-sql-database-entities.md) (Procedura dettagliata: accesso a un database SQL tramite entità e provider di tipi)

[Entity Framework](https://msdn.microsoft.com/data/ef)

[Cenni preliminari sui file con estensione edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[Generatore EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)

