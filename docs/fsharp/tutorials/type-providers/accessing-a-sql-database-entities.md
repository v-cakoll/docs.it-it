---
title: "Procedura dettagliata: Accesso a un database SQL tramite entità e provider di tipi (F#)"
description: 'Informazioni su come accedere ai dati tipizzati per un database SQL basato su ADO.NET Entity Data Model in F # 3.0.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>Procedura dettagliata: Accesso a un database SQL tramite entità e provider di tipi

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questa procedura dettagliata per F# 3.0 illustra come accedere ai dati tipizzati per un database SQL basato su ADO.NET Entity Data Model. In questa procedura dettagliata viene illustrato come configurare il provider di tipi `SqlEntityConnection` di F# per l'utilizzo con un database SQL, come scrivere query sui dati, ad esempio stored procedure nel database, e come utilizzare alcuni dei tipi e dei metodi di ADO.NET Entity Framework per aggiornare il database.

In questa procedura dettagliata vengono illustrate le seguenti attività, che è consigliabile eseguire in quest'ordine perché la procedura abbia esito positivo:


- Creare il database School
<br />

- Creare e configurare un progetto F#
<br />

- Configurare il provider di tipi e connettersi a Entity Data Model
<br />

- Eseguire query sul database
<br />

- Aggiornamento del database
<br />


## <a name="prerequisites"></a>Prerequisiti
Per completare questa procedura, è necessario avere accesso a un server che esegue SQL Server e in cui sia possibile creare un database.

## <a name="create-the-school-database"></a>Creare il database School
È possibile creare il database School in qualsiasi server che esegue SQL Server a cui si ha accesso come amministratore oppure è possibile utilizzare LocalDB.


#### <a name="to-create-the-school-database"></a>Per creare il database School

1. In **Esplora Server**, aprire il menu di scelta rapida per il **connessioni dati** nodo, quindi scegliere **Aggiungi connessione**.
<br />  Il **Aggiungi connessione** viene visualizzata la finestra di dialogo.
<br />

2. Nel **nome Server** casella, specificare il nome di un'istanza di SQL Server a cui si ha accesso amministrativo oppure specificare (localdb\v11.0) se non si dispone di accesso a un server.
<br />  SQL Server Express LocalDB fornisce un server di database semplice per lo sviluppo e il test nel proprio computer. Per ulteriori informazioni su LocalDB, vedere [procedura dettagliata: creazione di un File di Database locale in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).
<br />  Viene creato un nuovo nodo **Esplora Server** in **connessioni dati**.
<br />

3. Aprire il menu di scelta rapida per il nuovo nodo di connessione e quindi scegliere **nuova Query**.
<br />

4. Aprire [la creazione di Database di esempio School](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) sul sito Web Microsoft e quindi copiare e incollare lo script del database che crea il database School nella finestra dell'editor.
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>Creare e configurare un progetto F#
In questo passaggio viene creato un progetto e viene impostato l'utilizzo di un provider di tipi.


#### <a name="to-create-and-configure-an-f-project"></a>Per creare e configurare un progetto F#

1. Chiudere il progetto precedente, creare un altro progetto e denominarlo **SchoolEDM**.
<br />

2. In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.
<br />

3. Scegliere il **Framework** nodo, quindi il **Framework** scegliere **System. Data**, **System.Data.Entity**e **LINQ**.
<br />

