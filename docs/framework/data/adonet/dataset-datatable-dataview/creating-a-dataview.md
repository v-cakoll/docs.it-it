---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151338"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="59c18-102">Creazione di un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="59c18-102">Creating a DataView</span></span>
<span data-ttu-id="59c18-103">Per creare un <xref:System.Data.DataView>, sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="59c18-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="59c18-104">È possibile utilizzare il costruttore **DataView** oppure <xref:System.Data.DataTable.DefaultView%2A> creare <xref:System.Data.DataTable>un riferimento alla proprietà dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="59c18-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="59c18-105">Il **DataView** costruttore può essere vuoto o può accettare un **DataTable** come un singolo argomento o un **DataTable** con criteri di filtro, criteri di ordinamento e un filtro di stato di riga.</span><span class="sxs-lookup"><span data-stu-id="59c18-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="59c18-106">Per ulteriori informazioni sugli argomenti aggiuntivi disponibili per l'utilizzo con **DataView**, vedere [Ordinamento e filtro dei dati](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="59c18-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="59c18-107">Poiché l'indice per un **DataView** viene compilato sia quando viene creato il **DataView** e quando una delle proprietà **Sort**, **RowFilter**o **RowStateFilter** viene modificata, è possibile ottenere prestazioni ottimali fornendo qualsiasi criterio di ordinamento iniziale o di filtro come argomenti del costruttore quando si crea il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="59c18-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="59c18-108">La creazione di un **DataView** senza specificare i criteri di ordinamento o filtro e quindi impostando le proprietà **Sort**, **RowFilter**o **RowStateFilter** in un secondo momento determina la compilazione dell'indice almeno due volte: una volta quando viene creato il **DataView** e di nuovo quando una delle proprietà di ordinamento o filtro viene modificata.</span><span class="sxs-lookup"><span data-stu-id="59c18-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="59c18-109">Si noti che se si crea un **DataView** utilizzando il costruttore che non accetta argomenti, non sarà possibile utilizzare il **DataView** fino a quando non è stata impostata la **Table** proprietà.</span><span class="sxs-lookup"><span data-stu-id="59c18-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="59c18-110">Esempio di codice seguente viene illustrato come creare un **DataView** utilizzando il **DataView** costruttore.</span><span class="sxs-lookup"><span data-stu-id="59c18-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="59c18-111">Vengono forniti una colonna **RowFilter**, **Sort** e **DataViewRowState** insieme a **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="59c18-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],
    "Country = 'USA'",
    "ContactName",
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="59c18-112">Esempio di codice seguente viene illustrato come ottenere un riferimento al **DataView** predefinito di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.</span><span class="sxs-lookup"><span data-stu-id="59c18-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="59c18-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59c18-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="59c18-114">DataView</span><span class="sxs-lookup"><span data-stu-id="59c18-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="59c18-115">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="59c18-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="59c18-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="59c18-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="59c18-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="59c18-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
