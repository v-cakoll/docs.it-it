---
title: Visualizzazione di dati in un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: c13f0b802b2714a17ea4014625a65ebd1b0011f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785857"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="08577-102">Visualizzazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="08577-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="08577-103">È possibile accedere al contenuto di un <xref:System.Data.DataTable> oggetto utilizzando le raccolte **Rows** e **Columns** di **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="08577-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="08577-104">È anche possibile usare il <xref:System.Data.DataTable.Select%2A> metodo per restituire subset dei dati in un **oggetto DataTable** in base ai criteri, inclusi i criteri di ricerca, l'ordinamento e lo stato della riga.</span><span class="sxs-lookup"><span data-stu-id="08577-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="08577-105">Inoltre, è possibile usare il <xref:System.Data.DataRowCollection.Find%2A> metodo di **DataRowCollection** durante la ricerca di una determinata riga usando un valore di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="08577-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="08577-106">Il metodo **Select** dell'oggetto **DataTable** restituisce un set di <xref:System.Data.DataRow> oggetti che corrispondono ai criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="08577-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="08577-107">**Select** accetta gli argomenti facoltativi di un'espressione di filtro, di un'espressione di ordinamento e di **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="08577-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="08577-108">L'espressione di filtro identifica le righe da restituire in base ai valori di DataColumn `LastName = 'Smith'`, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="08577-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="08577-109">Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="08577-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="08577-110">Per le regole sulla scrittura di espressioni, <xref:System.Data.DataColumn.Expression%2A> vedere la proprietà della classe **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="08577-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="08577-111">Se si eseguono una serie di chiamate al metodo **Select** di un **oggetto DataTable**, è possibile migliorare le prestazioni creando prima un <xref:System.Data.DataView> oggetto per la **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="08577-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="08577-112">La creazione di **DataView** indicizza le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="08577-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="08577-113">Il metodo **Select** usa quindi tale indice, riducendo in modo significativo il tempo necessario per generare il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="08577-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="08577-114">Per informazioni sulla creazione di un **DataView** per un **DataTable**, vedere [DataViews](dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="08577-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="08577-115">Il metodo **Select** determina la versione delle righe da visualizzare o modificare in base a un <xref:System.Data.DataViewRowState>oggetto.</span><span class="sxs-lookup"><span data-stu-id="08577-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="08577-116">Nella tabella seguente vengono descritti i possibili valori di enumerazione **DataViewRowState** .</span><span class="sxs-lookup"><span data-stu-id="08577-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="08577-117">Valore di DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="08577-117">DataViewRowState value</span></span>|<span data-ttu-id="08577-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08577-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="08577-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="08577-119">**CurrentRows**</span></span>|<span data-ttu-id="08577-120">Righe correnti, incluse le righe non modificate, aggiunte e modificate.</span><span class="sxs-lookup"><span data-stu-id="08577-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="08577-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="08577-121">**Deleted**</span></span>|<span data-ttu-id="08577-122">Riga eliminata.</span><span class="sxs-lookup"><span data-stu-id="08577-122">A deleted row.</span></span>|
|<span data-ttu-id="08577-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="08577-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="08577-124">Una versione corrente, ovvero una versione modificata dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="08577-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="08577-125">Vedere **ModifiedOriginal**.</span><span class="sxs-lookup"><span data-stu-id="08577-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="08577-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="08577-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="08577-127">La versione originale di tutte le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="08577-127">The original version of all modified rows.</span></span> <span data-ttu-id="08577-128">La versione corrente è disponibile tramite **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="08577-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="08577-129">**Aggiunto**</span><span class="sxs-lookup"><span data-stu-id="08577-129">**Added**</span></span>|<span data-ttu-id="08577-130">Nuova riga.</span><span class="sxs-lookup"><span data-stu-id="08577-130">A new row.</span></span>|
|<span data-ttu-id="08577-131">**None**</span><span class="sxs-lookup"><span data-stu-id="08577-131">**None**</span></span>|<span data-ttu-id="08577-132">No.</span><span class="sxs-lookup"><span data-stu-id="08577-132">None.</span></span>|
|<span data-ttu-id="08577-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="08577-133">**OriginalRows**</span></span>|<span data-ttu-id="08577-134">Righe originali, tra cui righe non modificate ed eliminate.</span><span class="sxs-lookup"><span data-stu-id="08577-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="08577-135">**Invariato**</span><span class="sxs-lookup"><span data-stu-id="08577-135">**Unchanged**</span></span>|<span data-ttu-id="08577-136">Riga non modificata.</span><span class="sxs-lookup"><span data-stu-id="08577-136">An unchanged row.</span></span>|

<span data-ttu-id="08577-137">Nell'esempio seguente l'oggetto **DataSet** viene filtrato in modo da usare solo le righe il cui **DataViewRowState** è impostato su **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="08577-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="08577-138">Il metodo **Select** può essere utilizzato per restituire righe con valori di campo o valori di **RowState** diversi.</span><span class="sxs-lookup"><span data-stu-id="08577-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="08577-139">Nell'esempio seguente viene restituita una matrice **DataRow** che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra matrice **DataRow** che fa riferimento a tutte le righe, ordinate per **CustLName**, in cui la colonna **CustID** è maggiore di 5.</span><span class="sxs-lookup"><span data-stu-id="08577-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="08577-140">Per informazioni su come visualizzare le informazioni nella riga **Deleted** , vedere Stati di [riga e versioni di riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="08577-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="08577-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08577-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="08577-142">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="08577-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="08577-143">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="08577-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="08577-144">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08577-144">ADO.NET Overview</span></span>](../ado-net-overview.md)
