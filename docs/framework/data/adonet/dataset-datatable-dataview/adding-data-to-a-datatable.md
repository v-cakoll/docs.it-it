---
title: Aggiunta di dati a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151533"
---
# <a name="adding-data-to-a-datatable"></a>Aggiunta di dati a un oggetto DataTable
Una volta creata una <xref:System.Data.DataTable> e definita la relativa struttura tramite colonne e vincoli, è possibile aggiungere nuove righe di dati alla tabella. Per aggiungere una nuova riga, dichiarare una nuova variabile come tipo <xref:System.Data.DataRow>. Un nuovo **oggetto DataRow** viene restituito <xref:System.Data.DataTable.NewRow%2A> quando si chiama il metodo. Il **DataTable** crea quindi il **DataRow** oggetto in base alla <xref:System.Data.DataColumnCollection>struttura della tabella, come definito dal metodo .  
  
 Nell'esempio seguente viene illustrato come creare una nuova riga chiamando il **NewRow** metodo.  
  
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
  
 Dopo l'inserimento dei dati **Add** nella nuova riga, il <xref:System.Data.DataRowCollection>Add metodo viene utilizzato per aggiungere la riga all'oggetto , illustrato nel codice seguente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 È inoltre possibile chiamare il **metodo Add** per aggiungere una nuova riga <xref:System.Object>passando una matrice di valori, tipizzata come , come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Il passaggio di una matrice di valori, tipizzata come **Object**, al metodo **Add** crea una nuova riga all'interno della tabella e ne imposta i valori di colonna sui valori nella matrice di oggetti. Notare che i valori contenuti nella matrice vengono associati in modo sequenziale alle colonne, in base all'ordine in cui sono presenti nella tabella.  
  
 Nell'esempio seguente vengono aggiunte 10 righe alla tabella **Customers** appena creata.  
  
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
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
