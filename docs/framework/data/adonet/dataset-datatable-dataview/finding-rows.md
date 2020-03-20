---
title: Ricerca di righe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151143"
---
# <a name="finding-rows"></a>Ricerca di righe
È possibile eseguire ricerche di righe in base ai relativi valori della chiave di ordinamento usando i metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> del tipo <xref:System.Data.DataView>. La distinzione tra maiuscole e minuscole dei valori di ricerca nei <xref:System.Data.DataTable>metodi **Find** e **FindRows** è determinata dalla proprietà **CaseSensitive** dell'oggetto sottostante. Per restituire un risultato, è necessario che i valori di ricerca corrispondano interamente ai valori della chiave di ordinamento esistenti.  
  
 Il **Find** metodo restituisce un <xref:System.Data.DataRowView> numero intero con l'indice di che corrisponde ai criteri di ricerca. Se più di una riga corrisponde ai criteri di ricerca, viene restituito solo l'indice del primo **DataRowView** corrispondente. Se non vengono trovate corrispondenze, Find restituisce -1.If no matches are found, **Find** returns -1.  
  
 Per restituire i risultati della ricerca che corrispondono a più righe, utilizzare il **FindRows** metodo. **FindRows** funziona come il **Find** metodo, ad eccezione del fatto che restituisce un **DataRowView** matrice che fa riferimento a tutte le righe corrispondenti nel **DataView**. Se non vengono trovate corrispondenze, la matrice **DataRowView** sarà vuota.  
  
 Per utilizzare i metodi **Find** o **FindRows** è necessario specificare un criterio di ordinamento impostando **ApplyDefaultSort** su **true** o utilizzando la proprietà **Sort.** Se non viene specificato alcun ordinamento, verrà generata un'eccezione.  
  
 I metodi **Find** e **FindRows** accettano una matrice di valori come input la cui lunghezza corrisponde al numero di colonne nell'ordinamento. In caso di ordinamento di una singola colonna, è possibile passare un unico valore. In caso di ordinamenti contenenti più colonne, viene passata una matrice di oggetti. Si noti che per un ordinamento in base a più colonne, i valori nella matrice di oggetti devono corrispondere all'ordine delle colonne specificate nella proprietà **Sort** di **DataView**.  
  
 Esempio di codice seguente viene illustrato il **Find** metodo viene chiamato su un **DataView** con un ordinamento a colonna singola.  
  
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
  
 Se la proprietà **Sort** specifica più colonne, è necessario passare una matrice di oggetti con i valori di ricerca per ogni colonna nell'ordine specificato dalla proprietà **Sort,** come nell'esempio di codice seguente.  
  
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
