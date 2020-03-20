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
# <a name="copying-dataset-contents"></a>Copia di contenuti di dataset
È possibile creare una <xref:System.Data.DataSet> copia di un oggetto in modo da poter utilizzare i dati senza influire sui dati originali oppure utilizzare un sottoinsieme di dati da un **DataSet**. Quando si copia un **DataSet**, è possibile:  
  
- Creare una copia esatta del **DataSet**, inclusi lo schema, i dati, le informazioni sullo stato delle righe e le versioni di riga.  
  
- Creare un **DataSet** contenente lo schema di un **DataSet**esistente, ma solo le righe modificate. È possibile restituire tutte le righe che sono state modificate o specificare un **DataRowState**specifico. Per ulteriori informazioni sugli stati delle righe, vedere [Stati riga e Versioni riga](row-states-and-row-versions.md).  
  
- Copiare solo lo schema, o struttura relazionale, del **DataSet,** senza copiare alcuna riga. È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Per creare una copia esatta del **DataSet** che include <xref:System.Data.DataSet.Copy%2A> sia lo schema che i dati, utilizzare il metodo del **DataSet**. Nell'esempio di codice riportato di seguito viene illustrato come creare una copia esatta del **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Per creare una copia di un **DataSet** che include lo schema e solo <xref:System.Data.DataSet.GetChanges%2A> i dati che rappresentano righe **Added**, **Modified**o **Deleted,** utilizzare il metodo del **DataSet**. È inoltre possibile utilizzare **GetChanges** per restituire solo le righe con uno stato di riga specificato passando un **Valore DataRowState** quando si chiama **GetChanges**. Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.  
  
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
  
 Per creare una copia di un **DataSet** <xref:System.Data.DataSet.Clone%2A> che includa solo lo schema, utilizzare il metodo del **DataSet**. È inoltre possibile aggiungere righe esistenti al **DataSet** clonato utilizzando il metodo **ImportRow** di **DataTable**. **ImportRow** aggiunge i dati, lo stato della riga e le informazioni sulla versione della riga alla tabella specificata. I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.  
  
 Nell'esempio di codice riportato di seguito viene creato un clone di un **DataSet** e quindi vengono aggiunte le righe del **DataSet** originale alla tabella **Customers** nel clone del **DataSet** per i clienti in cui la colonna **CountryRegion** ha il valore "Germany".  
  
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
