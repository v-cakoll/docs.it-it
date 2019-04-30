---
title: Copia di contenuti di dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: cb2a172ac4e6a0ce4852f4c7cf7044583d9ab6c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034429"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="6d84e-102">Copia di contenuti di dataset</span><span class="sxs-lookup"><span data-stu-id="6d84e-102">Copying DataSet Contents</span></span>
<span data-ttu-id="6d84e-103">È possibile creare una copia di un <xref:System.Data.DataSet> in modo da poter usare i dati senza influire sui dati originali, o utilizzare un subset dei dati da un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="6d84e-104">Quando si copia una **set di dati**, è possibile:</span><span class="sxs-lookup"><span data-stu-id="6d84e-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="6d84e-105">Creare una copia esatta del **set di dati**, inclusi dello schema, i dati, le informazioni sullo stato di riga e le versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="6d84e-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="6d84e-106">Creare un **set di dati** che contiene lo schema di esistente **DataSet**, ma solo le righe che sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="6d84e-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="6d84e-107">È possibile restituire tutte le righe che sono state modificate oppure specificare un determinato **DataRowState**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="6d84e-108">Per altre informazioni sugli stati delle righe, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6d84e-108">For more information about row states, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="6d84e-109">Copiare lo schema o struttura relazionale, del **set di dati** solo, senza copiare alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="6d84e-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="6d84e-110">È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="6d84e-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="6d84e-111">Per creare una copia esatta del **set di dati** che include lo schema sia dei dati, utilizzare il <xref:System.Data.DataSet.Copy%2A> metodo il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6d84e-112">Esempio di codice seguente viene illustrato come creare una copia esatta del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="6d84e-113">Per creare una copia di un **set di dati** che include lo schema e solo i dati che rappresentano **Added**, **Modified**, o **Deleted** righe, usare il <xref:System.Data.DataSet.GetChanges%2A> metodo per il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6d84e-114">È anche possibile usare **GetChanges** da restituire solo le righe con uno stato di riga specificato passando una **DataRowState** valore quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="6d84e-115">Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="6d84e-116">Per creare una copia di un **set di dati** che include solo lo schema, usare il <xref:System.Data.DataSet.Clone%2A> metodo per il **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="6d84e-117">È anche possibile aggiungere le righe esistenti al **set di dati** usando la **ImportRow** metodo per il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="6d84e-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="6d84e-118">**ImportRow** aggiunge i dati, lo stato di riga e informazioni sulla versione di riga nella tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="6d84e-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="6d84e-119">I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.</span><span class="sxs-lookup"><span data-stu-id="6d84e-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="6d84e-120">Il codice seguente crea un clone di un **set di dati** e quindi le righe vengono aggiunte dalla versione originale **set di dati** per il **clienti** tabella il **set di dati**  duplicato per i clienti in cui la **CountryRegion** colonna ha il valore "Germany".</span><span class="sxs-lookup"><span data-stu-id="6d84e-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d84e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d84e-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="6d84e-122">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="6d84e-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="6d84e-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="6d84e-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
