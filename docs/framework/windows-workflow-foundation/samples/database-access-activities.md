---
title: Attività di accesso al database
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: efcdd25ee3e6b86d87d551623b166eab4fa76845
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850402"
---
# <a name="database-access-activities"></a><span data-ttu-id="d6f5d-102">Attività di accesso al database</span><span class="sxs-lookup"><span data-stu-id="d6f5d-102">Database Access Activities</span></span>
<span data-ttu-id="d6f5d-103">Le attività di accesso al database consentono di accedere a un database all'interno di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="d6f5d-104">Queste attività consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6f5d-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d6f5d-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-106">Check for the following (default) directory before continuing.</span></span>
>
>  `<InstallDrive>:\WF_WCF_Samples`
>
>  <span data-ttu-id="d6f5d-107">Se questa directory non esiste, passare a (pagina di download) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d6f5d-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-108">This sample is located in the following directory.</span></span>
>
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="d6f5d-109">Attività di database</span><span class="sxs-lookup"><span data-stu-id="d6f5d-109">Database Activities</span></span>
 <span data-ttu-id="d6f5d-110">Nelle sezioni seguenti viene descritto in dettaglio l'elenco delle attività incluse in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-110">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="d6f5d-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="d6f5d-111">DbUpdate</span></span>
 <span data-ttu-id="d6f5d-112">Esegue una query SQL che produce una modifica nel database (inserimento, aggiornamento, eliminazione e altre modifiche).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

 <span data-ttu-id="d6f5d-113">Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity> e usa le relative funzionalità asincrone).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

 <span data-ttu-id="d6f5d-114">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="d6f5d-115">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="d6f5d-116">Dopo l'esecuzione di `DbUpdate`, il numero di record interessati viene restituito nella proprietà `AffectedRecords`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

```
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

|<span data-ttu-id="d6f5d-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="d6f5d-117">Argument</span></span>|<span data-ttu-id="d6f5d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-118">Description</span></span>|
|-|-|
|<span data-ttu-id="d6f5d-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-119">ProviderName</span></span>|<span data-ttu-id="d6f5d-120">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="d6f5d-121">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="d6f5d-122">ConnectionString</span></span>|<span data-ttu-id="d6f5d-123">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-123">Connection string to connect to the database.</span></span> <span data-ttu-id="d6f5d-124">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-124">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-125">ConfigName</span></span>|<span data-ttu-id="d6f5d-126">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="d6f5d-127">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="d6f5d-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="d6f5d-128">CommandType</span></span>|<span data-ttu-id="d6f5d-129">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="d6f5d-130">Sql</span><span class="sxs-lookup"><span data-stu-id="d6f5d-130">Sql</span></span>|<span data-ttu-id="d6f5d-131">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-131">The SQL command to be executed.</span></span>|
|<span data-ttu-id="d6f5d-132">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f5d-132">Parameters</span></span>|<span data-ttu-id="d6f5d-133">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-133">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="d6f5d-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="d6f5d-134">AffectedRecords</span></span>|<span data-ttu-id="d6f5d-135">Numero di record interessato dall'ultima operazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-135">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="d6f5d-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="d6f5d-136">DbQueryScalar</span></span>
 <span data-ttu-id="d6f5d-137">Esegue una query che recupera un singolo valore dal database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-137">Executes a query that retrieves a single value from the database.</span></span>

 <span data-ttu-id="d6f5d-138">Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity%601> e usa le relative funzionalità asincrone).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

 <span data-ttu-id="d6f5d-139">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="d6f5d-140">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="d6f5d-141">Dopo aver `DbQueryScalar` viene eseguita, viene restituito il valore scalare nel `Result``out` argomento (di tipo `TResult`, vale a dire definito nella classe di base <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```
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

