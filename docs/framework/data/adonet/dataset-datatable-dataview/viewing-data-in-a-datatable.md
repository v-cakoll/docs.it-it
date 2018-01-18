---
title: Visualizzazione di dati in un oggetto DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2576c95ad7739d28e2ca822fd13fb6f176900814
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="3f0ab-102">Visualizzazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="3f0ab-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="3f0ab-103">È possibile accedere al contenuto di un <xref:System.Data.DataTable> utilizzando il **righe** e **colonne** insiemi di **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="3f0ab-104">È inoltre possibile utilizzare il <xref:System.Data.DataTable.Select%2A> per restituire subset di dati in un **DataTable** in base ai criteri compresi i criteri di ricerca, ordinamento e lo stato della riga.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="3f0ab-105">Inoltre, è possibile utilizzare il <xref:System.Data.DataRowCollection.Find%2A> metodo il **DataRowCollection** durante la ricerca di una particolare riga mediante un valore di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="3f0ab-106">Il **selezionare** metodo il **DataTable** oggetto restituisce un set di <xref:System.Data.DataRow> gli oggetti che soddisfano i criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="3f0ab-107">**Selezionare** accetta gli argomenti facoltativi di un'espressione di filtro, un'espressione di ordinamento e **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="3f0ab-108">L'espressione di filtro identifica le righe da restituire in base alle **DataColumn** valori, ad esempio `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="3f0ab-109">Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="3f0ab-110">Per le regole sulla scrittura di espressioni, vedere il <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="3f0ab-111">Se si esegue un numero di chiamate per il **selezionare** metodo di un **DataTable**, è possibile migliorare le prestazioni creando innanzitutto un <xref:System.Data.DataView> per il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="3f0ab-112">Creazione di **DataView** indicizzate le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="3f0ab-113">Il **selezionare** metodo quindi utilizza l'indicizzazione, riducendo notevolmente il tempo necessario per generare il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="3f0ab-114">Per informazioni sulla creazione di un **DataView** per un **DataTable**, vedere [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="3f0ab-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="3f0ab-115">Il **selezionare** (metodo) determina quale versione delle righe da visualizzare o modificare in base a un <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="3f0ab-116">Nella tabella seguente vengono descritti i possibili **DataViewRowState** valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="3f0ab-117">Valore di DataViewRowState</span><span class="sxs-lookup"><span data-stu-id="3f0ab-117">DataViewRowState value</span></span>|<span data-ttu-id="3f0ab-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f0ab-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="3f0ab-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-119">**CurrentRows**</span></span>|<span data-ttu-id="3f0ab-120">Righe correnti, incluse le righe non modificate, aggiunte e modificate.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="3f0ab-121">**Eliminato**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-121">**Deleted**</span></span>|<span data-ttu-id="3f0ab-122">Riga eliminata.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-122">A deleted row.</span></span>|  
|<span data-ttu-id="3f0ab-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="3f0ab-124">Una versione corrente, ovvero una versione modificata dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="3f0ab-125">(Vedere **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="3f0ab-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="3f0ab-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="3f0ab-127">La versione originale di tutte le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-127">The original version of all modified rows.</span></span> <span data-ttu-id="3f0ab-128">La versione corrente è disponibile tramite **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="3f0ab-129">**Aggiunta**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-129">**Added**</span></span>|<span data-ttu-id="3f0ab-130">Nuova riga.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-130">A new row.</span></span>|  
|<span data-ttu-id="3f0ab-131">**None**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-131">**None**</span></span>|<span data-ttu-id="3f0ab-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-132">None.</span></span>|  
|<span data-ttu-id="3f0ab-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-133">**OriginalRows**</span></span>|<span data-ttu-id="3f0ab-134">Righe originali, tra cui righe non modificate ed eliminate.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="3f0ab-135">**Non modificato**</span><span class="sxs-lookup"><span data-stu-id="3f0ab-135">**Unchanged**</span></span>|<span data-ttu-id="3f0ab-136">Riga non modificata.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="3f0ab-137">Nell'esempio seguente, il **DataSet** oggetto è filtrato in modo che si utilizza soltanto le righe il cui **DataViewRowState** è impostato su **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
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
  
 <span data-ttu-id="3f0ab-138">Il **selezionare** metodo può essere utilizzato per restituire le righe con diversi **RowState** valori o valori di campo.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="3f0ab-139">Nell'esempio seguente viene restituito un **DataRow** matrice che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra **DataRow** matrice che fa riferimento a tutte le righe, ordinate in base **CustLName**, dove il **CustID** colonna è maggiore di 5.</span><span class="sxs-lookup"><span data-stu-id="3f0ab-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="3f0ab-140">Per informazioni su come visualizzare le informazioni contenute nel **Deleted** di riga, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="3f0ab-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3f0ab-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f0ab-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="3f0ab-142">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="3f0ab-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="3f0ab-143">Stati e versioni delle righe</span><span class="sxs-lookup"><span data-stu-id="3f0ab-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="3f0ab-144">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="3f0ab-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
