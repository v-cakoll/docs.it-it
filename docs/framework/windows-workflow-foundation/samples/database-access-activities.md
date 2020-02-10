---
title: Attività di accesso al database
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: ed3f0ad3f2fd19f622c9cb0faf7d5cd864b81995
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094644"
---
# <a name="database-access-activities"></a>Attività di accesso al database

Le attività di accesso al database consentono di accedere a un database all'interno di un flusso di lavoro. Queste attività consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](../../data/adonet/index.md) per accedere al database.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare alla pagina di download per scaricare tutti gli esempi di Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>Attività di database

Nelle sezioni seguenti viene descritto in dettaglio l'elenco delle attività incluse in questo esempio.

## <a name="dbupdate"></a>DbUpdate

Esegue una query SQL che produce una modifica nel database (inserimento, aggiornamento, eliminazione e altre modifiche).

Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity> e usa le relative funzionalità asincrone).

È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.

La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.

Dopo l'esecuzione di `DbUpdate`, il numero di record interessati viene restituito nella proprietà `AffectedRecords`.

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|Argomento|Descrizione|
|-|-|
|ProviderName|Nome invariante del provider ADO.NET. Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.|
|ConnectionString|Stringa di connessione per connettersi al database. Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.|
|ConfigName|Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione. Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.|
|CommandType|Tipo di <xref:System.Data.Common.DbCommand> da eseguire.|
|Sql|Comando SQL da eseguire.|
|Parametri|Raccolta di parametri della query SQL.|
|AffectedRecords|Numero di record interessato dall'ultima operazione.|

## <a name="dbqueryscalar"></a>DbQueryScalar

Esegue una query che recupera un singolo valore dal database.

Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity%601> e usa le relative funzionalità asincrone).

È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.

La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.

Dopo l'esecuzione di `DbQueryScalar`, il valore scalare viene restituito nell'argomento `Result out` (di tipo `TResult`, definito nella classe di base <xref:System.Activities.AsyncCodeActivity%601>).

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argomento|Descrizione|
|-|-|
|ProviderName|Nome invariante del provider ADO.NET. Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.|
|ConnectionString|Stringa di connessione per connettersi al database. Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.|
|ConfigName|Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione. Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.|
|CommandType|Tipo di <xref:System.Data.Common.DbCommand> da eseguire.|
|Sql|Comando SQL da eseguire.|
|Parametri|Raccolta di parametri della query SQL.|
|Risultato|Valore scalare ottenuto dopo l'esecuzione della query. Questo argomento è di tipo `TResult`.|

## <a name="dbquery"></a>DbQuery

Esegue una query che recupera un elenco di oggetti. Dopo l'esecuzione della query, viene eseguita una funzione di mapping (può essere <xref:System.Func%601><`DbDataReader`, `TResult`> o <xref:System.Activities.ActivityFunc%601><`DbDataReader``TResult`). Questa funzione di mapping ottiene un record in un oggetto `DbDataReader` e ne esegue il mapping all'oggetto da restituire.

È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.

La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.

I risultati della query SQL vengono recuperati usando un oggetto `DbDataReader`. L'attività scorre `DbDataReader` ed esegue il mapping delle righe in `DbDataReader` a un'istanza di `TResult`. L'utente di `DbQuery` deve fornire il codice di mapping. questa operazione può essere eseguita in due modi: usando un <xref:System.Func%601><`DbDataReader`, `TResult`> o <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>. Nel primo caso, il mapping viene eseguito in un singolo impulso. È pertanto più veloce, ma non può essere serializzato in XAML. Nel secondo caso, il mapping viene eseguito in più impulsi. Può quindi risultare più lento, ma può essere serializzato in XAML e modificato in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|Argomento|Descrizione|
|-|-|
|ProviderName|Nome invariante del provider ADO.NET. Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.|
|ConnectionString|Stringa di connessione per connettersi al database. Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.|
|ConfigName|Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione. Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.|
|CommandType|Tipo di <xref:System.Data.Common.DbCommand> da eseguire.|
|Sql|Comando SQL da eseguire.|
|Parametri|Raccolta di parametri della query SQL.|
|Mapper|Funzione di mapping (<xref:System.Func%601><`DbDataReader`, `TResult`>) che accetta un record nel `DataReader` ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo `TResult` da aggiungere alla raccolta di `Result`.<br /><br /> In questo caso, il mapping viene eseguito in un singolo impulso, ma non può essere modificato in modo dichiarativo tramite la finestra di progettazione.|
|MapperFunc|Funzione di mapping (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) che accetta un record nel `DataReader` ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo `TResult` da aggiungere alla raccolta di `Result`.<br /><br /> In questo caso, il mapping viene eseguito in più impulsi. Questa funzione può essere serializzata in XAML e modificata in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).|
|Risultato|Elenco di oggetti ottenuto come risultato dell'esecuzione della query e dell'esecuzione della funzione di mapping per ogni record in `DataReader`.|

