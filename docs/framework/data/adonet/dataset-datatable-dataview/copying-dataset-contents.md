---
title: Copia di contenuti di dataset
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
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69709fea628e6cb1d10a23f29b60911ab07e1111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="b015e-102">Copia di contenuti di dataset</span><span class="sxs-lookup"><span data-stu-id="b015e-102">Copying DataSet Contents</span></span>
<span data-ttu-id="b015e-103">È possibile creare una copia di un <xref:System.Data.DataSet> in modo da poter utilizzare i dati senza influire sui dati originali, o utilizzare un subset dei dati da un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b015e-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="b015e-104">Quando si copia un **DataSet**, è possibile:</span><span class="sxs-lookup"><span data-stu-id="b015e-104">When copying a **DataSet**, you can:</span></span>  
  
-   <span data-ttu-id="b015e-105">Creare una copia esatta del **DataSet**, inclusi schema, dati, le informazioni sullo stato di riga e le versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="b015e-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
-   <span data-ttu-id="b015e-106">Creare un **DataSet** contenente lo schema di un oggetto esistente **DataSet**, ma solo le righe che sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="b015e-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="b015e-107">È possibile restituire tutte le righe che sono state modificate oppure specificare un determinato **DataRowState**.</span><span class="sxs-lookup"><span data-stu-id="b015e-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="b015e-108">Per ulteriori informazioni sugli stati delle righe, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="b015e-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
-   <span data-ttu-id="b015e-109">Copiare lo schema, o struttura relazionale, del **DataSet** solo, senza copiare alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="b015e-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="b015e-110">È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="b015e-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="b015e-111">Per creare una copia esatta del **DataSet** che include sia dello schema e dati, utilizzare il <xref:System.Data.DataSet.Copy%2A> metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="b015e-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b015e-112">Esempio di codice seguente viene illustrato come creare una copia esatta del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b015e-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="b015e-113">Per creare una copia di un **DataSet** che include lo schema e solo i dati che rappresentano **Added**, **Modified**, o **Deleted** righe, utilizzare il <xref:System.Data.DataSet.GetChanges%2A> metodo il **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b015e-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b015e-114">È inoltre possibile utilizzare **GetChanges** per restituire solo le righe con uno stato di riga specificata passando un **DataRowState** valore quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="b015e-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="b015e-115">Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="b015e-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="b015e-116">Per creare una copia di un **DataSet** che include solo schema, utilizzare il <xref:System.Data.DataSet.Clone%2A> metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="b015e-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="b015e-117">È anche possibile aggiungere righe esistenti al **DataSet** utilizzando il **ImportRow** metodo il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="b015e-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="b015e-118">**ImportRow** aggiunge i dati, lo stato di riga e informazioni sulla versione di riga alla tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="b015e-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="b015e-119">I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.</span><span class="sxs-lookup"><span data-stu-id="b015e-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="b015e-120">Esempio di codice seguente crea un clone di un **DataSet** e le righe vengono aggiunte dalla versione originale **set di dati** per il **clienti** tabella il **set di dati**  duplicato per i clienti in cui il **CountryRegion** colonna ha il valore "Germany".</span><span class="sxs-lookup"><span data-stu-id="b015e-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b015e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b015e-121">See Also</span></span>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="b015e-122">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="b015e-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="b015e-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b015e-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
