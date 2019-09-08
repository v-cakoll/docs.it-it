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
# <a name="finding-rows"></a><span data-ttu-id="5de46-102">Ricerca di righe</span><span class="sxs-lookup"><span data-stu-id="5de46-102">Finding Rows</span></span>
<span data-ttu-id="5de46-103">È possibile eseguire ricerche di righe in base ai relativi valori della chiave di ordinamento usando i metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> del tipo <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="5de46-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="5de46-104">La distinzione tra maiuscole e minuscole dei valori di ricerca nei metodi **Find** e **FindRows** è determinata dalla proprietà <xref:System.Data.DataTable> **CaseSensitive** dell'oggetto sottostante.</span><span class="sxs-lookup"><span data-stu-id="5de46-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="5de46-105">Per restituire un risultato, è necessario che i valori di ricerca corrispondano interamente ai valori della chiave di ordinamento esistenti.</span><span class="sxs-lookup"><span data-stu-id="5de46-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="5de46-106">Il metodo **Find** restituisce un integer con l'indice di corrispondente <xref:System.Data.DataRowView> ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5de46-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="5de46-107">Se più di una riga corrisponde ai criteri di ricerca, viene restituito solo l'indice del primo **DataRowView** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5de46-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="5de46-108">Se non vengono trovate corrispondenze, **Find** restituisce-1.</span><span class="sxs-lookup"><span data-stu-id="5de46-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="5de46-109">Per restituire i risultati della ricerca che corrispondono a più righe, usare il metodo **FindRows** .</span><span class="sxs-lookup"><span data-stu-id="5de46-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="5de46-110">**FindRows** funziona esattamente come il metodo **Find** , ad eccezione del fatto che restituisce una matrice **DataRowView** che fa riferimento a tutte le righe corrispondenti nell'oggetto **DataView**.</span><span class="sxs-lookup"><span data-stu-id="5de46-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="5de46-111">Se non viene trovata alcuna corrispondenza, la matrice **DataRowView** sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="5de46-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="5de46-112">Per usare i metodi **Find** o **FindRows** , è necessario specificare un ordinamento impostando **ApplyDefaultSort** su **true** o usando la proprietà **Sort** .</span><span class="sxs-lookup"><span data-stu-id="5de46-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="5de46-113">Se non viene specificato alcun ordinamento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5de46-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="5de46-114">I metodi **Find** e **FindRows** accettano una matrice di valori come input la cui lunghezza corrisponde al numero di colonne nell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="5de46-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="5de46-115">In caso di ordinamento di una singola colonna, è possibile passare un unico valore.</span><span class="sxs-lookup"><span data-stu-id="5de46-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="5de46-116">In caso di ordinamenti contenenti più colonne, viene passata una matrice di oggetti.</span><span class="sxs-lookup"><span data-stu-id="5de46-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="5de46-117">Si noti che per un ordinamento in base a più colonne, i valori nella matrice di oggetti devono corrispondere all'ordine delle colonne specificato nella proprietà **Sort** di **DataView**.</span><span class="sxs-lookup"><span data-stu-id="5de46-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="5de46-118">Nell'esempio di codice seguente viene illustrato il metodo **Find** chiamato su un **DataView** con un ordinamento a colonna singola.</span><span class="sxs-lookup"><span data-stu-id="5de46-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="5de46-119">Se la proprietà **Sort** specifica più colonne, è necessario passare una matrice di oggetti con i valori di ricerca per ogni colonna nell'ordine specificato dalla proprietà **Sort** , come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5de46-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5de46-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de46-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="5de46-121">DataView</span><span class="sxs-lookup"><span data-stu-id="5de46-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="5de46-122">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5de46-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
