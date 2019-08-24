---
title: Attività di accesso al database
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 31794a583e87b5948457fac754cb5bf66fafa09c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016030"
---
# <a name="database-access-activities"></a><span data-ttu-id="19a72-102">Attività di accesso al database</span><span class="sxs-lookup"><span data-stu-id="19a72-102">Database Access Activities</span></span>

<span data-ttu-id="19a72-103">Le attività di accesso al database consentono di accedere a un database all'interno di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="19a72-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="19a72-104">Queste attività consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.</span><span class="sxs-lookup"><span data-stu-id="19a72-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19a72-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="19a72-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="19a72-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="19a72-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="19a72-107">Se questa directory non esiste, andare alla pagina di download per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="19a72-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19a72-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="19a72-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="19a72-109">Attività di database</span><span class="sxs-lookup"><span data-stu-id="19a72-109">Database Activities</span></span>

<span data-ttu-id="19a72-110">Nelle sezioni seguenti viene descritto in dettaglio l'elenco delle attività incluse in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="19a72-110">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="19a72-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="19a72-111">DbUpdate</span></span>

<span data-ttu-id="19a72-112">Esegue una query SQL che produce una modifica nel database (inserimento, aggiornamento, eliminazione e altre modifiche).</span><span class="sxs-lookup"><span data-stu-id="19a72-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

<span data-ttu-id="19a72-113">Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity> e usa le relative funzionalità asincrone).</span><span class="sxs-lookup"><span data-stu-id="19a72-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="19a72-114">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="19a72-115">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="19a72-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="19a72-116">Dopo l'esecuzione di `DbUpdate`, il numero di record interessati viene restituito nella proprietà `AffectedRecords`.</span><span class="sxs-lookup"><span data-stu-id="19a72-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

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

|<span data-ttu-id="19a72-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="19a72-117">Argument</span></span>|<span data-ttu-id="19a72-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19a72-118">Description</span></span>|
|-|-|
|<span data-ttu-id="19a72-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="19a72-119">ProviderName</span></span>|<span data-ttu-id="19a72-120">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="19a72-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="19a72-121">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="19a72-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="19a72-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="19a72-122">ConnectionString</span></span>|<span data-ttu-id="19a72-123">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="19a72-123">Connection string to connect to the database.</span></span> <span data-ttu-id="19a72-124">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="19a72-124">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="19a72-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="19a72-125">ConfigName</span></span>|<span data-ttu-id="19a72-126">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="19a72-127">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="19a72-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="19a72-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="19a72-128">CommandType</span></span>|<span data-ttu-id="19a72-129">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="19a72-130">Sql</span><span class="sxs-lookup"><span data-stu-id="19a72-130">Sql</span></span>|<span data-ttu-id="19a72-131">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-131">The SQL command to be executed.</span></span>|
|<span data-ttu-id="19a72-132">Parametri</span><span class="sxs-lookup"><span data-stu-id="19a72-132">Parameters</span></span>|<span data-ttu-id="19a72-133">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="19a72-133">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="19a72-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="19a72-134">AffectedRecords</span></span>|<span data-ttu-id="19a72-135">Numero di record interessato dall'ultima operazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-135">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="19a72-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="19a72-136">DbQueryScalar</span></span>

<span data-ttu-id="19a72-137">Esegue una query che recupera un singolo valore dal database.</span><span class="sxs-lookup"><span data-stu-id="19a72-137">Executes a query that retrieves a single value from the database.</span></span>

<span data-ttu-id="19a72-138">Questa classe esegue le relative operazioni in modo asincrono (deriva da <xref:System.Activities.AsyncCodeActivity%601> e usa le relative funzionalità asincrone).</span><span class="sxs-lookup"><span data-stu-id="19a72-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="19a72-139">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="19a72-140">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="19a72-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="19a72-141">Dopo `DbQueryScalar` l'esecuzione `Result out` di, il valore scalare viene restituito nell'argomento ( `TResult`di tipo, definito nella classe <xref:System.Activities.AsyncCodeActivity%601>di base).</span><span class="sxs-lookup"><span data-stu-id="19a72-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

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

