---
title: Copia di contenuti di dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 29afeb84498f2b1d000940ddc28545602a44d408
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626146"
---
# <a name="copying-dataset-contents"></a>Copia di contenuti di dataset
È possibile creare una copia di un <xref:System.Data.DataSet> in modo da poter usare i dati senza influire sui dati originali, o utilizzare un subset dei dati da un **set di dati**. Quando si copia una **set di dati**, è possibile:  
  
- Creare una copia esatta del **set di dati**, inclusi dello schema, i dati, le informazioni sullo stato di riga e le versioni di riga.  
  
- Creare un **set di dati** che contiene lo schema di esistente **DataSet**, ma solo le righe che sono state modificate. È possibile restituire tutte le righe che sono state modificate oppure specificare un determinato **DataRowState**. Per altre informazioni sugli stati delle righe, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
- Copiare lo schema o struttura relazionale, del **set di dati** solo, senza copiare alcuna riga. È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Per creare una copia esatta del **set di dati** che include lo schema sia dei dati, utilizzare il <xref:System.Data.DataSet.Copy%2A> metodo il **set di dati**. Esempio di codice seguente viene illustrato come creare una copia esatta del **set di dati**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Per creare una copia di un **set di dati** che include lo schema e solo i dati che rappresentano **Added**, **Modified**, o **Deleted** righe, usare il <xref:System.Data.DataSet.GetChanges%2A> metodo per il **set di dati**. È anche possibile usare **GetChanges** da restituire solo le righe con uno stato di riga specificato passando una **DataRowState** valore quando si chiama **GetChanges**. Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.  
  
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
  
 Per creare una copia di un **set di dati** che include solo lo schema, usare il <xref:System.Data.DataSet.Clone%2A> metodo per il **set di dati**. È anche possibile aggiungere le righe esistenti al **set di dati** usando la **ImportRow** metodo per il **DataTable**. **ImportRow** aggiunge i dati, lo stato di riga e informazioni sulla versione di riga nella tabella specificata. I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.  
  
 Il codice seguente crea un clone di un **set di dati** e quindi le righe vengono aggiunte dalla versione originale **set di dati** per il **clienti** tabella il **set di dati**  duplicato per i clienti in cui la **CountryRegion** colonna ha il valore "Germany".  
  
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
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
