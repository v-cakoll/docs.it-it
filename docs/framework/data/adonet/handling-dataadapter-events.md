---
title: Gestione di eventi DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 11515b25-ee49-4b1d-9294-a142147c1ec5
ms.openlocfilehash: d01198d158c4e1c64f12e8a0756c3d4e599fce74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149544"
---
# <a name="handling-dataadapter-events"></a><span data-ttu-id="1cf45-102">Gestione di eventi DataAdapter</span><span class="sxs-lookup"><span data-stu-id="1cf45-102">Handling DataAdapter Events</span></span>
<span data-ttu-id="1cf45-103"><xref:System.Data.Common.DataAdapter> di ADO.NET espone tre eventi che è possibile usare per rispondere alle modifiche apportate ai dati nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1cf45-103">The ADO.NET <xref:System.Data.Common.DataAdapter> exposes three events that you can use to respond to changes made to data at the data source.</span></span> <span data-ttu-id="1cf45-104">Nella tabella seguente vengono descritti gli eventi di `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-104">The following table shows the `DataAdapter` events.</span></span>  
  
|<span data-ttu-id="1cf45-105">Event</span><span class="sxs-lookup"><span data-stu-id="1cf45-105">Event</span></span>|<span data-ttu-id="1cf45-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cf45-106">Description</span></span>|  
|-----------|-----------------|  
|`RowUpdating`|<span data-ttu-id="1cf45-107">Sta per iniziare un'operazione UPDATE, INSERT o DELETE su una riga tramite la chiamata a uno dei metodi `Update`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-107">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is about to begin.</span></span>|  
|`RowUpdated`|<span data-ttu-id="1cf45-108">È stata completata un'operazione UPDATE, INSERT o DELETE su una riga tramite la chiamata a uno dei metodi `Update`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-108">An UPDATE, INSERT, or DELETE operation on a row (by a call to one of the `Update` methods) is complete.</span></span>|  
|`FillError`|<span data-ttu-id="1cf45-109">Si è verificato un errore durante un'operazione `Fill`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-109">An error has occurred during a `Fill` operation.</span></span>|  
  