## <a name="dbquerydataset"></a>DbQueryDataSet

Esegue una query che restituisce un oggetto <xref:System.Data.DataSet>. Questa classe esegue le relative operazioni in modo asincrono. Deriva da <xref:System.Activities.AsyncCodeActivity><`TResult`> e usa le relative funzionalità asincrone.

È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.

La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.

Dopo l'esecuzione del `DbQueryDataSet` viene restituito `DataSet` nell'argomento `Result out` (di tipo `TResult`, definito nella classe di base <xref:System.Activities.AsyncCodeActivity%601>).

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argomento|Descrizione|
|-|-|
|ProviderName|Nome invariante del provider ADO.NET. Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.|
|ConnectionString|Stringa di connessione per connettersi al database. Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.|
|ConfigName|Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione. Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.|
|CommandType|Tipo di <xref:System.Data.Common.DbCommand> da eseguire.|
|Sql|Comando SQL da eseguire.|
|Parametri|Raccolta di parametri della query SQL.|
|Risultato|<xref:System.Data.DataSet> ottenuto dopo l'esecuzione della query.|

## <a name="configuring-connection-information"></a>Configurazione delle informazioni di connessione

Tutte le attività DbActivities condividono gli stessi parametri di configurazione. Possono essere configurate in due modi:

- `ConnectionString + InvariantName`: impostare il nome invariante del provider ADO.NET e la stringa di connessione.

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- `ConfigName`: impostare il nome della sezione di configurazione che contiene le informazioni di connessione.

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- Nell'attività:

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a>Esecuzione dell'esempio

### <a name="setup-instructions"></a>Istruzioni per l'impostazione

In questo esempio viene usato un database. Con l'esempio viene fornito uno script di impostazione e caricamento (Setup.cmd) . È necessario eseguire il file dal prompt dei comandi.

Lo script Setup.cmd richiama il file di script CreateDb.sql che contiene i comandi SQL per l'esecuzione delle operazioni seguenti:

- Crea un database denominato DbActivitiesSample.

- Crea la tabella Ruoli.

- Crea la tabella Employees.

- Inserisce tre record nella tabella Ruoli.

- Inserisce dodici record nella tabella Employees.

##### <a name="to-run-setupcmd"></a>Per eseguire Setup.cmd

1. Aprire un prompt dei comandi.

2. Passare alla cartella di esempio DbActivities.

3. Digitare "Setup. cmd" e premere INVIO.

    > [!NOTE]
    > Setup.cmd tenta di installare l'esempio nell'istanza di SqlExpress del computer locale. Se si desidera installarlo in un'altra istanza del server SQL, modificare Setup.cmd specificando il nome della nuova istanza.

##### <a name="to-uninstall-the-sample-database"></a>Per disinstallare il database di esempio

1. Eseguire Cleanup.cmd dalla cartella di esempio in un prompt dei comandi.

##### <a name="to-run-the-sample"></a>Per eseguire l'esempio

1. Aprire la soluzione in Visual Studio 2010

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire l'esempio senza debug, premere CTRL+F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
