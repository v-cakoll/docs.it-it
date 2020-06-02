---
title: Aggiornamento di origini dati con DataAdapter
description: Informazioni su come il metodo Update di DataAdapter risolve le modifiche da un set di dati di nuovo all'origine dati nelle applicazioni ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: e2348a3a89aa1c28856bfc21aaa25f2c8327aac7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286184"
---
# <a name="updating-data-sources-with-dataadapters"></a><span data-ttu-id="d82b5-103">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d82b5-103">Updating Data Sources with DataAdapters</span></span>

<span data-ttu-id="d82b5-104">Il metodo `Update` di <xref:System.Data.Common.DataAdapter> viene chiamato per applicare le modifiche apportate a un oggetto <xref:System.Data.DataSet> nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-104">The `Update` method of the <xref:System.Data.Common.DataAdapter> is called to resolve changes from a <xref:System.Data.DataSet> back to the data source.</span></span> <span data-ttu-id="d82b5-105">Il metodo `Update`, analogamente al metodo `Fill`, accetta come argomenti un'istanza di un oggetto `DataSet` e un oggetto <xref:System.Data.DataTable> o nome di `DataTable` facoltativi.</span><span class="sxs-lookup"><span data-stu-id="d82b5-105">The `Update` method, like the `Fill` method, takes as arguments an instance of a `DataSet`, and an optional <xref:System.Data.DataTable> object or `DataTable` name.</span></span> <span data-ttu-id="d82b5-106">L'istanza di `DataSet` rappresenta l'oggetto `DataSet` contenente le modifiche che sono state apportate e l'oggetto `DataTable` identifica la tabella da cui recuperare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d82b5-106">The `DataSet` instance is the `DataSet` that contains the changes that have been made, and the `DataTable` identifies the table from which to retrieve the changes.</span></span> <span data-ttu-id="d82b5-107">Se non viene specificato nessun oggetto `DataTable`, verrà usato il primo oggetto `DataTable` di `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-107">If no `DataTable` is specified, the first `DataTable` in the `DataSet` is used.</span></span>

<span data-ttu-id="d82b5-108">Quando si chiama il metodo `Update`, `DataAdapter` analizza le modifiche apportate ed esegue il comando appropriato (INSERT, UPDATE o DELETE).</span><span class="sxs-lookup"><span data-stu-id="d82b5-108">When you call the `Update` method, the `DataAdapter` analyzes the changes that have been made and executes the appropriate command (INSERT, UPDATE, or DELETE).</span></span> <span data-ttu-id="d82b5-109">Quando rileva una modifica a un oggetto `DataAdapter`, <xref:System.Data.DataRow> elabora la modifica usando <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> o <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="d82b5-109">When the `DataAdapter` encounters a change to a <xref:System.Data.DataRow>, it uses the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, or <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> to process the change.</span></span> <span data-ttu-id="d82b5-110">In questo modo è possibile ottimizzare le prestazioni dell'applicazione ADO.NET specificando la sintassi del comando in fase di progettazione e, dove possibile, mediante stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d82b5-110">This allows you to maximize the performance of your ADO.NET application by specifying command syntax at design time and, where possible, through the use of stored procedures.</span></span> <span data-ttu-id="d82b5-111">È necessario impostare in modo esplicito i comandi prima di chiamare `Update`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-111">You must explicitly set the commands before calling `Update`.</span></span> <span data-ttu-id="d82b5-112">Se `Update` viene chiamato e non esiste il comando appropriato per un determinato aggiornamento, ad esempio nessun `DeleteCommand` per le righe cancellate, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d82b5-112">If `Update` is called and the appropriate command does not exist for a particular update (for example, no `DeleteCommand` for deleted rows), an exception is thrown.</span></span>

> [!NOTE]
> <span data-ttu-id="d82b5-113">Se si usano stored procedure SQL Server per modificare o eliminare dati tramite `DataAdapter`, assicurarsi di non usare SET NOCOUNT ON nella definizione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d82b5-113">If you are using SQL Server stored procedures to edit or delete data using a `DataAdapter`, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="d82b5-114">Con tale comando il totale restituito delle righe interessate è pari a zero e tale situazione viene interpretata da `DataAdapter` come un conflitto di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="d82b5-114">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="d82b5-115">In questo caso verrà generata un'eccezione <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="d82b5-115">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>

<span data-ttu-id="d82b5-116">È possibile usare i parametri Command per specificare i valori di input e di output di un'istruzione SQL o una stored procedure per ogni riga modificata in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-116">Command parameters can be used to specify input and output values for an SQL statement or stored procedure for each modified row in a `DataSet`.</span></span> <span data-ttu-id="d82b5-117">Per ulteriori informazioni, vedere [DataAdapter Parameters](dataadapter-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d82b5-117">For more information, see [DataAdapter Parameters](dataadapter-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d82b5-118">È importante capire la differenza tra eliminazione di una riga in un oggetto <xref:System.Data.DataTable> e rimozione della riga.</span><span class="sxs-lookup"><span data-stu-id="d82b5-118">It is important to understand the difference between deleting a row in a <xref:System.Data.DataTable> and removing the row.</span></span> <span data-ttu-id="d82b5-119">Quando si chiama il metodo `Remove` o `RemoveAt`, la riga viene rimossa immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d82b5-119">When you call the `Remove` or `RemoveAt` method, the row is removed immediately.</span></span> <span data-ttu-id="d82b5-120">Eventuali righe corrispondenti nell'origine dati di back-end non saranno interessate se si passa `DataTable` o `DataSet` a un oggetto `DataAdapter` e si chiama `Update`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-120">Any corresponding rows in the back end data source will not be affected if you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`.</span></span> <span data-ttu-id="d82b5-121">Quando si usa il metodo `Delete`, la riga rimane in `DataTable` e viene contrassegnato per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d82b5-121">When you use the `Delete` method, the row remains in the `DataTable` and is marked for deletion.</span></span> <span data-ttu-id="d82b5-122">Se quindi si passa `DataTable` o `DataSet` a un oggetto `DataAdapter` e si chiama `Update`, la riga corrispondente nell'origine dati di back-end verrà eliminata.</span><span class="sxs-lookup"><span data-stu-id="d82b5-122">If you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`, the corresponding row in the back end data source is deleted.</span></span>