4. Scegliere il **estensioni** nodo, aggiungere un riferimento al [Typeproviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, quindi scegliere il **OK** per chiudere la finestra di dialogo.
<br />

5. Aggiungere il codice seguente per definire un modulo interno e aprire gli spazi dei nomi appropriati. Il provider di tipi può inserire i tipi solo in uno spazio dei nomi privato o interno.
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. Per eseguire il codice in questa procedura dettagliata interattivamente come script anziché come un programma compilato, aprire il menu di scelta rapida per il nodo del progetto, scegliere **Aggiungi nuovo elemento**, aggiungere un file di script F # e quindi aggiungere il codice in ogni passaggio allo script. Per caricare i riferimenti agli assembly, aggiungere le righe seguenti.
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. Evidenziare ogni blocco di codice mentre lo si aggiunge e premere ALT+INVIO per eseguirlo in F# Interactive.
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Configurare il provider di tipi e connettersi a Entity Data Model
In questo passaggio si installa un provider di tipi con una connessione dati e si ottiene un contesto dati che consente di utilizzare i dati.


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Per configurare il provider di tipi e connettersi a Entity Data Model

1. Digitare il codice seguente per configurare il provider di tipi `SqlEntityConnection` che genera i tipi F# basati su Entity Data Model creato precedentemente. Anziché la stringa di connessione EDMX completa utilizzare solo la stringa di connessione SQL.
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  Questa azione installa un provider di tipi con la connessione al database creata precedentemente. La proprietà `MultipleActiveResultSets` è necessaria quando si utilizza ADO.NET Entity Framework poiché questa proprietà consente di eseguire più controlli in modo asincrono nel database in una connessione, cosa che può verificarsi frequentemente nel codice ADO.NET Entity Framework. Per altre informazioni, vedere [MARS (Multiple Active Result Sets)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).
<br />

2. Ottenere il contesto dei dati, un oggetto contenente le tabelle del database come proprietà e le stored procedure e le funzioni del database come metodi.
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>Esecuzione di query nel database
In questo passaggio si utilizzano le espressioni di query F# per eseguire varie query sul database.


#### <a name="to-query-the-data"></a>Per eseguire una query sui dati

- Digitare il codice seguente per analizzare i dati provenienti da Entity Data Model. Notare l'effetto Pluralize = true che modifica la tabella del database Course in Courses e la tabella Person in People.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a>Aggiornamento del database
Per aggiornare il database, utilizzare le classi e i metodi di Entity Framework. È possibile utilizzare due tipi di contesti dei dati con il provider di tipi SQLEntityConnection. Innanzitutto, `ServiceTypes.SimpleDataContextTypes.EntityContainer` è il contesto dei dati semplificato, che include solo le proprietà specificate che rappresentano le tabelle e le colonne del database. In secondo luogo, il contesto dei dati completo è un'istanza della classe Entity Framework `System.Data.Objects.ObjectContext`, che contiene il metodo `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` per aggiungere righe al database. Entity Framework riconosce le tabelle e le relazioni tra di esse, pertanto rafforza la coerenza tra database.


#### <a name="to-update-the-database"></a>Per aggiornare il database

1. Aggiungere il seguente codice al programma: In questo esempio aggiungere due oggetti con una relazione tra di essi e aggiungere un docente e l'assegnazione dell'ufficio. La tabella `OfficeAssignments` contiene la colonna `InstructorID` che fa riferimento alla colonna `PersonID` nella tabella `Person`.
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

Non viene apportata alcuna modifica al database finché non viene chiamato `System.Data.Objects.ObjectContext.SaveChanges`.
<br />

2. A questo punto ripristinare il database allo stato iniziale eliminando gli oggetti aggiunti.
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
Quando si utilizza un'espressione di query, è necessario ricordare che la query è soggetta alla valutazione differita. Pertanto, il database è ancora aperto per la lettura di tutte le valutazioni concatenate, come nei blocchi di espressione lambda dopo ogni espressione di query. Qualsiasi operazione di database che in modo esplicito o implicito utilizza una transazione deve avvenire dopo che le operazioni di lettura sono state completate.


## <a name="next-steps"></a>Passaggi successivi
Esaminare altre opzioni di query prendendo in considerazione gli operatori di query disponibili nella [espressioni di Query](../../language-reference/query-expressions.md)ed esaminare anche il [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) per comprendere quali funzionalità sono disponibili quando Utilizzare questo tipo provider.


## <a name="see-also"></a>Vedere anche
[Provider di tipi](index.md)  
[Provider di tipi SqlEntityConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[Procedura dettagliata: Generazione di tipi F # da un File di Schema EDMX](generating-fsharp-types-from-edmx.md)  
[ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572)  
[Cenni preliminari sui file con estensione edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[Generatore EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)  
