---
title: Ricerca di righe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: daa8097bc5dfee203f988915b1e4a8bdcd2c50e0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408084"
---
# <a name="finding-rows"></a>Ricerca di righe
È possibile eseguire ricerche di righe in base ai relativi valori della chiave di ordinamento usando i metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> del tipo <xref:System.Data.DataView>. La distinzione maiuscole/minuscole di ricerca di valori nel **trovare** e **FindRows** metodi è determinato dal **CaseSensitive** proprietà dell'oggetto sottostante <xref:System.Data.DataTable>. Per restituire un risultato, è necessario che i valori di ricerca corrispondano interamente ai valori della chiave di ordinamento esistenti.  
  
 Il **trovare** metodo restituisce un intero con l'indice del <xref:System.Data.DataRowView> che corrisponde ai criteri di ricerca. Se più di una riga corrisponde ai criteri di ricerca, solo l'indice del primo corrispondente **DataRowView** viene restituito. Se viene trovata alcuna corrispondenza, **trovare** restituisce -1.  
  
 Per restituire i risultati di ricerca corrispondenti a più righe, usare il **FindRows** (metodo). **FindRows** funziona come il **trovare** metodo, ad eccezione del fatto che restituisca una **DataRowView** matrice che fa riferimento a tutte le righe corrispondenti nel **DataView**. Se viene trovata alcuna corrispondenza, il **DataRowView** matrice sarà vuota.  
  
 Usare il **trovare** o **FindRows** metodi è necessario specificare un ordinamento ordinare, impostare **ApplyDefaultSort** al **true** o tramite il **Ordinamento** proprietà. Se non viene specificato alcun ordinamento, verrà generata un'eccezione.  
  
 Il **trovare** e **FindRows** metodi accettano una matrice di valori come input la cui lunghezza corrisponde al numero di colonne nell'ordinamento. In caso di ordinamento di una singola colonna, è possibile passare un unico valore. In caso di ordinamenti contenenti più colonne, viene passata una matrice di oggetti. Si noti che per un ordinamento su più colonne, i valori nella matrice di oggetti devono corrispondere all'ordine delle colonne specificate nel **ordinamento** proprietà delle **DataView**.  
  
 Nell'esempio di codice riportato di seguito viene illustrato il **trovare** chiamata del metodo per un **DataView** con un ordinamento colonna singola.  
  
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
  
 Se il **ordinamento** proprietà specificate più colonne, è necessario passare una matrice di oggetti con i valori di ricerca per ogni colonna nell'ordine specificato dalle **ordinamento** proprietà, come nell'esempio di codice seguente.  
  
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
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