## <a name="rowupdating-and-rowupdated"></a><span data-ttu-id="1cf45-110">RowUpdating e RowUpdated</span><span class="sxs-lookup"><span data-stu-id="1cf45-110">RowUpdating and RowUpdated</span></span>  
 <span data-ttu-id="1cf45-111">`RowUpdating` viene generato prima che un aggiornamento a una riga di <xref:System.Data.DataSet> sia stato elaborato nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1cf45-111">`RowUpdating` is raised before any update to a row from the <xref:System.Data.DataSet> has been processed at the data source.</span></span> <span data-ttu-id="1cf45-112">`RowUpdated` viene generato dopo che un aggiornamento a una riga di `DataSet` è stato elaborato nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1cf45-112">`RowUpdated` is raised after any update to a row from the `DataSet` has been processed at the data source.</span></span> <span data-ttu-id="1cf45-113">Di conseguenza, è possibile usare `RowUpdating` per modificare il comportamento dell'aggiornamento prima che venga eseguito, in modo da fornire una gestione aggiuntiva quando verrà eseguito l'aggiornamento, conservare un riferimento a una riga aggiornata, annullare l'aggiornamento corrente e pianificarlo per un processo in batch che verrà eseguito successivamente e così via.</span><span class="sxs-lookup"><span data-stu-id="1cf45-113">As a result, you can use `RowUpdating` to modify update behavior before it happens, to provide additional handling when an update will occur, to retain a reference to an updated row, to cancel the current update and schedule it for a batch process to be processed later, and so on.</span></span> <span data-ttu-id="1cf45-114">`RowUpdated` risulta utile per rispondere a errori ed eccezioni che si verificano durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1cf45-114">`RowUpdated` is useful for responding to errors and exceptions that occur during the update.</span></span> <span data-ttu-id="1cf45-115">È possibile aggiungere le informazioni sugli errori al `DataSet` così come riprovare la logica e così via.</span><span class="sxs-lookup"><span data-stu-id="1cf45-115">You can add error information to the `DataSet`, as well as retry logic, and so on.</span></span>  
  
 <span data-ttu-id="1cf45-116">Gli argomenti <xref:System.Data.Common.RowUpdatingEventArgs> e <xref:System.Data.Common.RowUpdatedEventArgs> passati agli eventi `RowUpdating` e `RowUpdated` includono una proprietà `Command` che fa riferimento all'oggetto `Command` usato per eseguire l'aggiornamento, una proprietà `Row` che fa riferimento all'oggetto `DataRow` contenente le informazioni aggiornate, una proprietà `StatementType` relativa al tipo di aggiornamento eseguito, l'oggetto `TableMapping`, se applicabile, e lo `Status` dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-116">The <xref:System.Data.Common.RowUpdatingEventArgs> and <xref:System.Data.Common.RowUpdatedEventArgs> arguments passed to the `RowUpdating` and `RowUpdated` events include the following: a `Command` property that references the `Command` object being used to perform the update; a `Row` property that references the `DataRow` object containing the updated information; a `StatementType` property for what type of update is being performed; the `TableMapping`, if applicable; and the `Status` of the operation.</span></span>  
  
 <span data-ttu-id="1cf45-117">È possibile usare la proprietà `Status` per determinare se si è verificato un errore durante l'operazione ed eventualmente per controllare le operazioni relative alle righe correnti e risultanti.</span><span class="sxs-lookup"><span data-stu-id="1cf45-117">You can use the `Status` property to determine if an error has occurred during the operation and, if desired, to control the actions against the current and resulting rows.</span></span> <span data-ttu-id="1cf45-118">Quando si verifica l'evento, la proprietà `Status` sarà uguale a `Continue` o `ErrorsOccurred`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-118">When the event occurs, the `Status` property equals either `Continue` or `ErrorsOccurred`.</span></span> <span data-ttu-id="1cf45-119">Nella tabella seguente sono indicati i valori su cui è possibile impostare la proprietà `Status` per controllare le operazioni successive durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1cf45-119">The following table shows the values to which you can set the `Status` property in order to control later actions during the update.</span></span>  
  
