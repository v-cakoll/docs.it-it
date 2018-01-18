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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bdeb462955816a53372719bf374f7d4b55aa7f18
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="copying-dataset-contents"></a>Copia di contenuti di dataset
È possibile creare una copia di un <xref:System.Data.DataSet> in modo da poter utilizzare i dati senza influire sui dati originali, o utilizzare un subset dei dati da un **DataSet**. Quando si copia un **DataSet**, è possibile:  
  
-   Creare una copia esatta del **DataSet**, inclusi schema, dati, le informazioni sullo stato di riga e le versioni di riga.  
  
-   Creare un **DataSet** contenente lo schema di un oggetto esistente **DataSet**, ma solo le righe che sono state modificate. È possibile restituire tutte le righe che sono state modificate oppure specificare un determinato **DataRowState**. Per ulteriori informazioni sugli stati delle righe, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Copiare lo schema, o struttura relazionale, del **DataSet** solo, senza copiare alcuna riga. È possibile importare le righe in un tipo <xref:System.Data.DataTable> esistente usando il metodo <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Per creare una copia esatta del **DataSet** che include sia dello schema e dati, utilizzare il <xref:System.Data.DataSet.Copy%2A> metodo il **set di dati**. Esempio di codice seguente viene illustrato come creare una copia esatta del **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Per creare una copia di un **DataSet** che include lo schema e solo i dati che rappresentano **Added**, **Modified**, o **Deleted** righe, utilizzare il <xref:System.Data.DataSet.GetChanges%2A> metodo il **DataSet**. È inoltre possibile utilizzare **GetChanges** per restituire solo le righe con uno stato di riga specificata passando un **DataRowState** valore quando si chiama **GetChanges**. Esempio di codice seguente viene illustrato come passare un **DataRowState** quando si chiama **GetChanges**.  
  
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
  
 Per creare una copia di un **DataSet** che include solo schema, utilizzare il <xref:System.Data.DataSet.Clone%2A> metodo il **set di dati**. È anche possibile aggiungere righe esistenti al **DataSet** utilizzando il **ImportRow** metodo il **DataTable**. **ImportRow** aggiunge i dati, lo stato di riga e informazioni sulla versione di riga alla tabella specificata. I valori di colonna vengono aggiunti solo nel caso in cui i nomi di colonna corrispondano e il tipo di dati sia compatibile.  
  
 Esempio di codice seguente crea un clone di un **DataSet** e le righe vengono aggiunte dalla versione originale **set di dati** per il **clienti** tabella il **set di dati**  duplicato per i clienti in cui il **CountryRegion** colonna ha il valore "Germany".  
  
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
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
