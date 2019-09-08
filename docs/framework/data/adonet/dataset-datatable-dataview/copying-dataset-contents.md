---
title: Copia di contenuti di dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: d8a7762c4ec5d650295ca0626180285723549051
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786523"
---
# <a name="copying-dataset-contents"></a>Copia di contenuti di dataset
È possibile creare una copia di un <xref:System.Data.DataSet> oggetto in modo che sia possibile utilizzare i dati senza influire sui dati originali oppure utilizzare un subset dei dati di un **set**di dati. Quando si copia un **set di dati**, è possibile:  
  
- Creare una copia esatta del **set**di dati, inclusi lo schema, i dati, le informazioni sullo stato della riga e le versioni delle righe.  
  
- Creare un **set di dati** che contiene lo schema di un **set di dati**esistente, ma solo le righe che sono state modificate. È possibile restituire tutte le righe modificate o specificare un **DataRowState**specifico. Per altre informazioni sugli Stati delle righe, vedere [Stati di riga e versioni di riga](row-states-and-row-versions.md).  
  
- Copiare lo schema, o la struttura relazionale, solo del **set di dati** , senza copiare alcuna riga. È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Per creare una copia esatta del **set** di dati che include sia lo schema che i dati <xref:System.Data.DataSet.Copy%2A> , usare il metodo del **set**di dati. Nell'esempio di codice seguente viene illustrato come creare una copia esatta del **set di dati**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Per creare una copia di un **set** di dati che includa lo schema e solo idati che rappresentano le righe **aggiunte**, modificate <xref:System.Data.DataSet.GetChanges%2A> o **eliminate** , utilizzare il metodo del **set**di dati. È inoltre possibile utilizzare **GetChanges** per restituire solo le righe con uno stato di riga specificato passando un valore **DataRowState** durante la chiamata a **GetChanges**. Nell'esempio di codice seguente viene illustrato come passare un **DataRowState** durante la chiamata a **GetChanges**.  
  
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
  
 Per creare una copia di un **set di dati** che includa solo lo <xref:System.Data.DataSet.Clone%2A> schema, usare il metodo del **set di dati**. È anche possibile aggiungere righe esistenti al **set di dati** clonato usando il metodo **ImportRow** della **DataTable**. **ImportRow** aggiunge i dati, lo stato della riga e le informazioni sulla versione della riga alla tabella specificata. I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.  
  
 L'esempio di codice seguente crea un clone di **un set di dati** e quindi aggiunge le righe dal set di **dati** originale alla tabella **Customers** nel clone del **set di dati** per i clienti in cui la colonna **CountryRegion** ha il valore "Germania". ".  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