|<span data-ttu-id="1cf45-120">Stato</span><span class="sxs-lookup"><span data-stu-id="1cf45-120">Status</span></span>|<span data-ttu-id="1cf45-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cf45-121">Description</span></span>|  
|------------|-----------------|  
|`Continue`|<span data-ttu-id="1cf45-122">Continua l'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1cf45-122">Continue the update operation.</span></span>|  
|`ErrorsOccurred`|<span data-ttu-id="1cf45-123">Interrompe l'operazione di aggiornamento e genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-123">Abort the update operation and throw an exception.</span></span>|  
|`SkipCurrentRow`|<span data-ttu-id="1cf45-124">Ignora la riga corrente e continua l'operazione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1cf45-124">Ignore the current row and continue the update operation.</span></span>|  
|`SkipAllRemainingRows`|<span data-ttu-id="1cf45-125">Interrompe l'operazione di aggiornamento, ma non genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-125">Abort the update operation but do not throw an exception.</span></span>|  
  
 <span data-ttu-id="1cf45-126">Se si imposta la proprietà `Status` su `ErrorsOccurred`, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-126">Setting the `Status` property to `ErrorsOccurred` causes an exception to be thrown.</span></span> <span data-ttu-id="1cf45-127">È possibile controllare l'eccezione generata impostando la proprietà `Errors` sull'eccezione desiderata.</span><span class="sxs-lookup"><span data-stu-id="1cf45-127">You can control which exception is thrown by setting the `Errors` property to the desired exception.</span></span> <span data-ttu-id="1cf45-128">Se si usa uno degli altri valori di `Status` non verrà generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-128">Using one of the other values for `Status` prevents an exception from being thrown.</span></span>  
  
 <span data-ttu-id="1cf45-129">È inoltre possibile usare la proprietà `ContinueUpdateOnError` per gestire gli errori relativi alle righe aggiornate.</span><span class="sxs-lookup"><span data-stu-id="1cf45-129">You can also use the `ContinueUpdateOnError` property to handle errors for updated rows.</span></span> <span data-ttu-id="1cf45-130">Se `DataAdapter.ContinueUpdateOnError` è `true`, quando un aggiornamento di una riga determina la generazione di un'eccezione, il testo dell'eccezione viene inserito nelle informazioni `RowError` della stessa riga e l'elaborazione continua senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-130">If `DataAdapter.ContinueUpdateOnError` is `true`, when an update to a row results in an exception being thrown, the text of the exception is placed into the `RowError` information of the particular row, and processing continues without throwing an exception.</span></span> <span data-ttu-id="1cf45-131">In questo modo è possibile rispondere agli errori quando l'evento `Update` è completato, a differenza di quanto avviene con l'evento `RowUpdated` che consente di rispondere agli errori nel momento in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="1cf45-131">This enables you to respond to errors when the `Update` is complete, in contrast to the `RowUpdated` event, which enables you to respond to errors when the error is encountered.</span></span>  
  
 <span data-ttu-id="1cf45-132">Nell'esempio di codice seguente viene illustrato come aggiungere e rimuovere i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="1cf45-132">The following code sample shows how to both add and remove event handlers.</span></span> <span data-ttu-id="1cf45-133">Il gestore dell'evento `RowUpdating` scrive un log di tutti i record eliminati con un timestamp.</span><span class="sxs-lookup"><span data-stu-id="1cf45-133">The `RowUpdating` event handler writes a log of all deleted records with a time stamp.</span></span> <span data-ttu-id="1cf45-134">Il `RowUpdated` gestore eventi aggiunge `RowError` informazioni sull'errore `DataSet`alla proprietà della riga in , elimina `ContinueUpdateOnError`  =  `true`l'eccezione e continua l'elaborazione (mirroring del comportamento di ).</span><span class="sxs-lookup"><span data-stu-id="1cf45-134">The `RowUpdated` event handler adds error information to the `RowError` property of the row in the `DataSet`, suppresses the exception, and continues processing (mirroring the behavior of `ContinueUpdateOnError` = `true`).</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
' Add handlers.  
AddHandler custAdapter.RowUpdating, New SqlRowUpdatingEventHandler( _  
  AddressOf OnRowUpdating)  
AddHandler custAdapter.RowUpdated, New SqlRowUpdatedEventHandler(  
  AddressOf OnRowUpdated)  
  
' Set DataAdapter command properties, fill DataSet, and modify DataSet.  
  
custAdapter.Update(custDS, "Customers")  
  
' Remove handlers.  
RemoveHandler custAdapter.RowUpdating, _  
  New SqlRowUpdatingEventHandler(AddressOf OnRowUpdating)  
RemoveHandler custAdapter.RowUpdated, _  
  New SqlRowUpdatedEventHandler(AddressOf OnRowUpdated)  
  
Private Shared Sub OnRowUpdating(sender As Object, _  
  args As SqlRowUpdatingEventArgs)  
  If args.StatementType = StatementType.Delete Then  
    Dim tw As System.IO.TextWriter = _  
  System.IO.File.AppendText("Deletes.log")  
    tw.WriteLine( _  
      "{0}: Customer {1} Deleted.", DateTime.Now, args.Row(_  
      "CustomerID", DataRowVersion.Original))  
    tw.Close()  
  End If  
End Sub  
  
Private Shared Sub OnRowUpdated( _  
  sender As Object, args As SqlRowUpdatedEventArgs)  
  If args.Status = UpdateStatus.ErrorsOccurred  
    args.Status = UpdateStatus.SkipCurrentRow  
    args.Row.RowError = args.Errors.Message  
  End If  
