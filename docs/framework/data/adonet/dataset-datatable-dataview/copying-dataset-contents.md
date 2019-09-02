---
title: Copia di contenuti di dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: f60ef817773b6234b19856bfc0727eedb67e113e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205166"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="c75c5-102">Copia di contenuti di dataset</span><span class="sxs-lookup"><span data-stu-id="c75c5-102">Copying DataSet Contents</span></span>
<span data-ttu-id="c75c5-103">È possibile creare una copia di un <xref:System.Data.DataSet> oggetto in modo che sia possibile utilizzare i dati senza influire sui dati originali oppure utilizzare un subset dei dati di un **set**di dati.</span><span class="sxs-lookup"><span data-stu-id="c75c5-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="c75c5-104">Quando si copia un **set di dati**, è possibile:</span><span class="sxs-lookup"><span data-stu-id="c75c5-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="c75c5-105">Creare una copia esatta del **set**di dati, inclusi lo schema, i dati, le informazioni sullo stato della riga e le versioni delle righe.</span><span class="sxs-lookup"><span data-stu-id="c75c5-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="c75c5-106">Creare un **set di dati** che contiene lo schema di un **set di dati**esistente, ma solo le righe che sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="c75c5-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="c75c5-107">È possibile restituire tutte le righe modificate o specificare un **DataRowState**specifico.</span><span class="sxs-lookup"><span data-stu-id="c75c5-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="c75c5-108">Per altre informazioni sugli Stati delle righe, vedere [Stati di riga e versioni di riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c75c5-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="c75c5-109">Copiare lo schema, o la struttura relazionale, solo del **set di dati** , senza copiare alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="c75c5-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="c75c5-110">È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="c75c5-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="c75c5-111">Per creare una copia esatta del **set** di dati che include sia lo schema che i dati <xref:System.Data.DataSet.Copy%2A> , usare il metodo del **set**di dati.</span><span class="sxs-lookup"><span data-stu-id="c75c5-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c75c5-112">Nell'esempio di codice seguente viene illustrato come creare una copia esatta del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="c75c5-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="c75c5-113">Per creare una copia di un **set** di dati che includa lo schema e solo i dati che rappresentano le righe **aggiunte**, **modificate**o **eliminate** , utilizzare il <xref:System.Data.DataSet.GetChanges%2A> metodo del **set**di dati.</span><span class="sxs-lookup"><span data-stu-id="c75c5-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c75c5-114">È inoltre possibile utilizzare GetChanges per restituire solo le righe con uno stato di riga specificato passando un valore **DataRowState** durante la chiamata a GetChanges.</span><span class="sxs-lookup"><span data-stu-id="c75c5-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="c75c5-115">Nell'esempio di codice seguente viene illustrato come passare un **DataRowState** durante la chiamata a GetChanges.</span><span class="sxs-lookup"><span data-stu-id="c75c5-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="c75c5-116">Per creare una copia di un **set di dati** che includa solo lo <xref:System.Data.DataSet.Clone%2A> schema, usare il metodo del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="c75c5-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c75c5-117">È anche possibile aggiungere righe esistenti al **set di dati** clonato usando il metodo **ImportRow** della **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c75c5-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="c75c5-118">**ImportRow** aggiunge i dati, lo stato della riga e le informazioni sulla versione della riga alla tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="c75c5-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="c75c5-119">I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.</span><span class="sxs-lookup"><span data-stu-id="c75c5-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="c75c5-120">L'esempio di codice seguente crea un clone di un **set di dati** e quindi aggiunge le righe dal set di **dati** originale alla tabella **Customers** nel clone del set di **dati** per i clienti in cui la colonna **CountryRegion** ha il valore "Germania". ".</span><span class="sxs-lookup"><span data-stu-id="c75c5-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =   
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c75c5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c75c5-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="c75c5-122">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="c75c5-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c75c5-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c75c5-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
