---
title: 'Procedura dettagliata: generazione di tipi F# da un file DBML (F#)'
description: 'Informazioni su come creare tipi F # per i dati da un database in F # 3.0 quando si dispone di informazioni sullo schema con codificate in un file. dbml.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>Procedura dettagliata: generazione di tipi F# da un file DBML

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questa procedura dettagliata per F # 3.0 viene descritto come creare tipi di dati da un database quando si dispone di informazioni sullo schema con codificate in un file. dbml. LINQ to SQL Usa questo formato di file per rappresentare lo schema del database. È possibile generare un file LINQ to SQL dello schema in Visual Studio utilizzando la finestra di Progettazione relazionale oggetti (O/R). Per ulteriori informazioni, vedere [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) e [generazione di codice in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).

Il provider di tipi di Database Markup Language (DBML) consente di scrivere codice che usa i tipi basati su uno schema di database senza che sia necessario specificare una stringa di connessione statica in fase di compilazione. Che può essere utile se è necessario consentire la possibilità che l'applicazione finale utilizzerà un database diverso, credenziali diverse o una stringa di connessione diverso da quello utilizzato per sviluppare l'applicazione. Se si dispone di una connessione diretta del database che è possibile utilizzare in fase di compilazione e questo è lo stesso database e le credenziali che verranno usati nell'applicazione compilata, è inoltre possibile utilizzare il provider di tipi SQLDataConnection. Per ulteriori informazioni, vedere [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md).

In questa procedura dettagliata vengono illustrate le attività seguenti. È necessario completare in quest'ordine perché la procedura abbia esito positivo:


- Creazione di un file con estensione dbml
<br />

- Creazione e configurazione di un progetto F #
<br />

- Configurazione del provider di tipo e la generazione di tipi
<br />

- Esecuzione di query nel database
<br />


## <a name="prerequisites"></a>Prerequisiti

## <a name="creating-a-dbml-file"></a>Creazione di un file con estensione dbml
Se non si dispone di un database, eseguire i test su, crearne una seguendo le istruzioni riportate in fondo [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md). Se si seguono queste istruzioni, si creerà un database denominato MyDatabase contenente alcuni semplici tabelle e stored procedure in SQL Server.

Se si dispone già di un file. dbml, è possibile ignorare la sezione **creare e impostare backup di un progetto F #**. In caso contrario, è possibile creare un file con estensione dbml assegnato a un database SQL esistente e tramite la riga di comando dello strumento SqlMetal.exe.


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>Per creare un file con estensione dbml usando SqlMetal.exe

1. Aprire un **prompt dei comandi per sviluppatori**.
<br />

2. Assicurarsi di disporre dell'accesso a SqlMetal.exe immettendo `SqlMetal.exe /?` al prompt dei comandi. SqlMetal.exe viene in genere installato nel **SDKs** cartella **programmi** o **programmi (x86)**.
<br />

3. Eseguire SqlMetal.exe con le seguenti opzioni della riga di comando. Sostituire con un percorso appropriato al posto di `c:\destpath` per creare il file con estensione dbml e inserire i valori appropriati per il server di database, istanza, nome e il nome di database.
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
Se SqlMetal.exe dispone di un problema durante la creazione del file a causa di problemi relativi alle autorizzazioni, è possibile modificare la directory corrente in una cartella che si dispone di accesso in scrittura.


4. È anche possibile esaminare le altre opzioni della riga di comando disponibili. Ad esempio, sono disponibili opzioni che è possibile utilizzare se si desidera viste e funzioni SQL incluse con i tipi generati. Per ulteriori informazioni, vedere [SqlMetal.exe &#40; Lo strumento di generazione di codice &#41; ](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>Creazione e configurazione di un progetto F #
In questo passaggio si crea un progetto e aggiungere i riferimenti appropriati per utilizzare il provider di tipi DBML.


#### <a name="to-create-and-set-up-an-f-project"></a>Per creare e configurare un progetto F#

1. Aggiungere un nuovo progetto applicazione Console c# alla soluzione.
<br />

2. In **Esplora**, aprire il menu di scelta rapida per **riferimenti**, quindi scegliere **Aggiungi riferimento**.
<br />

3. Nel **assembly** area, scegliere il **Framework** nodo, quindi nell'elenco di assembly disponibili, scegliere il **System. Data** e **LINQ**  assembly.
<br />

4. Nel **assembly** area scegliere **estensioni**, quindi nell'elenco di assembly disponibili, scegliere **Typeproviders**.
<br />

5. Scegliere il **OK** pulsante per aggiungere riferimenti a questi assembly al progetto.
<br />

6. (Facoltativo) Copiare il file con estensione dbml creato nel passaggio precedente e incollare il file nella cartella principale per il progetto. Questa cartella contiene file di progetto (con estensione fsproj) e i file di codice. Nella barra dei menu, scegliere **progetto**, **Aggiungi elemento esistente**e quindi specificare il file dbml per aggiungerlo al progetto. Dopo aver completato questi passaggi, è possibile omettere il parametro static ResolutionFolder nel passaggio successivo.
<br />

## <a name="configuring-the-type-provider"></a>Configurazione del provider di tipi
In questa sezione, creare un provider di tipi e generare tipi dallo schema descritto nel file. dbml.


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>Per configurare il provider di tipi e generare i tipi

- Aggiungere il codice che apre il **TypeProviders** dello spazio dei nomi e crea il provider di tipi per il file dbml che si desidera utilizzare. Se il file. dbml aggiunto al progetto, è possibile omettere il parametro static ResolutionFolder.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

Il tipo DataContext fornisce l'accesso a tutti i tipi generati ed eredita da `System.Data.Linq.DataContext`. Il provider di tipi DbmlFile ha diversi parametri statici che è possibile impostare. Ad esempio, è possibile utilizzare un nome diverso per il tipo DataContext specificando `DataContext=MyDataContext`. In tal caso, il codice analogo all'esempio seguente:
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>Esecuzione di query nel database
In questa sezione, utilizzare le espressioni di query F # per eseguire query sul database.


#### <a name="to-query-the-data"></a>Per eseguire una query sui dati

- Aggiungere il codice per eseguire query sul database.
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>Passaggi successivi
È possibile utilizzare altre espressioni di query, o ottenere una connessione al database del contesto dei dati e di eseguire le normali operazioni di dati ADO.NET. Per i passaggi aggiuntivi, vedere le sezioni dopo "Query dei dati" in [procedura dettagliata: accesso a un Database SQL dal provider di tipi con](accessing-a-sql-database.md).


## <a name="see-also"></a>Vedere anche
[Provider di tipi DbmlFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[Provider di tipi](index.md)

[Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md) (Procedura dettagliata: accesso a un database SQL tramite provider di tipi)

[SqlMetal.exe &#40; Lo strumento di generazione di codice &#41;](https://msdn.microsoft.com/library/bb386987)

[Espressioni di query](../../language-reference/query-expressions.md)
