---
title: Stati e versioni delle righe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: d36556b62a95a7af1097d8fe88597569c81c0111
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="0bc55-102">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="0bc55-102">Row States and Row Versions</span></span>
<span data-ttu-id="0bc55-103">In ADO.NET le righe delle tabelle vengono gestite tramite gli stati e le versioni delle righe.</span><span class="sxs-lookup"><span data-stu-id="0bc55-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="0bc55-104">Lo stato di una riga indica lo stato corrente di una particolare riga. Le versioni delle righe consentono di mantenere i valori archiviati in una riga durante le modifiche. Vengono conservati anche i valori correnti, originali e predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0bc55-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="0bc55-105">Ad esempio, dopo aver apportato una modifica in una colonna di una riga, lo stato della riga sarà impostato su `Modified` e saranno disponibili due versioni, ovvero `Current`, che contiene i valori correnti della riga, e `Original`, che contiene i valori della riga prima della modifica della colonna.</span><span class="sxs-lookup"><span data-stu-id="0bc55-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="0bc55-106">A ogni oggetto <xref:System.Data.DataRow> è assegnata una proprietà <xref:System.Data.DataRow.RowState%2A>, che è possibile esaminare per determinare lo stato corrente della riga.</span><span class="sxs-lookup"><span data-stu-id="0bc55-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="0bc55-107">Nella tabella seguente viene fornita una breve descrizione di ogni valore dell'enumerazione `RowState`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="0bc55-108">Valore di RowState</span><span class="sxs-lookup"><span data-stu-id="0bc55-108">RowState value</span></span>|<span data-ttu-id="0bc55-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bc55-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="0bc55-110">Non è stata apportata alcuna modifica rispetto all'ultima chiamata a `AcceptChanges` o alla creazione della riga da parte di `DataAdapter.Fill`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="0bc55-111">La riga è stata aggiunta alla tabella, ma `AcceptChanges` non è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="0bc55-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="0bc55-112">Alcuni elementi della riga sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="0bc55-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="0bc55-113">La riga è stata eliminata da una tabella e `AcceptChanges` non è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="0bc55-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="0bc55-114">La riga non fa parte di alcun oggetto `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="0bc55-115">Il valore di `RowState` di una riga appena creata viene impostato su `Detached`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="0bc55-116">Dopo l'aggiunta della nuova `DataRow` al `DataRowCollection` tramite la chiamata al metodo `Add`, il valore della proprietà `RowState` viene impostato su `Added`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> <span data-ttu-id="0bc55-117">Il valore `Detached` viene impostato anche per una riga rimossa da un `DataRowCollection` mediante il metodo `Remove` oppure mediante il metodo `Delete` seguito dal metodo `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-117">`Detached` is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="0bc55-118">Quando `AcceptChanges` viene chiamato su un oggetto <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow>, tutte le righe il cui stato corrisponde a `Deleted` vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="0bc55-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="0bc55-119">Alle righe rimanenti viene assegnato lo stato `Unchanged` e i valori con versione di riga `Original` vengono sovrascritti dai valori con versione di riga `Current`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="0bc55-120">Quando `RejectChanges` viene chiamato, tutte le righe il cui stato corrisponde a `Added` vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="0bc55-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="0bc55-121">Alle righe rimanenti viene assegnato lo stato `Unchanged` e i valori con versione di riga `Current` vengono sovrascritti dai valori con versione di riga `Original`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="0bc55-122">È possibile visualizzare le diverse versioni di una riga passando un parametro <xref:System.Data.DataRowVersion> contenente il riferimento alla colonna, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0bc55-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="0bc55-123">Nella tabella seguente viene fornita una breve descrizione di ogni valore dell'enumerazione `DataRowVersion`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="0bc55-124">Valore di DataRowVersion</span><span class="sxs-lookup"><span data-stu-id="0bc55-124">DataRowVersion value</span></span>|<span data-ttu-id="0bc55-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bc55-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="0bc55-126">Valori correnti della riga.</span><span class="sxs-lookup"><span data-stu-id="0bc55-126">The current values for the row.</span></span> <span data-ttu-id="0bc55-127">Questa versione di riga non è disponibile per le righe in cui il valore di `RowState` è `Deleted`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="0bc55-128">Versione di riga predefinita per una particolare riga.</span><span class="sxs-lookup"><span data-stu-id="0bc55-128">The default row version for a particular row.</span></span> <span data-ttu-id="0bc55-129">La versione predefinita per una riga `Added`, `Modified` o `Unchanged` è `Current`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-129">The default row version for an `Added`, `Modified`, or `Unchanged` row is `Current`.</span></span> <span data-ttu-id="0bc55-130">La versione predefinita per una riga `Deleted` è `Original`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-130">The default row version for a `Deleted` row is `Original`.</span></span> <span data-ttu-id="0bc55-131">La versione predefinita per una riga `Detached` è `Proposed`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-131">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="0bc55-132">Valori originali della riga.</span><span class="sxs-lookup"><span data-stu-id="0bc55-132">The original values for the row.</span></span> <span data-ttu-id="0bc55-133">Questa versione di riga non è disponibile per le righe in cui il valore di `RowState` è `Added`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-133">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="0bc55-134">Valori proposti per la riga.</span><span class="sxs-lookup"><span data-stu-id="0bc55-134">The proposed values for the row.</span></span> <span data-ttu-id="0bc55-135">Questa versione di riga è disponibile durante un'operazione di modifica di una riga o per una riga che non fa parte di un `DataRowCollection`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-135">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="0bc55-136">Per verificare se a `DataRow` è associata una particolare versione di riga, è possibile chiamare il metodo <xref:System.Data.DataRow.HasVersion%2A> e passare `DataRowVersion` come argomento.</span><span class="sxs-lookup"><span data-stu-id="0bc55-136">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="0bc55-137">`DataRow.HasVersion(DataRowVersion.Original)`, ad esempio, restituirà `false` per le nuove righe aggiunte prima della chiamata a `AcceptChanges`.</span><span class="sxs-lookup"><span data-stu-id="0bc55-137">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="0bc55-138">Nell'esempio di codice seguente vengono visualizzati i valori in tutte le righe eliminate di una tabella.</span><span class="sxs-lookup"><span data-stu-id="0bc55-138">The following code example displays the values in all the deleted rows of a table.</span></span> <span data-ttu-id="0bc55-139">Le righe `Deleted` non dispongono di una versione della riga `Current`, pertanto è necessario passare `DataRowVersion.Original` quando si accede ai valori della colonna.</span><span class="sxs-lookup"><span data-stu-id="0bc55-139">`Deleted` rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bc55-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bc55-140">See Also</span></span>  
 [<span data-ttu-id="0bc55-141">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="0bc55-141">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="0bc55-142">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="0bc55-142">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="0bc55-143">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="0bc55-143">DataAdapters and DataReaders</span></span>](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="0bc55-144">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0bc55-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