|<span data-ttu-id="19a72-142">Argomento</span><span class="sxs-lookup"><span data-stu-id="19a72-142">Argument</span></span>|<span data-ttu-id="19a72-143">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="19a72-143">Description</span></span>|
|-|-|
|<span data-ttu-id="19a72-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="19a72-144">ProviderName</span></span>|<span data-ttu-id="19a72-145">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="19a72-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="19a72-146">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="19a72-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="19a72-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="19a72-147">ConnectionString</span></span>|<span data-ttu-id="19a72-148">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="19a72-148">Connection string to connect to the database.</span></span> <span data-ttu-id="19a72-149">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="19a72-149">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="19a72-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="19a72-150">ConfigName</span></span>|<span data-ttu-id="19a72-151">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="19a72-152">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="19a72-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="19a72-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="19a72-153">CommandType</span></span>|<span data-ttu-id="19a72-154">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="19a72-155">Sql</span><span class="sxs-lookup"><span data-stu-id="19a72-155">Sql</span></span>|<span data-ttu-id="19a72-156">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-156">The SQL command to be executed.</span></span>|
|<span data-ttu-id="19a72-157">Parametri</span><span class="sxs-lookup"><span data-stu-id="19a72-157">Parameters</span></span>|<span data-ttu-id="19a72-158">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="19a72-158">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="19a72-159">Risultato</span><span class="sxs-lookup"><span data-stu-id="19a72-159">Result</span></span>|<span data-ttu-id="19a72-160">Valore scalare ottenuto dopo l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="19a72-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="19a72-161">Questo argomento è di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="19a72-161">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="19a72-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="19a72-162">DbQuery</span></span>

<span data-ttu-id="19a72-163">Esegue una query che recupera un elenco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="19a72-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="19a72-164">Dopo l'esecuzione della query, viene eseguita una funzione di mapping (può essere <xref:System.Func%601> < < `DbDataReader`, `TResult`> o <xref:System.Activities.ActivityFunc%601> `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="19a72-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="19a72-165">Questa funzione di mapping ottiene un record in un oggetto `DbDataReader` e ne esegue il mapping all'oggetto da restituire.</span><span class="sxs-lookup"><span data-stu-id="19a72-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

<span data-ttu-id="19a72-166">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="19a72-167">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="19a72-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="19a72-168">I risultati della query SQL vengono recuperati usando un oggetto `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="19a72-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="19a72-169">L'attività scorre `DbDataReader` ed esegue il mapping delle righe in `DbDataReader` a un'istanza di `TResult`.</span><span class="sxs-lookup"><span data-stu-id="19a72-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="19a72-170">L'utente di `DbQuery` deve fornire il codice di mapping. questa operazione può essere eseguita in due modi: `TResult` <xref:System.Func%601> < `DbDataReader`usando, > o un <xref:System.Activities.ActivityFunc%601> < `DbDataReader` `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="19a72-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="19a72-171">Nel primo caso, il mapping viene eseguito in un singolo impulso.</span><span class="sxs-lookup"><span data-stu-id="19a72-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="19a72-172">È pertanto più veloce, ma non può essere serializzato in XAML.</span><span class="sxs-lookup"><span data-stu-id="19a72-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="19a72-173">Nel secondo caso, il mapping viene eseguito in più impulsi.</span><span class="sxs-lookup"><span data-stu-id="19a72-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="19a72-174">Può quindi risultare più lento, ma può essere serializzato in XAML e modificato in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).</span><span class="sxs-lookup"><span data-stu-id="19a72-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

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

