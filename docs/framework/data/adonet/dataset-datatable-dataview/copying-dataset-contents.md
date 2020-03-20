---
title: Copia di contenuti di dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151364"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="14638-102">Copia di contenuti di dataset</span><span class="sxs-lookup"><span data-stu-id="14638-102">Copying DataSet Contents</span></span>
<span data-ttu-id="14638-103">È possibile creare una <xref:System.Data.DataSet> copia di un oggetto in modo da poter utilizzare i dati senza influire sui dati originali oppure utilizzare un sottoinsieme di dati da un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="14638-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="14638-104">Quando si copia un **DataSet**, è possibile:</span><span class="sxs-lookup"><span data-stu-id="14638-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="14638-105">Creare una copia esatta del **DataSet**, inclusi lo schema, i dati, le informazioni sullo stato delle righe e le versioni di riga.</span><span class="sxs-lookup"><span data-stu-id="14638-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="14638-106">Creare un **DataSet** contenente lo schema di un **DataSet**esistente, ma solo le righe modificate.</span><span class="sxs-lookup"><span data-stu-id="14638-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="14638-107">È possibile restituire tutte le righe che sono state modificate o specificare un **DataRowState**specifico.</span><span class="sxs-lookup"><span data-stu-id="14638-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="14638-108">Per ulteriori informazioni sugli stati delle righe, vedere [Stati riga e Versioni riga](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="14638-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="14638-109">Copiare solo lo schema, o struttura relazionale, del **DataSet,** senza copiare alcuna riga.</span><span class="sxs-lookup"><span data-stu-id="14638-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="14638-110">È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="14638-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="14638-111">Per creare una copia esatta del **DataSet** che include <xref:System.Data.DataSet.Copy%2A> sia lo schema che i dati, utilizzare il metodo del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="14638-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="14638-112">Nell'esempio di codice riportato di seguito viene illustrato come creare una copia esatta del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="14638-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="14638-113">Per creare una copia di un **DataSet** che include lo schema e solo <xref:System.Data.DataSet.GetChanges%2A> i dati che rappresentano righe **Added**, **Modified**o **Deleted,** utilizzare il metodo del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="14638-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="14638-114">È inoltre possibile utilizzare **GetChanges** per restituire solo le righe con uno stato di riga specificato passando un **Valore DataRowState** quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="14638-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="14638-115">Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.</span><span class="sxs-lookup"><span data-stu-id="14638-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="14638-116">Per creare una copia di un **DataSet** <xref:System.Data.DataSet.Clone%2A> che includa solo lo schema, utilizzare il metodo del **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="14638-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="14638-117">È inoltre possibile aggiungere righe esistenti al **DataSet** clonato utilizzando il metodo **ImportRow** di **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="14638-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="14638-118">**ImportRow** aggiunge i dati, lo stato della riga e le informazioni sulla versione della riga alla tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="14638-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="14638-119">I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.</span><span class="sxs-lookup"><span data-stu-id="14638-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="14638-120">Nell'esempio di codice riportato di seguito viene creato un clone di un **DataSet** e quindi vengono aggiunte le righe del **DataSet** originale alla tabella **Customers** nel clone del **DataSet** per i clienti in cui la colonna **CountryRegion** ha il valore "Germany".</span><span class="sxs-lookup"><span data-stu-id="14638-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14638-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14638-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="14638-122">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="14638-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="14638-123">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14638-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
