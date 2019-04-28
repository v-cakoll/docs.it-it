---
title: Visualizzazione di dati in un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: fa8749550e10256ee0623714cc95e03a838655c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607029"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="f33ef-102">Visualizzazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="f33ef-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="f33ef-103">È possibile accedere al contenuto di un <xref:System.Data.DataTable> usando il **righe** e **colonne** raccolte del **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f33ef-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="f33ef-104">È anche possibile usare la <xref:System.Data.DataTable.Select%2A> per restituire subset di dati in un **DataTable** in base ai criteri inclusi i criteri di ricerca, l'ordinamento e lo stato della riga.</span><span class="sxs-lookup"><span data-stu-id="f33ef-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="f33ef-105">Inoltre, è possibile usare la <xref:System.Data.DataRowCollection.Find%2A> metodo per il **DataRowCollection** durante la ricerca di una particolare riga mediante un valore di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f33ef-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="f33ef-106">Il **seleziona** metodo per il **DataTable** oggetto restituisce un set di <xref:System.Data.DataRow> gli oggetti che corrispondono ai criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="f33ef-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="f33ef-107">**Selezionare** accetta gli argomenti facoltativi di un'espressione di filtro, espressione di ordinamento, e **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="f33ef-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="f33ef-108">L'espressione di filtro identifica le righe da restituire in base alle **DataColumn** valori, ad esempio `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="f33ef-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="f33ef-109">Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="f33ef-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="f33ef-110">Per informazioni sulla scrittura di espressioni, vedere la <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.</span><span class="sxs-lookup"><span data-stu-id="f33ef-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="f33ef-111">Se si sta eseguendo un numero di chiamate per il **selezionare** metodo di un **DataTable**, è possibile migliorare le prestazioni tramite la creazione di un <xref:System.Data.DataView> per i **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f33ef-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="f33ef-112">Creazione di **DataView** Indicizza le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="f33ef-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="f33ef-113">Il **seleziona** metodo quindi utilizza tale indice, riducendo in modo significativo il tempo necessario per generare il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="f33ef-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="f33ef-114">Per informazioni sulla creazione di un **DataView** per una **DataTable**, vedere [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="f33ef-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>

<span data-ttu-id="f33ef-115">Il **selezionate** metodo determina la versione delle righe da visualizzare o modificare in base un <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="f33ef-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="f33ef-116">Nella tabella seguente vengono descritti i possibili **DataViewRowState** valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f33ef-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="f33ef-117">Valore di DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="f33ef-117">DataViewRowState value</span></span>|<span data-ttu-id="f33ef-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f33ef-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="f33ef-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="f33ef-119">**CurrentRows**</span></span>|<span data-ttu-id="f33ef-120">Righe correnti, incluse le righe non modificate, aggiunte e modificate.</span><span class="sxs-lookup"><span data-stu-id="f33ef-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="f33ef-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="f33ef-121">**Deleted**</span></span>|<span data-ttu-id="f33ef-122">Riga eliminata.</span><span class="sxs-lookup"><span data-stu-id="f33ef-122">A deleted row.</span></span>|
|<span data-ttu-id="f33ef-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="f33ef-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="f33ef-124">Una versione corrente, ovvero una versione modificata dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="f33ef-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="f33ef-125">(Vedere **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="f33ef-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="f33ef-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="f33ef-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="f33ef-127">La versione originale di tutte le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="f33ef-127">The original version of all modified rows.</span></span> <span data-ttu-id="f33ef-128">La versione corrente è disponibile se si usa **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="f33ef-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="f33ef-129">**Aggiunto**</span><span class="sxs-lookup"><span data-stu-id="f33ef-129">**Added**</span></span>|<span data-ttu-id="f33ef-130">Nuova riga.</span><span class="sxs-lookup"><span data-stu-id="f33ef-130">A new row.</span></span>|
|<span data-ttu-id="f33ef-131">**None**</span><span class="sxs-lookup"><span data-stu-id="f33ef-131">**None**</span></span>|<span data-ttu-id="f33ef-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f33ef-132">None.</span></span>|
|<span data-ttu-id="f33ef-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="f33ef-133">**OriginalRows**</span></span>|<span data-ttu-id="f33ef-134">Righe originali, tra cui righe non modificate ed eliminate.</span><span class="sxs-lookup"><span data-stu-id="f33ef-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="f33ef-135">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="f33ef-135">**Unchanged**</span></span>|<span data-ttu-id="f33ef-136">Riga non modificata.</span><span class="sxs-lookup"><span data-stu-id="f33ef-136">An unchanged row.</span></span>|

<span data-ttu-id="f33ef-137">Nell'esempio seguente, il **set di dati** l'oggetto viene escluso in modo che si utilizza soltanto con righe la cui proprietà **DataViewRowState** è impostata su **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="f33ef-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

<span data-ttu-id="f33ef-138">Il **selezionate** metodo può essere utilizzato per restituire righe con diversi **RowState** valori o valori di campo.</span><span class="sxs-lookup"><span data-stu-id="f33ef-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="f33ef-139">L'esempio seguente restituisce un **DataRow** che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra matrice **DataRow** array che fa riferimento a tutte le righe, ordinate in base **CustLName**, dove il **CustID** colonna è maggiore di 5.</span><span class="sxs-lookup"><span data-stu-id="f33ef-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="f33ef-140">Per informazioni su come visualizzare le informazioni contenute nel **Deleted** righe, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f33ef-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a><span data-ttu-id="f33ef-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f33ef-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="f33ef-142">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="f33ef-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f33ef-143">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="f33ef-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="f33ef-144">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f33ef-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