|<span data-ttu-id="d6f5d-142">Argomento</span><span class="sxs-lookup"><span data-stu-id="d6f5d-142">Argument</span></span>|<span data-ttu-id="d6f5d-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-143">Description</span></span>|
|-|-|
|<span data-ttu-id="d6f5d-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-144">ProviderName</span></span>|<span data-ttu-id="d6f5d-145">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="d6f5d-146">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="d6f5d-147">ConnectionString</span></span>|<span data-ttu-id="d6f5d-148">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-148">Connection string to connect to the database.</span></span> <span data-ttu-id="d6f5d-149">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-149">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-150">ConfigName</span></span>|<span data-ttu-id="d6f5d-151">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="d6f5d-152">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="d6f5d-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="d6f5d-153">CommandType</span></span>|<span data-ttu-id="d6f5d-154">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="d6f5d-155">Sql</span><span class="sxs-lookup"><span data-stu-id="d6f5d-155">Sql</span></span>|<span data-ttu-id="d6f5d-156">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-156">The SQL command to be executed.</span></span>|
|<span data-ttu-id="d6f5d-157">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f5d-157">Parameters</span></span>|<span data-ttu-id="d6f5d-158">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-158">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="d6f5d-159">Risultato</span><span class="sxs-lookup"><span data-stu-id="d6f5d-159">Result</span></span>|<span data-ttu-id="d6f5d-160">Valore scalare ottenuto dopo l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="d6f5d-161">Questo argomento è di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-161">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="d6f5d-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="d6f5d-162">DbQuery</span></span>
 <span data-ttu-id="d6f5d-163">Esegue una query che recupera un elenco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="d6f5d-164">Dopo l'esecuzione della query, viene eseguita una funzione di mapping (può essere <xref:System.Func%601> < `DbDataReader`, `TResult`> o un <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="d6f5d-165">Questa funzione di mapping ottiene un record in un oggetto `DbDataReader` e ne esegue il mapping all'oggetto da restituire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

 <span data-ttu-id="d6f5d-166">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="d6f5d-167">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="d6f5d-168">I risultati della query SQL vengono recuperati usando un oggetto `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="d6f5d-169">L'attività scorre `DbDataReader` ed esegue il mapping delle righe in `DbDataReader` a un'istanza di `TResult`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="d6f5d-170">L'utente del `DbQuery` deve fornire il codice di mapping e ciò può essere eseguite in due modi: utilizzando un <xref:System.Func%601> < `DbDataReader`, `TResult`> o un <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="d6f5d-171">Nel primo caso, il mapping viene eseguito in un singolo impulso.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="d6f5d-172">È pertanto più veloce, ma non può essere serializzato in XAML.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="d6f5d-173">Nel secondo caso, il mapping viene eseguito in più impulsi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="d6f5d-174">Può quindi risultare più lento, ma può essere serializzato in XAML e modificato in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

```
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