<span data-ttu-id="d82b5-123">Se `DataTable` esegue il mapping o viene generato da una singola tabella di database, è possibile usare l'oggetto <xref:System.Data.Common.DbCommandBuilder> per generare automaticamente gli oggetti `DeleteCommand`, `InsertCommand` e `UpdateCommand` di `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-123">If your `DataTable` maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` objects for the `DataAdapter`.</span></span> <span data-ttu-id="d82b5-124">Per altre informazioni, vedere [generazione di comandi con CommandBuilder](generating-commands-with-commandbuilders.md).</span><span class="sxs-lookup"><span data-stu-id="d82b5-124">For more information, see [Generating Commands with CommandBuilders](generating-commands-with-commandbuilders.md).</span></span>

## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a><span data-ttu-id="d82b5-125">Uso di UpdatedRowSource per eseguire il mapping di valori su un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="d82b5-125">Using UpdatedRowSource to Map Values to a DataSet</span></span>

<span data-ttu-id="d82b5-126">Per controllare come viene eseguito il mapping dei valori restituiti dall'origine dati su un oggetto `DataTable` in seguito a una chiamata al metodo Update di un oggetto `DataAdapter`, è possibile usare la proprietà <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> dell'oggetto <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="d82b5-126">You can control how the values returned from the data source are mapped back to the `DataTable` following a call to the Update method of a `DataAdapter`, by using the <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> property of a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="d82b5-127">Impostando la proprietà `UpdatedRowSource` su uno dei valori di enumerazione <xref:System.Data.UpdateRowSource>, è possibile controllare se i parametri restituiti dai comandi di `DataAdapter` vengono ignorati o applicati alla riga modificata in `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-127">By setting the `UpdatedRowSource` property to one of the <xref:System.Data.UpdateRowSource> enumeration values, you can control whether output parameters returned by the `DataAdapter` commands are ignored or applied to the changed row in the `DataSet`.</span></span> <span data-ttu-id="d82b5-128">È possibile inoltre specificare se la prima riga restituita (se esiste) viene applicata alla riga modificata in `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-128">You can also specify whether the first returned row (if it exists) is applied to the changed row in the `DataTable`.</span></span>