|<span data-ttu-id="19a72-175">Argomento</span><span class="sxs-lookup"><span data-stu-id="19a72-175">Argument</span></span>|<span data-ttu-id="19a72-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19a72-176">Description</span></span>|
|-|-|
|<span data-ttu-id="19a72-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="19a72-177">ProviderName</span></span>|<span data-ttu-id="19a72-178">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="19a72-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="19a72-179">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="19a72-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="19a72-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="19a72-180">ConnectionString</span></span>|<span data-ttu-id="19a72-181">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="19a72-181">Connection string to connect to the database.</span></span> <span data-ttu-id="19a72-182">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="19a72-182">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="19a72-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="19a72-183">ConfigName</span></span>|<span data-ttu-id="19a72-184">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="19a72-185">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="19a72-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="19a72-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="19a72-186">CommandType</span></span>|<span data-ttu-id="19a72-187">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="19a72-188">Sql</span><span class="sxs-lookup"><span data-stu-id="19a72-188">Sql</span></span>|<span data-ttu-id="19a72-189">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-189">The SQL command to be executed.</span></span>|
|<span data-ttu-id="19a72-190">Parametri</span><span class="sxs-lookup"><span data-stu-id="19a72-190">Parameters</span></span>|<span data-ttu-id="19a72-191">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="19a72-191">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="19a72-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="19a72-192">Mapper</span></span>|<span data-ttu-id="19a72-193">Funzione di mapping<xref:System.Func%601><(`DbDataReader`, `DataReader` `TResult` >) che accetta un record nell'oggetto ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo da aggiungere al metodo `TResult` `Result` raccolta.</span><span class="sxs-lookup"><span data-stu-id="19a72-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="19a72-194">In questo caso, il mapping viene eseguito in un singolo impulso, ma non può essere modificato in modo dichiarativo tramite la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="19a72-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="19a72-195">MapperFunc</span></span>|<span data-ttu-id="19a72-196">Funzione di mapping<xref:System.Activities.ActivityFunc%601><(`DbDataReader`, `DataReader` `TResult` >) che accetta un record nell'oggetto ottenuto come risultato dell'esecuzione della query e restituisce un'istanza di un oggetto di tipo da aggiungere al metodo `TResult` `Result` raccolta.</span><span class="sxs-lookup"><span data-stu-id="19a72-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="19a72-197">In questo caso, il mapping viene eseguito in più impulsi.</span><span class="sxs-lookup"><span data-stu-id="19a72-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="19a72-198">Questa funzione può essere serializzata in XAML e modificata in modo dichiarativo (qualsiasi attività esistente può partecipare al mapping).</span><span class="sxs-lookup"><span data-stu-id="19a72-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="19a72-199">Risultato</span><span class="sxs-lookup"><span data-stu-id="19a72-199">Result</span></span>|<span data-ttu-id="19a72-200">Elenco di oggetti ottenuto come risultato dell'esecuzione della query e dell'esecuzione della funzione di mapping per ogni record in `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="19a72-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="19a72-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="19a72-201">DbQueryDataSet</span></span>

<span data-ttu-id="19a72-202">Esegue una query che restituisce un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="19a72-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="19a72-203">Questa classe esegue le relative operazioni in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="19a72-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="19a72-204">Deriva da <xref:System.Activities.AsyncCodeActivity> <> eusalerelativefunzionalitàasincrone.`TResult`</span><span class="sxs-lookup"><span data-stu-id="19a72-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

<span data-ttu-id="19a72-205">È possibile configurare le informazioni di connessione impostando un nome invariante del provider (`ProviderName`) e la stringa di connessione (`ConnectionString`) o solo usando un nome di configurazione della stringa di connessione (`ConfigFileSectionName`) dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="19a72-206">La query da eseguire viene configurata nella relativa proprietà `Sql` e i parametri vengono passati tramite la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="19a72-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="19a72-207">`Result out` `TResult` <xref:System.Activities.AsyncCodeActivity%601>Dopo l'esecuzione di, `DataSet` l'oggetto viene restituito nell'argomento (di tipo, definito nella classe di base). `DbQueryDataSet`</span><span class="sxs-lookup"><span data-stu-id="19a72-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

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

|<span data-ttu-id="19a72-208">Argomento</span><span class="sxs-lookup"><span data-stu-id="19a72-208">Argument</span></span>|<span data-ttu-id="19a72-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19a72-209">Description</span></span>|
|-|-|
|<span data-ttu-id="19a72-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="19a72-210">ProviderName</span></span>|<span data-ttu-id="19a72-211">Nome invariante del provider ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="19a72-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="19a72-212">Se viene impostato questo argomento, è necessario impostare anche `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="19a72-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="19a72-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="19a72-213">ConnectionString</span></span>|<span data-ttu-id="19a72-214">Stringa di connessione per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="19a72-214">Connection string to connect to the database.</span></span> <span data-ttu-id="19a72-215">Se viene impostato questo argomento, è necessario impostare anche `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="19a72-215">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="19a72-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="19a72-216">ConfigName</span></span>|<span data-ttu-id="19a72-217">Nome della sezione del file di configurazione in cui sono archiviate le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="19a72-218">Quando viene impostato questo argomento, `ProviderName` e `ConnectionString` non sono richiesti.</span><span class="sxs-lookup"><span data-stu-id="19a72-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="19a72-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="19a72-219">CommandType</span></span>|<span data-ttu-id="19a72-220">Tipo di <xref:System.Data.Common.DbCommand> da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="19a72-221">Sql</span><span class="sxs-lookup"><span data-stu-id="19a72-221">Sql</span></span>|<span data-ttu-id="19a72-222">Comando SQL da eseguire.</span><span class="sxs-lookup"><span data-stu-id="19a72-222">The SQL command to be executed.</span></span>|
|<span data-ttu-id="19a72-223">Parametri</span><span class="sxs-lookup"><span data-stu-id="19a72-223">Parameters</span></span>|<span data-ttu-id="19a72-224">Raccolta di parametri della query SQL.</span><span class="sxs-lookup"><span data-stu-id="19a72-224">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="19a72-225">Risultato</span><span class="sxs-lookup"><span data-stu-id="19a72-225">Result</span></span>|<span data-ttu-id="19a72-226"><xref:System.Data.DataSet> ottenuto dopo l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="19a72-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="19a72-227">Configurazione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="19a72-227">Configuring Connection Information</span></span>

<span data-ttu-id="19a72-228">Tutte le attività DbActivities condividono gli stessi parametri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="19a72-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="19a72-229">Possono essere configurate in due modi:</span><span class="sxs-lookup"><span data-stu-id="19a72-229">They can be configured in two ways:</span></span>

- <span data-ttu-id="19a72-230">`ConnectionString + InvariantName`: Impostare il nome invariante del provider ADO.NET e la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

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

- <span data-ttu-id="19a72-231">`ConfigName`: Impostare il nome della sezione di configurazione che contiene le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="19a72-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- <span data-ttu-id="19a72-232">Nell'attività:</span><span class="sxs-lookup"><span data-stu-id="19a72-232">In the activity:</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a><span data-ttu-id="19a72-233">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="19a72-233">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="19a72-234">Istruzioni per l'impostazione</span><span class="sxs-lookup"><span data-stu-id="19a72-234">Setup instructions</span></span>

<span data-ttu-id="19a72-235">In questo esempio viene usato un database.</span><span class="sxs-lookup"><span data-stu-id="19a72-235">This sample uses a database.</span></span> <span data-ttu-id="19a72-236">Con l'esempio viene fornito uno script di impostazione e caricamento (Setup.cmd) .</span><span class="sxs-lookup"><span data-stu-id="19a72-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="19a72-237">È necessario eseguire il file dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="19a72-237">You must execute that file using the command prompt.</span></span>

<span data-ttu-id="19a72-238">Lo script Setup.cmd richiama il file di script CreateDb.sql che contiene i comandi SQL per l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19a72-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

- <span data-ttu-id="19a72-239">Crea un database denominato DbActivitiesSample.</span><span class="sxs-lookup"><span data-stu-id="19a72-239">Creates a database called DbActivitiesSample.</span></span>

- <span data-ttu-id="19a72-240">Crea la tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="19a72-240">Creates the Roles table.</span></span>

- <span data-ttu-id="19a72-241">Crea la tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="19a72-241">Creates Employees table.</span></span>

- <span data-ttu-id="19a72-242">Inserisce tre record nella tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="19a72-242">Inserts three records into the Roles table.</span></span>

- <span data-ttu-id="19a72-243">Inserisce dodici record nella tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="19a72-243">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="19a72-244">Per eseguire Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="19a72-244">To run Setup.cmd</span></span>

1. <span data-ttu-id="19a72-245">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="19a72-245">Open a command prompt.</span></span>

2. <span data-ttu-id="19a72-246">Passare alla cartella di esempio DbActivities.</span><span class="sxs-lookup"><span data-stu-id="19a72-246">Go to the DbActivities sample folder.</span></span>

3. <span data-ttu-id="19a72-247">Digitare "Setup. cmd" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="19a72-247">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19a72-248">Setup.cmd tenta di installare l'esempio nell'istanza di SqlExpress del computer locale.</span><span class="sxs-lookup"><span data-stu-id="19a72-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="19a72-249">Se si desidera installarlo in un'altra istanza del server SQL, modificare Setup.cmd specificando il nome della nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="19a72-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="19a72-250">Per disinstallare il database di esempio</span><span class="sxs-lookup"><span data-stu-id="19a72-250">To uninstall the sample database</span></span>

1. <span data-ttu-id="19a72-251">Eseguire Cleanup.cmd dalla cartella di esempio in un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="19a72-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="19a72-252">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="19a72-252">To run the sample</span></span>

1. <span data-ttu-id="19a72-253">Aprire la soluzione in Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="19a72-253">Open the solution in Visual Studio 2010</span></span>

2. <span data-ttu-id="19a72-254">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="19a72-254">To compile the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="19a72-255">Per eseguire l'esempio senza debug, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="19a72-255">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19a72-256">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="19a72-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="19a72-257">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="19a72-257">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="19a72-258">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi.</span><span class="sxs-lookup"><span data-stu-id="19a72-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="19a72-259">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="19a72-259">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