|<span data-ttu-id="d6f5d-175">Argomento</span><span class="sxs-lookup"><span data-stu-id="d6f5d-175">Argument</span></span>|<span data-ttu-id="d6f5d-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-176">Description</span></span>|
|-|-|
|<span data-ttu-id="d6f5d-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-177">ProviderName</span></span>|<span data-ttu-id="d6f5d-178">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="d6f5d-179">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="d6f5d-180">ConnectionString</span></span>|<span data-ttu-id="d6f5d-181">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-181">Connection string to connect to the database.</span></span> <span data-ttu-id="d6f5d-182">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-182">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-183">ConfigName</span></span>|<span data-ttu-id="d6f5d-184">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="d6f5d-185">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="d6f5d-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="d6f5d-186">CommandType</span></span>|<span data-ttu-id="d6f5d-187">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="d6f5d-188">Sql</span><span class="sxs-lookup"><span data-stu-id="d6f5d-188">Sql</span></span>|<span data-ttu-id="d6f5d-189">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-189">The SQL command to be executed.</span></span>|
|<span data-ttu-id="d6f5d-190">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f5d-190">Parameters</span></span>|<span data-ttu-id="d6f5d-191">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-191">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="d6f5d-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="d6f5d-192">Mapper</span></span>|<span data-ttu-id="d6f5d-193">Funzione di mapping (<xref:System.Func%601><`DbDataReader`, `TResult`>) che accetta un record `DataReader` ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo `TResult` da aggiungere al `Result` collection.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="d6f5d-194">In questo caso, il mapping viene eseguito in un singolo impulso, ma non può essere modificato in modo dichiarativo tramite la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="d6f5d-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="d6f5d-195">MapperFunc</span></span>|<span data-ttu-id="d6f5d-196">Funzione di mapping (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) che accetta un record `DataReader` ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo `TResult` da aggiungere al `Result` collection.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="d6f5d-197">In questo caso, il mapping viene eseguito in più impulsi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="d6f5d-198">Questa funzione può essere serializzata in XAML e modificata in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="d6f5d-199">Risultato</span><span class="sxs-lookup"><span data-stu-id="d6f5d-199">Result</span></span>|<span data-ttu-id="d6f5d-200">Elenco di oggetti ottenuto come risultato dell'esecuzione della query e dell'esecuzione della funzione di mapping per ogni record in `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="d6f5d-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="d6f5d-201">DbQueryDataSet</span></span>
 <span data-ttu-id="d6f5d-202">Esegue una query che restituisce un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d6f5d-203">Questa classe esegue le relative operazioni in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="d6f5d-204">Deriva da <xref:System.Activities.AsyncCodeActivity> < `TResult`> e Usa le relative funzionalità asincrone.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

 <span data-ttu-id="d6f5d-205">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

 <span data-ttu-id="d6f5d-206">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

 <span data-ttu-id="d6f5d-207">Dopo il `DbQueryDataSet` viene eseguita la `DataSet` viene restituito nel `Result``out` argomento (di tipo `TResult`, vale a dire definito nella classe base <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="d6f5d-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```
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

|<span data-ttu-id="d6f5d-208">Argomento</span><span class="sxs-lookup"><span data-stu-id="d6f5d-208">Argument</span></span>|<span data-ttu-id="d6f5d-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-209">Description</span></span>|
|-|-|
|<span data-ttu-id="d6f5d-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-210">ProviderName</span></span>|<span data-ttu-id="d6f5d-211">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="d6f5d-212">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="d6f5d-213">ConnectionString</span></span>|<span data-ttu-id="d6f5d-214">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-214">Connection string to connect to the database.</span></span> <span data-ttu-id="d6f5d-215">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-215">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="d6f5d-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="d6f5d-216">ConfigName</span></span>|<span data-ttu-id="d6f5d-217">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="d6f5d-218">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="d6f5d-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="d6f5d-219">CommandType</span></span>|<span data-ttu-id="d6f5d-220">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="d6f5d-221">Sql</span><span class="sxs-lookup"><span data-stu-id="d6f5d-221">Sql</span></span>|<span data-ttu-id="d6f5d-222">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-222">The SQL command to be executed.</span></span>|
|<span data-ttu-id="d6f5d-223">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f5d-223">Parameters</span></span>|<span data-ttu-id="d6f5d-224">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-224">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="d6f5d-225">Risultato</span><span class="sxs-lookup"><span data-stu-id="d6f5d-225">Result</span></span>|<span data-ttu-id="d6f5d-226"><xref:System.Data.DataSet> ottenuto dopo l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="d6f5d-227">Configurazione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-227">Configuring Connection Information</span></span>
 <span data-ttu-id="d6f5d-228">Tutte le attività DbActivities condividono gli stessi parametri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="d6f5d-229">Possono essere configurate in due modi:</span><span class="sxs-lookup"><span data-stu-id="d6f5d-229">They can be configured in two ways:</span></span>

