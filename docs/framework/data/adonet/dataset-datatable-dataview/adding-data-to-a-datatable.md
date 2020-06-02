---
title: Aggiunta di dati a un oggetto DataTable
description: Fare riferimento a questo codice di esempio per aggiungere nuove righe di dati a una tabella in ADO.NET, dopo avere creato una DataTable e definirne la struttura usando le colonne e i vincoli.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 94ebc97d5f90b5bb92186ba6f33015633bd01127
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286934"
---
# <a name="adding-data-to-a-datatable"></a>Aggiunta di dati a un oggetto DataTable
Una volta creata una <xref:System.Data.DataTable> e definita la relativa struttura tramite colonne e vincoli, è possibile aggiungere nuove righe di dati alla tabella. Per aggiungere una nuova riga, dichiarare una nuova variabile come tipo <xref:System.Data.DataRow>. Quando si chiama il metodo, viene restituito un nuovo oggetto **DataRow** <xref:System.Data.DataTable.NewRow%2A> . Il **DataTable** crea quindi l'oggetto **DataRow** in base alla struttura della tabella, come definito da <xref:System.Data.DataColumnCollection> .  
  
 Nell'esempio seguente viene illustrato come creare una nuova riga chiamando il metodo **NewRow** .  
  
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
  
 Dopo l'inserimento dei dati nella nuova riga, il metodo **Add** viene utilizzato per aggiungere la riga a <xref:System.Data.DataRowCollection> , illustrato nel codice seguente.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 È anche possibile chiamare il metodo **Add** per aggiungere una nuova riga passando una matrice di valori, tipizzata come <xref:System.Object> , come illustrato nell'esempio seguente.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Il passaggio di una matrice di valori, tipizzato come **oggetto**, al metodo **Add** crea una nuova riga all'interno della tabella e imposta i relativi valori di colonna sui valori nella matrice di oggetti. Notare che i valori contenuti nella matrice vengono associati in modo sequenziale alle colonne, in base all'ordine in cui sono presenti nella tabella.  
  
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