End Sub  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
// Add handlers.  
custAdapter.RowUpdating += new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
// Set DataAdapter command properties, fill DataSet, modify DataSet.  
  
custAdapter.Update(custDS, "Customers");  
  
// Remove handlers.  
custAdapter.RowUpdating -= new SqlRowUpdatingEventHandler(OnRowUpdating);  
custAdapter.RowUpdated -= new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
protected static void OnRowUpdating(  
  object sender, SqlRowUpdatingEventArgs args)  
{  
  if (args.StatementType == StatementType.Delete)  
  {  
    System.IO.TextWriter tw = System.IO.File.AppendText("Deletes.log");  
    tw.WriteLine(  
      "{0}: Customer {1} Deleted.", DateTime.Now,
       args.Row["CustomerID", DataRowVersion.Original]);  
    tw.Close();  
  }  
}  
  
protected static void OnRowUpdated(  
  object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.Status == UpdateStatus.ErrorsOccurred)  
  {  
    args.Row.RowError = args.Errors.Message;  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="fillerror"></a><span data-ttu-id="1cf45-135">FillError</span><span class="sxs-lookup"><span data-stu-id="1cf45-135">FillError</span></span>  
 <span data-ttu-id="1cf45-136">`DataAdapter` genera l'evento `FillError` quando si verifica un errore durante un'operazione `Fill`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-136">The `DataAdapter` issues the `FillError` event when an error occurs during a `Fill` operation.</span></span> <span data-ttu-id="1cf45-137">Questo tipo di errore si verifica solitamente quando i dati nella riga che viene aggiunta non possono essere convertiti in un tipo .NET Framework senza una perdita di precisione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-137">This type of error commonly occurs when the data in the row being added could not be converted to a .NET Framework type without some loss of precision.</span></span>  
  
 <span data-ttu-id="1cf45-138">Se si verifica un errore durante un'operazione `Fill`, la riga corrente non verrà aggiunta a `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-138">If an error occurs during a `Fill` operation, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="1cf45-139">L'evento `FillError` consente di risolvere l'errore e aggiungere la riga o di ignorare la riga esclusa e continuare l'operazione `Fill`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-139">The `FillError` event enables you to resolve the error and add the row, or to ignore the excluded row and continue the `Fill` operation.</span></span>  
  
 <span data-ttu-id="1cf45-140">`FillErrorEventArgs` passato all'evento `FillError` può contenere diverse proprietà che consentono di rispondere agli errori e di risolverli.</span><span class="sxs-lookup"><span data-stu-id="1cf45-140">The `FillErrorEventArgs` passed to the `FillError` event can contain several properties that enable you to respond to and resolve errors.</span></span> <span data-ttu-id="1cf45-141">Nella tabella seguente sono illustrate le proprietà dell'oggetto `FillErrorEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-141">The following table shows the properties of the `FillErrorEventArgs` object.</span></span>  
  
|<span data-ttu-id="1cf45-142">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1cf45-142">Property</span></span>|<span data-ttu-id="1cf45-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cf45-143">Description</span></span>|  
|--------------|-----------------|  
|`Errors`|<span data-ttu-id="1cf45-144">`Exception` generata.</span><span class="sxs-lookup"><span data-stu-id="1cf45-144">The `Exception` that occurred.</span></span>|  
|`DataTable`|<span data-ttu-id="1cf45-145">Oggetto `DataTable` in fase di riempimento quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="1cf45-145">The `DataTable` object being filled when the error occurred.</span></span>|  
|`Values`|<span data-ttu-id="1cf45-146">Matrice di oggetti contenente i valori della riga in fase di inserimento quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="1cf45-146">An array of objects that contains the values of the row being added when the error occurred.</span></span> <span data-ttu-id="1cf45-147">I riferimenti ordinali della matrice di `Values` corrispondono ai riferimenti ordinali delle colonne della riga che viene aggiunta.</span><span class="sxs-lookup"><span data-stu-id="1cf45-147">The ordinal references of the `Values` array correspond to the ordinal references of the columns of the row being added.</span></span> <span data-ttu-id="1cf45-148">`Values[0]`, ad esempio, è il valore che era stato aggiunto come prima colonna della riga.</span><span class="sxs-lookup"><span data-stu-id="1cf45-148">For example, `Values[0]` is the value that was being added as the first column of the row.</span></span>|  
|`Continue`|<span data-ttu-id="1cf45-149">Consente di scegliere se generare o meno una Exception.</span><span class="sxs-lookup"><span data-stu-id="1cf45-149">Allows you to choose whether or not to throw an exception.</span></span> <span data-ttu-id="1cf45-150">Se si imposta la proprietà `Continue` su `false`, l'operazione `Fill` corrente verrà interrotta e verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-150">Setting the `Continue` property to `false` will halt the current `Fill` operation, and an exception will be thrown.</span></span> <span data-ttu-id="1cf45-151">Se si imposta `Continue` su `true`, l'operazione `Fill` continuerà nonostante l'errore.</span><span class="sxs-lookup"><span data-stu-id="1cf45-151">Setting `Continue` to `true` continues the `Fill` operation despite the error.</span></span>|  
  
 <span data-ttu-id="1cf45-152">Nell'esempio di codice seguente viene aggiunto un gestore per l'evento `FillError` di `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="1cf45-152">The following code example adds an event handler for the `FillError` event of the `DataAdapter`.</span></span> <span data-ttu-id="1cf45-153">Nel codice dell'evento `FillError` viene determinato se esiste il rischio potenziale di una perdita di precisione e viene fornita la possibilità di rispondere all'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1cf45-153">In the `FillError` event code, the example determines if there is the potential for precision loss, providing the opportunity to respond to the exception.</span></span>  
  
```vb  
AddHandler adapter.FillError, New FillErrorEventHandler( _  
  AddressOf FillError)  
  
Dim dataSet As DataSet = New DataSet  
adapter.Fill(dataSet, "ThisTable")  
  
Private Shared Sub FillError(sender As Object, _  
  args As FillErrorEventArgs)  
  If args.Errors.GetType() Is Type.GetType("System.OverflowException") Then  
    ' Code to handle precision loss.  
    ' Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(New Object() _  
      {args.Values(0), args.Values(1), DBNull.Value})  
    ' Set the RowError containing the value for the third column.  
    myRow.RowError = _  
      "OverflowException encountered. Value from data source: " & _  
      args.Values(2)  
    args.Continue = True  
  End If  
End Sub  
```  
  
```csharp  
adapter.FillError += new FillErrorEventHandler(FillError);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "ThisTable");  
  
protected static void FillError(object sender, FillErrorEventArgs args)  
{  
  if (args.Errors.GetType() == typeof(System.OverflowException))  
  {  
    // Code to handle precision loss.  
    //Add a row to table using the values from the first two columns.  
    DataRow myRow = args.DataTable.Rows.Add(new object[]  
       {args.Values[0], args.Values[1], DBNull.Value});  
    //Set the RowError containing the value for the third column.  
    myRow.RowError =
       "OverflowException Encountered. Value from data source: " +  
       args.Values[2];  
    args.Continue = true;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cf45-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cf45-154">See also</span></span>

- [<span data-ttu-id="1cf45-155">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="1cf45-155">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="1cf45-156">Gestione di eventi dataset</span><span class="sxs-lookup"><span data-stu-id="1cf45-156">Handling DataSet Events</span></span>](./dataset-datatable-dataview/handling-dataset-events.md)
- [<span data-ttu-id="1cf45-157">Gestione di eventi DataTable</span><span class="sxs-lookup"><span data-stu-id="1cf45-157">Handling DataTable Events</span></span>](./dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="1cf45-158">Events</span><span class="sxs-lookup"><span data-stu-id="1cf45-158">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="1cf45-159">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cf45-159">ADO.NET Overview</span></span>](ado-net-overview.md)