<span data-ttu-id="d82b5-129">La tabella seguente descrive i diversi valori dell'enumerazione `UpdateRowSource` e viene illustrato il modo in cui influenzano il comportamento di un comando usato con un `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-129">The following table describes the different values of the `UpdateRowSource` enumeration and how they affect the behavior of a command used with a `DataAdapter`.</span></span>

|<span data-ttu-id="d82b5-130">Enumerazione UpdatedRowSource</span><span class="sxs-lookup"><span data-stu-id="d82b5-130">UpdatedRowSource Enumeration</span></span>|<span data-ttu-id="d82b5-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d82b5-131">Description</span></span>|
|----------------------------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|<span data-ttu-id="d82b5-132">È possibile eseguire il mapping dei parametri di output e della prima riga di un set di risultati restituiti sulla riga modificata nel `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-132">Both the output parameters and the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|<span data-ttu-id="d82b5-133">È possibile eseguire il mapping sulla riga modificata nel `DataSet` solo dei dati nella prima riga di un set di risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="d82b5-133">Only the data in the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.None>|<span data-ttu-id="d82b5-134">Tutti i parametri di output, o righe, di un set di risultati restituiti vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-134">Any output parameters or rows of a returned result set are ignored.</span></span>|
|<xref:System.Data.UpdateRowSource.OutputParameters>|<span data-ttu-id="d82b5-135">È possibile eseguire il mapping sulla riga modificata nel `DataSet` solo dei parametri di output.</span><span class="sxs-lookup"><span data-stu-id="d82b5-135">Only output parameters may be mapped to the changed row in the `DataSet`.</span></span>|

<span data-ttu-id="d82b5-136">Il metodo `Update` applica le modifiche nell'origine dati, ma è possibile che altri client abbiano modificato i dati nell'origine dati dall'ultima volta che è stato compilato il `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-136">The `Update` method resolves your changes back to the data source; however other clients may have modified data at the data source since the last time you filled the `DataSet`.</span></span> <span data-ttu-id="d82b5-137">Per aggiornare `DataSet` con i dati correnti, usare i metodi `DataAdapter` e `Fill`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-137">To refresh your `DataSet` with current data, use the `DataAdapter` and `Fill` method.</span></span> <span data-ttu-id="d82b5-138">Le nuove righe verranno aggiunte alla tabella e le informazioni aggiornate verranno inserite nelle righe esistenti.</span><span class="sxs-lookup"><span data-stu-id="d82b5-138">New rows will be added to the table, and updated information will be incorporated into existing rows.</span></span> <span data-ttu-id="d82b5-139">Quando si esegue il metodo `Fill`, verrà determinato se aggiungere una nuova riga o aggiornare una riga esistente esaminando i valori delle chiavi primarie delle righe del `DataSet` e delle righe restituite da `SelectCommand`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-139">The `Fill` method determines whether a new row will be added or an existing row will be updated by examining the primary key values of the rows in the `DataSet` and the rows returned by the `SelectCommand`.</span></span> <span data-ttu-id="d82b5-140">Se il metodo `Fill` rileva un valore di chiave primaria di una riga del `DataSet` che corrisponde al valore di chiave primaria di una riga presente nei risultati restituiti da `SelectCommand`, la riga esistente verrà aggiornata con le informazioni presenti nella riga restituita da `SelectCommand` e la proprietà <xref:System.Data.DataRow.RowState%2A> della riga esistente verrà impostata su `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-140">If the `Fill` method encounters a primary key value for a row in the `DataSet` that matches a primary key value from a row in the results returned by the `SelectCommand`, it updates the existing row with the information from the row returned by the `SelectCommand` and sets the <xref:System.Data.DataRow.RowState%2A> of the existing row to `Unchanged`.</span></span> <span data-ttu-id="d82b5-141">Se una riga restituita da `SelectCommand` presenta un valore di chiave primaria che non corrisponde ad alcuno dei valori di chiave primaria delle righe del `DataSet`, il metodo `Fill` aggiungerà una nuova riga con il valore relativo a `RowState` impostato su `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-141">If a row returned by the `SelectCommand` has a primary key value that does not match any of the primary key values of the rows in the `DataSet`, the `Fill` method adds a new row with a `RowState` of `Unchanged`.</span></span>

> [!NOTE]
> <span data-ttu-id="d82b5-142">Se `SelectCommand` restituisce i risultati di un OUTER JOIN, il `DataAdapter` non imposterà un valore `PrimaryKey` per l'oggetto `DataTable` risultante.</span><span class="sxs-lookup"><span data-stu-id="d82b5-142">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` will not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="d82b5-143">Per assicurarsi che le righe duplicate vengano risolte correttamente, sarà necessario definire `PrimaryKey` in modo autonomo.</span><span class="sxs-lookup"><span data-stu-id="d82b5-143">You must define the `PrimaryKey` yourself to ensure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="d82b5-144">Per ulteriori informazioni, vedere [definizione delle chiavi primarie](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="d82b5-144">For more information, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>

<span data-ttu-id="d82b5-145">Per gestire le eccezioni che possono verificarsi quando si chiama il `Update` metodo, è possibile usare l' `RowUpdated` evento per rispondere agli errori di aggiornamento delle righe nel momento in cui si verificano (vedere [gestione di eventi DataAdapter](handling-dataadapter-events.md)) oppure impostare `DataAdapter.ContinueUpdateOnError` su `true` prima di chiamare `Update` e rispondere alle informazioni sugli errori archiviate nella `RowError` proprietà di una determinata riga al termine dell'aggiornamento (vedere [informazioni sugli errori di riga](./dataset-datatable-dataview/row-error-information.md)).</span><span class="sxs-lookup"><span data-stu-id="d82b5-145">To handle exceptions that may occur when calling the `Update` method, you can use the `RowUpdated` event to respond to row update errors as they occur (see [Handling DataAdapter Events](handling-dataadapter-events.md)), or you can set `DataAdapter.ContinueUpdateOnError` to `true` before calling `Update`, and respond to the error information stored in the `RowError` property of a particular row when the update is complete (see [Row Error Information](./dataset-datatable-dataview/row-error-information.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="d82b5-146">Se `AcceptChanges` si chiama su `DataSet` , `DataTable` o, `DataRow` tutti `Original` i valori per un oggetto `DataRow` verranno sovrascritti con i `Current` valori per l'oggetto `DataRow` .</span><span class="sxs-lookup"><span data-stu-id="d82b5-146">Calling `AcceptChanges` on the `DataSet`, `DataTable`, or `DataRow` will cause all `Original` values for a `DataRow` to be overwritten with the `Current` values for the `DataRow`.</span></span> <span data-ttu-id="d82b5-147">Se i valori di campo che identificano la riga come univoca sono stati modificati, dopo la chiamata a `AcceptChanges` i valori `Original` non corrisponderanno più ai valori dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-147">If the field values that identify the row as unique have been modified, after calling `AcceptChanges` the `Original` values will no longer match the values in the data source.</span></span> <span data-ttu-id="d82b5-148">`AcceptChanges` viene chiamato automaticamente per ogni riga durante una chiamata al metodo Update di un oggetto `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-148">`AcceptChanges` is called automatically for each row during a call to the Update method of a `DataAdapter`.</span></span> <span data-ttu-id="d82b5-149">Per mantenere i valori originali durante una chiamata al metodo Update, impostare prima la proprietà `AcceptChangesDuringUpdate` di `DataAdapter` su false oppure creare un gestore eventi per l'evento `RowUpdated` e impostare <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> su <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span><span class="sxs-lookup"><span data-stu-id="d82b5-149">You can preserve the original values during a call to the Update method by first setting the `AcceptChangesDuringUpdate` property of the `DataAdapter` to false, or by creating an event handler for the `RowUpdated` event and setting the <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> to <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span></span> <span data-ttu-id="d82b5-150">Per ulteriori informazioni, vedere [Unione di contenuto del set di dati](./dataset-datatable-dataview/merging-dataset-contents.md) e [gestione di eventi DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="d82b5-150">For more information, see [Merging DataSet Contents](./dataset-datatable-dataview/merging-dataset-contents.md) and [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="d82b5-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="d82b5-151">Example</span></span>

<span data-ttu-id="d82b5-152">Negli esempi seguenti viene illustrato come eseguire gli aggiornamenti delle righe modificate impostando in modo esplicito l'oggetto `UpdateCommand` di un oggetto `DataAdapter` e chiamando il relativo `Update` metodo.</span><span class="sxs-lookup"><span data-stu-id="d82b5-152">The following examples demonstrate how to perform updates to modified rows by explicitly setting the `UpdateCommand` of a `DataAdapter` and calling its `Update` method.</span></span> <span data-ttu-id="d82b5-153">Notare che il parametro specificato nella clausola WHERE dell'istruzione UPDATE viene impostato in modo da usare il valore `Original` di `SourceColumn`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-153">Notice that the parameter specified in the WHERE clause of the UPDATE statement is set to use the `Original` value of the `SourceColumn`.</span></span> <span data-ttu-id="d82b5-154">Questo è importante in quanto è possibile che il valore `Current` sia stato modificato e che non corrisponda più al valore nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-154">This is important, because the `Current` value may have been modified and may not match the value in the data source.</span></span> <span data-ttu-id="d82b5-155">Il valore `Original` è il valore che è stato usato per compilare `DataTable` dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-155">The `Original` value is the value that was used to populate the `DataTable` from the data source.</span></span>

[!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]

## <a name="autoincrement-columns"></a><span data-ttu-id="d82b5-156">Colonne AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="d82b5-156">AutoIncrement Columns</span></span>

<span data-ttu-id="d82b5-157">Se nelle tabelle dell'origine dati sono presenti colonne con incremento automatico, è possibile riempire le colonne nel `DataSet` restituendo il valore dell'incremento automatico come un parametro di output di una stored procedure ed eseguendone il mapping su una colonna della tabella, restituendo il valore dell'incremento automatico nella prima riga di un set di risultati restituito da una stored procedure o un'istruzione SQL oppure usando l'evento `RowUpdated` di `DataAdapter` per eseguire un'ulteriore istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="d82b5-157">If the tables from your data source have auto-incrementing columns, you can fill the columns in your `DataSet` either by returning the auto-increment value as an output parameter of a stored procedure and mapping that to a column in a table, by returning the auto-increment value in the first row of a result set returned by a stored procedure or SQL statement, or by using the `RowUpdated` event of the `DataAdapter` to execute an additional SELECT statement.</span></span> <span data-ttu-id="d82b5-158">Per ulteriori informazioni e un esempio, vedere [recupero di valori Identity o Autonumber](retrieving-identity-or-autonumber-values.md).</span><span class="sxs-lookup"><span data-stu-id="d82b5-158">For more information and an example, see [Retrieving Identity or Autonumber Values](retrieving-identity-or-autonumber-values.md).</span></span>

## <a name="ordering-of-inserts-updates-and-deletes"></a><span data-ttu-id="d82b5-159">Ordine di Insert, Update e Delete</span><span class="sxs-lookup"><span data-stu-id="d82b5-159">Ordering of Inserts, Updates, and Deletes</span></span>

<span data-ttu-id="d82b5-160">In molti casi l'ordine in cui le modifiche apportate mediante `DataSet` vengono inviate all'origine dati è importante.</span><span class="sxs-lookup"><span data-stu-id="d82b5-160">In many circumstances, the order in which changes made through the `DataSet` are sent to the data source is important.</span></span> <span data-ttu-id="d82b5-161">Se ad esempio il valore di una chiave primaria relativo a una riga esistente viene aggiornato ed è stata aggiunta una nuova riga con il nuovo valore della chiave primaria come chiave esterna, è importante elaborare l'aggiornamento prima di effettuare l'inserimento.</span><span class="sxs-lookup"><span data-stu-id="d82b5-161">For example, if a primary key value for an existing row is updated, and a new row has been added with the new primary key value as a foreign key, it is important to process the update before the insert.</span></span>

<span data-ttu-id="d82b5-162">È possibile usare il metodo `Select` di `DataTable` per restituire una matrice `DataRow` che faccia riferimento solo a righe con un particolare `RowState`.</span><span class="sxs-lookup"><span data-stu-id="d82b5-162">You can use the `Select` method of the `DataTable` to return a `DataRow` array that only references rows with a particular `RowState`.</span></span> <span data-ttu-id="d82b5-163">È quindi possibile passare la matrice `DataRow` restituita al metodo `Update` di `DataAdapter` per elaborare le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="d82b5-163">You can then pass the returned `DataRow` array to the `Update` method of the `DataAdapter` to process the modified rows.</span></span> <span data-ttu-id="d82b5-164">Se si specifica un subset di righe da aggiornare, è possibile controllare l'ordine in cui vengono elaborati gli inserimenti, gli aggiornamenti e le eliminazioni.</span><span class="sxs-lookup"><span data-stu-id="d82b5-164">By specifying a subset of rows to be updated, you can control the order in which inserts, updates, and deletes are processed.</span></span>

## <a name="example"></a><span data-ttu-id="d82b5-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="d82b5-165">Example</span></span>

<span data-ttu-id="d82b5-166">Il codice seguente, ad esempio, assicura che vengano elaborate prima le righe cancellate della tabella, quindi le righe aggiornate e infine le righe inserite.</span><span class="sxs-lookup"><span data-stu-id="d82b5-166">For example, the following code ensures that the deleted rows of the table are processed first, then the updated rows, and then the inserted rows.</span></span>

```vb
Dim table As DataTable = dataSet.Tables("Customers")

' First process deletes.
dataSet.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Deleted))

' Next process updates.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.ModifiedCurrent))

' Finally, process inserts.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Added))
```

```csharp
DataTable table = dataSet.Tables["Customers"];

// First process deletes.
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));

// Next process updates.
adapter.Update(table.Select(null, null,
  DataViewRowState.ModifiedCurrent));

// Finally, process inserts.
adapter.Update(table.Select(null, null, DataViewRowState.Added));
```

## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a><span data-ttu-id="d82b5-167">Uso di un oggetto DataAdapter per recuperare e aggiornare dati</span><span class="sxs-lookup"><span data-stu-id="d82b5-167">Use a DataAdapter to Retrieve and Update Data</span></span>

<span data-ttu-id="d82b5-168">È possibile usare un oggetto DataAdapter per recuperare e aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="d82b5-168">You can use a DataAdapter to retrieve and update the data.</span></span>

- <span data-ttu-id="d82b5-169">Nell'esempio viene usato DataAdapter.AcceptChangesDuringFill per clonare i dati nel database.</span><span class="sxs-lookup"><span data-stu-id="d82b5-169">The sample uses DataAdapter.AcceptChangesDuringFill to clone the data in the database.</span></span> <span data-ttu-id="d82b5-170">Se la proprietà è impostata su false, AcceptChanges non viene chiamato quando viene compilata la tabella e le righe appena aggiunte sono considerate righe inserite.</span><span class="sxs-lookup"><span data-stu-id="d82b5-170">If the property is set as false, AcceptChanges is not called when filling the table, and the newly added rows are treated as inserted rows.</span></span> <span data-ttu-id="d82b5-171">Di conseguenza, nell'esempio queste righe vengono usate per inserire nuove righe nel database.</span><span class="sxs-lookup"><span data-stu-id="d82b5-171">So, the sample uses these rows to insert the new rows into the database.</span></span>

- <span data-ttu-id="d82b5-172">Negli esempi viene usato DataAdapter.TableMappings per definire il mapping tra la tabella di origine e DataTable.</span><span class="sxs-lookup"><span data-stu-id="d82b5-172">The samples uses DataAdapter.TableMappings to define the mapping between the source table and DataTable.</span></span>

- <span data-ttu-id="d82b5-173">Nell'esempio viene usato DataAdapter.FillLoadOption per determinare come l'adattatore riempie l'elemento DataTable dall'elemento DbDataReader.</span><span class="sxs-lookup"><span data-stu-id="d82b5-173">The sample uses DataAdapter.FillLoadOption to determine how the adapter fills the DataTable from the DbDataReader.</span></span> <span data-ttu-id="d82b5-174">Quando si crea un oggetto DataTable, è possibile scrivere i dati solo da un database alla versione corrente o alla versione originale impostando la proprietà come LoadOption.Upsert o LoadOption.PreserveChanges.</span><span class="sxs-lookup"><span data-stu-id="d82b5-174">When you create a DataTable, you can only write the data from database to the current version or the original version by setting the property as the LoadOption.Upsert or the LoadOption.PreserveChanges.</span></span>

- <span data-ttu-id="d82b5-175">Viene inoltre aggiornata la tabella usando DbDataAdapter.UpdateBatchSize per eseguire operazioni batch.</span><span class="sxs-lookup"><span data-stu-id="d82b5-175">The sample will also update the table by using DbDataAdapter.UpdateBatchSize to perform batch operations.</span></span>

<span data-ttu-id="d82b5-176">Prima di compilare ed eseguire l'esempio, è necessario creare il database di esempio:</span><span class="sxs-lookup"><span data-stu-id="d82b5-176">Before you compile and run the sample, you need to create the sample database:</span></span>

```sql
USE [master]
GO

CREATE DATABASE [MySchool]

GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)

SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF

ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
```

<span data-ttu-id="d82b5-177">I progetti C# e Visual Basic con questo esempio di codice sono disponibili in [esempi di codice per sviluppatori](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span><span class="sxs-lookup"><span data-stu-id="d82b5-177">C# and Visual Basic projects with this code sample can be found on [Developer Code Samples](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.SqlClient;
using System.Linq;
using CSDataAdapterOperations.Properties;

namespace CSDataAdapterOperations.Properties {
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {

      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));

      public static Settings Default {
         get {
            return defaultInstance;
         }
      }

      [global::System.Configuration.ApplicationScopedSettingAttribute()]
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]
      public string MySchoolConnectionString {
         get {
            return ((string)(this["MySchoolConnectionString"]));
         }
      }
   }
}

class Program {
   static void Main(string[] args) {
      Settings settings = new Settings();

      // Copy the data from the database.  Get the table Department and Course from the database.
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]
                                     FROM [MySchool].[dbo].[Department];

                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]
                                   FROM [MySchool].[dbo].[Course]
                                   Group by [CourseID]";

      DataSet mySchool = new DataSet();

      SqlCommand selectCommand = new SqlCommand(selectString);
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);

      // Use DataTableMapping to map the source tables and the destination tables.
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);

      Console.WriteLine("The following tables are from the database.");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      // Roll back the changes
      DataTable department = mySchool.Tables["Department"];
      DataTable course = mySchool.Tables["Course"];

      department.Rows[0]["Name"] = "New" + department.Rows[0][1];
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];
      course.Rows[0]["Credits"] = 10;

      Console.WriteLine("After we changed the tables:");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      department.RejectChanges();
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");
      ShowDataTable(department);

      DataColumn[] primaryColumns = { course.Columns["CourseID"] };
      DataColumn[] resetColumns = { course.Columns["Title"] };
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");
      ShowDataTable(course);

      // Batch update the table.
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],
                                   [Credits],[DepartmentID])
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";
      SqlCommand insertCommand = new SqlCommand(insertString);
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");

      const Int32 batchSize = 10;
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);
   }

   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a
            // DataRow after it is added to the DataTable during any of the Fill operations.
            adapter.AcceptChangesDuringFill = false;

            adapter.Fill(dataSet);
         }
      }
   }

   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.
   private static void ResetCourse(DataTable table, String connectionString,
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {
      table.PrimaryKey = primaryColumns;

      // Build the query string
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));

      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");

      SqlCommand selectCommand = new SqlCommand(selectString);

      ResetDataTable(table, connectionString, selectCommand);
   }

   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges
   // The ResetDataTable method rolls back one or more columns of data.
   private static void ResetDataTable(DataTable table, String connectionString,
       SqlCommand selectCommand) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {
            // The incoming values for this row will be written to the current version of each
            // column. The original version of each column's data will not be changed.
            adapter.FillLoadOption = LoadOption.Upsert;

            adapter.Fill(table);
         }
      }
   }

   private static void BatchInsertUpdate(DataTable table, String connectionString,
       SqlCommand insertCommand, Int32 batchSize) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         insertCommand.Connection = connection;
         // When setting UpdateBatchSize to a value other than 1, all the commands
         // associated with the SqlDataAdapter have to have their UpdatedRowSource
         // property set to None or OutputParameters. An exception is thrown otherwise.
         insertCommand.UpdatedRowSource = UpdateRowSource.None;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter()) {
            adapter.InsertCommand = insertCommand;
            // Gets or sets the number of rows that are processed in each round-trip to the server.
            // Setting it to 1 disables batch updates, as rows are sent one at a time.
            adapter.UpdateBatchSize = batchSize;

            adapter.Update(table);

            Console.WriteLine("Successfully to update the table.");
         }
      }
   }

   private static void ShowDataTable(DataTable table) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-14}", col.ColumnName);
      }
      Console.WriteLine("{0,-14}", "RowState");

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-14:d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-14:C}", row[col]);
            else
               Console.Write("{0,-14}", row[col]);
         }
         Console.WriteLine("{0,-14}", row.RowState);
      }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="d82b5-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82b5-178">See also</span></span>

- [<span data-ttu-id="d82b5-179">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="d82b5-179">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="d82b5-180">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="d82b5-180">Row States and Row Versions</span></span>](./dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="d82b5-181">AcceptChanges e RejectChanges</span><span class="sxs-lookup"><span data-stu-id="d82b5-181">AcceptChanges and RejectChanges</span></span>](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [<span data-ttu-id="d82b5-182">Unione di contenuti di set di dati</span><span class="sxs-lookup"><span data-stu-id="d82b5-182">Merging DataSet Contents</span></span>](./dataset-datatable-dataview/merging-dataset-contents.md)
- [<span data-ttu-id="d82b5-183">Recupero di identità o di valori numerati automaticamente</span><span class="sxs-lookup"><span data-stu-id="d82b5-183">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)
- [<span data-ttu-id="d82b5-184">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d82b5-184">ADO.NET Overview</span></span>](ado-net-overview.md)
