---
title: Ricerca di righe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 57ed6045ca0ea9f9579640839e8198716cf79fe0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760882"
---
# <a name="finding-rows"></a><span data-ttu-id="c1d68-102">Ricerca di righe</span><span class="sxs-lookup"><span data-stu-id="c1d68-102">Finding Rows</span></span>
<span data-ttu-id="c1d68-103">È possibile eseguire ricerche di righe in base ai relativi valori della chiave di ordinamento usando i metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> del tipo <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="c1d68-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="c1d68-104">La distinzione maiuscole/minuscole della ricerca i valori di **trovare** e **FindRows** metodi è determinato dal **CaseSensitive** proprietà dell'oggetto sottostante <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="c1d68-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c1d68-105">Per restituire un risultato, è necessario che i valori di ricerca corrispondano interamente ai valori della chiave di ordinamento esistenti.</span><span class="sxs-lookup"><span data-stu-id="c1d68-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="c1d68-106">Il **trovare** metodo restituisce un intero con indice di <xref:System.Data.DataRowView> che corrisponde ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1d68-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="c1d68-107">Se più di una riga corrisponde ai criteri di ricerca, solo l'indice della prima corrispondenza **DataRowView** viene restituito.</span><span class="sxs-lookup"><span data-stu-id="c1d68-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="c1d68-108">Se non vengono trovate corrispondenze, **trovare** restituisce -1.</span><span class="sxs-lookup"><span data-stu-id="c1d68-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="c1d68-109">Per restituire i risultati di ricerca che corrispondono a più righe, utilizzare il **FindRows** metodo.</span><span class="sxs-lookup"><span data-stu-id="c1d68-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="c1d68-110">**FindRows** funziona come il **trovare** metodo, ad eccezione del fatto che restituisca un **DataRowView** che fa riferimento a tutte le righe corrispondenti nella matrice di **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c1d68-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="c1d68-111">Se viene trovata alcuna corrispondenza, il **DataRowView** matrice sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="c1d68-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="c1d68-112">Utilizzare il **trovare** o **FindRows** metodi è necessario specificare un ordinamento ordinare impostando **ApplyDefaultSort** a **true** o tramite il **Ordinamento** proprietà.</span><span class="sxs-lookup"><span data-stu-id="c1d68-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="c1d68-113">Se non viene specificato alcun ordinamento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c1d68-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="c1d68-114">Il **trovare** e **FindRows** metodi accettano una matrice di valori come input, la cui lunghezza corrisponde al numero di colonne dell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="c1d68-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="c1d68-115">In caso di ordinamento di una singola colonna, è possibile passare un unico valore.</span><span class="sxs-lookup"><span data-stu-id="c1d68-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="c1d68-116">In caso di ordinamenti contenenti più colonne, viene passata una matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="c1d68-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="c1d68-117">Si noti che per l'ordinamento su più colonne, i valori della matrice di oggetti devono corrispondere all'ordine delle colonne specificate nel **ordinamento** proprietà del **DataView**.</span><span class="sxs-lookup"><span data-stu-id="c1d68-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="c1d68-118">Nell'esempio di codice riportato di seguito viene illustrato il **trovare** chiamata del metodo per un **DataView** con un ordinamento singola colonna.</span><span class="sxs-lookup"><span data-stu-id="c1d68-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="c1d68-119">Se il **ordinamento** proprietà sono specificate più colonne, è necessario passare una matrice di oggetti con i valori di ricerca per ogni colonna nell'ordine specificato per il **ordinamento** proprietà, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c1d68-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1d68-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1d68-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="c1d68-121">DataView</span><span class="sxs-lookup"><span data-stu-id="c1d68-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="c1d68-122">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c1d68-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
