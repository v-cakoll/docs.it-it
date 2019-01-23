---
title: Aggiunta di dati a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: adf2378cead054efcef10a73bfd00ef541940949
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494120"
---
# <a name="adding-data-to-a-datatable"></a>Aggiunta di dati a un oggetto DataTable
Una volta creata una <xref:System.Data.DataTable> e definita la relativa struttura tramite colonne e vincoli, è possibile aggiungere nuove righe di dati alla tabella. Per aggiungere una nuova riga, dichiarare una nuova variabile come tipo <xref:System.Data.DataRow>. Una nuova **DataRow** oggetto viene restituito quando si chiama il <xref:System.Data.DataTable.NewRow%2A> (metodo). Il **DataTable** crea quindi il **DataRow** oggetto basati sulla struttura della tabella, come definito dal <xref:System.Data.DataColumnCollection>.  
  
 Nell'esempio seguente viene illustrato come creare una nuova riga chiamando la **NewRow** (metodo).  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 È quindi possibile modificare la riga appena aggiunta usando un indice o il nome della colonna, come illustrato nell'esempio seguente.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 Dopo che i dati vengono inseriti nella nuova riga, il **Add** metodo viene utilizzato per aggiungere la riga per il <xref:System.Data.DataRowCollection>, come illustrato nel codice seguente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 È inoltre possibile chiamare il **Add** per aggiungere una nuova riga passando una matrice di valori, tipizzata come <xref:System.Object>, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Passando una matrice di valori, tipizzata come **oggetti**, per il **Add** metodo crea una nuova riga all'interno della tabella e imposta i valori di colonna ai valori nella matrice di oggetti. Notare che i valori contenuti nella matrice vengono associati in modo sequenziale alle colonne, in base all'ordine in cui sono presenti nella tabella.  
  
 L'esempio seguente aggiunge 10 righe all'oggetto appena creato **clienti** tabella.  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)   
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
