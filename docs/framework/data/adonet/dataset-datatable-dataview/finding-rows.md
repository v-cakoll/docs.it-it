---
title: Ricerca di righe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: ad10557a55b498fe004bff6ce89801e975e7138b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786326"
---
# <a name="finding-rows"></a>Ricerca di righe
È possibile eseguire ricerche di righe in base ai relativi valori della chiave di ordinamento usando i metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> del tipo <xref:System.Data.DataView>. La distinzione tra maiuscole e minuscole dei valori di ricerca nei metodi **Find** e **FindRows** è determinata dalla proprietà <xref:System.Data.DataTable> **CaseSensitive** dell'oggetto sottostante. Per restituire un risultato, è necessario che i valori di ricerca corrispondano interamente ai valori della chiave di ordinamento esistenti.  
  
 Il metodo **Find** restituisce un integer con l'indice di corrispondente <xref:System.Data.DataRowView> ai criteri di ricerca. Se più di una riga corrisponde ai criteri di ricerca, viene restituito solo l'indice del primo **DataRowView** corrispondente. Se non vengono trovate corrispondenze, **Find** restituisce-1.  
  
 Per restituire i risultati della ricerca che corrispondono a più righe, usare il metodo **FindRows** . **FindRows** funziona esattamente come il metodo **Find** , ad eccezione del fatto che restituisce una matrice **DataRowView** che fa riferimento a tutte le righe corrispondenti nell'oggetto **DataView**. Se non viene trovata alcuna corrispondenza, la matrice **DataRowView** sarà vuota.  
  
 Per usare i metodi **Find** o **FindRows** , è necessario specificare un ordinamento impostando **ApplyDefaultSort** su **true** o usando la proprietà **Sort** . Se non viene specificato alcun ordinamento, verrà generata un'eccezione.  
  
 I metodi **Find** e **FindRows** accettano una matrice di valori come input la cui lunghezza corrisponde al numero di colonne nell'ordinamento. In caso di ordinamento di una singola colonna, è possibile passare un unico valore. In caso di ordinamenti contenenti più colonne, viene passata una matrice di oggetti. Si noti che per un ordinamento in base a più colonne, i valori nella matrice di oggetti devono corrispondere all'ordine delle colonne specificato nella proprietà **Sort** di **DataView**.  
  
 Nell'esempio di codice seguente viene illustrato il metodo **Find** chiamato su un **DataView** con un ordinamento a colonna singola.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 Se la proprietà **Sort** specifica più colonne, è necessario passare una matrice di oggetti con i valori di ricerca per ogni colonna nell'ordine specificato dalla proprietà **Sort** , come nell'esempio di codice seguente.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