-   <span data-ttu-id="d6f5d-230">`ConnectionString + InvariantName`: impostare il nome invariante del provider ADO.NET e la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

    ```
    Activity dbSelectCount = new DbQueryScalar<DateTime>()
    {
        ProviderName = "System.Data.SqlClient",
        ConnectionString = @"Data Source=.\SQLExpress;
                             Initial Catalog=DbActivitiesSample;
                             Integrated Security=True",
        Sql = "SELECT GetDate()"
    };
    ```

-   <span data-ttu-id="d6f5d-231">`ConfigName`: impostare il nome della sezione di configurazione che contiene le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

    ```xml
    <connectionStrings>
        <add name="DbActivitiesSample"
             providerName="System.Data.SqlClient"
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
      </connectionStrings>
    ```

-   <span data-ttu-id="d6f5d-232">Nell'attività:</span><span class="sxs-lookup"><span data-stu-id="d6f5d-232">In the activity:</span></span>

    ```
    Activity dbSelectCount = new DbQueryScalar<int>()
    {
        ConfigName = "DbActivitiesSample",
        Sql = "SELECT COUNT(*) FROM Roles"
    };
    ```

## <a name="running-this-sample"></a><span data-ttu-id="d6f5d-233">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="d6f5d-233">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="d6f5d-234">Istruzioni per l'impostazione</span><span class="sxs-lookup"><span data-stu-id="d6f5d-234">Setup instructions</span></span>
 <span data-ttu-id="d6f5d-235">In questo esempio viene usato un database.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-235">This sample uses a database.</span></span> <span data-ttu-id="d6f5d-236">Con l'esempio viene fornito uno script di impostazione e caricamento (Setup.cmd) .</span><span class="sxs-lookup"><span data-stu-id="d6f5d-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="d6f5d-237">È necessario eseguire il file dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-237">You must execute that file using the command prompt.</span></span>

 <span data-ttu-id="d6f5d-238">Lo script Setup.cmd richiama il file di script CreateDb.sql che contiene i comandi SQL per l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6f5d-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

-   <span data-ttu-id="d6f5d-239">Crea un database denominato DbActivitiesSample.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-239">Creates a database called DbActivitiesSample.</span></span>

-   <span data-ttu-id="d6f5d-240">Crea la tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-240">Creates the Roles table.</span></span>

-   <span data-ttu-id="d6f5d-241">Crea la tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-241">Creates Employees table.</span></span>

-   <span data-ttu-id="d6f5d-242">Inserisce tre record nella tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-242">Inserts three records into the Roles table.</span></span>

-   <span data-ttu-id="d6f5d-243">Inserisce dodici record nella tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-243">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="d6f5d-244">Per eseguire Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="d6f5d-244">To run Setup.cmd</span></span>

1.  <span data-ttu-id="d6f5d-245">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-245">Open a command prompt.</span></span>

2.  <span data-ttu-id="d6f5d-246">Passare alla cartella di esempio DbActivities.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-246">Go to the DbActivities sample folder.</span></span>

3.  <span data-ttu-id="d6f5d-247">Digitare "Setup. cmd" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-247">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d6f5d-248">Setup.cmd tenta di installare l'esempio nell'istanza di SqlExpress del computer locale.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="d6f5d-249">Se si desidera installarlo in un'altra istanza del server SQL, modificare Setup.cmd specificando il nome della nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="d6f5d-250">Per disinstallare il database di esempio</span><span class="sxs-lookup"><span data-stu-id="d6f5d-250">To uninstall the sample database</span></span>

1.  <span data-ttu-id="d6f5d-251">Eseguire Cleanup.cmd dalla cartella di esempio in un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="d6f5d-252">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d6f5d-252">To run the sample</span></span>

1.  <span data-ttu-id="d6f5d-253">Aprire la soluzione in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="d6f5d-253">Open the solution in Visual Studio 2010</span></span>

2.  <span data-ttu-id="d6f5d-254">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-254">To compile the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="d6f5d-255">Per eseguire l'esempio senza debug, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-255">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="d6f5d-256">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d6f5d-257">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-257">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d6f5d-258">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d6f5d-259">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d6f5d-259">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
